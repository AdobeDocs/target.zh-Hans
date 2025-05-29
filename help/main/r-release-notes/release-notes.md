---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: bc9a0fe1977629a00eebb2f7aafd30263c8b55af
workflow-type: tm+mt
source-wordcount: '2119'
ht-degree: 18%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.5.4（2025年5月29日）

此版本包含以下修复和更新：

* 修复了阻止在QA模式下添加或编辑URL的问题。 (TGT-51941)
* 在[!UICONTROL Reports] > [!UICONTROL Report Settings]下添加了QA模式流量设置（ ![报表设置图标](/help/main/assets/icons/Setting.svg) ），以便与旧版[!DNL Target] UI中的功能保持一致。 （TGT-52228 和 TGT-52329）
* 修复了基于表单的活动生成错误的QA链接的问题。 活动URL/位置在末尾包含一个意外的“1”，为了确保准确关联，现已删除该URL。 （TGT-52355 和 TGT-52358）
* 修复了基于表单的活动生成错误的QA链接的问题。 活动URL在URL的开头包含意外的`http://pid-ppc`，为了确保准确链接，该URL现已删除。 (TGT-52557)
* 修复了[!DNL Target]为基于表单的活动生成无效QA链接的问题。 （TGT-52528 和 TGT-52603）
* 修复了保存修改后的活动似乎已处理但从未完成，并且[!DNL Target]中未显示任何错误消息的问题。 (TGT-52461)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)无法自动检测`at_property`值的问题。 (TGT-52347)
* 修复了一个问题，该问题导致在与表单元素交互时，在VEC中的[!UICONTROL Browse]和[!UICONTROL Design]模式之间切换后，预期仅记录一次修改，从而引发两次修改。 (TGT-52455)
* 修复了由于错误表明选择器无效、已使用或不可见而阻止在更新的VEC中选择[!UICONTROL Clicked an Element]设置的问题。 (TGT-52467)
* 修复了在更新的VEC中添加[!UICONTROL Recommendation Offer]框导致显示重复（重影）框的问题。 在体验A和B之间切换时反复添加了更多虚框。 （TGT-52505 和 TGT-52519）
* 修复了在更新的[!DNL Target] UI中，通过[!UICONTROL Offer]菜单对HTML选件所做的更改未反映在关联活动中，反之亦然。 此行为现在与旧版UI匹配，在该旧版UI中，更新在[!UICONTROL Offer]菜单和活动之间正确同步。 （TGT-52540 和 TGT-52541）
* 修复了在活动中尝试使用[!UICONTROL Offers Library]中的[!UICONTROL Experience Fragments]最近更新时，未反映它们的问题。 (TGT-52659)
* 修复了确认消息的简体中文翻译中的本地化问题。 以前的版本在位置名称周围缺少引号，并且使用非正式语言，这与客户的风格指南相反。 更新后的翻译现在使用正确的标点符号和正式语调。 (TGT-52364)

## 弃用Target UI版本切换（2025年5月23日） {#toggle}

新[!DNL Target]用户界面的转出将在&#x200B;**2025年5月27日**&#x200B;之前完成。 到那时，所有客户都将有权访问最新的UI版本。

从&#x200B;**2025年6月22日**&#x200B;开始，将删除UI版本切换。 所有用户都将永久过渡到新界面，没有恢复到先前版本的选项。

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

## [!DNL Target Standard/Premium] 25.5.3（2025年5月22日）

此版本包含以下修复和更新：

* 修复了[!UICONTROL Activities]列表中的按名称搜索功能在多词查询中无法正常工作的问题。 (TGT-52529)
* 修复了阻止从[!UICONTROL Automated Personalization] (AP)活动中排除体验的问题。 (TGT-52383)
* 修复了管理AP活动中的内容时，[!UICONTROL Filter Rules]中缺少“[!UICONTROL Contains]”选项的问题。 (TGT-52384)
* 修复了[!UICONTROL Automated Personalization] (AP)活动中的报表不一致问题，具体问题与如何使用[!DNL Target]内部系统中的`optionLocalId`值跟踪和报告默认选件有关。
* 修复了QA链接无法提供预期活动体验的问题。 (TGT-52163)
* 修复了具有[!UICONTROL Approver]权限的用户被错误阻止编辑实时活动的问题，该问题会收到“访问被拒绝”错误消息。 (TGT-52416)
* 修复了在更新的[!DNL Target] UI中无法针对某些活动显示受众细化的问题。 (TGT-52057)
* 修复了一个问题，该问题导致在更新后的UI中逆转受众细化和活动受众。 (TGT-52158)
* 修复了生成临时优惠导致重复优惠的问题。 (TGT-51938)
* 修复了阻止选件更新并错误显示“用户无效”错误的问题。 (TGT-52361)
* 修复了阻止保存现有活动并触发“用户输入无效”错误的问题。 (TGT-52422)
* 修复了阻止编辑现有HTML选件的问题，该问题会在保存时触发“无效用户输入”错误，即使未进行任何代码更改也是如此。 (TGT-52351)
* 修复了阻止[!DNL Target]识别网站URL中“#”字符的问题。 (TGT-52093)
* 修复了阻止编辑[!DNL Recommendations]活动以添加或更新促销活动的问题，该问题会导致保存失败和重复促销活动。 (TGT-52343)
* 修复了一个问题，该问题阻止在[!DNL Recommendations]活动中更改标准或设计，从而导致“JSON无效：无法识别的属性名称”错误。 (TGT-52375)
* 修复了序列条件无法在[!DNL Recommendations]活动的[!UICONTROL Visual Experience Composer] (VEC)中正确显示的问题。 (TGT-52435)
* 修复了在使用[!DNL Adobe Experience Platform Web SDK]时SPA页面上未正确识别视图的问题。 (TGT-52106)
* 修复了尽管包含在批量操作有效负载中，但设备上决策(ODS)详细信息未正确保存的问题。 (TGT-52406)
* 向活动添加了`audienceMetadata`字段，使其可在编辑期间读取和更新。 (TGT-51004)
* 添加了错误消息，以在受众时间范围无效时提醒用户。 (TGT52522)
* 更新了活动结构以支持不同类型的重复受众。 (TGT-51200)

