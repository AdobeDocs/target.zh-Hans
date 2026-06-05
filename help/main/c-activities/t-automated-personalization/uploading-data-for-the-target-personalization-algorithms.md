---
keywords: Automated Personalization；ap；上传数据；离线数据；个性化算法；自动定位；自动定位；最佳实践
description: 了解在 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和[!UICONTROL 自动定位]活动中构建个性化模型时如何上载离线数据。
title: 如何为Personalization算法上传数据？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 323
ht-degree: 12%

---

# 上传[!DNL Target]个性化算法的数据

在[!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和[!UICONTROL 自动定位]活动中构建个性化模型时，离线数据（如CRM信息或客户流失倾向分数）可能会非常有价值。

有几种方法可在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL 自动定位]个性化算法中输入数据。 除了[方法中用于将数据导入Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}的方法之外，[!DNL Target]算法中还使用了[!DNL Experience Cloud]共享受众([!UICONTROL Adobe Analytics]，[!DNL Audience Manager])和活动中的报表受众。

有关[!UICONTROL Automated Personalization]和[!UICONTROL 自动定位]个性化算法自动收集和使用的数据的信息，请参阅[Automated Personalization数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

以下列表介绍了上传[!DNL Target]个性化算法数据的最佳实践：

* 可用于[!DNL Target]个性化算法的高质量数据越多，您的[!UICONTROL Automated Personalization]和[!UICONTROL 自动定位]活动中生成的模型的质量就越好。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 请勿传递唯一ID，例如会话ID（如果需要）。
* 查看[!DNL Target]自动收集的数据（[为Target Personalization算法收集的数据](/help/main/c-activities/t-automated-personalization/ap-data.md)），以便您不会发送重复信息。 例如，[!DNL Target]使用IP地址确定访客的邮政编码。 这就不需要将此信息作为单独的变量进行传递。
* 请勿在同一属性或变量中传递多个值。 如果连接了多个变量，[!DNL Target]个性化算法会将每个字符串视为唯一值，从而减少个性化信息的值。
* 使用令人难忘且有意义的命名惯例以使您的[Personalization分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)更易于理解。
