---
description: 选择要在创建自动个性化(AP)或自动Target活动时用作控制的体验。
keywords: 体验；控制；自动个性化；auto-target
seo-description: 选择要用作控制的体验，同时在Adobe Target中创建自动个性化(AP)或自动Target活动。
seo-title: 在Adobe Target中使用特定体验作为控制
solution: Target,Analytics
title: 使用特定体验作为控制
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: add895d353e7483dfcbe82f1bca55b277bc65f20

---


# ![高级](/help/assets/premium.png) 选择控制自动个性化或自动定位活动

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

此功能允许您根据活动中配置的流量分配百分比将控制流量路由到相关体验。然后，您可以根据控制流量来评估个性化流量的性能报告。

在AP和AT活动中设置控件的选项与其他活动类型略有不同。在手动A/B测试中，您可以更改显示为控件的报告，并根据该控制体验的转化率计算提升。您可以轻松地进行此更改，因为流量会随机提供给活动中包含的每个体验，无论最初设置为什么控件。换句话说，选择控件并不会影响流量的提供方式。在AP和AT活动中，您决定如何选择该控件会影响如何提供访客流量。因此，您需要更仔细地考虑您的决策。

您的AP和AT活动中有两个可供您控制的选项：随机提供的体验或特定体验。

* **随机提供**：为了进行随机控制，流量的控制百分比随机提供活动中的所有体验，而不考虑访客的个人资料。您可以将控制视为帮助回答问题：“如果我只随机向访客提供体验(或选件)，而不考虑他们的档案，那么该体验的转化率是多少？”此控件类似于AI活动中的A/B测试。为每个体验或选件提供非个性化转化率信息有助于了解活动结果。

* **特定体验**：通过特定体验控制，您可以比较Target个性化模型提供给特定营销人员定义体验的流量(例如，您的默认主页)。通过此选项，控制流量百分比只会随机服务这一体验。

## 指定特定体验作为控制

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. 为控制体验和其他体验指定所需的流量分配。

   对于特定体验控制，建议使用10%到30%。

1. Continue with the [!UICONTROL Goals &amp; Settings] page.

## 已知限制和注意事项

在使用特定体验作为控制时，请记住以下要点：

* 不建议在已经实时活动中更改控制体验。选择的最新控制体验在报告中命名(即使旧报告基于其他体验)。
* 建议不要删除控制体验。
* 在不建议的情况下，将大量新选件/体验添加到具有特定体验的实时活动中。
* 在AP活动中，包括对控制体验的定位，这些体验可能会进一步constra谁可以看到体验的建议。
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. 提升和置信度信息在AP活动的总体“目标”与“控制”流量级别上可用。如果选择“random”作为控件，则提升和置信信息可用。这一差异是因为，与选件的转化率相比，将特定体验的转化率与选件的转化率相比较是不合逻辑的。无论选择哪种类型的控件，AT活动中的可用信息都是相同的。
* 由于在您选择体验时，所有控制流量都会转到单个体验或选件集(与随机相比，控制流量金额会在体验中的体验或选件数量上分列)，因此您通常不需要流量流向控件。开始是一个不错的开始。
* 如果您对具有特定体验的实时活动执行以下某项操作作为控制，则该控制会自动重置为随机提供的体验(而不是以前所选的特定体验)：

   * 删除体验
   * 删除位置或选件(仅限AP)
   * 通过删除重复的选件或通过排除组(仅限AP)，手动排除体验

