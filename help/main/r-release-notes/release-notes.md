---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f0536e466d59fc4e3cccd61c25b7fe7f48f03954
workflow-type: tm+mt
source-wordcount: '4858'
ht-degree: 7%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 25.9.3（2025年9月30日）

此版本包含以下增强功能和修复。

+++[!UICONTROL Audiences]

* **受众排除规则在[!DNL Target] UI中显示为包含不正确。在活动中编辑定位时，**&#x200B;配置排除规则的受众显示为已包括。 尽管在执行期间正确应用了排除逻辑，但UI无法正确反映规则，缺少“排除”标签。 [!DNL Target] UI现在可以在受众配置和定位工作流中正确显示排除规则，从而确保活动设置的明确性和一致性。 (TGT-53808)
* **[!UICONTROL Targeting]部分未指示受众规则已设置为排除。使用排除逻辑配置的受众**&#x200B;在活动创建UI的[!UICONTROL Targeting]部分中错误地显示为包含。 尽管后端正确应用了排除规则，但UI无法直观地表示该规则，在活动设置期间会忽略“排除”标签并导致混淆。 [!UICONTROL Targeting]部分现在可以清楚地显示排除规则，确保受众配置和定位可视化之间的一致性。 (TGT-53809)

+++

+++本地化

* **修复了“完整详细信息视图”的简体中文翻译中的术语不一致问题。**
以前，术语“Details”在简体中文(zh_CN)区域设置中被错误地翻译为“详情”，这违反了既定的术语指南。 已将此更正为“详细信息”，以确保与术语库一致。 (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **推荐框在VEC中难以查找和选择。**&#x200B;在(VEC)中添加推荐选件后，单击左侧面板中的修改未高亮显示或滚动到页面上相应的推荐框。 这使得查找和编辑选件变得困难，尤其是在选择器下隐藏或最小化样式时。 现在，单击推荐修改可正确高亮显示并滚动到关联的元素，从而提高更新的活动创建过程中的可用性和编辑效率。 (TGT-52571)
* 保存活动后，**推荐选择器重写不正确。**&#x200B;向VEC中的元素添加推荐时，选择器最初是正确的，但在保存并重新打开活动后，它更改为通用选择器。 尝试手动恢复原始选择器时导致验证错误。 现在，建议选择器在保存后可准确保留，从而确保在更新的活动创建过程中具有可靠的定位和可编辑性。 (TGT-53709)
* **修改现有活动时无法编辑标准内容。**&#x200B;在编辑活动时，[!UICONTROL Criteria]内容部分显示为禁用，按钮灰显且无响应。 通过确保[!UICONTROL Criteria]配置在活动更新期间完全可编辑，此问题已得到解决。 客户现在可以修改[!UICONTROL Criteria]内容，而无需切换选择或使用解决方法，从而改进了活动创建更新过程中的灵活性和可用性。 (TGT-53812)
* 无法在活动中编辑&#x200B;**标准。**&#x200B;从活动访问条件时，[!UICONTROL Edit Criteria]和[!UICONTROL Remove Criteria]选项已禁用。 但是，可通过[!UICONTROL Recommendations]选项卡成功编辑相同的标准。 现在，可以从活动编辑工作流和[!UICONTROL Recommendations]选项卡中完全编辑标准，从而确保一致且高效的编辑体验。 (TGT-53814)

+++

+++[!UICONTROL Reports]

* **在A[!UICONTROL utomated Personalization]活动中生成临时选件导致报表不一致。**&#x200B;在[!UICONTROL Automated Personalization] (AP)活动中使用生成临时选件功能导致报告不准确。 具体而言，选件ID在各个位置中重用，导致报表数据被错误归因或覆盖。 现在，每个位置生成的临时选件具有不同的标识符，从而确保所有配置的体验都能够准确跟踪和生成报表。 (TGT-53757)
* **由于JavaScript错误，无法加载活动报表。**&#x200B;客户在访问特定活动的[!UICONTROL Reports]选项卡时遇到“出现错误”消息。 该错误由JavaScript异常引起：无法读取在`getAnalyticsReportSummary` GraphQL调用期间触发的未定义的属性（读取“indexOf”）。 现在，报告可正确加载，并且错误处理已得到改进，以防止在更新的活动创建工作流中发生类似故障。 (TGT-53797)
* **报告与滚动条交互后崩溃。**&#x200B;单击[!UICONTROL Reports]选项卡中的滚动条导致页面崩溃，并伴有JavaScript错误：
  `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.`报告现在可以正确加载和滚动，而不会触发错误或崩溃。 (TGT-53828)
* **报告未显示主要指标。**&#x200B;活动报表中缺少使用mbox配置为转化量度的主要量度。 按量度名称或mbox名称搜索未产生任何结果，从而无法查看关键性能数据。 主要指标现在在[!UICONTROL Reports]选项卡中正确显示，从而确保准确跟踪和分析营销活动效果。 (TGT-53773)
* **与水平滚动条交互时，更新的UI中的[!UICONTROL Reports]选项卡崩溃。**&#x200B;当使用水平滚动条在视图外访问量度时，[!UICONTROL Reports]视图间歇性地崩溃，并出现“出现错误”错误。 现在，滚动条可以可靠地工作，允许客户查看和分析所有量度，而无需采取变通方法，例如缩小或使用按住Shift键滚动鼠标。 (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **在VEC中单击痕迹导航时，无法一致地显示编辑菜单。**
通过(VEC)中的痕迹导航选择HTML元素时，编辑菜单会间歇性地无法出现或快速消失，从而导致元素选择不可靠。 现在，通过痕迹导航导航时，会一致地显示编辑菜单，从而改进更新后的活动创建流程中的元素选择工作流。 (TGT-52873)
* **上下文菜单间歇性地无法在VEC中显示。**&#x200B;在单击元素时，更新后的VEC UI中的上下文菜单未一致显示，导致难以访问编辑选项。 现在，上下文菜单在元素选择时可靠地显示，从而改进了编辑工作流以及更新后的活动创建过程中的整体可用性。 (TGT-53015)
* **VEC中某些元素的上下文菜单无法显示。**&#x200B;在更新的VEC中选择特定元素时未显示上下文菜单，导致难以应用修改。 现在，所有受支持的元素都会一致显示上下文菜单，从而提高更新后的活动创建工作流中编辑体验的可靠性和可用性。 (TGT-53248)
* 在VEC中使用痕迹导航时，**上下文菜单在第一次单击时消失。**&#x200B;通过VEC中的痕迹导航选择父元素会导致上下文菜单短暂出现然后消失，从而难以访问编辑选项。 现在，在浏览痕迹导航元素时，上下文菜单保持可见且功能正常，这提高了更新后的活动创建流程中元素选择工作流的可靠性。 (TGT-53424)
* **VEC中的顶层元素未显示上下文菜单。**&#x200B;通过VEC中的痕迹导航选择顶级元素（如`<div>`或`<main>`标记）不会触发上下文菜单，从而阻止进一步编辑操作。 现在，所有受支持的元素（包括顶级容器）都会一致显示上下文菜单，从而提高活动创建工作流的灵活性和可用性。 (TGT-53770)
* **特定页面上的元素在VEC中不可编辑。**&#x200B;无法在更新的VEC中选择或编辑页面上的某些元素。 此问题仅存在于该页面，不影响同一帐户内的其他页面。 现在，页面上的所有元素均可按预期选择和编辑，从而恢复活动创建工作流中的完整功能。 (TGT-53353)
* **改进了在选择VEC中的元素期间查看子元素时的工作流。**&#x200B;为了提高活动创建期间的可用性和精确性，当鼠标悬停在父HTML元素上或选择父元素时，VEC现在会显示子元素。 此增强功能使客户能够更好地了解页面的结构并做出更准确的修改，从而简化更新后UI中的编辑工作流。 (TGT-53416)
* **无法使用修改栏编辑现有活动中的元素。**&#x200B;在编辑以前创建的活动时，修改栏无法激活页面上的某些元素，从而阻止更新。 此问题主要出现在修改后的活动中，并且难以在新创建的活动中复制。 修改栏现在可一致地显示并允许编辑所有受支持的元素，从而提高更新后的活动创建工作流中的可靠性和可用性。 (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **将活动克隆到其他工作区时触发了“用户输入无效”错误。**&#x200B;尝试将活动从一个工作区克隆到另一个工作区会导致错误：“InvalidProperty.Json — 无法识别的属性名称‘content’。” 导致此问题的原因是在克隆过程中未正确处理活动元数据。 现在，可以在不触发验证错误的情况下成功跨工作区克隆活动，从而确保更顺畅的活动部署工作流。 （TGT-53731 和 TGT-53736）

+++

## [!DNL Target Standard/Premium] 25.9.2（2025年9月22日）

此版本包括以下修复和增强功能：

**[!UICONTROL Audiences]**

+++查看详细信息
* **修复了由于受众ID无效而无法复制活动的问题。**&#x200B;客户尝试在更新的活动创建过程中复制活动时，遇到因受众ID无效(例如 — 1752722444307)导致的错误。 此后端验证问题可防止同一工作区中的活动重复。 此问题已得到解决，现在可以成功复制活动而不会出现与受众相关的错误。 (TGT-53717)
* **修复了[!UICONTROL Automated Personalization]模式的[!UICONTROL Manage Content]活动中仅活动受众出现无效用户输入错误的问题。**&#x200B;客户在AP活动的[!UICONTROL &#x200B; Manage Content]模式中配置仅限该活动的受众时遇到无效的用户输入错误。 尽管之前已成功使用受众，但还是出现了此问题。 现在，组合的受众配置可正确保存，而不会触发验证错误。 (TGT-53749)

+++

**文档**

+++查看详细信息
* **已将特定于Target的Web SDK文档页面移动到Adobe Target存储库。**&#x200B;作为Web SDK文档重组的一部分，特定于[!DNL Target]的内容已从常规Web SDK文档迁移到[!DNL Adobe Target] [开发人员指南](https://experienceleague.adobe.com/zh-hans/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}。 此更改改进了内容可搜索性，并确保相应的产品团队维护特定于解决方案的指导。 (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++查看详细信息
* **优惠决策选项在初始活动创建期间始终可见。**&#x200B;解决了更新后的UI中，首次创建A/B活动流程时，无法显示[!UICONTROL Offer Decision]选项的问题，尤其是在以无痕模式访问启用了优惠决策的租户时。 该选项仅在导航到[!UICONTROL Targeting]步骤并返回到[!UICONTROL Experiences]之后显示。 此修复程序确保[!UICONTROL Offer Decision]选项在初始设置期间立即可用，从而提高可用性并减少混淆。 (TGT-51888)

+++

**[!UICONTROL Offers]**

+++查看详细信息
* **修复了当`redirectOptions`时，重定向选件未在有效负载中包含`includeContent=true`的问题。使用**&#x200B;检索重定向优惠的`includeContent=true `客户在响应有效负载中缺少`redirectOptions`字段。 这种不一致会影响工作流，例如选件复制和活动创建。 在请求内容时，重定向选件现在正确包含`redirectOptions`。 (TGT-53737)

+++

**[!DNL Recommendations]**

+++查看详细信息
* **已恢复在更新的UI中创建的[!UICONTROL Recommendations]活动的点击跟踪。**&#x200B;解决了在更新的UI中创建的[!UICONTROL Recommendations]活动无法注册点击跟踪，导致报告转化为零的问题。 旧版UI中构建的活动可正确跟踪点击次数并报告预期转化。 此修复程序可确保在更新后的UI中创建的推荐活动现在包括正确的跟踪属性、恢复转化报表以及与A4T量度保持一致。 (TGT-53287)
* **已恢复推荐活动的点击跟踪。**&#x200B;解决了在更新的UI中创建的[!UICONTROL Recommendations]活动无法注册点击跟踪，导致报告转化为零的问题。 旧版UI将跟踪ID (`at-track-click`)正确应用于[!UICONTROL Recommendations]内容，而更新的UI错误地插入了占位符(`__recsClickTrackIdPlaceholder__`)，从而阻止后端跟踪。 此修复确保[!DNL Recommendations]内容现在包含正确的跟踪ID，从而恢复转化报表并与A4T量度保持一致。 (TGT-53496)
* 在更新的UI中解决了&#x200B;**收藏集编辑器崩溃问题。**&#x200B;修复了在更新的[!UICONTROL Visual Experience Composer] (VEC) UI中，从编辑器面板打开收藏集导致页面崩溃的问题，出现TypeError：无法读取未定义的属性（读取“customLocale”）。 此错误出现在多个活动类型中，包括[!UICONTROL Recommendations]和A/B测试。 (TGT-53703)
* **用于删除VEC中还原的选定收藏集的选项。**&#x200B;修复了VEC中的一个问题：用户只能替换[!UICONTROL Recommendations]活动中的选定集合，但无法将其完全删除。 此限制阻止了需要在不进行替换的情况下干净移除集合的用例。 此修复引入了一个用于删除所选收藏集的清除选项，从而允许在活动设置方面更加灵活，并与旧版UI行为保持一致。 (TGT-53652)
* **自定义条件集合现在在[!UICONTROL Recommendations] UI中正确显示。**&#x200B;修复了“推荐”界面中使用自定义条件构建的收藏集无法显示产品结果的问题。 尽管基于属性的标准收藏集按预期工作，但使用自定义筛选器的收藏集返回“未找到结果”，尽管目录匹配有效。 此修复确保使用自定义属性的收藏集现在能够在[!UICONTROL Product]选项卡中正确填充，从而恢复个性化推荐工作流的完整功能。 (TGT-53653)
* **修复了首次打开[!UICONTROL Products]页面时收藏集不显示产品的问题。**&#x200B;访问[!UICONTROL Recommendations]分区中的收藏集的客户在首次打开[!UICONTROL Products]页面时遇到了空的产品结果。 此问题是由于GraphQL查询中的后端错误导致的，该错误无法加载具有自定义标准的集合的产品数据。 问题已得到解决，产品现在可以正确显示，而无需切换环境。 (TGT-53694)
* **修复了在基于表单的[!UICONTROL Recommendations]活动中无法删除收藏集的问题。**&#x200B;使用[!UICONTROL Recommendations]创建[!UICONTROL Form-Based Experience Composer]活动的客户无法取消选择之前选择的收藏集。 UI要求在保存之前选择收藏集，以防用户恢复为“所有收藏集”。 此行为已更新以符合VEC功能，允许客户在没有选定收藏集的情况下进行保存，并按预期默认为“所有收藏集”。 (TGT-53708)
* **修复了由于缺少收藏集或筛选规则值，导致无法按属性设置促销活动的问题。**&#x200B;客户在活动创建过程中按属性配置促销时遇到错误，说明某个促销缺少集合ID或筛选规则值。 即使设置似乎已完成，此验证问题也会阻止进程。 现在，在按属性配置促销活动时，可以成功保存促销活动。 (TGT-53750)
* **修复了由于体验名称重复而无法保存活动的问题。**&#x200B;客户在保存包含特定标准和设计组合的活动时遇到无效的用户输入错误。 即使设置似乎有效，错误也因体验名称重复而触发。 现在可以保存具有不同配置的活动，而不会出现命名冲突。 (TGT-53805)
* **修复了属性配置的促销活动的验证仍然无效的问题。**&#x200B;客户在活动创建过程中按属性设置促销活动时遇到永久性验证错误，即使所有必填字段均已正确填充也是如此。 此问题是由于[!UICONTROL Recommendations]工作流中的验证逻辑不正确导致的。 现在，基于属性的促销活动会按预期进行验证和保存。 (TGT-53811)
* **修复了将促销活动应用于实时[!UICONTROL Recommendations]活动时触发错误的问题。**&#x200B;客户在尝试将前端促销应用于实时[!UICONTROL Recommendations]活动时遇到错误“促销活动缺少集合ID或筛选规则值”，即使提供了有效的配置详细信息后也是如此。 现在可以将促销活动成功应用于实时活动，而不会触发验证错误，从而确保在更新的活动创建UI中实现更顺畅的体验。 (TGT-53738)
* **修复了产品在[!UICONTROL Recommendations] UI中的收藏集中不可见的问题。**&#x200B;来自单个租户的客户报告说在新UI的[!UICONTROL Recommendations]部分中查看某些收藏集时加载产品列表失败。 通过切换环境暂时解决了此问题，但此解决方法会导致用户体验不佳。 现在，产品实体可以始终如一地加载，而无需切换环境。 (TGT-53783)
* **修复了活动创建UI中有一行未显示标准和设计的问题。**&#x200B;以前，活动创建过程中的标准和设计以压缩格式显示，因此客户很难查看和管理各个项目。 现在，每个标准和设计都独立显示，提高了更新后的UI中的可读性和可用性。 (TGT-53818)

+++

**报表**

+++查看详细信息
* **[!UICONTROL Total Revenue]指标现在包含在从活动报表导出的CSV中。**&#x200B;解决了更新的[!UICONTROL Overview] UI中的问题：总收入在活动报表视图中正确显示，但在CSV导出中缺失，显示为$0。 这种差异导致用户无法依赖导出的数据进行离线分析和报告。 (TGT-53325)
* **[!UICONTROL Total Sales]指标现在包含在从活动报表导出的CSV中。**&#x200B;解决了更新后的UI中，[!UICONTROL Total Sales]指标在活动报表视图中正确显示，但CSV导出中缺失的问题。 这种差异导致用户无法访问下载报表中的完整性能数据。 此修复程序确保[!UICONTROL Total Sales]值现在准确地包含在CSV导出中，从而恢复应用程序内报表和离线分析之间的一致性。 (TGT-53330)
* **改进了在未启用量度时[!UICONTROL Graph View]的错误消息传递。**&#x200B;修复了VEC中的一个问题，即在关联的[!UICONTROL Graph View]报表包中未启用所请求的量度时，[!DNL Analytics]显示一般的“出现错误”消息。 此问题是由后端GraphQL响应中的`not_enabled_metric`错误触发的。 此修复用信息更丰富的消息取代了模糊的错误，帮助用户识别[!DNL Analytics]中的配置问题，从而减少混淆和不必要的支持升级。 (TGT-53577)
* **修复了报表持续时间超出支持的90天限制的问题。**&#x200B;在[!UICONTROL Last X Days]部分中使用“[!UICONTROL Reports]”过滤器的客户能够选择超过90天的持续时间，这可能会导致性能问题和数据不完整。 更新了过滤器，强制实施最长90天的范围，以确保一致且可靠的报表。 (TGT-53795)
* **修复了使用默认环境而不是选定环境生成性能CSV报表的问题。**&#x200B;以前，当客户在报表设置中更改环境并生成性能报表时，生成的CSV包含默认环境的数据，而不是选定环境的数据。  UI现在可正确传递`environmentId`参数，从而确保报表反映所选环境。 此外，错误处理已得到改进。 如果在CSV生成期间出现GraphQL错误，则UI现在会显示一条明确的错误消息，而不是生成一个空的CSV文件。 (TGT-53064)
* **修复了Analytics for Target (A4T)报表无法在[!UICONTROL Graph View]中显示数据的问题。**&#x200B;客户将[!DNL Target]与A4T集成一起使用，在A/B测试活动的“报表”选项卡中切换到图形视图时遇到“出现错误”错误。 尽管[!UICONTROL Table View]已正确加载，[!UICONTROL Graph View]仍无法呈现选定时间范围内的量度趋势。 [!UICONTROL Graph View]现在可按预期显示所有受支持量度的性能数据，从而提高更新UI中的可见性和报告准确性。 (TGT-53573)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* **元素元数据现在显示在悬停在痕迹导航菜单中的位置。**&#x200B;改进了VEC中的痕迹导航菜单，当鼠标悬停在项上时，该菜单可显示其他元素详细信息，例如ID、类和名称。 此增强功能可帮助用户在活动设置期间更轻松地识别和区分元素。 (TGT-53409)
* **痕迹导航悬停现在会突出显示VEC中的相应元素。**&#x200B;改进了[!UICONTROL Visual Experience Composer]，在痕迹导航菜单中将鼠标悬停在项上时，突出显示编辑器中的相应元素。 还会显示元素类型，如容器、粗体文本或按钮。 此行为适用于同级元素，并根据验证列表排除不支持的类型，例如SVG。 (TGT-53411)
* **VEC修改工作流中还原了未保存的更改警报。**&#x200B;修复了VEC中的一个问题：当自定义代码修改未保存更改时，用户不再收到相关通知。 与旧版UI不同，新体验在导航离开或关闭个性化编辑器时缺少提示，这会导致意外丢失进度。 此修复程序可恢复所有修改类型（包括自定义代码）的警报，并确保用户在退出时收到警告而不保存。 (TGT-53435)。
* **在VEC的页面刷新期间，自定义代码更改现在持续存在。**&#x200B;修复了VEC中的以下问题：网站刷新期间自定义代码修改丢失。 在多次重新加载的页面上发生此问题，导致编辑器重置并还原未保存的更改。 修复程序可确保自定义代码编辑内容保持不变，即使页面在编辑期间重新加载也是如此，从而防止意外失去进度。 (TTGT-53501)
* **VEC中的网站访问登录问题已得到解决。**&#x200B;修复了用户在通过VEC访问网站时无法登录到网站的问题。 登录流会反复地将用户重定向回登录页面，从而阻止活动设置和预览。 此修复可确保VEC不再干扰登录行为，从而恢复经过身份验证的用户的预期访问权限。 (TGT-53524)
* 在VEC助手扩展中解决了&#x200B;**Cookie复制问题。**&#x200B;修复了[!UICONTROL Adobe Experience Cloud Visual Editing Helper]扩展在通过预览链接进行QA期间复制`at_qa_mode` Cookie的问题。 当手动切换预览索引时，会创建多个具有跨域冲突值的Cookie，从而阻止测试者可靠地切换变量。 甚至在Target UI外部也观察到此行为，它同时影响内部帐户和客户端帐户。 此修复通过防止重复条目并调整域范围来确保一致的Cookie处理，从而允许无缝的变体切换，而无需手动Cookie清理。 (TGT-53579)
* **修复了单击特定主页上的元素导致内存泄漏的问题。**&#x200B;在此主页上创建活动的客户在与页面元素交互时遇到内存泄漏问题。 该问题与过多控制台警告和增加子帧中的内存使用量有关，特别是与格式错误的srcset属性有关。 现在，内存使用在交互过程中保持稳定。 (TGT-53761)
* **修复了VEC崩溃并在加载某些活动时显示空白屏幕的问题。**&#x200B;特定租户的客户报告编辑器无法加载特定活动。 VEC在崩溃并显示空白屏幕之前停留在“应用初始修改”上。 现在，VEC在更新的活动创建过程中加载受影响的活动，而不会出现错误。 (TGT-52932)
* **修复了[!UICONTROL Manage Content]活动中的[!UICONTROL Automated Personalization]边栏显示不一致位置标签的问题。**&#x200B;客户报告[!UICONTROL Manage Content]边栏在[!UICONTROL Experiences]和[!UICONTROL Offers]选项卡中显示不匹配的位置编号。 （例如，体验中的位置2和位置4，以及选件中的位置1和位置2），即使仅配置了两个位置也是如此。 位置标签现在是一致的，并准确地映射到修改，从而提高活动创建过程中的清晰度和可用性。 (TGT-52934)
* **修复了VEC中的修改在保存后丢失的问题。**&#x200B;客户报告，在VEC中保存修改后，页面将刷新并将更改还原到之前的版本。 此问题导致最新更新丢失，除非立即保存整个活动。 现在，修改在保存后会正确保留，并且编辑器不会再意外还原更改，从而确保在活动创建工作流中提供可靠的体验。 (TGT-53500)
* **通过在悬停和选择时显示元素类型，增强了VEC中的元素选择。**&#x200B;为了提高活动创建期间的可用性，VEC现在会在将鼠标悬停在上面或选中时，使用HTML元素的类型对其进行修饰。 此增强功能可帮助客户更轻松地识别和选择正确的元素。 选定的元素以不同的颜色突出显示，悬停的元素以蓝色列出。 元素类型也会显示，在编辑过程中提供更清晰的上下文。 (TGT-53502)

+++

## 数据流更新（2025年9月19日）

数据流ID和沙盒组合对于[!DNL Adobe Target]目标连接必须是唯一的。

更新了[!DNL Target]目标连接的验证逻辑，以强制数据流ID和沙盒名称的组合在IMS组织中必须是唯一的。这意味着：

* 无法在多个[!DNL Target]目标连接中重用相同的数据流ID +沙盒名称对。
* 同一数据流ID只能用于不同的连接，前提是它们是在不同的沙盒中配置的。
* 此规则适用于所有数据流选择，包括选择“无”时。

此更新可确保配置的一致性，并防止在多沙盒环境中发生冲突。 有关详细信息，请参阅[Adobe Target目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank}指南中的&#x200B;*Experience Platform连接*。

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
