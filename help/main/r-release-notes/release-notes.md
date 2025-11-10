---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5c1dda629a33fc38f51e2e3198a7ea091a369897
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 19%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 25.11.1（2025年11月10日）


**Analytics for Target (A4T)**

+++查看详细信息
* 在更新的UI中使用&#x200B;**[!UICONTROL Goals & Settings]作为报表源时出现[!DNL Adobe Analytics]错误消息。**&#x200B;解决了更新[!UICONTROL Overview] UI中的问题，该问题导致目标部分显示“出现错误”错误。 我们无法完成您的请求。 如果选择[!DNL Adobe Client Care] (A4T)作为报表源，如果问题仍然存在，请联系[!DNL Adobe Analytics]。 目标现在可以正确显示为[!UICONTROL Adobe Analytics]个量度，从而确保跨报表源的一致可见性。 (TGT-54021)

+++

**受众**

+++查看详细信息
* **无法在更新的UI中选择多个报表受众。**&#x200B;解决了在更新的UI中，用户在编辑活动时无法同时选择多个新创建的报表受众的问题。 现在可以同时分配多个受众，从而提高报表设置的灵活性和效率。 (TGT-53253)

+++

**决策优惠**

+++查看详细信息
* **无法在更新的UI中编辑或替换决策选件。**&#x200B;解决了在更新的UI中，无法通过[!UICONTROL Modifications]面板编辑或替换决策优惠，且优惠名称显示为空白的问题。 Decisioning优惠现在完全可访问和编辑，从而恢复与旧版UI的等同性，并确保客户可以直接在活动中管理优惠。 (TGT-53884)

+++

**本地化**

