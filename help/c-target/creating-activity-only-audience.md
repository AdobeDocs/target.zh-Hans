---
description: 创建活动时，可在三步引导式工作流中创建仅限该活动的受众。这些临时受众可用于该相同活动内的其他位置，但不会存储在受众库中，因此无法用于其他活动。
keywords: 受众;受众规则;创建受众;仅限该活动;临时
seo-description: 创建活动时，可在 Adobe Target 三步引导式工作流中创建仅限该活动的受众。这些临时受众可用于该相同活动内的其他位置，但不会存储在受众库中，因此无法用于其他活动。
seo-title: 在 Adobe Target 中创建仅限该活动的受众 在Adobe Target中
solution: Target
title: 创建仅限该活动的受众
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 创建仅限该活动的受众{#create-an-activity-only-audience}

创建活动时，可在三步引导式工作流中创建仅限该活动的受众。这些临时受众可用于该相同活动内的其他位置，但不会存储在[!UICONTROL 受众库]中，因此无法用于其他活动。

仅限该活动的受众可提供以下好处：

* 您可以使用仅限该活动的受众来创建只想使用一次且不想存储到[!UICONTROL 受众库]中的受众。这样可防止[!UICONTROL 受众库]中堆满您绝不想再次使用的受众。
* 仅限该活动的受众在[!UICONTROL 受众库]中是不可见的。因此，可以避免组织中的他人对其进行不必要的更改。

1. 创建[活动](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)时，在 **[!UICONTROL Target]** 页面上单击三个垂直省略号，然后单击&#x200B;**[!UICONTROL 替换受众]**。

   ![步骤结果](assets/edit_audience.png)

1. 在“[!UICONTROL 选择受众]”页面上，单击&#x200B;**[!UICONTROL 仅限该活动的受众]**。

   ![](assets/activity-only-aud.png)

1. 单击&#x200B;**[!UICONTROL 创建受众]**。
1. 键入描述性受众名称。
1. 单击 **[!UICONTROL + 添加规则]**。

   规则可将您的受众限制为网站访客的子集。

1. 选择规则类型。

   每种规则类型都有其自身的参数。请参阅[受众类别](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以详细了解如何配置每种类型的受众规则。

1. 定义规则参数。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 注意事项

使用仅限该活动的受众时，请牢记以下信息：

* 您可以在可视化体验编辑器 (VEC) 或基于表单的体验编辑器中创建仅限该活动的受众。此功能取代了 Target 以前版本中的细化规则。
* 您可以创建活动并将其存储到[!UICONTROL 受众库]中以供在其他活动中重复使用，也可以创建仅限该活动的受众。保存受众后，无法更改受众类型。
* 现有活动的细化规则已迁移到仅限该活动的受众。
* 仅限该活动的受众具有两种状态：“[!UICONTROL 已使用]”或“[!UICONTROL 未使用]”。未使用的仅限该活动的受众在保存活动后将不会显示。如果将仅限该活动的受众保留为“未使用”状态，在您尝试保存活动时，系统会显示一条警告消息，告知您未使用的仅限该活动的受众将被删除。
* 您可以从受众选取器中访问弹出卡片，以查看该卡片上的受众定义详细信息，而无需打开受众。
* 您可以[合并多个受众](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)，以创建仅限该活动的受众。

