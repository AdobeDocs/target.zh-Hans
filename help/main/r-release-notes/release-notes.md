---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 65ac352a1de7ad532f8c39781054fb09fa62c0fa
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 27%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.6.1（2025年6月6日）

此版本包含以下修复和更新：

* 修复了QA链接没有为关联活动提供正确体验的问题。 （TGT-52163 和 TGT-52790）
* 修复了QA链接缺少关联的受众ID的问题。 (TGT-52722)
* 修复了一个问题，以确保仅在准确满足体验配置的“页面交付”URL条件时交付体验。 (TGT-52696)
* 修复了阻止客户创建[!DNL Recommendations]设计模板的问题。 尝试创建模板时触发了错误：“脚本中应至少使用1个实体变量。” (TGT-52395)
* 修复了阻止使用Velocity数组保存[!DNL Recommendations]设计的问题。 错误消息“脚本内应至少使用1个实体变量”未正确触发。 (TGT-52734)
* 修复了当内部网页无法加载页面时，[!UICONTROL Visual Experience Composer] (VEC)中无法访问修改的问题。 (TGT-52488 &amp;TGT-52470)
* 修复了VEC中较小屏幕尺寸上看不到[!UICONTROL Modifications]面板的问题。 (TGT-52470)
* 修复了更新后的VEC中的一个问题：从[!UICONTROL Browse]模式切换回[!UICONTROL Design]模式会导致控制台错误并阻止进一步的交互。 (TGT-52532)
* 修复了VEC中的一个问题：单击某些元素会无意中扩展其大小。 (TGT-52497)
* 修复了某些页面元素无法加载或在VEC中无法识别的问题，从而妨碍交互（例如选择按钮或横幅）并中断活动中的准确事件跟踪。 (TGT-52663)
* 修复了阻止客户删除或移除[!UICONTROL Automated Personalization] (AP)活动中的优惠的问题。 (TGT-52690)
* 修复了导致多页面活动中活动资格行为不一致的问题。 (TGT-52694)
* 修复了导致活动的[!UICONTROL Overview]页面显示[!UICONTROL Activity Location]的无效URL的问题。 (TGT-52695)
* 修复了更新的[!DNL Target] UI中导致活动位置出现重复条目的问题。 (TGT-52693)
* 修复了触发`getAudiencesV3`错误并阻止客户编辑或复制活动的问题。 (TGT-52709)
* 修复了在将[!UICONTROL Experience Fragments]或HTML选件添加到活动时导致无效有效负载错误的问题。 （TGT-52779 和 TGT-52773）
* 修复了更新的[!DNL Target] UI中，由于输入错误而导致无法正确显示E[!UICONTROL xperience Fragments]的问题。 (TGT-52701)
* 修复了由于无效的用户错误而导致客户无法编辑[!UICONTROL Form-based Experience Composer]中的活动的问题。 (TGT-52470)
* 修复了韩语的本地化问题，该问题导致之前的翻译使用基本多语言平面以外的字符。 更新的翻译使用能够准确传达预期含义的适当字符。 （TGT-52508 和 TGT-52509）
* 修复了韩语的本地化问题：在选择活动的开始和结束日期时，“date”的翻译不一致。 (TGT-52510)

## 弃用Target UI版本切换（2025年5月23日） {#toggle}

新[!DNL Target]用户界面的转出将在&#x200B;**2025年5月27日**&#x200B;之前完成。 到那时，所有客户都将有权访问最新的UI版本。

从&#x200B;**2025年6月22日**&#x200B;开始，将删除UI版本切换。 所有用户都将永久过渡到新界面，没有恢复到先前版本的选项。

>[!NOTE]
>
>具有特殊情况且在6月22日后需要保留切换的客户可以联系Adobe客户关怀部门寻求帮助。

### 有关UI版本切换的重要信息

我们提供了一项临时功能，可让您使用切换按钮在更新的[!DNL Target] UI和旧版本之间切换。 此选项仅在UI转出的最后阶段可用。

![Target UI版本切换](/help/main/r-release-notes/assets/toggle.png)

转出完成后，切换将被删除，所有用户都将在&#x200B;**2025年6月22日**&#x200B;永久转换为更新后的UI。 Adobe建议提前规划，因为这项功能将很快被淘汰。

### UI切换行为的限制

* **新活动的可见性**：如果切换回旧版UI，则在更新后的UI中创建的活动将不可见。
* **编辑现有活动**：使用更新的UI时，对现有活动（最初在旧版UI中创建）所做的更改将发布到您的网站。 但是，如果切换回去，这些更新将不会在旧版UI中显示；只有从旧版UI进行的最后一次更新将显示在该处。
* **活动详细信息的一致性**：无论您使用哪个UI，最新更改都将反映在您的实时网站上。 但是，旧版UI将仅显示从该版本中进行的最新更改。 如果在更新的UI中编辑的活动与您在旧版UI中看到的不同，则可能会导致混淆。

### 有关更新的UI的更多信息

* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的关键UI更改的摘要。

* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!UICONTROL Offers Library]在[!DNL Target]中关键UI更改的摘要。

* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

* [[!UICONTROL Visual Experience Composer]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。

* [[!UICONTROL Visual Experience Composer]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

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
