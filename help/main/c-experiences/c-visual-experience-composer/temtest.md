---
keywords: 模板测试;模板;相似页面上的相同体验
description: 了解如何使用Adobe [!DNL Target] 可视化体验编辑器(VEC)在结构类似或包含相同模板元素的多个页面上包含相同体验。
title: 我是否可以在类似页面上包含相同体验？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 24%

---

# 在相似页面上包含相同体验

使用[!DNL Adobe Target]中的页面模板为您的页面提供结构，或者如果您的页面包含类似的元素，则使用类似的页面元素或跨整个域测试变体。

要正常工作，必须在具有相似结构或包含在所有页面上具有相同结构的模板元素的页面上使用此功能。

>[!IMPORTANT]
>
>使用此功能更改不同页面中的元素可能会导致意外结果。

例如，您可以使用此功能执行以下某项操作：

* 通过重新排列或删除元素来测试全局导航栏
* 从所有使用了同一特定页面模板的产品页面中删除某个项目
* 将一个横幅添加到所有产品页面中
* 更改文章模板的布局

您可以指定包含更改元素的页面，或将更改应用到您的网站或域。

1. 按照[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中的说明创建或编辑活动。

1. 要指定显示体验的页面，请在[!UICONTROL Visual Experience Composer] (VEC)中单击[!UICONTROL Configure]图标（![配置图标](/help/main/assets/icons/Setting.svg)），然后选择&#x200B;**[!UICONTROL Page Delivery]**。

1. 单击&#x200B;**[!UICONTROL Add Rule]**，然后为要将体验添加到的页面指定条件。

1. 指定页面范围。页面范围可以是以下任一类型：

   * [!UICONTROL URL] （有关[!DNL Target]如何评估URL的详细信息，请参阅[目标和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。）
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment] （以#符号后面的URL部分为目标。）
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

1. 选择运算符。

   运算符可指定运算符后面的项目与页面范围之间的关系。可用的运算符包括：

   * [!UICONTROL Contains]
   * [!UICONTROL Does not contain]
   * [!UICONTROL Is (case sensitive)]
   * [!UICONTROL Is not]
   * [!UICONTROL Starts with]
   * [!UICONTROL Ends with]

1. 键入相应的字符串以定义要将体验添加到的位置，例如域或页面名称中包含的字符串。

   例如，如果您选择&#x200B;**[!UICONTROL Domain]**&#x200B;和&#x200B;**[!UICONTROL Is (case sensitive)]**，请键入要将体验添加到的所有页面所在的域。

   您可以包含多个项目。

   >[!IMPORTANT]
   >
   >多个项目使用OR逻辑，这意味着列表中的任一项目均满足条件。

1. 如有需要，单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;并重复前一步骤中的操作过程，以输入其他条件。

   多个标准会使用 AND 逻辑进行连接。[!DNL Target]将体验添加到符合指定条件的所有页面。

>[!IMPORTANT]
>
> [!DNL Target]无法检查页面以确保它们按预期方式显示，因此使用此功能时，务必要始终先测试受影响的页面，然后再发布这些页面。

## 用例

查看以下用例，了解在您的站点上使用模板规则的方法：

### 在整个域中呈现相同的活动

对于以下用例，您可以考虑使用模板规则在整个域中呈现相同的活动：

* 要包含全局页眉或页脚，请执行以下操作
* 添加全球横幅（例如，COVID-19公告）
* 包括全球免运费促销

1. 按照[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)中的说明创建或编辑活动。

1. 要指定显示体验的域，请在[!UICONTROL Visual Experience Composer]中单击[!UICONTROL Configure]图标（![配置图标](/help/main/assets/icons/Setting.svg)），然后选择&#x200B;**[!UICONTROL Page Delivery]**。

1. 单击&#x200B;**[!UICONTROL Add Rule]** > **[!UICONTROL Domain]**。

1. 从&#x200B;**[!UICONTROL Choose evaluator]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Contains]**，然后指定域。
