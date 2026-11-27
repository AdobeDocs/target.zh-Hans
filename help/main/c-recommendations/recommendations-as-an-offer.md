---
keywords: 推荐;产品建议
description: 了解如何在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中使用产品建议形式的 Adobe 推荐。
title: 如何在其他活动类型中使用产品建议形式的推荐？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: 'https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 12%
---
# “推荐”作为产品建议 {#recommendations-as-an-offer}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在[!UICONTROL A/B测试]和[!UICONTROL 体验定位] (XT)活动中添加、编辑和删除推荐作为选件。

>[!ENDSHADEBOX]

除了[!UICONTROL 推荐]活动之外，推荐还可以包含在[!UICONTROL A/B测试]（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）和[!UICONTROL 体验定位] (XT)活动中。 这允许执行以下操作：

* 可在同一活动中测试和锁定推荐和非推荐内容。
* 尝试在页面上放置推荐，包括多个推荐的顺序。
* 通过&#x200B;**[!UICONTROL 自动分配]**，自动将流量推送到性能最佳的推荐体验。
* 通过&#x200B;**[!UICONTROL 自动定位]**，根据访客的配置文件动态地为他们分配量身定制的推荐体验。

## 添加推荐作为选件 {#add-recs-offer}

在[!UICONTROL A/B测试]或XT活动中使用[!UICONTROL 可视化体验编辑器] (VEC)创建体验时，推荐将作为选件添加。

1. 启动VEC的三步引导式工作流以创建[A/B测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)或[体验定位](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT)活动。

   >[!NOTE]
   >
   >对于A/B测试，[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)选项会自动将流量推送到性能最佳的推荐，而[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)选项会根据访客的配置文件为其分配量身定制的推荐体验。

1. 在创建[体验](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)时，可通过以下方式之一将推荐作为选件添加：

   * 单击要向其添加推荐的元素，单击&#x200B;**[!UICONTROL 替换内容]**，然后选择&#x200B;**[!UICONTROL 推荐]**。

     ![可视化体验编辑器，在HTML选件和体验片段选项旁的菜单中，选中标题并突出显示推荐选项](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

   * 在&#x200B;**[!UICONTROL 组件]**&#x200B;边栏中，选择&#x200B;**[!UICONTROL 动态]**&#x200B;下的&#x200B;**[!UICONTROL 推荐]**，将鼠标悬停在页面上的现有元素上，然后单击&#x200B;**[!UICONTROL 此项前插入]**&#x200B;或&#x200B;**[!UICONTROL 此项后插入]**，将推荐置于该元素之前或之后。

1. 访问&#x200B;**[!UICONTROL 显示属性]**&#x200B;菜单并单击&#x200B;**[!UICONTROL Select推荐]**。

1. Select所需的[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. Select所需的[设计](/help/main/c-recommendations/c-design-overview/design-overview.md)，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. 在&#x200B;**[!UICONTROL 选项]**&#x200B;对话框中，指定以下内容：

   * 选择一个[收藏集](/help/main/c-recommendations/c-products/collections.md)。
   * 如有必要，请配置[前端促销活动和后端促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)选项。

1. 单击&#x200B;**[!UICONTROL 保存]**。

1. 使用三步引导式工作流完成[!UICONTROL A/B测试]或XT活动的配置。

## 编辑推荐选件 {#edit-recs-offer}

推荐选件的条件、设计、收藏和促销可在添加选件后从&#x200B;**[!UICONTROL 推荐]**&#x200B;窗格中更改。

1. 单击选件以编辑并浏览右窗格菜单中的选项。

   ![包含标准、设计和收藏集名称的建议窗格，以及选定优惠的“添加促销活动”按钮](assets/create_reco_7.png)

1. Select提供以下任一选项：

   * [更改标准](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [更改设计](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [更改收藏集](/help/main/c-recommendations/c-products/collections.md)
   * [更改促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. 进行编辑。

## 删除推荐产品建议 {#delete-recs-offer}

可以从&#x200B;**[!UICONTROL 推荐]**&#x200B;窗格中删除不再需要的推荐选件。

单击要删除的选件，然后单击&#x200B;**[!UICONTROL 推荐]**&#x200B;窗格中的bin图标（![Bin图标](assets/Smock_Delete_18_N.svg)）。

![推荐窗格，其中突出显示bin图标](assets/create_reco_8.png)

## 查看推荐选件的状态 {#status}

推荐选件（算法）的状态将显示在包含推荐选件的[!UICONTROL A/B测试]和XT活动的&#x200B;**[!UICONTROL 概述]**&#x200B;页面的底部。 状态为以下状态之一：

* **[!UICONTROL 个结果已准备就绪]**
* **[!UICONTROL 个结果未就绪]**
* **[!UICONTROL 馈送失败]**

## 培训视频：产品建议形式的推荐![“概述”徽章](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
