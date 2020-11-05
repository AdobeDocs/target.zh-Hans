---
keywords: template testing;template;same experience on similar pages;template test
description: 使用Adobe Target的页面模板为页面提供结构，或者如果页面包含类似元素，则测试结构相似的页面元素中的变体。
title: 使用Adobe Target在类似页面上提供相同的体验
feature: experiences
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 45%

---


# 在相似页面上包含相同体验

使用中的页面模 [!DNL Adobe Target] 板为页面提供结构，或者如果页面包含类似元素，则测试结构相似的页面元素中或整个域中的变量。

要正确工作，此功能必须用于结构相似或包含在所有页面上结构相同的模板元素的页面。

>[!IMPORTANT]
>
>使用此功能更改不相似的页面中的元素可能会引发意外结果。

例如，您可以使用此功能执行以下某项操作：

* 通过重新排列或删除元素来测试全局导航栏
* 从所有使用了同一特定页面模板的产品页面中删除某个项目
* 将一个横幅添加到所有产品页面中
* 更改文章模板的布局

您可以指定包含更改元素的页面，或在网站或域中应用更改。

1. Create  or edit an activity as described in [Activities](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the pages where the experience will appear, in the [!UICONTROL Visual Experience Composer] (VEC) click the gear icon, then select **[!UICONTROL Page Delivery]**.

   ![齿轮图标>页面投放](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 单击&#x200B;**[!UICONTROL 添加模板规则]**，然后为要将体验添加到的页面指定标准。

1. 指定页面范围。页面范围可以是以下任一类型：

   * URL (有关目标如何评估URL的更多信息，请参 [阅目标和受众常见问题解答](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)。)
   * 域
   * 路径
   * 哈希(#)片段(目标URL中跟在#符号后的部分。)
   * 查询
   * 参数

1. 选择运算符。

   运算符可指定运算符后面的项目与页面范围之间的关系。可用的运算符包括：

   * 包含
   * 不包含
   * 是（区分大小写）
   * 不是
   * 开始于
   * 结束于

1. 键入相应的字符串以定义要将体验添加到的位置，例如域或页面名称中包含的字符串。

   例如，如果您选择了&#x200B;**[!UICONTROL 域]**&#x200B;和&#x200B;**[!UICONTROL 是（区分大小写）]**，则需键入要将体验添加到的所有页面所在的域。

   您可以包含多个项目。

   >[!IMPORTANT]
   >
   >多个项目使用OR逻辑，这意味着列表中的任何单个项目都使条件成为真。

1. If desired, enter additional criteria by clicking **[!UICONTROL Add Template Rule]** and repeating the procedure in the previous steps.

   多个标准会使用 AND 逻辑进行连接。[!DNL Target] 会将体验添加到符合指定标准的所有页面。

>[!IMPORTANT]
>
> [!DNL Target] 无法检查页面以确保它们按预期方式显示，因此使用此功能时，务必要始终先测试受影响的页面，然后再发布这些页面。

## 用例

查看以下使用案例，了解如何在站点上使用模板规则：

### 在整个域中呈现相同的活动

对于以下用例，您可以考虑使用模板规则在整个域中呈现相同的活动:

* 要包括全局页眉或页脚，请执行以下操作：
* 加入全局横幅（例如，COVID-19公告）
* 要包含全球免费送货促销，请

1. Create or edit an activity as described in [Activities](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the domain where the experience will appear, in the Visual Experience Composer click the gear icon, then select **[!UICONTROL Page Delivery]**.

1. 单击 **[!UICONTROL 添加模板规则]** > **[!UICONTROL 域]**。

1. 从“选 **[!UICONTROL 择计算器]** ”(Choose evaluator **[!UICONTROL )下拉框中，选择]**“包含”(Contains)，然后指定域。

   ![域包含](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Training video: Visual Experience Composer (2 of 2) (7:29) ![Tutorial badge](/help/assets/tutorial.png)

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)