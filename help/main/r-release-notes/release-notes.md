---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: cad8c365028b28bd9349d2d283370e2c8a750180
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 34%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。


## [!DNL Target Standard/Premium] 26.4.1（2026年4月2日）

**活动**

+++查看详细信息

* **在“活动”视图中可见的受众属性。**&#x200B;修复了以下问题：从&#x200B;**[!UICONTROL Activity]**&#x200B;查看的受众规则详细信息时，未显示从&#x200B;**[!UICONTROL Audiences]**&#x200B;部分打开同一受众时显示的特定属性。 (TGT-54742)

* **应用于其他视图时保留的自定义代码。**&#x200B;修复了在同一&#x200B;**[!UICONTROL View]**&#x200B;中为另一个&#x200B;**[!UICONTROL View]**&#x200B;添加或保存自定义代码时，可能会删除应用于一个&#x200B;**[!UICONTROL Activity]**&#x200B;的自定义代码的问题。 (TGT-53933)

* 在“活动”和“受众”列表页面上&#x200B;**导出CSV。**&#x200B;添加了&#x200B;**[!UICONTROL Export CSV]**&#x200B;操作，以便您可以从用户界面导出活动列表，包括在应用过滤器时，而无需仅依赖API进行例行导出。 (TGT-51466)

* **未找到选择器时标记的Experience修改。**&#x200B;体验修改现在运行选择器存在性检查；在页面上未找到选择器时，修改将被标记为无效。 (TGT-54815)

* **[!UICONTROL Automated personalization]活动。**&#x200B;修复了阻止用户可靠地创建、编辑或管理自动个性化活动的界面和活动加载问题，这些问题会阻止活动设置并延迟个性化用例。 (TGT-54421)

+++

**受众**

+++查看详细信息

* **从活动创建受众时显示的受众名称和描述。**&#x200B;修复了在从活动流创建或编辑受众时，与直接在&#x200B;**[!UICONTROL Name]**&#x200B;下创建受众相比，受众&#x200B;**[!UICONTROL Description]**&#x200B;和&#x200B;**[!UICONTROL Audiences]**&#x200B;字段未明确脱颖而出的问题。 (TGT-54837)

+++

**分析**

+++查看详细信息

* **[!UICONTROL Live Activities]计入分析。**&#x200B;修复了分析仪表板上的&#x200B;**[!UICONTROL Live Activities]**&#x200B;量度报告的总数可能高于&#x200B;**[!UICONTROL All Activities]**&#x200B;中显示为实时的活动数的问题。 (TGT-54788)

+++

**推荐**

+++查看详细信息

* **中的[!UICONTROL Global Exclusions]长ID列表。**&#x200B;修复了在更新后的界面中，与旧版相比，**[!UICONTROL Global Exclusions]**&#x200B;中粘贴或输入较长ID列表可能会被截断的问题，从而导致排除列表不完整。 (TGT-54422)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++查看详细信息

* **中的[!UICONTROL Visual Experience Composer]增强型体验编辑器(EEC)状态指示器。** EEC指示器表示是否已启用增强型体验编辑器。 其演示文稿已修订，不再类似于交互式切换，因为它仅用作非交互式状态显示。 (TGT-54828)

* **[!UICONTROL Visual Experience Composer]中的左边栏可折叠。**&#x200B;现在可以折叠左边栏，同时活动处于打开状态以进行编辑。 这改进了对于包含多个受众和页面的活动（包括在较小的显示屏上）的&#x200B;**[!UICONTROL Components]**&#x200B;和&#x200B;**[!UICONTROL Properties]**&#x200B;的访问权限。 (TGT-54269)

+++

## [!DNL Target Standard/Premium] 26.3.7（2026年3月26日）

**受众**

+++查看详细信息

* **受众界面中的受众源标签准确性。**&#x200B;修复了以下问题：来自Adobe Experience Platform中Adobe Target v2目标的受众可能显示为&#x200B;**Adobe Experience Cloud**&#x200B;而不是&#x200B;**Adobe Experience Platform**&#x200B;作为源。 此更新改进了筛选和查看受众时的源标签一致性。 (TGT-54802)

+++

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
| [Adobe Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
