---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 29ddf23b41531e5fab80fe7d0f6bc913e778d839
workflow-type: tm+mt
source-wordcount: '1670'
ht-degree: 15%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

+++查看详细信息
[!DNL Target]团队正在提供一项临时功能，可让您使用切换按钮在更新的[!DNL Target] UI和旧版本之间切换。 此选项仅在UI转出的最后阶段可用。

![Target UI版本切换](/help/main/r-release-notes/assets/toggle.png)

转出完成后，切换将被删除，所有用户将永久转换为更新后的UI。 [!DNL Adobe]建议提前计划，因为此功能将很快淘汰。

#### 弃用时间线

由于最近发现的问题（主要与复杂的客户自定义相关），[!DNL Target]团队已调整弃用时间表：

* **2025年6月17日**：已为特定用户或组织范围的更新的[!DNL Target] UI启用所有IMS组织，以开始测试新体验。

* **2025年6月30日**： [已更新 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)成为已启用UI版本切换的所有IMS组织的默认体验。

   * 默认情况下，当前看到旧版UI的客户现在会在登录时看到更新后的UI。
   * 用户界面版本切换在7月底之前仍然可用，允许用户在需要时切换回去。

  >[!IMPORTANT]
  >
  > [!DNL Adobe]强烈建议使用更新的[!DNL Target] UI。 由于切换切换行为的[限制](#limitations)，因此出现阻止程序问题时才能切换回旧版UI。

* **2025年7月15日至7月30日**：将分阶段永久禁用UI版本切换。 受影响的IMS组织无法再还原到旧版UI。

   * 例外情况按个别情况予以审查。
   * 在解决阻止程序问题时，仅短暂地授予对切换弃用的延迟（几天）。

如有任何顾虑或您预计在此过渡期间会出现任何问题，请联系[Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md)。

#### UI切换行为的限制 {#limitations}

以下信息介绍了在选择使用版本切换时应该注意的限制：

* **新活动的可见性**：如果切换回旧版UI，则在更新后的UI中创建的活动将不可见。
* **编辑现有活动**：在使用更新的UI时，对现有活动（最初在旧版UI中创建）所做的更改将发布到您的网站。 但是，如果切换回去，这些更新在旧版UI中不可见；只有从旧版UI中进行的最后一次更新会出现在那里。
* **活动详细信息的一致性**：无论您使用哪个UI，最新更改都会反映在您的实时网站上。 但是，旧版UI仅显示从该版本中进行的最新更改。 如果在更新的UI中编辑的活动与您在旧版UI中看到的活动外观不同，这种情况可能会导致混淆。

#### 更多资源以了解更新的UI

* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答关于新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。
* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的关键UI更改的摘要。
* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]在[!UICONTROL Offers Library]中关键UI更改的摘要。
* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。
* [[!UICONTROL Visual Experience Composer]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。
* [[!UICONTROL Visual Experience Composer]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

+++

## [!DNL Target Standard/Premium] 25.9.1（2025年9月5日）

此版本包含以下更新和修复：

**[!UICONTROL Experience Fragments]**

+++查看详细信息
* **已改进[!UICONTROL AEM Experience Fragment]优惠的用户归因。**&#x200B;解决了VEC中[!UICONTROL Last updated] (XF)选件的“[!UICONTROL AEM Experience Fragment]”字段错误地显示代码ID而非用户名的问题。 在更新的UI中选择选件期间出现此差异，导致与旧版UI和HTML选件不一致，后者正确显示最后编辑者的名称。 此修复确保跨选件类型的一致用户归因，从而提高透明度并与预期行为保持一致。 （TGT-52880 和 TGT-52898）

+++

**Offer Decisioning**

+++查看详细信息
* 已解决ODE优惠的&#x200B;**优惠决策错误。**&#x200B;解决了通过[!DNL Target]插入的优惠决策引擎(ODE)优惠因缺少格式元数据而返回400错误的问题。 错误消息指示MIME类型为空，阻止成功处理优惠决策。 此修复确保正确处理优惠元数据，恢复个性化内容投放的功能，并实现营销活动的不中断执行。 (TGT-53635)
* 已解决&#x200B;**ODS选件呈现问题。**&#x200B;解决了在更新的UI中使用VEC生成活动时，通过[!DNL Offer Decision Service] (AJO)创建的[!DNL Adobe Journey Optimizer] (ODS)选件无法呈现的问题。 相同的配置在旧版UI中可正常使用，这会导致混淆并阻止活动执行。 此修复可确保两个UI版本之间提供一致的选件，从而恢复AJO驱动型个性化的预期行为。

+++

**报表**

+++查看详细信息
* 更新后的报表概述UI中的报表部分恢复了&#x200B;**下载选项。**&#x200B;解决了新概述UI中“报表”部分缺少[!UICONTROL Download]按钮，导致用户无法导出属性重要性得分的问题。 此更新将恢复完整的导出功能，从而简化对用于分析和报告的可下载数据的访问。 (TGT-53222)
* 已在&#x200B;**[!UICONTROL Download full CSV report]视图中恢复[!UICONTROL Important attributes]按钮。**&#x200B;解决了在更新的活动创建UI中，报告视图的[!UICONTROL Download full CSV report]部分中缺少[!UICONTROL Important Attributes]按钮的问题。 此修复可恢复对可下载见解的访问权限，从而确保更新和旧版UI中的功能一致。 (TGT-53238)
* **已解决影响更新后的概述UI中[!UICONTROL Auto Target]报告的UI问题。**&#x200B;修复了更新的概述界面中影响[!UICONTROL Auto Target]活动报表的多个UI问题。 这些修复包括：

   * 摘要报表中缺少提升和置信度量度
   * “已构建模型”复选框的颜色指示器不正确
   * 尽管[!DNL Analytics]中存在数据差异，但无法正常显示图形报告
   * [!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]报告缺少下载链接
   * [!UICONTROL Automated Segments]报告显示已损坏

  这些修复恢复了预期的报告行为，并提高了在更新后的UI中对[!UICONTROL Auto Target]性能的可见性。 (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++查看详细信息
* **已针对更新的UI中的参数存在条件更正表单验证。**&#x200B;解决了更新UI中的一个问题：选择“[!UICONTROL Custom mbox parameter value is present]”或“[!UICONTROL Parameter is present]”错误地要求客户输入值。 此行为与预期逻辑冲突，预期逻辑只是检查参数是否存在，而不管其值如何。 该修复将表单验证与预期行为保持一致，从而能够更顺畅地设置活动并支持完全采用更新后的UI。 (TGT-53638)
* **为页面交付中的参数存在规则更正了表单逻辑。”**&#x200B;解决了在更新的UI中选择页面投放规则（如“[!UICONTROL Parameter is present]”、“[!UICONTROL Parameter is not present]”、“[!UICONTROL Parameter value is present]”或“[!UICONTROL Parameter value is not present]”）时错误地要求用户输入其他参数值的问题。 此行为与旧版UI不一致，并且与在不指定值的情况下检测参数存在的预期逻辑相冲突。 此修复可恢复预期的规则配置行为，从而简化活动设置并提高可用性。 (TGT-53640)
* 在更新的UI中，改进了多页面规则生成器的&#x200B;**验证逻辑。**&#x200B;解决了更新后的UI中多页面规则生成器存在的多个验证问题。 这些修复包括：

   * 当mbox参数为空时阻止创建规则
   * 显示无效规则状态的相应错误消息
   * 更正不需要操作数值的一元运算符和基于参数的运算符的验证逻辑
   * 通过恢复保存功能启用带一元运算符的哈希片段规则

  这些更新可确保准确配置规则，并提高复杂页面交付方案中的可用性。 (TGT-53722)
* **在A/B和MVT活动中解决了位置重命名问题。**&#x200B;修复了更新UI中的一个错误，该错误导致在位置列表、定位和返回之间导航后，重命名[!UICONTROL A/B Test]或[!UICONTROL Multivariate Test] (MVT)活动中的位置不再有效。 此更新可确保保存位置名称更改，并在整个活动工作流中始终如一地反映这些更改。 (TGT-52367)
* 在更新的UI中修复了MVT和AP活动的&#x200B;**位置名称持久性。**&#x200B;解决了更新UI中在[!UICONTROL Multivariate Test] (MVT)和[!UICONTROL Automated Personalization] (AP)活动中编辑的位置名称未正确保存的问题。 重命名位置后，在选项卡（如[!UICONTROL Targeting]和[!UICONTROL Experiences]）之间导航会导致名称恢复到其以前的状态。 此修复确保在选项卡间进行一致的位置命名，并提高了活动设置期间的可靠性。 (TGT-52927)
* **在“管理MVT体验”面板中更正了“位置标签”。**&#x200B;解决了在更新的UI中，[!UICONTROL Manage Experiences] (MVT)活动中的[!UICONTROL Multivariate Test]面板显示不一致的位置编号的问题。 此修复程序可确保位置标签按顺序排列并正确与用户定义的修改保持一致，从而提高体验设置期间的清晰度和可用性。 (TGT-52929)

+++

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
