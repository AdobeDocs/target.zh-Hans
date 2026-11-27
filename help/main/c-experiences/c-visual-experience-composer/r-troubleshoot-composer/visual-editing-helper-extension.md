---
keywords: vec；可视化体验编辑器；vec；iframe；扩展；浏览器；faq
description: 了解为什么某些网站可能无法在[!UICONTROL 可视化体验编辑器] (VEC)中以可靠的方式打开。 [!UICONTROL 可视化编辑帮助程序]浏览器扩展允许您在VEC中以可靠的方式加载网站。
title: 如何使用[!UICONTROL 可视化编辑帮助程序]扩展？
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
TQID: 'https://experienceleague.adobe.com/wUWUT-FvVIAo52PDaBMfmT7vxv8VOR71hSGhxFvylus'
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
source-wordcount: '829'
ht-degree: 4%
---
# [!UICONTROL 可视化编辑帮助程序]扩展 {#visual-editing-helper}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解&#x200B;**[!UICONTROL 可视化编辑帮助程序]**&#x200B;浏览器扩展如何在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中以可靠的方式加载网站，以及如何安装和使用它。

>[!ENDSHADEBOX]

[!DNL Google Chrome]的[!DNL Adobe Experience Cloud] **[!UICONTROL 可视化编辑帮助程序]**&#x200B;浏览器扩展在[!DNL Adobe Target] **[!UICONTROL 可视化体验编辑器]** (VEC)中以可靠的方式加载网站，从而加快创作和检查Web体验的速度。

>[!IMPORTANT]
>
>此扩展取代了以前的[Target VEC助手浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，如该文章顶部的重要说明中所述。 清单V3引入了安全增强功能，因此[!DNL Adobe]需要下载此新扩展才能继续在[!DNL Target]中以可视方式创作网站。

## 为什么某些网站无法在VEC中以可靠的方式打开

网站可能无法在VEC中以可靠的方式打开，原因如下：

* 网站具有严格的安全策略。
* 网站位于 iframe 中。
* 客户的QA或暂存站点为内部站点，在网络外部不可用。

该扩展可以解决这些网站加载问题，否则，客户将依赖于[增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)或第三方扩展（例如Requestly）来解决这些问题。

## 扩展的好处

* **删除了Iframe-busting标头：**&#x200B;扩展从网站中隐式删除了`X-Frame-Options`和`Content-Security-Policy`等标头，因此不需要复杂的Requestly规则。
* **at.js注入：**&#x200B;当网页尚未包含[!DNL Target] at.js库时，扩展可以将其插入。 随后可以为网站创作体验，并可通过预览链接创建和检查活动。 使用[增强型体验编辑器](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) (EEC)，扩展不会插入at.js，但SameSite Cookie功能会保留。 要在网页上插入at.js，请关闭EEC。
* 即使没有&#x200B;**[!UICONTROL 增强型体验编辑器]** (EEC)，也支持&#x200B;**移动设备视区：** [移动设备视区](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。
* **新[!DNL Target]客户：**&#x200B;该扩展使尝试使用[!DNL Target]成为可能，即使IT开发人员尚未在网站上实施[!DNL Target]也是如此。
* **合作伙伴：**&#x200B;为多个客户的网站和[!DNL Target]帐户提供服务的合作伙伴将获得一个支持VEC加载的机制，而不是第三方工具中的多个规则。

## 获取并安装扩展

在[!DNL Chrome]中安装扩展后，可以在VEC中以可靠的方式加载网站，包括阻止iframe或尚未实施at.js的网站。

1. 转到Chrome网上应用商店[&#128279;](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}中的[!DNL Adobe Experience Cloud] **[!UICONTROL 可视化编辑帮助程序&#x200B;]**&#x200B;浏览器扩展。
1. 单击&#x200B;**[!UICONTROL 添加到Chrome]** > **[!UICONTROL 添加扩展]**。
1. 打开 [!DNL Target] 中的 VEC。
1. 在VEC或QA模式下，单击[!DNL Chrome]工具栏中的&#x200B;**[!UICONTROL 可视化编辑帮助程序]**&#x200B;浏览器扩展图标（![可视化编辑帮助程序图标](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)）。

   当在[!DNL Target] VEC中打开网站以进行创作时，会自动启用该扩展。 它没有条件设置，并且会自动处理所有设置，包括SameSite Cookie设置。 有关`SameSite=None`属性浏览器修复的详细信息，请参阅[Google Chrome SameSite Cookie策略](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## 使用说明

* 该扩展加载最新版本的at.js，该版本在[!DNL Target] UI中的&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实现]**&#x200B;下可用，at.js将下载创作库。
* 若要使用此扩展在[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)中插入at.js，必须打开另一个Chrome选项卡。 此选项卡必须通过创建该活动的同一[!DNL Adobe Experience Cloud]组织的身份验证。
* 在以下情况下，VEC会显示建议安装扩展的消息：

  * 网站无法在VEC中加载。
  * 尚未在网站上实施at.js或alloy.js。

* 如果尝试了新扩展并且再次使用[旧扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)，但[!DNL Target]无法加载网站，请清除所有浏览器数据并禁用新扩展。

## 延期最新更改（2026年1月17日）

该扩展向VEC助手添加了启动Cookie清理实验功能。 该功能会在创作开始时对每个选项卡未分区的Cookie进行一次清理，而不是持续清理，从而提高性能和可靠性。 它跟踪每个选项卡的历史记录，以防止进行冗余清理，并在选项卡关闭时清除该历史记录，因此，在选项卡重新打开时，清理操作会正常运行。 单元测试可确保一致的行为。

![VEC Helper扩展的选项，包括Cookie处理模式、高级日志记录选项和实验功能（延迟网页加载、Cookie清理和启动Cookie清理）](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper.png)

## 常见问题解答

+++ 当扩展在[!DNL Adobe Target]或[!UICONTROL Adobe Journey Optimizer] (AJO)之外使用时，它是否执行任何操作？

只有当网站加载到[!DNL Adobe]产品([!DNL Target]、[!DNL AJO])的iFrame中时，该扩展程序才会激活。 在此流程之外，扩展程序不会尝试添加、删除或修改任何标头，并且不会尝试在网站内注入任何代码。

+++

+++ 当扩展在 [!DNL Adobe Target] VEC 中处于活动状态时会做什么？

当网站加载到[!DNL Adobe]产品([!DNL Target]、[!DNL AJO])的iFrame中时，扩展程序会将与该扩展程序捆绑的代码注入该网站并下载来自[!DNL Adobe] CDN的帮助程序文件，以启用可视化创作。

+++
