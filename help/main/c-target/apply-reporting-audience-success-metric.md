---
keywords: 定位;受众;报表;成功量度
description: 了解如何在 [!DNL Adobe Target] 让用户符合报表受众的条件。
title: 是否可以将报表受众应用到成功量度？
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 52%

---

# 将报表受众应用于成功量度

选择一个成功量度，以便让用户符合 [!DNL Adobe Target].

对于所有活动，您都可以通过“[!UICONTROL 应用位置]”下拉列表将受众应用于成功量度，以便查看达到成功量度后的报表数量以及后续操作的报表数量。

![success_metric图像](assets/success_metric.png)

例如，假设您为所有从您的主页进入并到达转化页面的访客创建了一个活动，但是您还希望进一步了解在转化之前向购物车中添加的商品金额高于 $50 的访客。

的 [!UICONTROL 应用于] 下拉列表可能提供三个类别：活动的任何访客、活动中达到某一步骤的访客，或仅访客达到转化。 换言之，您可以指定访客必须到达活动登入页面上的 mbox，访客必须到达定义活动中间某个点处的 mbox，或访客必须到达活动结束时的转化 mbox。

[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)只有在为活动配置后才可用。如果您未定义成功量度，则从下拉列表中只看到两个选项： [!UICONTROL 营销活动登录] 和 [!UICONTROL 转化].

将报表受众应用于成功量度时，请考虑以下信息：

* 对于应用了成功量度的操作之前的操作， [!DNL Target] 不应用分段受众。
* 对于应用成功量度后执行的操作， [!DNL Target] 应用分段受众。

要在报表中查看分段，请从 [!UICONTROL 受众] 下拉列表。

![reporting_audience_dropdown图像](assets/reporting_audience_dropdown.png)
