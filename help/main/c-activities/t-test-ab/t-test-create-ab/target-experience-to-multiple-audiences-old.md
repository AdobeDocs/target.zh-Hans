---
keywords: 多个受众;体验版本;锁定体验版本
description: 了解如何在 [!DNL Adobe Target] A/B活动中将同一体验的版本定位到不同的受众。
title: 能否在A/B活动中使用多个体验版本？
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 53%

---

# A/B 测试中的多个体验受众

您可以在[!DNL Adobe Target] A/B活动中将同一体验的版本定位到不同的受众。 您可以在[!UICONTROL Visual Experience Composer] (VEC)或基于表单的体验编辑器中为一个体验设置多个受众。

当访客的配置文件发生更改时，访客可在体验受众之间切换。 在活动的生命周期内，访客不会卡在同一个体验中。

例如，如果您网站上的各个页面或产品使用了统一设计，而且您想要对多个受众（例如使用不同浏览器语言的访客）使用同一个体验，则可以设置多个体验版本。您可以向英语访客和日语访客呈现同一个体验，而唯一的区别在于显示的文本分别为访客所用的语言。收集到的体验数据不区分语言，这样，报表就可以显示体验而不是某个体验版本的效果。

如果不能设置多个体验版本，那么您就必须为每种语言（本示例）分别设置不同的测试，然后手动整合结果，以便了解这个具有两种语言的体验效果如何。这样会降低结果的准确性。由于访客是随机分配的，有些测试的计算结果甚至可能没有任何意义。

通过创建体验的不同版本，您可以获取更准确的信息，而无需进行手动计算，也无需做出假设。

## 场景

您正在测试两个体验，地理定位横幅和通用横幅。 每个地理位置的横幅需要不同，但总体测试是确定地理定位是否优于显示通用内容。 如果您为每个位置设置单独的体验，则实际上您将测量每个地理位置对另一个地理位置的表现如何，而不是当对照通用横幅进行测量时，地理定位是否有助于实现您的成功目标。

在此例中，您需要的是特定于地理位置的体验版本，因此您可以针对非地理目标控制测试地理目标体验。

1. [创建 A/B 活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)（按常规步骤操作）。

   配置具有多个版本的体验时，请按照以下步骤所示，为每个版本选择相应的受众。

1. 选择体验，然后单击&#x200B;**[!UICONTROL Configure]** > **[!UICONTROL Audiences]** > **[!UICONTROL Multiple Audiences]**。

   ![“多个受众”选项](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/multiple-audiences-new.png)

1. 单击&#x200B;**[!UICONTROL Add Audience]**，然后选择要定位的第一个受众。 对每个受众重复执行上述步骤。

   ![exp-versions图像](assets/exp-versions.png)

   如果受众尚不存在，请单击[创建受众](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558)，然后对其进行设置。

   如果访客符合多个受众的条件，则会返回适用于所有受众的内容，但页面上呈现的实际上是适用于列表中最后一个受众的内容。

1. 继续设置活动。

## 最佳实践

* 选择互斥受众。 如果活动是在VEC中创建的，且访客与多个受众匹配，则会返回每个受众的内容，并在页面上最后显示所列受众的内容。
* 活动图中定义的活动参加受众是通过“与”条件与体验受众进行组合的。因此，要参加活动，访客必须符合活动受众的条件，同时还必须符合某个体验受众的条件。
* 将相同的受众作为报表中的区段进行添加。这有助于您查看“浏览器lang ja_JP”的体验A与B高级别以及体验A与B较低级别的测试结果。 这仅适用于基于[!DNL Target]的报告，不适用于基于[!DNL Analytics]的报告。
