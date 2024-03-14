---
keywords: 发行说明;新功能;版本;更新;更新;版本;增强;增强;修复;错误修复;更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5df9ba6eb249dfc690279177ecb5936aaefa7bdd
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 57%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 更新 `Browser:iPad` 和 `Browser:iPhone` 在 [!UICONTROL Browser] 受众属性（2024年4月30日）

| 更新 | 详细信息 |
|--- |--- |
| [!UICONTROL Browser:iPad] 和 [!UICONTROL Browser:iPhone] 更新于 [浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) 在创建受众时使用。 | [!DNL Adobe Target] 允许您 [定位多个类别属性中的任意一个](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括使用特定的 [浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md) 访客访问您的页面时。<P>从 [!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日），使用Target UI创建的内置受众，例如 `Browser:iPad` 和 `Browser:iPhone` 将更新以对执行适当的定位 [!DNL iPad] 和 [!DNL iPhone] 使用 `profile.mobile.deviceVendor`， `profile.mobile.isMobilePhone` 和 `profile.mobile.isTablet`.<P>客户无需对此更新执行任何操作。<p><B>重要</b>：供客户对以下内容执行适当的定位 [!DNL iPad] 和 [!DNL iPhone] 在配置文件脚本（和JavaScript区段）中，必须由客户手动进行更改 **2024年4月30日**. 有关必须手动更改的替代设置的示例，请参阅 [更新 [!DNL iPad] 和 [!DNL iPhone] 在 [!UICONTROL Browser] 受众属性](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!UICONTROL Visual Editing Helper] 延期（2023年3月14日）

此版本包含以下增强功能和修复 [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) 扩展 [!DNL Google Chrome]：

* 增强了在客户网站中执行创作时的iFrame加载机制。
* 修复了在中执行创作时导致扩展重复Cookie的问题 [!UICONTROL Visual Experience Composer] (VEC)。
* 删除了对正在使用的客户下载at.js的依赖关系 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

## [!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）

此版本计划在接下来的几天发布：

* **3 月 4 日**：欧洲、中东和非洲 (EMEA) 地区
* **3 月 5 日**：亚太 (APAC) 地区
* **3 月 6 日**：美洲地区

此版本包含以下增强和修复：

* 修复了计算活动中唯一选择器数量的逻辑。 (TGT-47878)
* 修复了导致错误的问题 [!UICONTROL Multivariate] (MVT)活动配置有 [!UICONTROL Analytics for Target] (A4T)报表无法正确显示。 (TGT-47490)
* 改进了在将无流量的体验用作控制体验时报表中显示的警告消息。 (TGT-47537)
* 添加了许多后端和本地化修复。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| [文档更改](/help/main/r-release-notes/doc-change.md) | 查看这些发行说明中未包括的关于本指南的更新的详细信息。 |
| [以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。 |
| [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
