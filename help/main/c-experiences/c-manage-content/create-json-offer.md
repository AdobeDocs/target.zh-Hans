---
keywords: 远程选件;创建远程选件
description: 了解如何在Adobe中创建JSON选件 [!DNL Target] ，以便在基于表单的体验编辑器中使用。
title: 如何创建JSON选件？
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: fedef4bfa5fdcc757dc1bd5e0d3577a85896c918
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 32%

---

# 创建 JSON 选件

在中创建JSON选件 [!UICONTROL 选件库] 在 [!DNL Adobe Target] 在中使用 [!UICONTROL 基于表单的体验编辑器].

JSON选件可用于基于表单的活动，由此在以下情况下启用用例： [!DNL Target] 需要决策才能以JSON格式发送选件，以便在SPA框架或服务器端集成中使用。

## JSON注意事项

使用 JSON 选件时，请考虑以下信息：

* JSON选件当前仅适用于 [!UICONTROL A/B测试]、Automated Personalization (AP)和 [!UICONTROL 体验定位] (XT)活动。
* JSON选件可用于 [基于表单的活动](/help/main/c-experiences/form-experience-composer.md) 仅此而已。
* 使用时，可以直接检索JSON选件 [服务器端API和移动节点.js、Java、.NET和Python SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html){target=_blank}.
* 在浏览器中，只能通过at.js 1.2.3（或更高版本）并使用以下方式检索JSON选件 [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank} 通过使用 `setJson` 操作。
* JSON 选件可作为原生 JSON 对象而不是字符串来交付。这些对象的用户不必再将对象作为字符串处理后再将其转换为 JSON 对象。
* 与其他选件（例如 HTML 选件）不同，JSON 选件不会自动应用，因为 JSON 选件不是可视化选件。开发人员必须编写相应代码，以便使用 [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank}.

## 创建JSON选件 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 单击 **[!UICONTROL 选件]** > **[!UICONTROL 代码选件]**.

   ![“选件”>“代码选件”选项卡](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL JSON 选件]**。

   ![offer-json图像](assets/offer-json.png)

1. 键入选件名称。
1. 在&#x200B;**[!UICONTROL 代码]**&#x200B;框中键入或粘贴您的 JSON 代码。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## JSON示例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

只有在使用创建的活动中才支持JSON选件 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md). 目前，能够使用JSON选件的唯一方法是通过直接API/SDK调用。

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

操作数组的结构如下：

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

## 使用实时CDP配置文件属性的JSON选件示例

Real-time CDP配置文件属性可与共享 [!DNL Target] 用于HTML选件和JSON选件。

有关更多信息，请参阅 [与共享Real-time CDP配置文件属性 [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## 按JSON选件类型筛选选件 {#section_52533555BCE6420C8A95EB4EB8907BDE}

您可以筛选 [!UICONTROL 选件] 库，方法是单击 **[!UICONTROL 类型]** 下拉列表，然后通过选择 **[!UICONTROL JSON]** 复选框。

![offer-json-filter图像](assets/offer-json-filter.png)
