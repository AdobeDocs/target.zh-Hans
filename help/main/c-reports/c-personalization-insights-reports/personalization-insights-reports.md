---
keywords: 定位;AP 报表;自动个性化报表;自动定位;自动定位报表;个性化;分析;自动化区段;常见问题解答;常见问题解答;重要属性
description: 了解如何为Automated Personalization (AP)和自动定位(AT)活动使用专用报表 — 自动化区段和重要属性。
title: 如何使用Personalization分析报表？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights]个报告

[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] (AT)活动的用户可以使用两个专用报告： [!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]报告。

## 注意事项

使用[!UICONTROL Personalization Insights]报表时，请考虑以下事项：

* AP和AT活动作为[[!DNL Target Premium] 解决方案](/help/main/c-intro/intro.md#premium)的一部分提供。 在没有 [!DNL Target Premium] 许可证的情况下，它们将不会包含在 [!DNL Target Standard] 中。

* [!UICONTROL Personalization Insights]报告仅适用于如下配置的AP和AT活动：

   * [!DNL Target]报告> [!UICONTROL Conversion]

     例如：

     ![目标报表>转化](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics]报告> [!DNL Conversion]

     例如：

     ![Analytic Reporting >转换](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics]报告> [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     例如：

     ![使用Analytics量度>最大化访问转化率](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* 活动上线后将优化目标从收入更改为转化的活动也不受支持。

* 仅当从[!UICONTROL Personalization Insights]下拉列表中选择[!UICONTROL Primary Goal]时，[!UICONTROL Report Metric]报告才可用。

* 仅[!UICONTROL Personalization Insights]默认环境[支持](/help/main/administrating-target/hosts.md)报告。

* 仅为处于[!UICONTROL Personalization Insights]状态并且已激活且接收流量至少15天的活动生成[!UICONTROL Live]报告。

## Personalization Insights报表概述 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL Personalization Insights]报表的目标是提供有关AP和AT活动背后的[!UICONTROL Target]个性化模型如何个性化访客流量的更多信息。 [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)是[!DNL Target]个性化模型的基础。

由于[!UICONTROL Personalization Insights]报表的目标是了解[!DNL Target]个性化模型如何决定向哪些访客发送哪些内容，因此[!UICONTROL Personalization Insights]报表仅反映AP或AT活动提供的所有流量的子区段。 具体而言，这两个报表反映了使用个性化模型的所有流量。换句话说，[!UICONTROL Personalization Insights]报表不考虑控制流量或整个入选者模型提供的流量。

有两个[!UICONTROL Personalization Insights]报告可用：

| 报表 | 详细信息 |
|--- |--- |
| [!UICONTROL Automated Segments] | 不同的访客对您的 AP/AT 活动中的选件/体验做出的响应会有所不同。此报表显示[!DNL Target]个性化模型定义的不同自动化区段如何响应活动中的选件/体验。 |
| [!UICONTROL Important Attributes] | 在不同的活动中，不同的属性对模型如何决定进行个性化的重要性也大小不一。此报表可显示影响模型的排名靠前的属性及其相对重要性。 |

## 解释Personalization Insights中的属性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

在[!UICONTROL Personalization Insights]报表中表示的AP或自动定位模型中使用了两种类型的属性：

* **Target自动收集的属性：** [!DNL Target]使用基础数据集在AP和AT活动中构建其个性化算法，这些算法反映在Personalization Insights中。 有关数据类型、示例属性及其[命名约定，请参阅](/help/main/c-activities/t-automated-personalization/ap-data.md)Target Personalization算法的数据收集[!UICONTROL Personalization Insights]。 请注意，虽然考虑了这些属性，但单个活动的模型可能不会在最终模型中使用所有这些属性。
* **传递到Target的属性：**&#x200B;请参阅[上传Target Personalization算法的数据](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target]为您提供了多种方法来将附加数据传递到[!DNL Target]，以扩充用于在AP和AT活动中构建其个性化算法的基本数据集：

| 数据类型 | 描述 | 数据类型命名约定 |
|--- |--- |--- |
| 配置文件属性，包括配置文件脚本、配置文件更新 API 和页面内配置文件属性 | 您决定要包含在 Target 用户轮廓中的任何信息。<br>这些信息可能来自配置文件脚本、使用配置文件更新 API 上传的信息，或 mbox 内前缀为“profile”的配置文件参数。 | `Custom - Profile - [parameter name]` |
| 页面参数（也称为“mbox参数”） | 直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客户属性 | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，即可在 Adobe Analytics 和 Adobe Target 中利用这些数据。 | `Custom - Customer Attributes - [parameter name]` |
| 共享受众（Adobe Audience Manager 或 Adobe Analytics） | 通过 Adobe Audience Manager 或 Adobe Analytics 创建并与 Target 共享的受众。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共享受众(Adobe Experience Platform/Real-time CDP) | 通过Adobe Experience Platform/Real-time CDP创建并通过Destinations与Target共享的受众。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共享属性(Adobe Experience Platform/Real-time CDP) | 通过Adobe Experience Platform/Real-time CDP创建并通过目标与Target共享的属性。 此功能当前位于Beta中。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| 活动内报表受众/区段 | 在“目标和量度”中设置期间，在AP或自动定位活动中定义的受众。 | `Custom - Reporting Segment - [segment name]` |

## 常见问题解答

有关[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target] [!UICONTROL Insights]报告的常见问题解答列表。

### [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型的数据会保留多长时间？

针对活动过去45天的用户行为（用户配置文件、展示事件和转化事件），对[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型进行了培训。

[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型将用户行为、培训记录和模型决策数据保留90天以生成[!UICONTROL Insights]报告。 90天后，将丢弃培训记录和模型决策。 [!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]模型还会保留两年汇总的体验/选件级别的展示和转化数据以用于报表目的。 此数据仅是聚合级别的数据，不包含任何个人级别的用户档案数据。

## 培训视频：使用Personalization Insights报表![教程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/328064?captions=chi_hans)

有关详细信息，请参阅[在Adobe Target中使用Personalization分析报表](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)。

## Adobe博客

* 第1部分：[揭开人工智能驱动的Personalization的神秘面纱](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分：[在Adobe Target的Personalization人工智能幕后窥视](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第3部分：[MAGIX — 解决AI驱动的Personalization的黑盒问题](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
