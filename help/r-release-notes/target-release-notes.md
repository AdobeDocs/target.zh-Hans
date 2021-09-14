---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 6957eb88e2ee7d54fdad5afeaedf75b091b601e7
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 36%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 9 月 14 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Target Standard/Premium] 21.9.1（2021年9月14日）

此维护版本包含以下增强、修复和更改。

* 修复了由于某些Web浏览器中第三方Cookie的新安全策略，客户无法登录到[!UICONTROL 可视化体验编辑器](VEC)的问题。 在[对与可视化体验编辑器和增强型体验编辑器相关的问题进行故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)中，“使用Google Chrome版本80及更高版本时，在可视化体验编辑器(VEC)或增强型体验编辑器(EEC)中，“页面未加载”讨论了此问题。
* 修复了导致VEC中的选件名称显示选件的路径而不是选件的友好名称的问题。 (TGT-41300)
* 修复了[!DNL Recommendations]中存在的一个问题，该问题会错误地将实体ID在复制活动中的促销活动中进行更改，以将其应用于原始活动。 (TGT-41482)
* 修复了VEC中[!DNL Recommendations]活动的[!UICONTROL 体验]页面上无法正确显示“编辑标准”按钮的问题。 (TGT-39512)
* 修复了复制活动并将其复制到测试工作区时无法同步活动的问题。 (TGT-40686)
* 修复了在VEC中使用“[!UICONTROL Insert After]”时，阻止修改具有[体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md)的选择器的问题。 (TGT-41802)
* 修复了阻止将选件中的空JSON内容发送到后端的问题。 [!DNL Target] 现在会发送JSON对象，即使该对象为空也是如此。(TGT-41555)
* 修复了当客户在查看报表时单击“[!UICONTROL 在Analytics中查看]”时，导致旧版[!DNL Analytics]报表打开而不是[!DNL Analysis Workspace]的问题。 (TGT-41867)
* 为当客户尝试为[!UICONTROL Automated Personalization]活动选择[!DNL Analytics]作为报表源(A4T)时显示的UI消息添加了其他说明。 该消息指出，“[!DNL Target]是[!UICONTROL Automated Personalization]活动唯一支持的源。” (TGT-41954)
* 为当客户尝试使用“换行符”而不是逗号来分隔主机时的错误消息添加了额外说明。 (TGT-40671)
* 更新了区段的[!UICONTROL Type]字段，以准确包含[!DNL Platform]和[!DNL AAM]([!DNL Adobe Audience Manager])。 (TGT-41328)
* 修复了在单击[!UICONTROL Save]后导致流量源操作数发生更改的问题。 (TGT-41408)
* 现在，保存仅限该活动的受众（基于规则或组合）后，UI会加载[!UICONTROL Audience]选取器，并应用仅限该活动的过滤器。 (TGT-41747).
* 修复了导致从源中删除的受众([!DNL Adobe Experience Platform]、[!UICONTROL AAM]等)继续显示在[!DNL Target] UI中的问题。
* 在[!UICONTROL 受众]页面中添加了过滤器选项，以仅显示从[!DNL Adobe Experience Platform]导入的受众。 (TGT-41298)
* 在[!UICONTROL 受众] UI中添加了增强的键盘辅助功能选项。 (TGT-39927)
* 修复了导致某些活动的“[!UICONTROL 上次更新]”日期与西班牙和日语客户的英语UI不同（在查看西班牙语和日语版UI时）的问题。 (TGT-38980)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
