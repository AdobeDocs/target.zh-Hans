---
keywords: Automated Personalization;ap；上传数据；离线数据；个性化算法；自动目标；自动目标；最佳实践
description: 了解在Adobe [!DNL Target] Automated Personalization(AP)活动中构建个性化模型时如何上传离线数据（如CRM信息）。
title: 如何上传个性化算法的数据？
feature: 自动个性化
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 75%

---

# 上传[!DNL Target]个性化算法的数据

在[!DNL Adobe Target] [!UICONTROL  Automated Personalization](AP)活动中构建个性化模型时，离线数据（如CRM信息或客户流失倾向得分）可能极其有价值。

可通过多种方式在[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 自动定位]个性化算法中输入数据。除了[将数据导入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)中的方法之外，我们的算法中还使用了 Experience Cloud 共享受众（Adobe Analytics、Audience Management）和活动中的报表受众。

有关自动个性化和自动定位个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](/help/c-activities/t-automated-personalization/ap-data.md)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

下面列出了为 Target 个性化算法上传数据的最佳实践：

* 提供给 Target 个性化算法的高质量数据越多，AP 和自动定位活动中所生成模型的质量就越高。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 如果不需要，请不要传递唯一的 ID，例如会话 ID。
* 查看 Target 自动收集的数据（[为 Target 个性化算法收集数据](/help/c-activities/t-automated-personalization/ap-data.md)）以便您不会发送重复信息。例如，Target 使用 IP 地址来确定访客的邮政编码。这就不需要将此信息作为单独的变量进行传递。
* 不要在同一属性/变量中传递多个值。如果将多个变量连接起来，Target 个性化算法会将每个字符串视为唯一值，从而减少个性化信息的值。
* 使用便于记忆且有意义的命名约定，以使您的[个性化分析报表](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更易于理解。
