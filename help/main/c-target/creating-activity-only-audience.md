---
keywords: 受众;受众规则;创建受众;仅限该活动;临时
description: 了解如何在Adobe [!DNL Target] 中创建一次性使用的仅限该活动的受众。
title: 能否创建只使用一次的受众？
feature: Audiences
exl-id: 5fe0507a-75d1-47bc-a941-8c8eeeaf3b75
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 31%

---

# 创建仅限活动的受众

创建活动时，可在[!DNL Adobe Target]三步引导式工作流中创建仅限该活动的受众。 这些临时受众可用于该相同活动内的其他位置，但不会存储在[!UICONTROL Audiences Library]中以用于其他活动。

仅限该活动的受众可提供以下好处：

* 您可以使用仅限该活动的受众来创建只想使用一次且不想存储到[!UICONTROL Audiences Library]中的受众。 仅限该活动的受众有助于防止[!UICONTROL Audiences Library]中栈满您绝不想再次使用的受众。
* 仅限该活动的受众在[!UICONTROL Audiences Library]中不可见。 由于这些受众在库中不可见，因此可以避免组织中的其他人对其进行不必要的更改。

1. 创建[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)时，在&#x200B;**[!UICONTROL Targeting]**&#x200B;页面上单击三个垂直省略号，然后单击&#x200B;**[!UICONTROL Replace Audience]**。

   ![步骤结果](assets/edit_audience.png)

1. 单击 **[!UICONTROL Create Audience]**。

1. 单击 **[!UICONTROL This activity only]**。

   ![仅用于活动的审核图像](assets/activity-only-aud.png)

1. 键入描述性受众名称。
1. 将所需的属性拖放到受众生成器中。

   通过规则，可将受众限制为网站访客的子集。 每种规则类型都有其自身的参数。请参阅[受众类别](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以详细了解如何配置每种类型的受众规则。

1. 单击 **[!UICONTROL Done]**。

## 注意事项

使用仅限该活动的受众时，请牢记以下信息：

* 您可以在[!UICONTROL Visual Experience Composer] (VEC)或[!UICONTROL Form-Based Experience Composer]中创建仅限该活动的受众。 此功能取代了以前版本的[!DNL Target]中的细化规则。
* 您可以创建要在[!UICONTROL Audience Library]中存储以供在其他活动中重复使用的活动，也可以创建仅限该活动的受众。 保存受众后，无法更改受众类型。
* 现有活动的细化规则已迁移到仅限该活动的受众。
* 仅限该活动的受众的状态为[!UICONTROL Used]或[!UICONTROL Unused]。 未使用的仅限该活动的受众在保存活动后将不会显示。如果将仅限该活动的受众保留为“未使用”状态，在您尝试保存活动时，系统会显示一条警告消息，告知您未使用的仅限该活动的受众将被删除。
* 您可以从受众选取器中访问弹出卡片，以查看该卡片上的受众定义详细信息，而无需打开受众。
* 您可以[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以创建仅限该活动的受众。
* 仅限该活动的受众不支持排除规则。

  您可以使用以下替代方案来使用“排除规则”：

   * [创建和使用库受众](/help/main/c-target/c-audiences/create-audience.md)，而不是仅用于活动的受众。
   * [将多个](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)（最多20个）库受众合并为仅限该活动的受众。 在组合受众时，即使组合受众另存为仅限该活动的受众，也可以在各个库受众中使用包含和排除规则。
