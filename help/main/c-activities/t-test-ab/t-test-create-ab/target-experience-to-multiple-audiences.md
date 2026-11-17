---
keywords: 多个受众;体验版本;锁定体验版本
description: 了解如何在A/B活动中使用同一体验的版本定位不同的受众区段。
title: 能否在A/B活动中使用多个体验版本？
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
TQID: 'https://experienceleague.adobe.com/FleyH-u5cWI5vku9E4-RMWeIc95WgPy-VQ-eytxka18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 8%
---
# A/B 测试中的多个体验受众 {#multiple-experience-audiences}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在A/B活动中使用相同体验的版本定位不同的受众，并通过包含要遵循的步骤的用例和最佳实践进行说明。

>[!ENDSHADEBOX]

在[!DNL Adobe Target]个A/B活动中，您可以将同一体验的版本定位到不同的受众。 您可以在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)或基于表单的体验编辑器中为某个体验设置多个受众。

数据收集时会为体验而不考虑版本，因此报表会显示体验的性能，而不是每个版本的性能。 当访客的配置文件发生更改时，访客还可以在体验受众之间切换。 在活动期间，他们不会陷入相同的体验。

## 用例 {#use-case}

您正在测试两个体验：

* 地理定位横幅

* 通用横幅。

每个地理位置的横幅需要不同，但测试的目标是确定地理定位的效果是否优于常规内容。

如果您为每个地点设置单独的体验，则可以测量每个地理位置相对于其他地理位置的表现。 与通用横幅相比，您无法衡量地理定位是否有助于实现成功目标。

在这种情况下，您需要特定于地理位置的体验版本，以便针对非地理目标控制体验测试地理目标体验。

要设置特定于地理位置的版本，请执行以下操作：

1. [创建 A/B 活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)（按常规步骤操作）。

   在配置具有多个版本的体验时，请按照以下步骤所述，为每个版本选择受众。

1. 选择体验，然后单击&#x200B;**[!UICONTROL 配置]** > **[!UICONTROL 多个受众]**。

1. 在&#x200B;**[!UICONTROL 体验受众]**&#x200B;窗格中，单击&#x200B;**[!UICONTROL 添加受众]**&#x200B;图标（![添加图标](/help/main/assets/icons/Add.svg)），然后选择要定位的第一个受众。 对每个受众重复执行上述步骤。

   如果受众尚不存在，请[创建受众](/help/main/c-target/c-audiences/create-audience.md)并进行设置。

1. 继续设置活动。

## 最佳实践 {#best-practices}

* 选择互斥受众。 如果访客符合多个受众的条件，则会返回所有这些受众的内容，并在页面上显示最后列出的受众内容。 这适用于在VEC中创建的活动。
* 图表中定义的活动进入受众通过使用AND条件与体验受众相结合。 要进入活动，访客必须符合活动受众和其中一个体验受众的条件。
* 将相同的受众作为报表中的区段进行添加。 这有助于您查看仅针对“浏览器lang ja_JP”的体验A与B高级别以及体验A与B较低级别的测试结果。 这仅适用于基于[!DNL Target]的报告，不适用于基于[!DNL Analytics]的报告。
