---
keywords: Automated Personalization；ap；上传数据；离线数据；个性化算法；自动定位；自动定位；最佳实践
description: 了解如何在中构建个性化模型时上传离线数据 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自动定位] 活动。
title: 如何上传个性化算法的数据？
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 20%

---

# 上传以下项的数据 [!DNL Target] 个性化算法

在中构建个性化模型时，离线数据（如CRM信息或客户流失倾向分数）可能非常有价值 [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP)和 [!UICONTROL 自动定位] 活动。

可通过多种方式在[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 自动定位]个性化算法中输入数据。除了中的方法之外， [将数据导入Target的方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}， [!DNL Experience Cloud] 共享受众([!UICONTROL Adobe Analytics]， [!DNL Audience Manager])，活动中的报表受众也用于 [!DNL Target] 算法。

有关[!UICONTROL 自动个性化]和[!UICONTROL 自动定位]个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 最佳实践 {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

以下列表介绍了为上传数据的最佳实践 [!DNL Target] 个性化算法：

* 可用的高质量数据越多 [!DNL Target] 个性化算法，可使您生成的模型质量提高 [!UICONTROL Automated Personalization] 和 [!UICONTROL 自动定位] 活动。
* 限制使用多个具有相同用途的配置文件脚本或属性。
* 请勿传递唯一ID，例如会话ID（如果需要）。
* 查看哪些数据 [!DNL Target] 自动收集( [为Target个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md))，这样您就不会发送重复的信息。 例如， [!DNL Target] 使用IP地址确定访客的邮政编码。 这就不需要将此信息作为单独的变量进行传递。
* 请勿在同一属性或变量中传递多个值。 如果连接多个变量， [!DNL Target] 个性化算法将每个字符串都视为唯一值，从而减少个性化信息的价值。
* 使用一种令人难忘且有意义的命名惯例来让您的 [个性化分析报表](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) 更易于理解。