+++查看详细信息
* **更正了朝鲜语和日语UI中的几个本地化错误。** (TGT-54003、TGT-54004、TGT-54006、TGT-54007和TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++查看详细信息
* **具有实体属性匹配的按属性促销，在活动保存后无法加载推荐键。**&#x200B;修复了在保存活动后进行编辑时，规则类型为[!UICONTROL Promotion by Attribute]且类型为[!UICONTROL Entity Attribute Matching]的促销未加载推荐键的问题。 问题是由未通过GraphQL请求`customKeyId`导致的。 现在，推荐键可在编辑促销活动期间正确加载。 (TGT-53117)
* 从ExpB切换到ExpA时，**推荐会以可视方式持续存在。**&#x200B;解决了在体验B中插入推荐，然后切换到体验A以使推荐选件框可见的问题。 这只是视觉上的不一致；现在，在体验之间切换时，修改可正确呈现，从而确保准确的UI行为。 (TGT-53911)
* **推荐键未加载[!UICONTROL Promotion by Attribute]且匹配[!UICONTROL Entity Attribute]。**&#x200B;解决了规则类型为[!UICONTROL Promotion by Attribute]且类型为[!UICONTROL Entity Attribute Matching]的促销活动在保存活动后编辑时未加载推荐键的问题。 现在，可通过GraphQL正确检索推荐键，从而确保促销活动按预期显示和运行。 (TGT-53917)
* **无法对更新后的UI中隐藏的HTML元素编辑推荐。**&#x200B;解决了[!UICONTROL New Create]和VEC UI中的一个问题，该问题导致无法编辑应用于隐藏HTML元素的推荐活动。 此功能现在可按预期工作，从而恢复与旧版UI的等同性，并确保无论元素可见性如何，推荐都可以修改。 (TGT-53953)
* **无法在更新的UI中编辑有关隐藏HTML元素的推荐活动。**&#x200B;解决了在更新的UI中，无法编辑应用于隐藏HTML元素的推荐活动的问题。 此功能现在可按预期工作，从而恢复与旧版UI的等同性，并确保无论元素可见性如何，推荐都可以修改。 (TGT-53951)
* **推荐目录在更新的UI中间歇性地缺少属性值。**&#x200B;解决了在更新的[!UICONTROL Recommendations] UI中，目录搜索列表间歇性地无法显示某些属性值（例如，消息）的问题，即使该值存在于产品馈送中也是如此。 现在，搜索结果中的属性值加载一致，无需重新配置列，提高了目录管理的可靠性和效率。 (TGT-52769)
* 更新后的UI中&#x200B;**[!UICONTROL Download Recommendations]活动缺少[!DNL Recommendations]按钮。**&#x200B;解决了在更新的[!DNL Recommendations] UI中，使用推荐的A/B活动无法显示[!UICONTROL Download Recommendations]按钮的问题。 现在，按钮可正确显示，允许用户按预期导出推荐数据，这与旧版UI中的功能一致。 (TGT-53768)
* 更新后的概述UI中缺少&#x200B;**[!UICONTROL Download Recommendation Data]按钮。**&#x200B;解决了更新后的[!UICONTROL Overview] UI中，[!UICONTROL Download Recommendation Data]按钮对包含推荐的活动不可见的问题。 按钮现在可正确显示，从而确保用户无需切换回旧版UI即可直接导出推荐数据。 (TGT-53772)
* **编辑活动条件有时会在更新后的UI中导致出现空白屏幕。**&#x200B;解决了更新UI中的一个问题：单击[!UICONTROL Edit Criteria in Experiences]有时会导致某些活动的屏幕变成空白。 现在，标准编辑器可以在所有活动中可靠地加载，从而确保用户能够不受中断地编辑。 (TGT-53961)
* **无法在更新的UI中编辑序列条件。**&#x200B;解决了更新UI中的问题：尝试编辑[!UICONTROL Sequence Criteria]导致标准弹出窗口在加载时卡住，然后显示空白屏幕。 标准编辑器现在可正确加载，允许用户编辑和更新序列标准而不会中断。 (TGT-53985)

+++

**[!UICONTROL Reports]**

+++查看详细信息
* **[!UICONTROL Multivariate Test] (MVT)位置和图形报告问题阻止生成报告。**&#x200B;解决了MVT活动无法在Target UI中生成[!UICONTROL Location Contribution]和图形报告的问题，显示错误“出现错误。 我们无法完成您的请求。” 现在，报告可在UI中正确加载，确保完全可见。 (TGT-53654)
* 由于&#x200B;**贡献报表错误，[!UICONTROL Element]MVT报表未加载。**&#x200B;修复了Target UI中无法加载MVT活动报表，并显示“无法获取元素贡献报表”错误的问题。 现在，报表可正确显示，从而确保元素贡献的全面可见。 (TGT-53691)
* **将订单详细信息导出到[!UICONTROL Experience Targeting] (XT)活动的CSV问题。**&#x200B;修复了XT活动中[!UICONTROL Export Order Details to CSV]选项显示不正确并返回空文件的问题。 现在，仅对AP活动显示选项，以确保准确的导出功能并防止混淆。 (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息
* **[!UICONTROL Delete Modification]按钮问题阻止删除活动修改。**&#x200B;解决了[!UICONTROL Delete Modification] UI中的[!DNL Target]按钮无法正常工作的问题，该按钮阻止用户删除活动中的修改。 现在，按钮按预期工作，允许毫不延迟地可靠地删除修改。 (TGT-53728)
* 更新的UI中无法识别&#x200B;**首选选择器。**&#x200B;解决了更新后的UI中，VEC的CSS选择器列表中未显示首选选择器（例如`data-target-component-id`）的问题。 用户现在可以可靠地选择首选属性而不是动态生成的类名，从而确保在进行SPA页面更新时稳定定位。 (TGT-53908)
* **活动位置在[!UICONTROL Edit]和[!UICONTROL Overview]页面之间对齐不匹配。**&#x200B;解决了[!UICONTROL Overview]页面中的活动位置编号与[!UICONTROL &#x200B; Edit Experience]页面中的更新不一致的问题。 现在，两个视图中的位置保持一致，确保精确的对齐并防止位置缺失或编号错误。 （TGT-53960 和 TGT-53954）
* **无法在更新的VEC中切换回[!UICONTROL Design]模式。**&#x200B;解决了更新后的VEC UI中的问题，该问题导致用户在[!UICONTROL Design]模式下导航到新页面后无法切换回[!UICONTROL Browse]模式。 [!UICONTROL Design]切换功能现在可以正常工作，允许修改无缝地跨页面应用。 （TGT-53988 和 TGT-53993）
* **查询参数未显示在活动概述中。**&#x200B;解决了更新UI中的问题：查询参数未显示在活动的[!UICONTROL Overview]页面中，从而导致[!UICONTROL Overview]和页面交付URL之间存在差异。 现在，查询参数可正确显示，从而确保活动位置在各个视图中完全表示并保持一致。 (TGT-53701)

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
