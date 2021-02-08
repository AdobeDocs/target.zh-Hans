---
keywords: 发行说明；发行；更新；未来发行；增强；新增功能；修复；更新；预发行
description: 了解即将发布的Adobe Target版本（包括SDK、API和JavaScript库）中包含的新功能、增强和修复。
title: 即将发布的版本中包含哪些新增功能？
feature: Release Notes
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 26%

---


# Target 发行说明（预发行版本）

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 1 月 14 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

## Target Standard/Premium 21.1.1（2021 年 1 月 19 日） 

此维护版本包含以下增强、修复和更改。

括号中的问题编号供 [!DNL Adobe] 内部使用。

* 在[!UICONTROL 自动目标]活动中，当使用[!UICONTROL 分析作为报告源](A4T)时，在选择[!DNL Adobe Analytics]度量时添加了警告。 [!UICONTROL 自动定] 位模型经过优化，可与二进制（基于转换）指标结合使用。选择连续指标（如收入）可能会产生次优结果，而[!UICONTROL 个性化洞察]报告可能不准确。 (TGT-38926)
* 在[!UICONTROL 自动目标摘要]报告中为使用A4T的[!UICONTROL 自动目标]活动添加了状态图标。 报表中每个体验旁边的绿色复选标记表示已为该体验生成个性化的机器学习模型。时钟图标表示用于构建模型的流量不足。(TGT-38925)
* 生成使用A4T和[!DNL Analytics]转换度量的[!UICONTROL 自动目标段]和[!UICONTROL 重要属性]活动的报告，其外观与使用[!DNL Target]作为报告源时相同。 (TGT-38931)
* 在[!UICONTROL Recommendations] [!UICONTROL 集合]环境中添加了列表过滤选项。 (TGT-38353)
* 修复了导致在[!UICONTROL Recommendations]集合中显示错误产品计数的问题。 (TGT-39162)
* 向[!UICONTROL Recommendations][!UICONTROL 目录搜索]添加了[!UICONTROL 上次更新]筛选器。 (TGT-38340)
* 修复了[!UICONTROL Recommendations]中的一个问题，该问题导致在更改行业垂直后，[!UICONTROL 创建序列]页面挂起。 (TGT-38160)
* 修复了在启用设备协作且用户从[!DNL Target]作为活动源更改为[!DNL Analytics](A4T)时，无法保存报告的问题。 (TGT-38163)
* 修复了阻止用户从[!UICONTROL Automated Personalization](AP)活动中的优惠删除受众的问题。 (TGT-39058)
* 修复了导致某些客户在[!UICONTROL 受众信息]卡中显示不正确的时间帧(开始和结束日期)的问题。 (TGT-39150)
* 修复了导致某些客户无法在[!UICONTROL 默认工作区]中看到活动列表的问题。 (TGT-38526)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
