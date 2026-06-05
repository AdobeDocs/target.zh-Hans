---
keywords: target用户界面；用户界面；ui；常见问题解答；faq
description: 有关更新的 [!DNL Target]t用户界面的问答。
title: 可在何处找到有关更新的 [!DNL Target] UI的常见问题解答？
feature: Overview
exl-id: 75db4791-ca51-472d-99dd-583f7a74b222
TQID: https://experienceleague.adobe.com/yMMNq7GL-lvpzJL9nw9mPm8QHmp0A0hgDK3spB1Z2r0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2013
ht-degree: 1%

---

# [!DNL Target]用户界面更新常见问题解答

[!DNL Adobe Target]用户界面重新设计于2025年推出，可为所有用户提供更清晰、更直观的体验。 此常见问题解答涵盖对[!DNL Target] UI和[!UICONTROL 可视化体验编辑器] (VEC)的关键更新，包括导航更改、功能放置和移除临时UI切换。 无论您是营销人员、开发人员还是管理员，它都是您实现平稳过渡和智能工作流的指南。

## 是否更新了弃用Target UI版本切换的时间表？

+++查看详细信息
[!DNL Target]团队正在提供一项临时功能，可让您使用切换按钮在更新的[!DNL Target] UI和旧版本之间切换。 此选项仅在UI转出的最后阶段可用。

![Target UI版本切换](/help/main/r-release-notes/assets/toggle.png)

转出完成后，切换将被删除，所有用户将永久转换为更新后的UI。 [!DNL Adobe]建议提前计划，因为此功能将很快淘汰。

### 弃用时间线

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

### UI切换行为的限制 {#limitations}

以下信息介绍了在选择使用版本切换时应该注意的限制：

* **新活动的可见性**：如果切换回旧版UI，则在更新后的UI中创建的活动将不可见。
* **编辑现有活动**：在使用更新的UI时，对现有活动（最初在旧版UI中创建）所做的更改将发布到您的网站。 但是，如果切换回去，这些更新在旧版UI中不可见；只有从旧版UI中进行的最后一次更新会出现在那里。
* **活动详细信息的一致性**：无论您使用哪个UI，最新更改都会反映在您的实时网站上。 但是，旧版UI仅显示从该版本中进行的最新更改。 如果在更新的UI中编辑的活动与您在旧版UI中看到的活动外观不同，这种情况可能会导致混淆。

### 更多资源以了解更新的UI

* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答是关于新的[!DNL Target] UI和[!UICONTROL 可视化体验编辑器] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。
* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!UICONTROL 活动]、[!UICONTROL 推荐]和[!UICONTROL 可视化体验编辑器] (VEC)在[!DNL Target]中的主要UI更改摘要。
* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!UICONTROL 选件库]在[!DNL Target]中关键UI更改的摘要。
* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。
* [[!UICONTROL 可视化体验编辑器]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL 可视化体验编辑器] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。
* [[!UICONTROL 可视化体验编辑器]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

+++

## 在哪里可以找到有关更新的[!DNL Target] UI的更多信息？

+++详细信息
以下资源提供了有关已更新[!DNL Target] UI的详细信息的信息：

* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!UICONTROL 选件库]在[!DNL Target]中关键UI更改的摘要。

* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

* [[!UICONTROL 可视化体验编辑器]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL 可视化体验编辑器] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。