## [!DNL Adobe Target] [!DNL AI Assistant]版本（2025年5月16日）

我们很高兴在[!DNL Adobe Target]中宣布[!DNL AI Assistant]的启动！ 此强大的用户界面功能旨在帮助您轻松导航和了解[!DNL Target]概念。 在[!DNL Adobe Experience Cloud]的多个产品（包括[!DNL Target]）中均可用，[!DNL AI Assistant]将为您的体验带来翻天覆地的变化。

[!UICONTROL Target]中的[!DNL AI Assistant]是一个对话工具，可用于通过[!DNL Experience Platform]应用程序和服务加速工作流。 使用[!DNL AI Assistant]提高您的整体工作效率并增强您对产品知识的理解

在[!DNL Target]中，[!DNL AI Assistant]的第一阶段以[!DNL Experience League]文档为基础，提供了宝贵的产品知识。 无论您是设置配置文件脚本、排除错误还是考虑升级到AEP Web SDK，[!DNL AI Assistant]都已涵盖。

有关详细信息，请参阅[Adobe Experience Platform AI助手概述](/help/main/c-intro/ai-assistant.md)。

## [!DNL Target Standard/Premium] 25.5.2（2025年5月8日）

此版本包含以下修复和更新：

* 具有[!UICONTROL Product Administrator]和[!UICONTROL System Administrator]权限的[!DNL Target]用户现在可以编辑[!UICONTROL Administration]页面上的所有设置，无论他们在[!DNL Target]中的角色如何。 没有这些权限的用户对这些设置具有只读访问权限。 此更新确保对[管理设置](/help/main/administrating-target/administrating-target.md)进行更严格的访问控制。 (TGT-48179)
* 修复了阻止保存活动[网站首选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings)的缓存问题。 (TGT-52213)
* 修复了以下问题：在VEC中加载网站后，客户无法在[!UICONTROL Site Preferences]部分中按ID和类启用选择。 [!UICONTROL Site Preferences]设置自动还原为已禁用，即使在启用后也是如此。 (TGT-52207)
* 修复了[页面交付](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings)URL以正斜杠(/)结尾时，[!UICONTROL Visual Experience Composer] (VEC)无法显示正确页面的问题。 (TGT-52237)
* 修复了在更改体验时阻止删除自定义代码修改的问题。 (TGT-52240)
* 修复了VEC中的HTML修改覆盖现有页面元素的问题。 (TGT-52265)
* 修复了由于现有自定义代码在编辑器中不可见而阻止在更新的VEC中编辑自定义代码的问题。 (TGT-52272)
* 修复了在保存推荐活动时导致出现“不允许存在重复名称”错误消息的问题。 (TGT-52318)
* 修复了更新后的VEC中存在的一个问题，该问题会阻止客户编辑文本元素或删除容器对象。 (TGT-52348)
* 修复了阻止[!DNL Customer Journey Analytics]在活动[!UICONTROL Overview]页面上正确显示的问题。 (TGT-52359)
* 修复了阻止报表组在[!UICONTROL Automated Personalization] (AP)活动中持久存在的问题。 (TGT-52368)
* 修复了阻止保存包含Offer Decisioning的活动的问题。 (TGT-52390)
* 修复了以下问题：选择了默认选件，但在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Multivariate Test] (MVT)活动中显示了其他选件内容。 (TGT-52372)
* 修复了GET权限逻辑，以检查完全组织访问权限与特定组织+用户访问权限之间的OR。 (TGT-52374)
* 修复了为[!UICONTROL Managed Content]和[!UICONTROL Reporting Audiences]选择受众后未显示受众名称的问题，即使启用了[!UICONTROL Show Only Selected]也是如此。 (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1（2025年5月5日）

此版本包含以下修复和更新：

* 修复了无法在更新后的UI中为某些活动显示受众细化的问题。 (TGT-52057)
* 修复了阻止在活动中使用组合受众的问题。 (TGT-52346)
* 修复了阻止使用来自同一工作区的仅限该活动的受众，在非默认工作区中创建新活动的问题。 (TGE-52349)
* 修复了在创建和选择新受众后，导致仅限该活动的受众从更新后的UI中消失的问题。 (TGT=52091)
* 修复了阻止在活动中使用重复受众的问题。 （TGT-51200 和 TGT-52057）
* 修复了一个问题，该问题导致在更新后的UI中逆转受众细化和活动受众。 (TGT-52158)
* 修复了由于用户输入错误“此用户不允许使用非默认工作区”而阻止创建新活动的问题。 (TGT-52267)
* 修复了导致无法在默认工作区和非默认工作区的更新UI中显示选件的问题。 [!DNL Target]现在显示来自两个工作区的选件。 (TGT-52339)
* 修复了在编辑活动和更改修改的网站元素时，[!DNL Target]未警告客户的问题。 (TGT-52100)
* 修复了以下问题：编辑具有临时选件的选件时，会创建一个新选件而不是更新现有选件。 (TGT-52135)
* 修复了将选件移动到文件夹时导致无效有效负载错误的问题。 (TGT-52325)
* 修复了将选件移动到文件夹时导致用户输入错误的问题。 (TGT-52296)
* 为每个活动添加了`audienceMetadata`字段，并确保在编辑活动时已读取并更新该字段。 (TGT-51004)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
