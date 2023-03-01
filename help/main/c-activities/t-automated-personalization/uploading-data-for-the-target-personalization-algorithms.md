---
keywords: Automated Personalization；ap；上传数据；离线数据；个性化算法；自动定位；最佳实践
description: 了解在Adobe中构建个性化模型时如何上传离线数据，如CRM信息 [!DNL Target] Automated Personalization (AP)活动。
title: 如何上传个性化算法的数据？
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 32%

---

# 上传以下项的数据： [!DNL Target] 个性化算法

在中构建个性化模型时，离线数据（如CRM信息或客户流失倾向分数）可能非常有价值 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)活动。

可通过多种方式在[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 自动定位]个性化算法中输入数据。除了中的方法之外， [将数据导入Target的方法](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} 我们的算法中还使用了活动内报表受众。

有关自动个性化和自动定位个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

下面列出了为 Target 个性化算法上传数据的最佳实践：

* Target个性化算法可用的高质量数据越多，AP和自动定位活动中生成的模型的质量就越好。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 不要传递唯一ID，例如会话ID（如果需要）。
* 查看Target自动收集的数据( [为Target个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md))，这样您就不会发送重复信息。 例如，Target 使用 IP 地址来确定访客的邮政编码。这就不需要将此信息作为单独的变量进行传递。
* 不要在同一属性/变量中传递多个值。如果连接多个变量，Target的个性化算法会将每个字符串都视为唯一值，从而减少个性化信息的值。
* 使用令人印象深刻且有意义的命名惯例来确保 [个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) 更易于理解。
