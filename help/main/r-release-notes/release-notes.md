---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b0de4b039dd2a130d55fac3058fbdb40771d4fc7
workflow-type: tm+mt
source-wordcount: '2731'
ht-degree: 15%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 25.6.4（2025年6月27日）

此版本包含以下修复和更新：

* 已将[!UICONTROL Rearrange]选项添加到更新的[!UICONTROL Visual Experience Composer] (VEC) UI，以便与旧版VEC中可用的功能保持一致。 （TGT-46957 和 TGT-52876）
* 修复了对[!UICONTROL A/B Test]活动中的变体体验（例如体验B）所做的修改未保留的问题。 在体验之间切换后，对变量的更改将消失。 此问题不会影响控制体验。 (TGT-52664)
* 修复了以下问题：某些客户无法创建或保存活动，而其他客户可以正常执行相同的操作。 不同帐户之间的问题不一致。(TGT-52842)
* 修复了在更新后的VEC中，用户无法移动对[!UICONTROL Page Load event]的修改的问题，该功能存在于旧版UI中。 (TGT-52617)
* 修复了更新后的UI中的一个问题：在创建更改时[!UICONTROL page load]事件在[!DNL Target]中不可见；更新仅应用于视图。 (TGT-52604)
* 修复了一个问题，该问题导致某些活动修改无法在更新后的VEC中正常显示。 (TGT-52818)
* 修复了在获取[!UICONTROL Automated Personalization] (AP)活动的报表数据时发生的空指针异常。 (TGT-52362)
* 修复了导致选件级别详细信息无法在[!UICONTROL Automated Personalization] (AP)活动的.CSV文件中显示的问题。 (TGT-52675)
* 修复了在更新的VEC中应用修改时，更改最初正确显示的问题，包括预期的[!UICONTROL Experience Fragment]。 但是，在切换体验或进行其他编辑时，由于选择器问题，某些修改无法应用。 (TGT-52679)
* 修复了在通过克隆现有活动创建新活动时，克隆活动中的QA链接错误地保留原始活动中的页面URL的问题。 (TGT-52775)
* 修复了无意中导致[!UICONTROL On-device Decisioning]在更新的VEC中不可用的问题。 (TGT-52371)
* 修复了阻止编辑产品[!DNL Recommendations]活动的问题。 尝试通过Target UI访问VEC时，[!UICONTROL Overview]页面上出现错误，导致无法进行任何编辑。 (TGT-52823)
* 修复了在体验名称超过50个字符时阻止保存[!DNL Recommendations]活动的问题。 (TGT-52619)
* 修复了客户在新UI中修改标准后无法保存“推荐”活动的问题。 该问题似乎与权限相关，并不影响具有相似角色的所有用户。 (TGT-52816)
* 修复了具有[!UICONTROL Editor]角色的用户无法编辑[!DNL Recommendations]活动的问题。 尝试更改设计并保存活动会导致403禁止错误，声明“[编辑者]”权限是必需的，即使用户已在相关工作区中拥有该角色。 (TGT-52836)

## [!DNL Target Standard/Premium] 25.6.3（2025年6月20日）

此版本包含以下修复和更新：

* 修复了将活动从一个工作区复制到另一个工作区时触发错误（如“不能为空”或“出现错误”）的问题。 (TGT-52474)
* 修复了无法为某些活动生成[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]报告的问题。 (TGT-52904)
* 修复了更新后的VEC中，[!UICONTROL Automated Personalization] (AP)活动中的默认内容处理与旧版UI不匹配的问题。 在没有显式添加组时，系统现在将自动添加名为“默认内容”的默认`optionGroup`和`optionGroupLocalId = 0`。 此组包含默认选项（例如，`optionLocalId: 0`）。 如果移除默认内容，则也会移除相应的选项组。 (TGT-52651)
* 修复了[!UICONTROL Multivariate Test] (MVT)活动中的一个问题，该问题导致不正确地不允许重用之前已删除体验中的`experienceLocalId`。 (TGT-52672)
* 修复了阻止复制或编辑包含体验片段的活动的问题。 这触发了错误： `Enum "AemOfferType" cannot represent value: "html"`。 (TGT-52635)
* 修复了活动位置中的URL由于斜杠(/)等无效字符而无法显示查询参数的问题。 (TNT52845)
* 改进了通过后端API进行的[!DNL A/B Test]活动更新的验证错误消息。 当存在重复的位置名称时，该消息现在会明确声明：`locations.selectors`的“不允许存在重复的名称”。 (TGT-52589)
* 修复了更新实时[!UICONTROL Recommendations]活动时由于请求有效负载中的属性无法识别而发生的错误。 系统现在可以正确处理“无效JSON”。 无法识别的属性名称”错误。 (TGT-52723)
* 修复了阻止创建[!DNL Recommendations]设计的问题。 单击[!UICONTROL Create]触发消息：“脚本中应至少使用1个实体变量。” （TGT-52395 和 TGT-52899）
* 修复了阻止在不进行修改的情况下重新保存[!DNL Recommendations]设计的问题。 (TGT-52879)
* 修复了在保存[!UICONTROL Recommendations]活动时导致出现“400错误请求”错误的后端验证错误。 (TGT-52716)
* 修复了[!UICONTROL Form-Based Experience Composer]中的一个问题，该问题导致将鼠标悬停在[!UICONTROL Location]下拉列表中具有特殊字符的mbox上导致编辑器变为空白并触发“无法对‘元素’执行‘querySelector’”。 错误。(TGT-52717)
* 通过新的“PARTIALLY_IMPORTED”指示符提高了馈送状态准确性。 以前，即使未导入文件中的所有行，信息源也会标记为“success”，这很有误导性。 (TGT-52892)
* 修复了迁移到AP V2后，对`/admin/rest/ui/v1/campaigns`的特定API调用返回客户端错误(HTTP 4xx)的错误。 (TGT-52721)

