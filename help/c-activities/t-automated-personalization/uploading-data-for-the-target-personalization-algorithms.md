---
description: 在构建个性化模型时，离线数据（例如 CRM 信息或客户流失倾向评分）可能会有极大的价值。
title: 上传 Target 个性化算法数据
feature: ap
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---


# 为 Target 个性化算法上传数据{#upload-data-for-target-s-personalization-algorithms}

在构建个性化模型时，离线数据（例如 CRM 信息或客户流失倾向评分）可能会有极大的价值。

可通过多种方式在自动个性化 (AP) 和自动定位个性化算法中输入数据。除了[将数据导入 Target 的方法](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)中的方法之外，我们的算法中还使用了 Experience Cloud 共享受众（Adobe Analytics、Audience Management）和活动中的报表受众。

有关自动个性化和自动定位个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

下面列出了为 Target 个性化算法上传数据的最佳实践：

* 提供给 Target 个性化算法的高质量数据越多，AP 和自动定位活动中所生成模型的质量就越高。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 如果不需要，请不要传递唯一的 ID，例如会话 ID。
* 查看 Target 自动收集的数据（[为 Target 个性化算法收集数据](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)）以便您不会发送重复信息。例如，Target 使用 IP 地址来确定访客的邮政编码。这就不需要将此信息作为单独的变量进行传递。
* 不要在同一属性/变量中传递多个值。如果将多个变量连接起来，Target 个性化算法会将每个字符串视为唯一值，从而减少个性化信息的值。
* 使用便于记忆且有意义的命名约定，以使您的[个性化分析报表](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更易于理解。

