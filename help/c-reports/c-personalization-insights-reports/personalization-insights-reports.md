---
keywords: 定位;AP 报表;自动个性化报表;自动定位;自动定位报表;个性化;分析;自动化区段;常见问题解答;常见问题解答;重要属性
description: 自动个性化 (AP) 和自动定位 (AT) 活动的用户可以使用两个专门的报表：自动化区段和重要属性报表。
title: 个性化分析报表
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 72%

---


# ![PREMIUM](/help/assets/premium.png) 个性化分析报表{#personalization-insights-reports}

“[!UICONTROL 自动个性化]”(AP) 和自动定位 (AT) 活动的用户可以使用两个专门的报表：“[!UICONTROL 自动化区段]”和重要属性报表。

>[!NOTE]
>
>使用个性化洞察报告时，请考虑以下事项：
>
>* AP 和 AT 活动会作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，它们将不会包含在 [!DNL Target Standard] 中。
   >
   >
* [!UICONTROL 个性化分析报表仅适用于使用转化优化目标的 AP 和 AT 活动。]活动上线后将优化目标从收入更改为转化的活动也不受支持。
   >
   >
* [!UICONTROL 仅当] 从“报表量度”下拉 [!UICONTROL 列表] 中选择的主Goalis时， [!UICONTROL “个性化洞察”报表才] 可用。
   >
   >
* 仅[默认环境](/help/administrating-target/hosts.md)支持个性化分析报表。
   >
   >
* [!UICONTROL 个] 性化洞察报表仅针对处于“实时”状  态且已激活并接收至少15天流量的活动生成。


## 个性化分析报表概述 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

“[!UICONTROL 个性化分析]”报表的目标是针对 AP 和 AT 活动背后的 Target 个性化模型如何个性化访客流量提供更多信息。[随机林算法](/help/c-activities/t-automated-personalization/algo-random-forest.md)是[!DNL Target]个性化模型的基础。

由于[!UICONTROL 个性化洞察]报告的目标是了解[!DNL Target]个性化模型如何决定将哪个访客发送到哪些内容，因此[!UICONTROL 个性化洞察]报告仅反映您的AP或AT活动所提供流量的子细分。 具体而言，这两个报表反映了使用个性化模型的所有流量。换句话说，“[!UICONTROL 个性化分析]”报表不会考虑控制流量或整个入选者模型提供的流量。

提供两份[!UICONTROL 个性化洞察]报告：

| 报表 | 详细信息 |
|--- |--- |
| [!UICONTROL 自动化区段] | 不同的访客对您的 AP/AT 活动中的选件/体验做出的响应会有所不同。此报告显示由[!DNL Target]个性化模型定义的不同自动细分对活动中的优惠/体验的响应情况。 |
| [!UICONTROL 重要属性] | 在不同的活动中，不同的属性对模型如何决定进行个性化的重要性也大小不一。此报表可显示影响模型的排名靠前的属性及其相对重要性。 |

## 解释个性化分析中的属性 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

在 AP 或自动定位模型中使用的“[!UICONTROL 个性化分析]”中显示有两种类型的属性：

* **自动收集的属性：**[!DNL Target]Target 使用基础数据集在 AP 和 AT 活动中构建其个性化算法，这些算法将反映在个性化分析中。请参阅[为 Target 个性化算法收集数据](/help/c-activities/t-automated-personalization/ap-data.md)，以了解数据类型、示例属性及其[!UICONTROL 个性化分析]命名约定。请注意，这些属性虽然会被考虑在内，但单个活动的模型可能不会在最终模型中使用所有这些属性。
* **传递给 Target 的属性：**&#x200B;请参阅[为 Target 个性化算法上传数据](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target] 为您提供了许多方法，用于将其他数据传递给 ，以丰富用于在 AP 和 AT 活动中构建其个性化算法的基础数据集：[!DNL Target]

| 数据类型 | 描述 | 数据类型命名约定 |
|--- |--- |--- |
| 配置文件属性，包括配置文件脚本、配置文件更新 API 和页面内配置文件属性 | 您决定要包含在 Target 用户配置文件中的任何信息。<br>这些信息可能来自配置文件脚本、使用配置文件更新 API 上传的信息，或 mbox 内前缀为“profile”的配置文件参数。 | `Custom - Profile - [parameter name]` |
| 页面参数（也称为“mbox 参数”） | 直接通过页面代码传入的名称/值对，它们未存储在访客的配置文件中供将来使用。 | `Custom - Mbox Parameter - [parameter name]` |
| 客户属性 | 客户属性可让您通过 FTP 将访客配置文件数据上传到 Experience Cloud。上传后，即可在 Adobe Analytics 和 Adobe Target 中利用这些数据。 | `Custom - Customer Attributes - [parameter name]` |
| 共享受众（Adobe Audience Manager 或 Adobe Analytics） | 通过 Adobe Audience Manager 或 Adobe Analytics 创建并与 Target 共享的受众。 | `Custom - Experience Cloud Segment - [segment name]` |
| 活动内报表受众/区段 | 在 AP 或自动定位活动中的“目标和量度”设置期间定义的受众。 | `Custom - Reporting Segment - [segment name]` |

## 培训视频：使用个性化分析报表  ![教程徽章](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

有关详细信息，请参阅Adobe Target的[使用个性化洞察报告](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)。

## Adobe博客

* 第1部分：[揭开AI驱动个性化魔法的神秘面纱](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第2部分：[Adobe TargetAI个性化幕后之谜](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第3部分：[MAGIX — AI驱动个性化黑匣子问题的解决方案](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
