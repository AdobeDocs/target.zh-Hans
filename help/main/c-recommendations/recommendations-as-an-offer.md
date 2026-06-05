---
keywords: 推荐;产品建议
description: 了解如何在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中使用产品建议形式的 Adobe 推荐。
title: 如何在其他活动类型中使用产品建议形式的推荐？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 571
ht-degree: 55%

---

# “推荐”作为产品建议

您现在可以在[!UICONTROL A/B测试]（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）和[!UICONTROL 体验定位] (XT)活动中包含推荐。

此功能提供了几项全新的功能，例如：

* 可在同一活动中测试和锁定推荐和非推荐内容。
* 可轻松尝试在页面上放置推荐内容，包括为多个推荐排序。
* 使用[!UICONTROL 自动分配]自动将流量推送到性能最佳的推荐体验。
* 使用[!UICONTROL 自动定位]，根据访客的配置文件动态地为他们分配量身定制的推荐体验。

若要开始，请使用[!UICONTROL 可视化体验编辑器]创建一个[!UICONTROL A/B测试]或[!UICONTROL 体验定位]活动，然后执行[!UICONTROL 此项前插入]、[!UICONTROL 此项后插入]或[!UICONTROL 替换为]操作以向体验添加推荐。

## 在 A/B 测试或 XT 活动中将推荐作为产品建议添加

1. 使用可视化体验编辑器 (VEC) 启动三步引导式工作流，以创建 [A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[体验定位](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) 活动。

   >[!NOTE]
   >
   >对于 A/B 测试，请记住您可以选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)选项以自动将流量推送到性能最佳的推荐，或者选择[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)选项以根据访客的轮廓为他们分配量身定制的推荐体验。

1. 创建[体验](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)时，单击要将推荐作为选件添加到的元素，单击&#x200B;**[!UICONTROL 替换内容]**，然后选择&#x200B;**[!UICONTROL 推荐]**。

   ![将推荐作为产品建议插入](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. 从以下选项中选择，以查看按页面类型划分的热门推荐标准：

   * 购物车页面
   * 类别页面
   * 首页
   * 登录页面
   * 产品页面
   * 搜索结果页面
   * 感谢页面
   * 其他

1. 选择所需的[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)，然后单击[!UICONTROL 下一步]。
1. 选择所需的[设计](/help/main/c-recommendations/c-design-overview/design-overview.md)，然后单击[!UICONTROL 下一步]。
1. 在[!UICONTROL 选项]对话框中，指定以下内容：

   * 选择一个[收藏集](/help/main/c-recommendations/c-products/collections.md)。
   * 根据需要配置[前端促销活动和后端促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)选项。

1. 单击[!UICONTROL 保存]。
1. 使用三步引导式工作流完成 A/B 测试或 XT 活动配置。

## 编辑推荐产品建议的配置

您可以通过两种方式编辑产品建议的配置：

* 使用[!UICONTROL 编辑]菜单
* 使用[!UICONTROL 修改]面板

### 使用“编辑”菜单编辑推荐产品建议

1. 单击要编辑的选件，然后单击&#x200B;**[!UICONTROL 编辑]**。

   ![编辑推荐产品建议](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. 从以下选项中进行选择：

   * [更改标准](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [更改设计](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [更改收藏集](/help/main/c-recommendations/c-products/collections.md)
   * [更改促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 进行编辑。

### 使用“修改”面板编辑推荐产品建议

1. 单击[!UICONTROL 修改]图标&#x200B;**( `</>` )**&#x200B;以显示[修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 将鼠标悬停在所需的操作上，然后单击&#x200B;**[!UICONTROL 编辑]**&#x200B;图标。

   ![“修改”面板](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. 进行编辑。

## 删除推荐产品建议

可通过两种方式来删除推荐产品建议：

* 使用[!UICONTROL 编辑]菜单
* 使用[!UICONTROL 修改]面板

### 使用“编辑”菜单删除推荐产品建议

1. 单击要删除的选件，然后单击&#x200B;**[!UICONTROL 布局>删除]**。

   ![删除](/help/main/c-recommendations/assets/recs-offer-remove.png)

### 使用“修改”面板删除推荐产品建议

1. 单击[!UICONTROL 修改]图标&#x200B;**( &lt;/> )**&#x200B;以显示[修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)窗格。
1. 将鼠标悬停在所需的操作上，然后单击[!UICONTROL 删除]图标。

   ![“删除”图标](/help/main/c-recommendations/assets/recs-offer-delete.png)

### 查看推荐选件的状态 {#status}

推荐选件（算法）的状态将显示在包含推荐选件的A/B测试和XT活动的[!UICONTROL 概述]页面底部：

* 结果已准备就绪
* 结果未准备就绪
* 信息源失败

![推荐产品建议状态](/help/main/c-recommendations/assets/recs-offer-status.png)

## 培训视频：产品建议形式的推荐![“概述”徽章](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
