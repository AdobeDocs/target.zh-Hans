---
keywords: 推荐;产品建议
description: 了解如何在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中使用产品建议形式的 Adobe 推荐。
title: 如何在其他活动类型中使用产品建议形式的推荐？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 47%

---

# “推荐”作为产品建议

您现在可以在[!UICONTROL A/B Test]（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）和[!UICONTROL Experience Targeting] (XT)活动中包含推荐。

此功能提供了几项全新的功能，例如：

* 可在同一活动中测试和锁定推荐和非推荐内容。
* 可轻松尝试在页面上放置推荐，包括多个推荐的顺序。
* 使用[!UICONTROL Auto-Allocate]自动将流量推送到性能最佳的推荐体验。
* 使用[!UICONTROL Auto-Target]根据访客的配置文件动态地为他们分配量身定制的推荐体验。

要开始使用此功能，请使用[!UICONTROL Visual Experience Composer]创建一个[!UICONTROL A/B Test]或[!UICONTROL Experience Targeting]活动，然后使用[!UICONTROL Recommend]操作向体验添加推荐。

## 在 A/B 测试或 XT 活动中将推荐作为产品建议添加

1. 使用可视化体验编辑器 (VEC) 启动三步引导式工作流，以创建 [A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[体验定位](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) 活动。

   >[!NOTE]
   >
   >对于 A/B 测试，请记住您可以选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)选项以自动将流量推送到性能最佳的推荐，或者选择[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)选项以根据访客的轮廓为他们分配量身定制的推荐体验。

1. 创建[体验](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)时，单击要将推荐作为选件添加到的元素，单击&#x200B;**[!UICONTROL Replace Content]** （ ![替换内容图标](/help/main/assets/icons/Switch.svg) ），然后选择&#x200B;**[!UICONTROL Recommendation]**。

   ![将推荐作为产品建议插入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 从右侧的[!UICONTROL Recommendation]边栏中，单击&#x200B;**[!UICONTROL Select a Recommendation]**&#x200B;以显示[!UICONTROL Select Criteria]对话框。

1. 单击&#x200B;**[!UICONTROL Create Criteria]**&#x200B;或选择现有条件。

1. （可选）单击&#x200B;**[!UICONTROL Filter]**&#x200B;图标（![过滤器图标](/help/main/assets/icons/Filter.svg) ）可从以下选项中进行选择，以查看按页面类型划分的热门推荐标准：

   * 购物车页面
   * 类别页面
   * 首页
   * 登录页面
   * 产品页面
   * 搜索结果页面
   * 感谢页面
   * 其他

1. 单击&#x200B;**[!UICONTROL Create Criteria]**&#x200B;或选择现有的[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)，然后单击&#x200B;**[!UICONTROL Next]**&#x200B;以显示[!UICONTROL Select Design]对话框。

1. 单击&#x200B;**[!UICONTROL Create Design]**&#x200B;或选择现有的[设计](/help/main/c-recommendations/c-design-overview/design-overview.md)，然后单击&#x200B;**[!UICONTROL  Next]**。

1. 在[!UICONTROL Options]对话框中，指定以下内容：

   * 选择一个[收藏集](/help/main/c-recommendations/c-products/collections.md)。
   * 根据需要配置[前端促销活动和后端促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)选项。

1. 单击 **[!UICONTROL Save]**。
1. 使用三步引导式工作流完成 A/B 测试或 XT 活动配置。

## 编辑推荐产品建议的配置

1. 从[!UICONTROL Recommendation]边栏中，单击[!UICONTROL Criteria Name]、[!UICONTROL Design Name]或[!UICONTROL Collection Name]旁边的&#x200B;**[!UICONTROL Edit]**&#x200B;图标（![编辑图标](/help/main/assets/icons/Edit.svg)）以更改元素。

## 删除推荐产品建议

1. 单击[!UICONTROL Recommendation]面板顶部的&#x200B;**[!UICONTROL Delete]**&#x200B;图标（![删除图标](/help/main/assets/icons/Delete.svg)）。

### 查看推荐选件的状态 {#status}

推荐选件（算法）状态显示在包含推荐选件的A/B测试和XT活动的活动[!UICONTROL Overview]页面底部：

* 结果已准备就绪
* 结果未准备就绪
* 信息源失败