## 已更新：[!DNL Target] UI版本切换已弃用（2025年6月17日） {#revised}

自2025年6月17日起，应为特定用户或组织范围内的更新的[!DNL Target] UI启用所有IMS组织，以开始测试新体验。

由于最近发现的问题（主要与复杂的客户自定义相关），[!DNL Target]团队已调整弃用时间表：

* **2025年6月30日**： [已更新 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)将成为已启用UI版本切换的所有IMS组织的默认体验。

   * 默认情况下，当前查看旧版UI的客户在登录后将看到更新后的UI。
   * 用户界面版本切换将在7月底之前保持可用，允许用户在需要时切换回来。

  >[!IMPORTANT]
  >
  > [!DNL Adobe]强烈建议使用更新的[!DNL Target] UI。 仅当发生阻止程序问题时，才切换回旧版UI。 请参阅以前版本的发行说明中的[[!DNL Target] UI版本切换弃用（2025年5月23日）](/help/main/r-release-notes/release-notes-for-previous-releases.md#toggle)，以了解有关切换的重要信息。

* **2025年7月15日至7月30日**：将分阶段永久禁用UI版本切换。 受影响的IMS组织将无法再还原到旧版UI。

   * 例外情况将逐一审查。
   * 在解决阻止程序问题时，仅会短暂地准予延迟切换弃用（几天）。

如果您有任何顾虑或者预计在此过渡期间会出现任何问题，请联系[Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)。

## [!DNL Target Standard/Premium] 25.6.2（2025年6月12日）

此版本包含以下修复和更新：

* 添加了[篇新的常见问题解答文章](/help/main/c-intro/updated-ui-faq.md)，以解决有关已更新的[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题。
* 修复了[!UICONTROL Page Delivery]中的“[!UICONTROL URL - does not contain]”规则无法正常工作的问题，即使应该阻止该规则，仍允许显示内容。 (TGT-52754)
* 修复了[!UICONTROL Page Delivery]错误显示错误消息“不允许存在重复的页面URL”的问题。 (TGT-52765)
* 修复了包含体验片段的[!UICONTROL Page Delivery] URL的受众创建时错误地附加了#的问题。 (TGT-52786)
* 修复了复制活动和编辑[!UICONTROL Goals and Settings]页面上的设置导致[!DNL Target] UI无响应的问题。 (TGT-52797)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中错误允许将[!UICONTROL A/B Test]活动中的其他页面重定向到同一URL的问题。 (TGT-51838)
* 修复了在编辑活动时未保存[!UICONTROL Goals and Settings]页面上量度更改的问题。 (TGT-52799)
* 修复了在Web编辑器仍在加载时添加新体验导致新体验与以前的体验重复内容的问题。 (TGT-51397)
* 已恢复在`<head>`标记之外使用自定义代码的功能，该功能以前在旧版Target UI中可用。 （TGT-52304 和 TGT-52300）
* 删除了在活动创建期间选择默认工作区时不必要的验证。 强制属性验证不再适用于默认工作区，但适用于非默认工作区。 (TGT-52449)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中未检测到`triggerView()`调用的问题。 (TGT-52575)
* 修复了更新的[!UICONTROL Visual Experience Composer] (VEC)中阻止用户向[!UICONTROL Single Page Application] (SPA)视图添加修改的问题。 (TGT-52556)
* 修复了更新的[!DNL Target] UI中阻止客户查看优惠详细信息的问题。 (TGT-52607)
* 修复了对[!UICONTROL Offers Library]中的优惠所做的更新未反映在更新的[!UICONTROL Visual Experience Composer] (VEC)中的问题。 (TGT-52637)
* 修复了在创建活动时导致“优惠”部分无法正确显示的问题。 (TGT-52773)
* 添加了验证，以确保`optionGroups`中引用的所有`optionLocalIds`都存在于选项数组中。 创建活动期间会自动删除无效引用。 (TGT-52687)
* 修复了在添加新选件后未保留报表组和排除项的问题。 (TGT-52728)
* 修复了没有[!UICONTROL Activity QA]按钮的活动显示空选项选择器的问题。 (TGT-52733)
* 修复了QA链接无法正确呈现内容的问题。 (TGT-52718)
* 修复了将元素替换为体验片段时无法正确反映QA环境中更改的问题。 (TGT-52762)
* 修复了更新[!UICONTROL Visual Experience Composer] (VEC)中的一个问题，该问题在用户尝试添加体验片段时导致“输入无效”错误。 (TGT-52701)
* 修复了在更新的[!UICONTROL Visual Experience Composer] (VEC)中编辑受众定位时，“编辑受众”模式显示为空的问题。 (TGT-52749)
* 添加了消息，以在所选工作区中无法访问实体时通知用户。 (TGT-52767)
* 修复了UI无法允许将环境ID手动分配给标准的问题。 而是默认为[!UICONTROL Product Catalog Search]主机组的ID。 此修复确保标准更改现在可以应用于所有环境，而不仅仅是默认环境。 (TGT-52817)
* 修复了包含推荐的[!UICONTROL Experience Targeting] (XT)活动缺少“[!UICONTROL Download Recommendations data]”选项的问题。 （TGT-52730 和 TGT-52756）

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

## [!DNL Target] UI版本切换弃用（2025年5月23日） {#toggle}

>[!IMPORTANT]
>
>[!DNL Target]团队已调整UI版本切换弃用的时间线。 有关详细信息，请参阅[已更新： [!DNL Target] UI版本切换弃用（2025年6月17日）](#revised)。

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

* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答关于新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。

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
