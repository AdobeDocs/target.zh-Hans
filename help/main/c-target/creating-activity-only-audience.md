---
keywords: 受众;受众规则;创建受众;仅限该活动;临时
description: 了解如何在Adobe中创建仅限该活动的受众 [!DNL Target] 一次性使用。
title: 能否创建仅使用一次的受众？
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 53%

---

# 创建仅限活动的受众

从内创建仅限该活动的受众 [!DNL Adobe Target] 创建活动时的三步引导式工作流。 这些临时受众可用于该相同活动内的其他位置，但不会存储在[!UICONTROL 受众库]中，因此无法用于其他活动。

仅限该活动的受众可提供以下好处：

* 您可以使用仅限该活动的受众来创建只想使用一次且不想存储到[!UICONTROL 受众库]中的受众。仅限该活动的受众有助于防止 [!UICONTROL 受众库] 避免受众过多，而您绝不想再次使用这些受众。
* 仅限该活动的受众在[!UICONTROL 受众库]中是不可见的。由于这些受众在库中不可见，因此可以避免组织中的其他人对其进行不必要的更改。

1. 创建 [活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)，位于 **[!UICONTROL 定位]** 页面上，单击三个垂直省略号，然后单击 **[!UICONTROL 替换受众]**.

   ![步骤结果](assets/edit_audience.png)

1. 单击&#x200B;**[!UICONTROL 创建受众]**。

1. 单击 **[!UICONTROL 仅此活动]**.

   ![activity-only-aud图像](assets/activity-only-aud.png)

1. 键入描述性受众名称。
1. 将所需的属性拖放到受众生成器中。

   通过规则，可将受众限制为网站访客的子集。 每种规则类型都有其自身的参数。请参阅[受众类别](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以详细了解如何配置每种类型的受众规则。

1. 单击&#x200B;**[!UICONTROL 完成]**。

## 注意事项

使用仅限该活动的受众时，请牢记以下信息：

* 您可以在中创建仅限该活动的受众 [!UICONTROL 可视化体验编辑器] (VEC)或中的 [!UICONTROL 基于表单的体验编辑器]. 此功能取代了以前版本中的细化规则 [!DNL Target].
* 您可以创建活动并将其存储到[!UICONTROL 受众库]中以供在其他活动中重复使用，也可以创建仅限该活动的受众。保存受众后，无法更改受众类型。
* 现有活动的细化规则已迁移到仅限该活动的受众。
* 仅限该活动的受众具有两种状态：“[!UICONTROL 已使用]”或“[!UICONTROL 未使用]”。未使用的仅限该活动的受众在保存活动后将不会显示。如果将仅限该活动的受众保留为“未使用”状态，在您尝试保存活动时，系统会显示一条警告消息，告知您未使用的仅限该活动的受众将被删除。
* 您可以从受众选取器中访问弹出卡片，以查看该卡片上的受众定义详细信息，而无需打开受众。
* 您可以[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)，以创建仅限该活动的受众。
* 仅限该活动的受众不支持排除规则。

   您可以使用以下替代方案来使用“排除规则”：

   * [创建和使用库受众](/help/main/c-target/c-audiences/create-audience.md) 而不是仅限该活动的受众。
   * [合并多个](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) （最多20个）将库受众转换为仅限该活动的受众。 在组合受众时，即使组合受众另存为仅限该活动的受众，也可以在各个库受众中使用包含和排除规则。
