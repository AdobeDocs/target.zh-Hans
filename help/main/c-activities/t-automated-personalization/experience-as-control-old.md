---
keywords: 体验;控制;自动个性化;自动锁定
description: 了解如何在 [!DNL Adobe Target]中创建[!UICONTROL Automated Personalization] (AP)或[!UICONTROL Auto-Target]活动时选择要用作控制的体验。
title: 如何在[!UICONTROL Automated Personalization]活动中使用特定体验作为控制？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 42%

---

# 为您的[!UICONTROL Automated Personalization]或[!UICONTROL Auto-Target]活动选择控件

您可以在创建[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP)或[[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动时，选择随机提供的体验或特定体验作为控制。

通过此功能，您可以根据活动中配置的流量分配百分比，将控制流量路由到特定体验。然后，您可以根据该控制的控制流量评估个性化流量的性能报表。

在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活动中设置控件的选项与其他活动类型略有不同。 在手动[!UICONTROL A/B Test]中，您可以更改显示为控制的报表，并根据该控制体验的转化率计算提升度。 您可以轻松地进行此更改，因为无论最初设置的控制是什么，系统都会随机将流量提供给您在活动中包含的每个体验。换言之，选择控制不会影响流量的提供方式。 在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活动中，您决定选作控制的内容确实会影响访客流量的提供方式。 因此，您必须更仔细地考虑您的决定。

在[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]活动中，有两个选项可供您控制：

* **随机提供的体验**：对于随机控制，流量的控制百分比会随机提供给活动中的所有体验，而不考虑该访客的配置文件。 您可以考虑使用控制来帮助回答以下问题：“如果我只是随机向访客提供体验（或选件）而不考虑他们的配置文件，那么该体验（或选件）的转化率是多少？” 该控件与AI活动中的[!UICONTROL A/B Test]类似。 在分析活动结果时，了解每个体验或产品建议的非个性化转化率信息可能会有所帮助。

* **特定体验**：通过特定体验控制，可将[!DNL Target]个性化模型所提供的流量与特定营销人员定义的体验（例如，您的默认主页）进行比较。 使用此选项，流量的控制百分比仅会随机为该一个体验提供流量。

## 指定特定体验作为控制

1. 创建或编辑[[!UICONTROL Automated Personalization]活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)或[[!UICONTROL Auto-Target]活动](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)时，根据需要配置体验。
1. 在[!UICONTROL Targeting]页面（三步引导式工作流的步骤2）上，选择所需的体验作为控制。
1. 为控制体验和其他体验指定所需的流量分配。

   对于特定体验控制，建议分配 10% 到 30% 的流量。

1. 继续[!UICONTROL Goals & Settings]页面。

## 已知限制和注意事项

在使用特定体验作为控制时，请记住以下几点：

* 不建议更改已处于实时状态的活动中的控制体验。所选的最新控制体验会在报表中进行命名（即使较旧的报表基于其他体验也是如此）。
* 不建议删除控制体验。
* 不建议向使用特定体验作为控制的实时活动中添加许多新选件或体验。
* 在[!UICONTROL Automated Personalization]活动中，不建议包含对控制体验的定位，这可能会进一步限制能够查看该体验的用户。
* 在[!UICONTROL Automated Personalization]活动中，如果选择了特定体验，则提升度和置信度信息在选件级别报表中为&#x200B;*NOT*&#x200B;可用。 提升度和置信度信息在[!UICONTROL Automated Personalization]活动的整体“目标”与“控制”流量级别可用。 如果选择“随机”作为控制，则可以使用提升度和置信度信息。造成这种差异的原因在于，由于单位不同，将特定体验的转化率与产品建议的转化率进行比较不合逻辑。无论选择哪种控制类型，[!UICONTROL Auto-Target]活动中的可用信息都是相同的。
* 由于当您选择体验作为控制时，所有控制流量都会流向一个体验或一组产品建议（与将随机体验作为控制相比，在这种情况下，控制流量会根据您的活动中的体验或产品建议数进行拆分），因此您通常无需使大量流量流向控制。分配 10% 的流量即可。
* 如果您对使用特定体验作为控制的实时活动执行以下操作之一，则控制会自动重置为随机提供的体验（而不是之前选择的特定体验）：

   * 删除体验
   * 删除位置或选件（仅限[!UICONTROL Automated Personalization]）
   * 通过删除重复的选件或通过排除组手动排除体验（仅限[!UICONTROL Automated Personalization]）
