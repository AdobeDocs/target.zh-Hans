---
keywords: 定位;AP 报表;自动个性化报表;自动定位;自动定位报表;个性化;分析;自动化区段;常见问题解答;常见问题解答;重要属性
description: 了解如何使用专门的Automated Personalization(AP)和自动定位(AT)活动报表 — 自动化区段和重要属性。
title: 如何使用个性化分析报表？
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: ca1f42b95399fbd136aee27ccec9ed0e38876234
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 57%

---

# ![PREMIUM](/help/main/assets/premium.png) 个性化分析报表

“[!UICONTROL 自动个性化]”(AP) 和自动定位 (AT) 活动的用户可以使用两个专门的报表：“[!UICONTROL 自动化区段]”和重要属性报表。

>[!NOTE]
>
>使用个性化分析报表时，请考虑以下事项：
>
>* AP 和 AT 活动会作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，它们将不会包含在 [!DNL Target Standard] 中。
>
>* [!UICONTROL 个性化分析报表仅适用于使用转化优化目标的 AP 和 AT 活动。]活动上线后将优化目标从收入更改为转化的活动也不受支持。
>
>* [!UICONTROL 个性化分析] 仅当 [!UICONTROL 主要目标] 的 [!UICONTROL 报表量度] 下拉列表。
>
>* 仅[默认环境](/help/main/administrating-target/hosts.md)支持个性化分析报表。
>
>* [!UICONTROL 个性化分析] 仅为中的活动生成报表 [!UICONTROL 实时] 状态和，且已激活且接收流量至少15天。


## 个性化分析报表概述 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

“[!UICONTROL 个性化分析]”报表的目标是针对 AP 和 AT 活动背后的 Target 个性化模型如何个性化访客流量提供更多信息。的 [随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) 是 [!DNL Target] 个性化模型。

因为 [!UICONTROL 个性化分析] 报告是为了了解 [!DNL Target] 个性化模型决定将哪位访客发送到哪些内容， [!UICONTROL 个性化分析] 报表仅反映您的AP或AT活动提供的所有流量的子区段。 具体而言，这两个报表反映了使用个性化模型的所有流量。换句话说，“[!UICONTROL 个性化分析]”报表不会考虑控制流量或整个入选者模型提供的流量。

两个 [!UICONTROL 个性化分析] 报表可用：

| 报表 | 详细信息 |
|--- |--- |
| [!UICONTROL 自动化区段] | 不同的访客对您的 AP/AT 活动中的选件/体验做出的响应会有所不同。此报表显示了 [!DNL Target] 个性化模型对活动中的选件/体验做出了响应。 |
| [!UICONTROL 重要属性] | 在不同的活动中，不同的属性对模型如何决定进行个性化的重要性也大小不一。此报表可显示影响模型的排名靠前的属性及其相对重要性。 |

## 解释个性化分析中的属性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

在 AP 或自动定位模型中使用的“[!UICONTROL 个性化分析]”中显示有两种类型的属性：

* **自动收集的属性：**[!DNL Target]Target 使用基础数据集在 AP 和 AT 活动中构建其个性化算法，这些算法将反映在个性化分析中。请参阅[为 Target 个性化算法收集数据](/help/main/c-activities/t-automated-personalization/ap-data.md)，以了解数据类型、示例属性及其[!UICONTROL 个性化分析]命名约定。请注意，这些属性虽然会被考虑在内，但单个活动的模型可能不会在最终模型中使用所有这些属性。
* **传递给 Target 的属性：**&#x200B;请参阅[为 Target 个性化算法上传数据](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target] 为您提供了许多方法，用于将其他数据传递给 ，以丰富用于在 AP 和 AT 活动中构建其个性化算法的基础数据集：[!DNL Target]

| 数据类型 | 描述 | 数据类型命名约定 |
|--- |--- |--- |
| 配置文件属性，包括配置文件脚本、配置文件更新 API 和页面内配置文件属性 | 您决定要包含在 Target 用户配置文件中的任何信息。<br>这些信息可能来自配置文件脚本、使用配置文件更新 API 上传的信息，或 mbox 内前缀为“profile”的配置文件参数。 | `Custom - Profile - [parameter name]` |
| 页面参数（也称为“mbox 参数”） | 直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客户属性 | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，即可在 Adobe Analytics 和 Adobe Target 中利用这些数据。 | `Custom - Customer Attributes - [parameter name]` |
| 共享受众（Adobe Audience Manager 或 Adobe Analytics） | 通过 Adobe Audience Manager 或 Adobe Analytics 创建并与 Target 共享的受众。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共享受众(Adobe Experience Platform/Real-time CDP) | 通过Adobe Experience Platform/Real-time CDP创建的受众，并通过目标与Target共享。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共享属性(Adobe Experience Platform/Real-time CDP) | 通过Adobe Experience Platform/Real-time CDP创建并通过目标与Target共享的属性。 此功能目前处于测试阶段。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| 活动内报表受众/区段 | 在 AP 或自动定位活动中的“目标和量度”设置期间定义的受众。 | `Custom - Reporting Segment - [segment name]` |

## 常见问题解答

有关 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] [!UICONTROL 分析] 报表。

### [!UICONTROL Automated Personalization] (AP) 和[!UICONTROL 自动定位]模型的数据会保留多长时间？

[!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] 系统会为模型提供有关活动最近45天用户行为（用户配置文件、展示事件和转化事件）的培训。

[!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] 模型会保留90天的用户行为、培训记录和模型决策数据以生成 [!UICONTROL 分析] 报表。 90天后，将丢弃培训记录和模型决策。 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 自动定位] 模型还会为报告目的而保留两年的总体体验/选件级别的展示和转化数据。 此数据仅是聚合级别数据，不包含任何单个级别的用户档案数据。

## 培训视频：使用个性化分析报表 ![教程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

有关更多信息，请参阅 [在Adobe Target中使用个性化分析报表](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobe博客

* 第一部分： [揭开AI驱动个性化的神秘面纱](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分： [AI个性化幕后的Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第三部分： [MAGIX — 解决AI驱动个性化黑匣子问题的方法](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
