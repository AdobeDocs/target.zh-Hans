---
keywords: target用户界面；用户界面；ui；常见问题解答；faq
description: 有关更新的 [!DNL Target]t用户界面的问答。
title: 可在何处找到有关更新的 [!DNL Target] UI的常见问题解答？
feature: Overview
exl-id: 75db4791-ca51-472d-99dd-583f7a74b222
source-git-commit: 107770a27a80943db858729ce1cb3dceeda22dfb
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 0%

---

# [!DNL Target]用户界面更新常见问题解答

2025年新增功能，[!DNL Adobe Target]更新的用户界面引入了简化且直观的体验，旨在提高所有角色的可用性和效率。 此常见问题解答解决了有关新[!DNL Target] UI和[!UICONTROL Visual Experience Composer] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。

## 是否更新了弃用Target UI版本切换的时间表？

+++详细信息
是的。 您可以在[需要了解的时间敏感更新](/help/main/r-release-notes/release-notes.md#time-sensitive)中找到新时间表和重要信息。

+++

## 在哪里可以找到有关更新的[!DNL Target] UI的更多信息？

+++详细信息
以下资源提供了有关已更新[!DNL Target] UI的详细信息的信息：

* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!DNL Target]中[!UICONTROL Activities]、[!UICONTROL Recommendations]和[!UICONTROL Visual Experience Composer] (VEC)的关键UI更改的摘要。

* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!DNL Target]在[!UICONTROL Offers Library]中关键UI更改的摘要。

* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

* [[!UICONTROL Visual Experience Composer]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL Visual Experience Composer] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。

* [[!UICONTROL Visual Experience Composer]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。

+++

## 更新的UI是否对所有当前[!DNL Target]客户（[!UICONTROL Standard]和[!UICONTROL Premium]）都可用？

+++详细信息
更新后的UI对所有[!DNL Target]客户[!UICONTROL Standard]和[!UICONTROL Premium]都可用。 无需升级许可证或SKU。

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

++++

## [!DNL Adobe]能否延迟我们向更新UI的迁移，直到完全转出完成？

+++详细信息
[!DNL Target]不提供延迟或自定义UI迁移时间的选项。 客户将分阶段转换，转出计划由[!DNL Adobe]管理。 有关最新更新，请参阅发行说明。

使用UI版本切换存在几个限制，包括新活动的可见性、现有活动的编辑以及活动详细信息的一致性。

有关详细信息，请参阅[您需要了解的时间性更新](/help/main/r-release-notes/release-notes.md#time-sensitive)。

+++

## 如何判断是在旧版UI中还是在更新后的UI中创建或编辑了活动？

+++详细信息
在更新后的UI中创建或编辑的活动遵循相同的引导式三步工作流，并且可能包含旧版创建的活动中不存在的特定于UI的元数据或格式。 尽管界面中没有可见的标记或标签，但版面、结构或可用选项（例如增强型定位或预览功能）中的差异可指示使用了哪个UI。 有关详细标识，请检查活动的更改历史记录或查阅您的实施日志。

+++

## 在旧版中创建选件与更新的UI之间有何区别？ 是否需要其他属性？

+++详细信息
[!UICONTROL Offer Library] UI要求所有选件具有一致的属性定义。 创建仅限该活动（临时）的选件时，用户还必须指定选件名称。 此信息显示在[!UICONTROL Form-based Experience Composer]中，这样无需查看代码或内容即可更轻松地识别选件。

+++

## 更新后的UI中的优惠预览链接发生了什么情况？

+++详细信息
[!UICONTROL Experience Fragment]预览链接在[!UICONTROL Quick Info]弹出框中可用，单击与所选片段对应的信息图标（ ![信息图标](/help/main/assets/icons/InfoOutline.svg)）时显示。

+++

## 使用更新的UI编辑现有活动时，必须禁用[!UICONTROL Enhanced Experience Composer]。 [!DNL Adobe]是否观察到与其他客户类似的行为？

+++详细信息
是的。 使用[!DNL Adobe Experience Cloud] [!DNL Visual Editing Helper extension]时，您可能需要禁用[!UICONTROL Enhanced Experience Composer] (EEC) 。

有关更多信息，请参阅[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

+++

## 您能告诉我用于列入允许列表的新IP的详细信息吗？

+++详细信息
有关可以允许列表的IP地址的详细信息，请参阅以下文章：

* **增强型体验编辑器(EEC)**：请参阅[在](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF)解决与增强型体验编辑器相关的问题&#x200B;*中，EEC无法加载在公共IP上不可访问的内部QA URL*
* **[!UICONTROL Recommendations]**：查看推荐信息源处理服务器使用的[IP地址](/help/main/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md)。

+++

## 默认情况下，环境会在新的推荐UI上重置为暂存环境吗？

+++详细信息
环境现在默认为客户使用的最后一个环境。 要切换环境，请使用[!UICONTROL Environment] UI右上角的[!UICONTROL Catalog Search]选择器。

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
