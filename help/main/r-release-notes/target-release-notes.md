---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 7%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月21日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.3（2025年8月21日）

此版本包含以下更新和修复：

**[!UICONTROL Activities]**

+++查看详细信息
* **修复了保存活动时由于属性数据的格式错误而触发无效用户输入错误的问题**：客户在尝试保存现有活动时遇到严重错误。 错误消息指示无效的用户输入，特别是引用了JSON有效负载中无法识别的属性名称内容。 特别要注意的是，使用相同资产的新活动已成功保存，这表示问题被隔离到旧活动数据中。 活动创建过程现在可以正确处理旧版属性配置，防止出现无效输入错误，并确保新活动和现有活动之间具有一致的保存行为。 (TGT-53507)
* **修复了由于InvalidProperty.Json错误而导致客户无法保存活动的问题**：客户尝试在更新的UI中保存活动时遇到错误，即使未进行任何修改也是如此。 错误消息指示无效的JSON结构：“无效的Json。 无法识别的属性名称“content”。 位置：行 — 1，列 — 432。” 此问题由请求有效负载中的无法识别的属性引起，现已得到解决。 客户可以成功保存活动，而不会遇到此错误。 (TGT-53513)
* **修复了在页面刷新之前计划活动错误地显示[!UICONTROL Live]状态的问题**：客户发现，在计划活动在未来日期和时间上线时，状态立即显示为[!UICONTROL Live]，而不是[!UICONTROL Scheduled]。 这会导致混淆，即使确认消息正确指示已计划活动。 刷新页面更正了状态显示。 此问题现已得到解决，计划的活动可正确显示计划状态，而无需刷新。 (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++查看详细信息
* **修复了在活动创建过程中客户无法键入报表包名称的问题**：在活动创建过程中使用[!DNL Adobe Analytics]作为报表源的客户无法键入到[!UICONTROL Report Suite]下拉列表中以搜索特定的报表包。 这会影响具有大量报表包的组织的工作流，在这些报表包中，手动滚动会显着延迟设置。 下拉列表未按字母顺序排序，并且未始终响应键入的输入，因此很难找到“Office + Store - Web - Prod”等报表包。 此问题已得到解决，客户现在可以通过键入报表包名称来高效搜索。 (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++查看详细信息
* **修复了过期的“期限”受众阻止活动保存的问题，即使在删除后也是如此**：由于与过期的“期限”受众相关的错误，客户无法在更新后的UI中保存活动。 即使删除了受影响的受众之后，仍存在错误消息：“活动包含具有无效时间范围的受众。” 出现此问题的原因是系统继续验证仅限该活动的受众，即使该受众不再使用也是如此。 时区差异使这种行为更加复杂。 验证逻辑已更正，客户现在可以在保存活动时不会遇到此错误。 (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++查看详细信息
* **修复了阻止客户在UI中使用[!UICONTROL Insert Before]或[!UICONTROL Insert After]插入体验片段的问题**&#x200B;客户在尝试在更新的UI中使用“此项前插入”或“此项后插入”选项将[!UICONTROL Experience Fragments]插入到活动中时遇到错误。 显示的错误消息为：“选件内容必须正好包含一个HTML元素。” 此问题特定于更新后的UI，而在以前的版本中未出现。 此问题现已得到解决，客户可以成功插入[!UICONTROL Experience Fragments]，而不会遇到此错误。 (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++查看详细信息
* **修复了阻止客户在更新的UI中编辑决策优惠和选择特定页面元素的问题**：在更新的活动创建流程中，客户无法在可视化体验编辑器(VEC)中编辑现有决策优惠或选择特定页面元素。 决策优惠显示为HTML优惠不正确，编辑期间所做的更改未保存。 此外，某些区域URL（如日本站点）无法在VEC中正确加载，阻止活动创建和更新。 决策优惠现在可正确显示，页面元素可按预期选择，并且区域URL可在VEC中正确加载，从而恢复完整的编辑功能。 (TGT-53425)
* **修复了在保存之后[!UICONTROL Offer Decision]选择器无法修改和意外更改的问题**：在更新的活动创建过程中，客户无法按预期修改[!UICONTROL Offer Decision]选择器。 尝试更改选择器失败，选择器在保存后恢复到不正确的值。 此行为导致决策选件从可视化体验编辑器(VEC)中消失，阻止进一步编辑。 现在，选择器更改会正确保留，并且决策选件在保存之后在VEC中保持可见和可编辑状态。(TGT-53433)
* **修复了保存[!UICONTROL Offer Decisions]后**&#x200B;从活动中消失的问题：在活动创建过程中添加的[!UICONTROL Offer Decisions]在保存并重新打开活动后未保留。 在编辑动态内容并使用特定选择器和属性插入[!UICONTROL Offer Decisions]时，出现此问题。 [!UICONTROL Offer Decisions]在保存后现在可正确保留，而选择器将保持不变，从而确保定位和编辑行为保持一致。 (TGT-53434)

+++

**[!DNL Recommendations]**

+++查看详细信息
* **修复了[!DNL Recommendations] UI中的自定义标准CSV下载返回404错误的问题**：修复了客户无法在活动创建过程中下载自定义标准CSV的问题。 现在，下载链接可以正常运行，允许客户按预期导出自定义标准。 (TGT-51966)
* **修复了[!UICONTROL Catalog Search]**&#x200B;中图像加载不一致的问题：修复了[!UICONTROL  Catalog Search]中的缩略图和图像在活动创建过程中加载不一致的问题。 除非“缩略图URL”列可见，并且某些产品图像在导航或搜索操作后已加载部分或完全未加载，否则图像无法显示。 图像加载行为已稳定，并且无论列可见性或导航操作如何，缩略图现在都可以可靠地显示。 (TGT-52778)
* **修复了在复制的体验中编辑推荐会影响原始体验的问题**：客户报告在复制的体验中修改推荐无意中更改了原始体验。 具体而言，在活动创建过程中复制体验B并编辑其设计或标准后，相同的更改会反映在原始体验B中，尽管它们是单独的实体。 重复的体验现在会维护单独的配置，确保对一个体验的编辑不会影响原始体验。 (TGT-53369)
* **修复了对重复体验的更改无意中影响活动中原始体验的问题**：客户报告说，在活动中复制体验并分配新受众时，对复制体验的设计或标准所做的任何更改也会反映在原始体验中。 即使没有直接对原始版本进行任何编辑，也会发生此问题，这影响了在同一活动中创建独立变体的能力。 现在，活动创建过程可正确隔离重复的体验，确保对一个体验所做的编辑不会影响原始体验。 (TGT-53361)
* **修复了[!UICONTROL Recommendation Catalog]间歇性地无法显示完整产品属性数据的问题**：在更新的[!DNL Recommendations] UI中，客户遇到了[!UICONTROL Catalog Search]结果中无法一致显示某些产品属性（如消息）的问题，即使馈送中存在数据也是如此。 此问题要求客户手动重新配置列可见性以检索缺少的值。 [!UICONTROL Catalog Search]现在可靠地显示所有已配置的属性，无需手动重置列。 (TGT-52769)
* **修复了无法在实时活动中禁用[!UICONTROL Front Promotion]的问题**：未保存尝试在实时活动中禁用[!UICONTROL Front Promotion]。 选择[!UICONTROL Change Promotion]并禁用它后，在重新编辑活动时促销活动保持活动状态，从而阻止更新推荐配置。 促销活动设置现在可正确保存，这样客户就可以按预期禁用或修改实时活动中的促销活动。 (TGT-53231)
* **修复了在启用不带数据的[!DNL Recommendations] [!UICONTROL Promotion]时触发不明确的错误消息的问题**：在[!UICONTROL Front]活动中启用[!UICONTROL Back Promotion]或[!DNL Recommendations]而不指定所需值会导致泛型“输入错误无效”消息。 基础问题是缺少配置字段，但错误消息未明确说明原因，因此难以进行故障诊断。 现在，活动创建流程可在必填字段（如`collectionId`或规则）缺失时提供明确且可操作的错误消息，帮助客户快速识别并解决配置问题。 (TGT-52616)
* **修复了导致[!UICONTROL Product]列表无法在[!UICONTROL Edit]选项卡[!UICONTROL Recommendations]的**&#x200B;模式中显示的问题：在[!UICONTROL collection]选项卡中编辑[!UICONTROL exclusion]或[!UICONTROL Recommendations]时，客户无法查看筛选的产品列表。 该列表应基于应用的规则实时更新，但似乎未按预期进行。 此问题已得到解决，产品列表现在可正确显示，并且随着规则的修改而动态更新。 (TGT-53481)
* **修复了更新的UI中“查看详细信息”对话框的布局问题**：更新的UI中的“查看详细信息”模式布局已修改，以提高清晰度和可用性。 该对话框现在包含两个选项卡：
   * [!UICONTROL Details]选项卡：显示选定项目的所有相关信息。
   * [!UICONTROL Inventory]选项卡：显示按当前集合和排除规则过滤的所有产品。

  此增强功能可帮助客户更轻松地在活动创建过程中导航和了解特定于项目的数据和库存上下文。 (TGT-53503)

   * **修复了在保存后推荐活动中移除的促销重新显示的问题**：客户报告说，当[!UICONTROL front]活动中移除[!UICONTROL back]或[!DNL Recommendations]促销并保存该活动时，重新打开时促销会继续显示。 此问题在暂存环境和生产环境中都发生，并影响更新的活动创建过程。 问题已得到解决。 现在，从活动中移除的促销活动在保存后可正确保留。 (TGT-53490)

+++

**报表**

+++查看详细信息
* **修复了[!UICONTROL Automated Segments]报表显示null受众值的问题**：客户报告活动报表中的[!UICONTROL Automated Segments]显示受众数据为null，从而无法准确分析区段性能。 在访问[!UICONTROL Reports]部分并选择[!UICONTROL Automated Segments]时，即使需要有效的受众数据，也会发生此问题。 [!UICONTROL Automated Segments]现在可正确显示受众值，从而确保获得可靠的报表和分段见解。 (TGT-52793)

+++

**单页应用程序(SPA)**

+++查看详细信息
* **修复了在更新的UI中在[!UICONTROL Browse]和[!UICONTROL Design]模式之间切换重置SPA状态的问题**：客户报告了在更新的UI中在[!UICONTROL Browse]和[!UICONTROL Design]模式之间切换导致Web编辑器重新加载，重置了SPA的状态。 此问题会中断工作流，并要求客户重新输入信息。 问题已得到解决。 现在，在模式之间切换时，会保留SPA状态，以确保在活动创建期间获得更顺畅且一致的体验。 (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++查看详细信息
* **修复了活动创建过程中阻止升级到AP活动中的[!UICONTROL Targeting]步骤的问题**：修复了活动创建过程中客户无法继续到[!UICONTROL Targeting] (AP)活动中的[!UICONTROL Automated Personalization]步骤的问题（除非添加了两个位置）。 此行为与以前的体验不同，在以前的体验中，具有多个选件的单个位置便已足够。 该要求已得到纠正，允许客户继续将单个位置设置作为其AP工作流的一部分。 (TGT-53426)
* **修复了新活动创建进程未为透明图像设置fmt=png-alpha参数的问题**：在更新的UI中，在活动创建进程中插入的图像默认不再包含`fmt=png-alpha`参数，从而导致透明度丢失。 此行为与以前的UI不同，后者自动将参数附加到图像URL，并保留透明背景。 在需要透明度时，活动创建过程现在可正确地将`fmt=png-alpha`参数应用于图像URL，从而确保透明资产的一致呈现。 (TGT-52615)
* **修复了阻止客户在更新的UI中搜索报表包的问题**：在更新的UI中，[!UICONTROL Report Suites]部分中的[!UICONTROL Goals & Settings]下拉列表不允许客户键入和搜索，这使得难以找到特定的报表包，尤其是对于具有大量条目的租户。 与以前的UI不同，列表未排序，缺少基于输入的筛选。 此问题已得到解决。 客户现在可以键入以搜索和筛选报表包，从而恢复旧版UI中提供的功能。 (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++查看详细信息
* **修复了以下问题：在活动创建过程中选择**&#x200B;时，受限于单个工作区的客户可以查看来自其他工作区的活动[!UICONTROL All Workspaces]：受限于一个工作区的客户意外地可以查看所有工作区的活动。 此可见性可能会对其他工作区中的实时活动造成意外更改，从而可能影响网站性能。 Workspace访问控制已得到增强，以确保客户只能查看其分配的工作区中的活动并与之交互。 (TGT-53101)
* **修复了以下问题：客户在没有访问权限的情况下可以从[!UICONTROL Default Workspace]查看活动：**&#x200B;只有暂存工作区访问权限的客户能够通过活动创建流程从[!UICONTROL Default Workspace]查看活动。 尽管后端配置和访问权限正确，仍会发生此行为。 Workspace访问控制已得到增强，以确保客户只能在其分配的工作区内查看活动。(TGT-53297)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
