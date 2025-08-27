---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 7%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月27日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.4（2025年8月28日）

此版本包含以下更新和修复：

**[!UICONTROL Activities]**

+++查看详细信息
* **修复了在活动创建过程中，计划活动在更新的UI中错误显示“[!UICONTROL Live]”状态的问题**：具有未来激活日期的活动现在正确显示“[!UICONTROL Scheduled]”状态。 (TGT-53187)
* **在页面刷新之前，计划的活动错误地显示[!UICONTROL Live]状态**：客户报告说，在计划活动在未来日期和时间上线时，状态最初显示为[!UICONTROL Live]，而不是[!UICONTROL Scheduled]。 这会导致混淆，尽管确认消息指示了正确的计划行为。 活动状态现在在保存后立即准确反映[!UICONTROL Scheduled]，无需刷新页面。 (TGT-52937)
* **对重复体验的更改无意中影响了原始体验**：客户报告说，在活动内复制体验并分配新受众时，对复制的体验所做的任何更改（例如设计或标准）也会反映在原始体验中。 这会阻止创建独立的变体，并影响生产工作流。 现在，可以独立编辑复制的体验，而不会影响原始版本。 (TGT-53361)
* **修复了由于`InvalidProperty.Json`错误而导致客户无法保存活动的问题**：以前，客户在尝试保存活动而不进行更改时遇到“无效用户输入”错误。 该错误是由于JSON有效负载中无法识别的属性名称“content”导致的。 此问题已得到解决，现在可以在更新后的UI中成功保存活动，即使未进行任何修改也是如此。 (TGT-53513)

+++

**Analytics for Target (A4T)**

