---
keywords: 模板测试;模板;相似页面上的相同体验
description: 了解如何使用Adobe [!DNL Target] 可视化体验编辑器(VEC)，可在结构类似或包含相同模板元素的多个页面上包含相同体验。
title: 我是否可以在相似页面上包含相同体验？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 46%

---

# 在相似页面上包含相同体验

在中使用页面模板 [!DNL Adobe Target] 为页面提供结构，或者如果页面包含类似的元素，则测试类似结构的页面元素中或整个域中的变体。

要正确工作，必须在具有相似结构或包含在所有页面上具有相同结构的模板元素的页面上使用此功能。

>[!IMPORTANT]
>
>使用此功能更改不相似的页面中的元素可能会引发意外结果。

例如，您可以使用此功能执行以下某项操作：

* 通过重新排列或删除元素来测试全局导航栏
* 从所有使用了同一特定页面模板的产品页面中删除某个项目
* 将一个横幅添加到所有产品页面中
* 更改文章模板的布局

您可以指定包含更改元素的页面，或者将更改应用于您的网站或域。

1. 创建或编辑活动，如中所述 [活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. 要指定将显示体验的页面，请在 [!UICONTROL 可视化体验编辑器] (VEC)单击齿轮图标，然后选择 **[!UICONTROL 页面交付]**.

   ![齿轮图标>页面交付](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 单击&#x200B;**[!UICONTROL 添加模板规则]**，然后为要将体验添加到的页面指定标准。

1. 指定页面范围。页面范围可以是以下任一类型：

   * URL (有关Target如何评估URL的更多信息，请参阅 [定位和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * 域
   * 路径
   * 井号(#)片段（以#符号后面的URL部分为目标。）
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
   >多个项目使用OR逻辑，这意味着列表中的任何单个项目都会使条件成立。

1. 如有需要，通过单击输入其他标准 **[!UICONTROL 添加模板规则]** 并重复上述步骤中的过程。

   多个标准会使用 AND 逻辑进行连接。[!DNL Target] 会将体验添加到符合指定标准的所有页面。

>[!IMPORTANT]
>
> [!DNL Target] 无法检查页面以确保它们按预期方式显示，因此使用此功能时，务必要始终先测试受影响的页面，然后再发布这些页面。

## 用例

查看以下用例，了解在您的站点上使用模板规则的方法：

### 在整个域中呈现相同的活动

对于以下用例，您可以考虑使用模板规则在整个域中呈现相同的活动：

* 要包含全局页眉或页脚，请执行以下操作
* 添加全球横幅（例如，COVID-19公告）
* 包括全球免运促销

1. 创建或编辑活动，如中所述 [活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. 要指定将显示体验的域，请在可视化体验编辑器中单击齿轮图标，然后选择 **[!UICONTROL 页面交付]**.

1. 单击 **[!UICONTROL 添加模板规则]** > **[!UICONTROL 域]**.

1. 从 **[!UICONTROL 选择计算器]** 下拉列表，选择 **[!UICONTROL 包含]**，然后指定域。

   ![域包含](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## 培训视频：可视化体验编辑器(2/2)(7:29) ![教程徽章](/help/main/assets/tutorial.png)

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)