* [[!UICONTROL 可视化体验编辑器]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

+++

## 更新的UI是否对所有当前[!DNL Target]客户（[!UICONTROL Standard]和[!UICONTROL Premium]）可用？

+++详细信息
更新的UI适用于所有[!DNL Target]客户，[!UICONTROL Standard]和[!UICONTROL Premium]。 无需升级许可证或SKU。

有关转出和弃用临时UI版本切换的详细信息，请参阅[您需要了解的时间性更新](/help/main/r-release-notes/release-notes.md#time-sensitive)。

+++

## 在弃用旧版UI之前，是否将修复当前的错误列表？

+++详细信息
[!DNL Target]团队正在积极解决与新UI转出相关的问题。 更新和持续改进的详情见发行说明。

有关转出和弃用临时UI版本切换的详细信息，请参阅[您需要了解的时间性更新](/help/main/r-release-notes/release-notes.md#time-sensitive)。

+++

## 如果客户希望保留旧版UI，他们是否可以申请将UI版本切换保留为其帐户？

+++详细信息
UI版本切换是一项临时功能，允许您使用切换按钮在更新的[!DNL Target] UI和旧版本之间切换。 此选项仅在UI转出的最后阶段可用。 转出完成后，切换将被删除，所有用户都将永久转换为更新后的UI。

使用UI版本切换存在几个限制，包括新活动的可见性、现有活动的编辑以及活动详细信息的一致性。

有关详细信息，请参阅[您需要了解的时间性更新](/help/main/r-release-notes/release-notes.md#time-sensitive)。

+++

## [!DNL Adobe]能否延迟我们向更新UI的迁移，直到完全转出完成？

+++详细信息
[!DNL Target]不提供延迟或自定义UI迁移时间的选项。 客户将分阶段转换，转出计划由[!DNL Adobe]管理。 有关最新更新，请参阅发行说明。

使用UI版本切换存在几个限制，包括新活动的可见性、现有活动的编辑以及活动详细信息的一致性。

有关详细信息，请参阅[您需要了解的时间性更新](/help/main/r-release-notes/release-notes.md#time-sensitive)。

+++

## 更新后的VEC如何处理重新排列、调整大小、移动、隐藏和删除选项，这些选项与旧版VEC有何不同？ {#options}

+++详细信息
**[!UICONTROL 重新排列*]*：在旧版VEC中，重新排列选项使用覆盖来允许用户重新定位其同级组中的元素。 迁移仅限于更改同级元素之间的顺序。

在更新的VEC中，此功能通过向前移动和向后移动操作进行了简化。 这些控件通过按栈叠顺序向前或向后移动元素来调整元素在布局中的位置（水平或垂直）。

**调整大小**： [!UICONTROL 调整大小]功能位于[!UICONTROL 大小]部分下的[!UICONTROL 属性]面板中。 用户可以直接调整元素的宽度和高度。 高级设置包括：

* 最小/最大宽度和高度控件
* 溢出行为设置。
* 媒体元素的“对象适合”选项

这些工具可精确控制元素维度和布局行为。

**移动**：在[!UICONTROL 位置]部分下的[!UICONTROL 属性]面板中找到[!UICONTROL 移动]选项。 此选项使用户能够：

* 设置元素的位置（例如，绝对、相对、固定）
* 定义用于分层的z索引
* 选择定位类型

更新的[!UICONTROL 属性]边栏还支持自定义内联样式，在预设选项无法满足布局需求时提供灵活性。

**[!UICONTROL 隐藏]**： [!UICONTROL 隐藏]功能位于[!UICONTROL 属性]面板中。 选择某个元素后，单击[!UICONTROL 隐藏元素]以将其从视图中删除而不将其删除。 这有助于在设计或预览期间管理可见性。

**[!UICONTROL 删除]**： [!UICONTROL 删除]功能可通过[!UICONTROL 属性]面板访问。 选择元素后，单击删除元素可从页面中删除该元素。 此操作将从布局中永久删除元素。

+++

## 我可以折叠[!UICONTROL 组件]、[!UICONTROL 修改]和[!UICONTROL 属性]边栏以便放大[!UICONTROL 设计]面板吗？ {#collapse}

+++详细信息

可以，您可以折叠这些边栏以允许您展开[!UICONTROL 设计]画布以便于编辑。 以下是具体操作方法：

>[!NOTE]
>
>[!UICONTROL 显示组件]图标（![显示组件图标](/help/main/assets/icons/Add.svg)）和[!UICONTROL 显示修改]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）用作切换以显示相应的选项。

**折叠[!UICONTROL 组件]边栏**

要折叠[!UICONTROL 组件]边栏并放大[!UICONTROL 设计]画布，请在[!UICONTROL 组件]边栏打开时单击（![显示组件图标](/help/main/assets/icons/Add.svg) ）图标。

**折叠[!UICONTROL 修改]边栏**

要折叠[!UICONTROL 修改]边栏并放大[!UICONTROL 设计]画布，同时打开[!UICONTROL 修改]边栏，请单击[!UICONTROL 显示修改]图标（![显示修改边栏](/help/main/assets/icons/History.svg)）图标。

**折叠[!UICONTROL 属性]边栏**

若要折叠[!UICONTROL 属性]边栏并放大[!UICONTROL 设计]画布，请单击边栏右侧的[!UICONTROL 显示/隐藏属性]图标（![属性图标](/help/main/assets/icons/Propertie.svg)）以折叠或显示[!UICONTROL 属性]边栏。

+++

## [!UICONTROL 另存为草稿]和[!UICONTROL 正在同步]状态是否仍然可用？

+++详细信息
随着用户界面的最新更新，[!UICONTROL 另存为草稿]和[!UICONTROL 正在同步]状态将不再可用。 有关详细信息，请参阅&#x200B;*[!UICONTROL 活动概述]*&#x200B;中的[将筛选器应用到“活动”列表](/help/main/c-activities/activities.md#filters)下的状态。

+++

## 如何判断是在旧版UI中还是在更新后的UI中创建或编辑了活动？

+++详细信息
在更新后的UI中创建或编辑的活动遵循相同的引导式三步工作流，并且可能包含旧版创建的活动中不存在的特定于UI的元数据或格式。 尽管界面中没有可见的标记或标签，但版面、结构或可用选项（例如增强型定位或预览功能）中的差异可指示使用了哪个UI。 有关详细标识，请检查活动的更改历史记录或查阅您的实施日志。

+++

## 在旧版中创建选件与更新的UI之间有何区别？ 是否需要其他属性？

+++详细信息
[!UICONTROL 选件库] UI要求所有选件具有一致的属性定义。 创建仅限该活动（临时）的选件时，用户还必须指定选件名称。 此信息显示在[!UICONTROL 基于表单的体验编辑器]中，这样无需查看代码或内容即可更轻松地识别选件。

+++

## 更新后的UI中的优惠预览链接发生了什么情况？

+++详细信息
[!UICONTROL 体验片段]预览链接在[!UICONTROL 快速信息]弹出框中可用，单击与所选片段对应的信息图标（![信息图标](/help/main/assets/icons/InfoOutline.svg)）时会显示该弹出框。

+++

## 使用更新的UI编辑现有活动时，我必须禁用[!UICONTROL 增强型体验编辑器]。 [!DNL Adobe]是否观察到与其他客户类似的行为？

+++详细信息
是. 使用[!DNL Adobe Experience Cloud] [!DNL Visual Editing Helper extension]时，您可能需要禁用[!UICONTROL 增强型体验编辑器] (EEC) 。

有关更多信息，请参阅[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

+++

## 您能告诉我用于列入允许列表的新IP的详细信息吗？

+++详细信息
有关可以允许列表的IP地址的详细信息，请参阅以下文章：

* **增强型体验编辑器(EEC)**：请参阅[在&#x200B;*解决与增强型体验编辑器相关的问题*&#x200B;中，EEC无法加载在公共IP上不可访问的内部QA URL](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF)
* **[!UICONTROL 推荐]**：查看[推荐信息源处理服务器使用的IP地址](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)。

+++

## 默认情况下，环境会在新的推荐UI上重置为暂存环境吗？

+++详细信息
环境现在默认为客户使用的最后一个环境。 要切换环境，请使用[!UICONTROL 目录搜索] UI右上角的[!UICONTROL 环境]选择器。

![环境开关](/help/main/c-intro/assets/environmnent.png)

+++

## 将[!DNL Adobe Analytics]或[!DNL Customer Journey Analytics]连接到[!DNL Target]有多复杂？

+++详细信息
将[!DNL Adobe Analytics] (AA)或[!DNL Customer Journey Analytics] (CJA)与[!DNL Target]集成的工作量可能介于中到高级之间，具体取决于您当前的设置。 如果您使用[!DNL Adobe Experience Platform]并已实施[!DNL Platform Web SDK]，则集成会更简化。 但是，使用at.js或AppMeasurement的旧版实施可能需要额外的配置，包括：

* 启用[Analytics for Target (A4T)集成](/help/main/c-integrating-target-with-mac/a4t/a4t.md)
* 将[[!DNL Target] 报告集成到 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中。
* 映射报表包和数据视图
* 确保一致的身份解析(ECID)
* 验证数据收集和归因设置

+++