+++查看详细信息
* **创建A4T活动时无法键入报表包名称**：在更新的UI中选择[!UICONTROL Report Suite]作为报表源时，客户无法在[!UICONTROL Analytics]下拉菜单中键入。  此问题使得难以找到特定的报表包，尤其是对于列表较多的组织。 下拉列表现在支持按名称键入和搜索，从而提高活动创建过程中的效率。 (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++查看详细信息
* **即使在删除之后，过期的“期限”受众也阻止保存活动**：以前，如果某个活动之前包含过期的“期限”受众，则客户无法保存该活动，即使删除了某个受众也是如此。 此问题是由对仅限该活动的受众的延迟验证导致的，该验证将继续触发错误。 删除过期受众后，现在即可按预期保存活动。 (TGT-53517)
* **保存活动后，其他页面和多个受众消失**：以前，在活动创建过程中创建[!UICONTROL A/B Test]活动的客户在保存后会丢失已配置的其他页面和多个受众。 此行为是意外行为，并在设置期间导致混淆。 现在，在保存活动后，这些配置会正确保留。 (TGT-52357)

+++

**决策优惠**

+++查看详细信息
* **无法在更新的VEC中编辑决策优惠或选择特定页面元素**：客户在更新的UI中遇到多个问题，这些问题阻止他们更新现有活动或创建新活动：

   * 决策选件显示为HTML选件有误，导致无法进行编辑。
   * 无法在VEC中选择特定页面元素。
   * 编辑期间所做的更改未保存。
   * 某些区域URL无法在VEC中正确加载，需要手动Cookie调整。

  客户现在可以编辑决策优惠、准确选择页面元素并按预期保存更改。 区域页面也会在VEC中正确加载。 (TGT-53425)

* **保存后无法修改和意外更改优惠决策选择器**：客户报告说，在更新的UI中应用优惠决策时，无法更改选择器的默认值。 尝试修改选择器（例如，`#tf-cq-hr or body`）的操作已被忽略，在保存活动后，选择器被替换为通用值，如`#cdq_element_0`。 此问题导致选件从可视化体验编辑器(VEC)中消失，并阻止进一步编辑。 客户现在可以根据需要修改优惠决策选择器，并且保存的选择器会正确保留，而不会发生意外更改。 (TGT-53433)
* **保存后，优惠决策从活动中消失**：客户报告说，在保存活动后，应用于更新UI中页面元素的优惠决策不再可见。 在某些情况下，选择器发生了意外更改，并且在重新编辑时无法在VEC中呈现选件。 现在，优惠决策在保存后可正确保留，并且选择器保持稳定，从而确保优惠可按预期显示和编辑。 (TGT-53434)

+++

**体验片段**

+++查看详细信息
* **客户在使用[!UICONTROL Experience Fragments]或[!UICONTROL Insert Before]插入[!UICONTROL Insert After]**&#x200B;时收到错误：客户在尝试使用更新的UI中的[!UICONTROL Experience Fragments]或[!UICONTROL Insert Before]选项将[!UICONTROL Insert After]插入到活动中时遇到错误。 显示的错误消息为：

  “选件内容必须正好包含一个HTML元素。”

  此问题特定于更新后的UI，而在以前的版本中未出现。 现在已解决该问题，客户可以成功插入[!UICONTROL Experience Fragments]，而不会遇到此错误。 (TGT-53432)

* **将[!UICONTROL Experience Fragment]添加到活动时的错误消息**：以前，尝试使用[!UICONTROL Experience Fragment]或[!UICONTROL Insert Before]选项插入[!UICONTROL Insert After]的客户遇到错误：“选件内容必须正好包含一个HTML元素。” 尽管片段有效并被旧版UI接受（包括支持此配置的切换），但出现此错误。 问题已在更新的VEC中解决。 (TGT-53442)

+++

**本地化**

+++查看详细信息
* **[!UICONTROL Goals & Settings]步骤中的Toast消息未本地化**：以前，客户在活动创建过程中的[!UICONTROL Objective]字段中输入不支持的字符（如表情符号）时，会遇到未本地化的快显通知消息。 Toast消息现在已正确本地化了所有受支持的语言，从而确保为全球客户提供一致且易于访问的体验。 (TGT-52251)
* **[!UICONTROL Create Audience]对话框中的字符串未本地化**：以前，配置时间范围属性时，[!UICONTROL Create Audience]模式中显示消息“为‘不重复’选择至少起始日期或结束日期”未本地化。 该字符串现已正确本地化为全部支持的语言，从而确保在[!UICONTROL Audiences]工作流中为全球客户提供一致的体验。 (TGT-52253)
* **[!UICONTROL Create Audience]对话框中的工具提示未本地化**：以前，当客户在受众名称字段中输入不支持的字符（如表情符号）后将鼠标悬停在错误工具提示上时，工具提示显示为未本地化。 工具提示现在可以跨所有支持的语言正确显示本地化的消息传递，从而确保在[!UICONTROL Audiences]工作流中保持一致和可访问的体验。 (TGT-52254)

+++

**[!DNL Recommendations]**

+++查看详细信息
* **无法在实时活动中禁用[!UICONTROL Front Promotion]**：修复了客户无法使用更新的UI在实时活动中禁用[!UICONTROL Front Promotion]的问题。 在活动创建过程中对促销部分所做的更改现在会按预期保留，从而确保[!UICONTROL Product Catalog Search]中实时活动的准确配置。 (TGT-53231)
* **编辑复制的体验的推荐会影响原始体验**：客户报告说，在活动内复制体验并修改副本中的推荐设计或标准时，这些更改无意中应用于原始体验。  此问题阻止创建独立的变体，并中断更新后的活动创建过程中的预期行为。 现在，可以独立编辑复制的体验，而不会影响原始版本。 (TGT-53369)
* **在[!UICONTROL Recommendations]选项卡中编辑收藏集或排除项时无法查看产品列表**&#x200B;以前，按应用规则过滤的产品列表在编辑模式中不可见，因此客户很难确认包括或排除哪些产品。 现在，修改规则时，产品列表可正确显示并实时更新，从而提高更新的[!DNL Recommendations] UI中的可见性和可用性。 (TGT-53481)
* **更新了[!UICONTROL View Details]选项卡中[!UICONTROL Recommendations]对话框的布局**：以前，[!UICONTROL View Details]对话框缺少清晰的结构，这使得客户难以访问特定于项目的信息和与库存相关的信息。 布局已更新为包含两个选项卡：一个选项卡显示选定项目的详细信息，第二个选项卡显示按集合或排除项的当前规则过滤的库存。 此项改进增强了更新[!DNL Recommendations] UI中的清晰度和可用性。 (TGT-53503)
* **客户无法在[!UICONTROL Goals & Settings]下拉列表中搜索报表包**：以前，活动创建过程的[!UICONTROL Goals & Settings]部分中的报表包下拉列表不支持用于搜索的文本输入，这使得具有大量报表包的客户难以找到正确的报表包。 旧版UI中提供的此功能已恢复。 客户现在可以更高效地键入以搜索和选择报表包。 (TGT-53514)
* **客户无法在[!DNL Recommendations] UI中下载自定义标准CSV**：以前，单击[!UICONTROL Recommendations]选项卡中自定义标准CSV的下载链接时返回404错误，无法在新选项卡中打开。 现在，下载链接将在新选项卡中打开，并正确提供CSV文件，从而提高管理自定义标准的客户的辅助功能和可用性。 (TGT-51966)
* **在没有输入数据的情况下启用[!UICONTROL Recommendations]促销活动会触发一般错误消息**：以前，在“推荐”活动中未指定必填字段而启用前端或后端促销活动的客户遇到代码为`error.restapi.missingFields`的模糊“输入错误无效”。 系统现在提供明确和可操作的错误消息，指示缺少哪些字段，从而提高可用性并减少活动创建过程中的混淆。 (TGT-52616)
* **在[!UICONTROL Catalog Search]**&#x200B;中加载的产品缩略图和图像不一致：客户报告[!UICONTROL Catalog Search]中的产品缩略图和全尺寸图像间歇性地丢失或损坏，尤其是在导航或修改列可见性之后。 现在，无论列设置或导航行为如何，缩略图和图像都能可靠地加载，从而改善了[!UICONTROL Recommendations]工作流中的整体体验。 (TGT-52778)
* **无法在[!UICONTROL Designs]环境中创建[!UICONTROL Criteria]和[!UICONTROL Stage]**：客户尝试在[!UICONTROL Designs]环境的[!UICONTROL Criteria]选项卡中创建[!UICONTROL Recommendations]或[!UICONTROL Stage]时遇到“用户输入无效”错误。 客户现在可以在[!UICONTROL Designs]环境中成功创建[!UICONTROL Criteria]和[!UICONTROL Stage]，而不会出现错误。 (TGT-53205)
* 保存&#x200B;**[!UICONTROL Promotions]后未从[!UICONTROL Recommendations]活动中删除**：客户报告说，即使删除并保存了促销活动，添加到[!DNL Recommendation]活动的促销活动仍继续出现。 此问题会影响暂存环境和生产环境，并在多次保存尝试期间持续存在。 现在，促销活动可正确反映在更新后的活动创建流程中进行活动编辑期间所做的更改。 (TGT-53490)

+++

**[!UICONTROL Reports]**

+++查看详细信息
* **[!UICONTROL Automated Segments]在活动报表**&#x200B;中显示了null受众：客户发现，在活动的[!UICONTROL Automated Segments]部分中查看[!UICONTROL Reports]时，受众字段显示为null，即使需要有效的区段数据。 此问题会影响受众定位和报告准确性的可见性。 [!UICONTROL Automated Segments]现在可以在活动报表中正确显示关联的受众信息。 (TGT-52793)
* **无法以CSV格式下载活动报告**：尝试从[!UICONTROL Reports]选项卡导出活动报告的客户在选择CSV下载选项时遇到失败。 此问题会影响标准报表和订单详细信息导出。 现在可以正确下载CSV格式的报表。 (TGT-53464)

+++

**单页应用程序(SPA)**

+++查看详细信息
* **在[!UICONTROL Browse]和[!UICONTROL Design]模式之间切换将重置Web编辑器中的单页应用程序(SPA)状态**：客户报告说，在VEC中的[!UICONTROL Browse]和[!UICONTROL Design]模式之间切换导致Web编辑器重新加载，重置SPA状态并中断活动创建过程。 现在，编辑器会在切换模式时保留SPA导航状态，从而确保更顺畅、更一致的编辑体验。 (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++查看详细信息
* **在导航到[!UICONTROL Automated Personalization]步骤并返回后，[!UICONTROL Multivariate Test] (AP)或[!UICONTROL Targeting] (MVT)活动中的位置重命名操作不持久。**&#x200B;客户现在可以成功编辑和保存位置名称，并且更改在整个活动创建过程中保持可见。 (TGT-52367)
* **在[!UICONTROL Stage]环境中的租户上显示的旧版VEC UI**：修复了访问[!UICONTROL Stage]环境中的某些租户时，未正确显示旧版UI而非更新的VEC的问题。 此问题可在多个登录路径中重现并影响[!UICONTROL Activities]部分。 更新后的UI现在可以在[!UICONTROL Stage]环境中正确显示两个租户。 (TGT-52261)
* **选择背景颜色导致页面在更新的VEC中崩溃**：
修复了在更新的VEC中从[!UICONTROL Style]面板中选择背景颜色导致页面崩溃并变为空白的问题。 控制台错误表示无法从未定义的元素中读取属性，特别是与`querySelector`相关的属性。 客户现在可以安全地选择背景颜色，而不会触发崩溃。 (TGT-53561)
* **由于无效的用户输入错误，无法保存活动**：修复了尝试在更新的VEC中保存现有活动时的错误。 该错误仅在编辑过程中出现，而不是在使用同一属性创建新活动时出现。 错误消息包括：

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  现在，使用受影响属性的活动可在编辑后成功保存。 (TGT-53507)

* **透明图像在更新的VEC中不再包含“fmt=png-alpha”参数**：客户报告说，在更新的UI中替换图像时，不再保留透明背景。 更新后的VEC生成的图像URL忽略了`fmt=png-alpha`参数，该参数以前确保旧UI中的透明度。 更新后的UI现在可正确附加透明图像的`fmt=png-alpha`参数，以恢复预期的渲染行为。 (TGT-52615)
* **如果不添加两个位置，客户就无法继续到AP活动中的定位部分**：在更新的UI中创建[!UICONTROL Automated Personalization] (AP)活动的客户无法继续到“定位”部分，除非添加了两个位置。 此行为与以前的UI不同，在以前的UI中，单个位置就足够了。 对于希望仅使用一个位置的客户，该问题会阻止其创建和保存活动。 客户现在可以在单个位置继续定位和保存AP活动，从而恢复预期的功能。 (TGT-53426)
* **切换体验时，工作区中重复的HTML选件**：以前，客户在体验之间切换后，将HTML选件插入工作区中体验过重复的内容。 此问题还会导致工作区变为不可滚动，从而影响可用性。 HTML选件不再重复，并且在更新的VEC中切换体验时，工作区保持可滚动状态。 (TGT-53487)
* **手动更新CSS选择器导致VEC屏幕变为空白**：客户报告说，在VEC中编辑选件时，手动更新CSS选择器会触发空白屏幕，即使选择器有效并显示在页面上也是如此。 现在，在活动创建过程中手动更新选择器时，VEC屏幕会保持稳定。 (TGT-53553)
* 在&#x200B;**中选择“指定的日期和时间”时，“开始日期”字段中的[!UICONTROL Goals & Settings]**&#x200B;截断问题：在活动创建期间，在[!DNL Start date]页面的持续时间部分中选择指定的日期和时间选项时，客户在[!UICONTROL Goals & Settings]字段遇到截断问题。 现在，完整的日期和时间可在支持的区域设置中正确显示。 (TGT-47843)
* 在&#x200B;**边栏中最小化浏览器时，[!UICONTROL Manage Content]筛选器图标消失**：客户报告，在调整浏览器窗口大小或最小化浏览器窗口时，[!UICONTROL Manage Content]活动创建流的[!UICONTROL Automated Personalization]边栏中的筛选器图标消失。 过滤器图标现在保持可见和可访问，而不管浏览器大小如何，从而提高所有屏幕分辨率的可用性。 (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++查看详细信息
* **仅限单个工作区的客户可以从其他工作区查看活动**：仅限特定工作区访问的客户仍然能够在更新的UI中选择[!UICONTROL All Workspaces]，并可以从其他工作区查看活动。 此行为可能会对超出其分配范围的实时活动造成意外更改。 Workspace限制现在已正确实施，客户只能在其分配的工作区内查看活动。 (TGT-53101)
* **客户可以在[!UICONTROL Default Workspace]中查看没有访问权限的活动**：客户可以在[!UICONTROL Default Workspace]中查看活动，尽管没有访问权限。 Workspace权限现在可以在更新后的UI中正确实施，从而确保客户只能看到与其分配的工作区关联的活动。 (TGT-53297)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
