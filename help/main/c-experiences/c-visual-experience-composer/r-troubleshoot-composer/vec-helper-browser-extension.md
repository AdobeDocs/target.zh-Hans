---
keywords: VEC;可视化体验编辑器;VEC;iframe;扩展;浏览器
description: 了解为什么某些网站可能无法在[!UICONTROL 可视化体验编辑器] (VEC)中以可靠的方式打开。 通过VEC助手浏览器扩展，您可以在VEC中以可靠的方式加载网站。
title: 如何使用[!UICONTROL 可视化体验编辑器] (VEC)助手扩展？
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
TQID: 'https://experienceleague.adobe.com/lqZGGWG1NVtKDzNGPq5k2bDPzxDfNWqPtJ-bYfLCr3Q'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 5%
---
# [!UICONTROL 可视化体验编辑器]帮助程序扩展 {#vec-helper-extension}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解旧版VEC Helper浏览器扩展如何在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中加载网站，以及如何安装和使用它。

>[!ENDSHADEBOX]

适用于[!DNL Google Chrome]的[!DNL Adobe Target] **[!UICONTROL 可视化体验编辑器]** (VEC)助手浏览器扩展可以在VEC中可靠地加载网站，从而加快创作和检查Web体验的速度。 [!DNL Mozilla Firefox]中不需要该扩展。

