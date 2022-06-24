---
keywords: Automated Personalization;AP；上传数据；离线数据；个性化算法；自动定位；自动定位；最佳实践
description: 了解如何在Adobe中构建个性化模型时上传离线数据（如CRM信息） [!DNL Target] Automated Personalization(AP)活动。
title: 如何为个性化算法上传数据？
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 63%

---

# 上传 [!DNL Target] 个性化算法

在中构建个性化模型时，离线数据（如CRM信息或客户流失倾向得分）可能会非常有价值 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活动。

可通过多种方式在[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 自动定位]个性化算法中输入数据。除了 [将数据导入Target的方法](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}、Experience Cloud共享受众(Adobe Analytics、受众管理){target=_blank}和活动中的报表受众也在我们的算法中使用。

有关自动个性化和自动定位个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

下面列出了为 Target 个性化算法上传数据的最佳实践：

* 提供给 Target 个性化算法的高质量数据越多，AP 和自动定位活动中所生成模型的质量就越高。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 如果不需要，请不要传递唯一的 ID，例如会话 ID。
* 查看 Target 自动收集的数据（[为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md)）以便您不会发送重复信息。例如，Target 使用 IP 地址来确定访客的邮政编码。这就不需要将此信息作为单独的变量进行传递。
* 不要在同一属性/变量中传递多个值。如果将多个变量连接起来，Target 个性化算法会将每个字符串视为唯一值，从而减少个性化信息的值。
* 使用便于记忆且有意义的命名约定，以使您的[个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更易于理解。
