---
keywords: 远程选件;创建远程选件
description: 了解如何在Adobe中创建JSON选件 [!DNL Target] ，以在基于表单的体验编辑器中使用。
title: 如何创建JSON选件？
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 24f445128aa76eb7e0af7d0f2c5de96f11b8d110
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 33%

---

# 创建 JSON 选件

在中创建JSON选件 [!UICONTROL 选件库] in [!DNL Adobe Target] ，在中使用 [!UICONTROL 基于表单的体验编辑器].

JSON选件可用于基于表单的活动，在这些活动中，可启用 [!DNL Target] 决策需要以JSON格式发送选件，以便在SPA框架或服务器端集成中使用。

## JSON注意事项

使用 JSON 选件时，请考虑以下信息：

* JSON选件当前仅适用于 [!UICONTROL A/B测试]、Automated Personalization（美联社）和 [!UICONTROL 体验定位] (XT)活动。
* JSON选件可用于 [基于表单的活动](/help/main/c-experiences/form-experience-composer.md) 仅。
* 使用 [服务器端API和Mobile Node.js、Java、.NET和Python SDK](https://developer.adobe.com/target/implement/server-side/){target=_blank}.
* 在浏览器中，JSON选件只能通过at.js 1.2.3（或更高版本）和使用 [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} (通过使用 `setJson` 操作。
* JSON 选件可作为原生 JSON 对象而不是字符串来交付。这些对象的用户不必再将对象作为字符串处理后再将其转换为 JSON 对象。
* 与其他选件（例如 HTML 选件）不同，JSON 选件不会自动应用，因为 JSON 选件不是可视化选件。开发人员必须编写相应代码，以便使用 [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank}.

## 创建JSON选件 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 单击 **[!UICONTROL 选件]** > **[!UICONTROL 代码选件]**.

   ![选件>代码选件选项卡](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL JSON 选件]**。

   ![offer-json图像](assets/offer-json.png)

1. 键入选件名称。
1. 在&#x200B;**[!UICONTROL 代码]**&#x200B;框中键入或粘贴您的 JSON 代码。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## JSON示例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON选件仅在使用 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md). 目前，能够使用JSON选件的唯一方法是通过直接API/SDK调用。

示例如下：

```json
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

传递到 success 回调的操作是一个对象数组。假设我们只有一个 JSON 选件，且该选件具有以下内容：

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

操作数组具有以下结构：

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

要提取JSON选件，您需要遍历各个操作，并使用 `setJson` 操作，然后遍历内容数组。

## 用例 {#section_85B07907B51A43239C8E3498EF58B1E5}

假设将以下 JSON 选件交付到您的网页：

```json
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

以下代码显示了如何访问“greeting”属性：

```json
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## JSON选件示例（使用实时CDP配置文件属性）

Real-time CDP Profile Attributes可与 [!DNL Target] 用于HTML选件和JSON选件。 （请注意，此功能目前处于测试阶段。）

有关更多信息，请参阅 [与共享Real-time CDP Profile Attributes [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## 按JSON选件类型筛选选件 {#section_52533555BCE6420C8A95EB4EB8907BDE}

您可以过滤 [!UICONTROL 选件] 库(通过单击 **[!UICONTROL 类型]** 下拉列表中，然后选择 **[!UICONTROL JSON]** 复选框。

![offer-json-filter图像](assets/offer-json-filter.png)