>[!IMPORTANT]
>
>* 本文中记录的旧版[!DNL Target] VEC Helper扩展是使用Manifest V2创建的。 [!DNL Google]宣布从2024年6月起，将停止允许使用清单V2创建的扩展。 有关详细信息，请参阅&#x200B;*面向开发人员的Chrome*&#x200B;网站上[!DNL Google]的[清单V2支持时间表公告](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank}。
>
>* 从2024年6月开始，[!DNL Google]将禁用使用清单V2创建的扩展，包括本文中记录的扩展。 [!DNL Adobe]建议尽快迁移到较新的[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

## 为什么某些网站无法在VEC中以可靠的方式打开

网站可能无法在VEC中以可靠的方式打开，原因如下：

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 尚未在网站上实施 at.js 库。
* 客户的QA或暂存站点为内部站点，在网络外部不可用。
* 网站使用[Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW)，VEC当前仅支持有限制的SW。 请参阅以下部分。
* 网站在[!DNL Chrome] 80或更高版本中打开，这将强制实施SameSite Cookie策略。 有关详细信息，请参阅[Google Chrome SameSite Cookie策略](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

针对[!DNL Chrome]的VEC Helper浏览器扩展可以解决网站加载问题，否则，客户将依赖于[!DNL Target] [增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)或第三方扩展（如Requestly）来解决该问题。

### 服务工作程序

Service Worker (SW)是网页安装的一种Web技术，用于拦截对其域的请求。 SW 在页面访问中留存，并在后续访问中自我激活。 它决定哪些请求通过，哪些请求被拦截并从缓存提供服务。

SW可以缓存网页本身、静态资源（如JS、CSS、IMG和AJAX请求）及其内容和响应标头。 这些标头包括[Target VEC Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)尝试删除的标头，如`X-Frame-Options: SAMEORIGIN`、CSP (`Content-Security-Policy`)和`Set-Cookie`。

拦截Web请求的[!DNL Chrome]扩展API不接收SW已拦截和处理的请求。 当SW从缓存中提供网页请求时，扩展无法修复标头和Cookie，并且由于缓存了`X-Frame-Options`或CSP标头，页面无法在VEC中加载。

作为潜在的解决方法，请在[!DNL Chrome]开发人员工具> **应用程序**&#x200B;选项卡中禁用Service Worker，然后在Service Worker部分中启用“绕过网络”复选框。

## VEC助手扩展的好处

* **删除了Iframe-busting标头：**&#x200B;扩展从网站中隐式删除了`X-Frame-Options`和`Content-Security-Policy`等标头，因此不需要复杂的Requestly规则。
* **at.js注入：**&#x200B;当网页尚未包含[!DNL Target] at.js JavaScript库时，扩展可以插入它。 随后可以为网站创作体验，并可通过预览链接创建和检查活动。 使用增强型体验编辑器(EEC)，扩展不会插入at.js，但SameSite Cookie功能会保留。 要在网页上插入at.js，请关闭EEC。
* 即使没有&#x200B;**[!UICONTROL 增强型体验编辑器]** (EEC)，也支持&#x200B;**移动设备视区：** [移动设备视区](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。
* **新[!DNL Target]客户：**&#x200B;该扩展使尝试使用[!DNL Target]成为可能，即使IT开发人员尚未在网站上实施[!DNL Target]也是如此。
* **合作伙伴：**&#x200B;为多个客户的网站和[!DNL Target]帐户提供服务的合作伙伴将获得一个支持VEC加载的机制，而不是第三方工具中的多个规则。

## 获取并安装 VEC 助手浏览器扩展

在[!DNL Chrome]中安装扩展后，可以在VEC中以可靠的方式加载网站，包括阻止iframe或尚未实施at.js的网站。

1. 转到Chrome网上应用商店[&#128279;](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca)中的Adobe Target VEC助手浏览器扩展。
1. 单击&#x200B;**[!UICONTROL 添加到Chrome]** > **[!UICONTROL 添加扩展]**。
1. 打开 [!DNL Target] 中的 VEC。
1. 在VEC或[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中，单击[!DNL Chrome]工具栏中的VEC助手浏览器扩展图标（![VEC助手图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)）。
1. （视情况而定）如果网页尚未包含[!DNL Target] at.js JavaScript库，请打开&#x200B;**[!UICONTROL 插入Target库]**&#x200B;切换开关。

   下图显示了已启用&#x200B;**[!UICONTROL 插入Target库]**&#x200B;设置的VEC助手：

   打开“插入Target库”开关并关闭“Cookie”开关的![VEC Helper扩展面板，显示“Cookie”设置在VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)内请求的所有Cookie上设置SameSite=None和Secure标记

   然后，VEC助手会询问是否应将[!DNL Target]库插入到页面中以启用创作功能：

   ![插入Target库提示符，表示Target VEC Helper扩展希望将Target库插入到页面中以启用创作功能，同时显示取消和允许按钮](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （视情况而定）打开&#x200B;**[!UICONTROL Cookie]**&#x200B;开关以自动添加`SameSite=None`属性浏览器修复。

   ![VEC Helper扩展面板（带有Cookie切换开关）在可视化体验编辑器中打开并突出显示，其中显示了一个示例页面](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   有关`SameSite=None`属性浏览器修复的详细信息，请参阅[Google Chrome SameSite Cookie策略](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## 使用说明

* 默认情况下，扩展中的&#x200B;**[!UICONTROL 插入Target库]**&#x200B;标志处于关闭状态。 将其打开以在尚未实现[!DNL Target]的网站上使用VEC。

  标记是全局设置，因此对于在VEC中打开的所有网站，均会启用或禁用此标记。 例如，当标记打开时，如果网站已实施at.js，则会显示一条消息，表明at.js已加载。 [!DNL Adobe]希望大多数客户已在其页面上实施了at.js，并且使用默认的“关”设置。

* 该扩展加载最新版本的at.js，该版本在&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实现]**&#x200B;下的[!DNL Target] UI中可用。
* 若要使用此扩展在[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中插入at.js，必须打开另一个Chrome选项卡。 此选项卡必须通过创建该活动的同一[!DNL Adobe Experience Cloud]组织的身份验证。
* 在以下情况下，VEC会显示消息：

  * 网站无法在VEC中加载。 此消息建议安装VEC助手浏览器扩展。
  * 尚未在网站上实施at.js。 此消息建议安装扩展。
  * 该扩展已启用并为加载提供支持。 如果必要，扩展会插入at.js库，或者有助于在VEC中可靠地打开网站，此时将显示消息。
