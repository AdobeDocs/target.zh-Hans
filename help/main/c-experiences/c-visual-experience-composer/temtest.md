---
keywords: 模板测试;模板;相似页面上的相同体验
description: 了解如何使用Adobe [!DNL Target]可视化体验编辑器(VEC)在结构类似或包含相同模板元素的多个页面上包含相同体验。
title: 我是否可以在类似页面上包含相同体验？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: 'https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: ef98a6e0-f26c-4870-9bd4-e6b72e9cc699
    internal-label: Experiences and offers
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 17%
---
# 在相似页面上包含相同体验 {#similar-pages}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在[!UICONTROL 可视化体验编辑器] (VEC)中使用页面交付规则，在具有相似结构的页面上包含相同体验。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的页面模板为页面提供结构。 当页面包含相似元素时，可以在多个页面或整个域中测试这些类似结构化页面元素中的变体。

要正常工作，必须在具有相似结构或包含在所有页面上具有相同结构的模板元素的页面上使用此功能。

>[!IMPORTANT]
>
>使用此功能更改不同页面中的元素可能会导致意外结果。

例如，此功能可用于执行以下操作之一：

* 通过重新排列或删除元素来测试全局导航栏
* 从所有使用了同一特定页面模板的产品页面中删除某个项目
* 将一个横幅添加到所有产品页面中
* 更改文章模板的布局

## 指定体验的页面 {#specify-pages}

显示体验的页面通过页面交付规则指定。 规则可以包括特定页面，或将更改应用到整个网站或域。

1. 按照[活动](/help/main/c-activities/activities.md)中的说明创建或编辑活动。

1. 在[!UICONTROL 可视化体验编辑器] (VEC)中，单击&#x200B;**[!UICONTROL 配置]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg)），然后选择&#x200B;**[!UICONTROL 页面交付]**。

   ![活动](assets/vec_edit_1.png)

1. 单击&#x200B;**[!UICONTROL 添加规则]**，然后为要将体验添加到的页面指定条件。

1. 指定页面范围： **[!UICONTROL URL]**、**[!UICONTROL 域]**、**[!UICONTROL 路径]**、**[!UICONTROL 哈希(#)片段]** （URL中跟随#符号的部分）、**[!UICONTROL 查询]**&#x200B;或&#x200B;**[!UICONTROL 自定义]**。

   有关[!DNL Target]如何评估URL的详细信息，请参阅[定位和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。

   ![活动](assets/vec_edit_2.png)

1. 选择运算符。 运算符可指定运算符后面的项目与页面范围之间的关系。

1. 键入相应的字符串以定义要将体验添加到的位置，例如域或页面名称中包含的字符串。

   例如，如果选择&#x200B;**[!UICONTROL 域]**&#x200B;和&#x200B;**[!UICONTROL 是（区分大小写）]**，则键入将体验添加到所有页面的域。

   可以包含多个项目。 多个项目使用OR逻辑，这意味着列表中的任一项目均满足条件。

1. （可选）单击&#x200B;**[!UICONTROL 添加规则]**&#x200B;并重复步骤3至6以输入其他条件。

   多个标准会使用 AND 逻辑进行连接。 [!DNL Target]将体验添加到符合指定条件的所有页面。

>[!IMPORTANT]
>
>[!DNL Target]无法检查页面以确保它们按预期方式显示，因此使用此功能时，务必要始终先测试受影响的页面，然后再发布这些页面。

## 用例 {#use-cases}

模板规则可在网站上以不同方式使用，如以下用例所示。

### 在整个域中呈现相同的活动 {#entire-domain}

模板规则可以在整个域中呈现相同的活动，例如：

* 要包含全局页眉或页脚，请执行以下操作
* 添加全球横幅（例如，COVID-19公告）
* 包括全球免运费促销

1. 按照[活动](/help/main/c-activities/activities.md)中的说明创建或编辑活动。

1. 要指定显示体验的域，请在[!UICONTROL 可视化体验编辑器]中单击&#x200B;**[!UICONTROL 配置]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg)），然后选择&#x200B;**[!UICONTROL 页面交付]**。

1. 单击&#x200B;**[!UICONTROL 添加规则]** > **[!UICONTROL 域]**。

1. 从&#x200B;**[!UICONTROL 选择计算器]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 包含]**，然后指定域。

   ![活动](assets/vec_edit_3.png)
