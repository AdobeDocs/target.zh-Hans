---
keywords: 远程选件;创建远程选件
description: 了解如何在Adobe [!DNL Target] 中创建JSON优惠，以便在基于表单的体验编辑器中使用。 JSON优惠对SPA框架或服务器端集成很有用。
title: 如何创建JSON优惠?
feature: 体验和优惠
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 54%

---

# 创建 JSON 选件

在[!DNL Adobe Target]中的[!UICONTROL 优惠库]中创建JSON优惠，以在[!UICONTROL 基于表单的体验编辑器]中使用。

JSON优惠可用于基于表单的活动中，在这些情况下，启用需要[!DNL Target]决策的用例，以JSON格式发送优惠以用于SPA框架或服务器端集成。

## JSON注意事项

使用 JSON 选件时，请考虑以下信息：

* JSON优惠当前仅适用于[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting](XT)活动。
* JSON优惠只能用于[基于表单的活动](/help/c-experiences/form-experience-composer.md)。
* 使用服务器端 API、Mobile SDK 或 NodeJS SDK 时，可以直接检索 JSON 选件。
* 在浏览器中，只能通过 at.js 1.2.3（或更高版本）并使用 [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) 来检索 JSON 选件，检索时可以使用 `setJson` 操作进行筛选。
* JSON 选件可作为原生 JSON 对象而不是字符串来交付。这些对象的用户不必再将对象作为字符串处理后再将其转换为 JSON 对象。
* 与其他选件（例如 HTML 选件）不同，JSON 选件不会自动应用，因为 JSON 选件不是可视化选件。开发人员必须编写相应代码，以便使用 [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)。
* 如果您使用的是 mbox.js，JSON 选件将不受支持。

## 创建JSON优惠{#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 单击&#x200B;**[!UICONTROL 优惠]** > **[!UICONTROL 代码优惠]**。

   ![优惠>代码优惠选项卡](/help/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL JSON 选件]**。

   ![](assets/offer-json.png)

1. 键入选件名称。
1. 在&#x200B;**[!UICONTROL 代码]**&#x200B;框中键入或粘贴您的 JSON 代码。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## JSON示例{#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON优惠仅在使用[基于表单的体验书写器](/help/c-experiences/form-experience-composer.md)创建的活动中受支持。 目前，唯有通过直接 API 调用才能使用 JSON 选件。

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

操作数组将具有以下结构：

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

要提取JSON优惠，请对操作进行迭代，找到包含`setJson`操作的操作，然后对内容数组进行迭代。

## 用例{#section_85B07907B51A43239C8E3498EF58B1E5}

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

## 按JSON优惠类型{#section_52533555BCE6420C8A95EB4EB8907BDE}筛选优惠

单击&#x200B;**[!UICONTROL 类型]**&#x200B;下拉列表，然后选中&#x200B;**[!UICONTROL JSON]**&#x200B;复选框，即可按JSON优惠类型筛选[!UICONTROL 优惠]库。

![](assets/offer-json-filter.png)
