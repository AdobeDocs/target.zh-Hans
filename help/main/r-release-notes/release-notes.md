---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f00cec3194863bb7187d4cdc91c39a87b624e9bd
workflow-type: tm+mt
source-wordcount: '4816'
ht-degree: 11%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的主要功能亮点：

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

## [!DNL Target Standard/Premium] 25.7.4（2025年8月1日）

此版本解决了最近的问题（主要由复杂的客户自定义引起），并包括以下修复和改进：

**活动**

+++查看详细信息
* 修复了客户在尝试保存实时活动（即使未进行更改）时遇到“用户输入无效”错误的问题。 GraphQL响应指示重复的LocalId问题。 (TGT-53329和TGT-53373和TGT-53195)
* 修复了阻止在更新的VEC中创建重定向体验的问题。 已忽略重定向URL，而是显示原始页面。 (TGT-53306)

+++

**本地化**

+++查看详细信息
* 修复了[!UICONTROL Create Criteria]模式中的本地化问题，在[!UICONTROL Choose Price Rule]下拉列表中选择“在以下值之间”选项时，[!UICONTROL Inclusion Rules]部分中的字符串“to”未本地化。 (TGT-49754)
* 修复了源创建向导的[!UICONTROL All host groups]下拉列表中的字符串“[!UICONTROL Environment]”未正确本地化的问题。 (TGT-46737)

+++

**QA**

+++查看详细信息
* 修复了QA环境无法跨多个选项卡加载数据，从而导致界面不可用的问题。 (TGT-53377)
* 修复了阻止在QA环境中创建活动的问题。 进程被重定向到[!UICONTROL Activities]页面而不是成功完成。 (TGT-53328)

+++

**推荐**

+++查看详细信息
* 修复了在[!DNL Recommendations]中创建收藏集时将鼠标悬停在“深度学习”操作数上导致页面崩溃的问题。 (TGT-53305)
* 修复了在更新的UI中[!UICONTROL Catalog Search]中的筛选器建议不准确的问题。 (TGT-52007)
* 修复了[!DNL Recommendations] UI中的一个问题：使用“value present”或“value not present”运算符时，出现操作数过滤器，不过应隐藏该问题。 (TGT-53012)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* 修复了在编辑Automated Personalization (AP)活动时，当用户单击[!UICONTROL Manage Content]然后单击[!UICONTROL Done]时，页面变为空白且无响应的问题。 （TGT-53047 和 TGT-52993）
* 修复了在[!UICONTROL Viewed an mbox]下选择[!UICONTROL Goals & Settings]转化量度导致页面崩溃的问题。 （TGT-53346、TGT-53343 和 TGT-53348）
* 修复了[!UICONTROL Redirect to URL]功能无法按预期工作的问题，即使URL有效，也不会进行重定向。 (TGT-53307)

+++

**工作区**

+++查看详细信息
* 修复了在工作区之间复制活动时导致重复的“受众复制”条目和ID冲突的问题。 现在，复制受众时会包含唯一ID、工作区上下文以及组合受众（最多5个级别）的递归处理。 (TGT-53081)
* 修复了当工作区设置为“[!UICONTROL All Workspaces]”时，复制默认工作区中已存在的活动会导致错误的问题：

  “对于非默认工作区，应至少包含一个属性。”

  由于副本位于默认工作区中，因此不需要属性。 尝试添加属性并保存会导致第二个错误：

  “无效的用户输入”

+++

## [!DNL Target Standard/Premium] 25.7.3（2025年7月24日）

由于最近发现的问题（主要与复杂的客户自定义相关），此版本包含以下修复和更新：

**活动**

+++查看详细信息
* 修复了Builder类中的`buildViews`方法不正确地将`viewMaxLocalId`设置为视图总计数而不是分配的最高值`viewLocalId`的问题。 (TGT-53207)
* 修复了更新的[!DNL Target] UI中的一个问题，该问题导致[!UICONTROL Automated Personalization] (AP)活动中删除的选件显示为`Deleted option with ID: X`，而不是其原始名称（例如，旧版UI中显示的`Offer Name [Deleted]`）。 此修复恢复了已删除选件的有意义的标签设置，提高了清晰度并使报告更准确、更便于用户使用。 (TGT-52921)
* 修复了由于先前修复的同步错误，某些从[!DNL Target]前端迁移到[!DNL Target]中央的活动存在量度配置不一致的问题。 具体而言，最初使用转化量度且后来更新为基于Analytics的量度的活动在`primaryMetricType`和`successCriteria`字段中保留过时的值。 (TGT-52643)
* 修复了由于HTML修改中意外包含`contentEditable`属性而导致QA预览页面的整个内容变为可编辑的问题。 这允许用户单击并编辑页面上的任何文本，这可能会导致在QA期间出现布局问题和混淆。 (TGT-53247)
* 修复了将修改从[!DNL Page Load]移动到[!UICONTROL View]导致修改重复的问题，该问题保留在[!UICONTROL Page Load]中，同时出现在[!UICONTROL View]中。 此外，从[!UICONTROL View]中移除修改也会错误地从[!UICONTROL Page Load]中移除它。 (TGT-53270)

+++

**API**

+++查看详细信息
* 修复了后端持久层中的一个问题：已删除的选项已正确存储，但无法通过现有API端点访问。 因此，前端应用程序无法为已删除的选项检索有意义的名称，从而影响历史报表视图。 此修复程序现在确保保留的已删除选项数据能够在UI中正确显示。 (TGT-52973)
* 实施了一个新的迁移终结点，以支持将已删除的活动选项从基于JCR的活动传输到[!DNL Target]中心。 此功能支持跨系统的一致跟踪和报告。 此功能可确保在[!DNL Target]前端和后端之间保留并同步已删除的选项，从而提高历史报表和数据完整性。 (TGT-53217)
* 引入了一个新的API端点，该端点允许用户从辅助数据库恢复以前删除的活动选项。 此功能利用`RemovedCampaignElements`和`RemovedOptionInfo`类提供的现有基础结构，确保已删除的选项无缝地重新整合到活动中。 (TGT-52903)
* 修复了由于API限制而无法打开或编辑度量名称长度超过25个字符的[!DNL Recommendations]活动的问题。 此修复确保与超出字符限制的量度名称兼容，从而恢复对受影响活动的完全访问权限。 (TGT-52839)

+++

**Form-Based Experience Composer（基于表单的体验编辑器）**

+++查看详细信息
* 修复了在创建或编辑[!UICONTROL Form-Based Experience Composer] (AP)活动时，在&#x200B;**[!UICONTROL Manage Content]**&#x200B;中单击![图标（ ](/help/main/assets/icons/Experience.svg)管理内容图标[!UICONTROL Automated Personalization]）后导致编辑器崩溃的问题。 (TGT-53047)

+++

**推荐**

+++查看详细信息
* 修复了一个问题，该问题导致[!UICONTROL Catalog Search]在滚动到列表底部时无法加载其他结果，从而恢复与旧版UI一致的行为。 (TGT-53088)
* 修复了阻止从[!UICONTROL Criteria Details]对话框中删除项目的问题。 (TGT-53245)
* 修复了导致无法打开或无法与无名称的产品交互的问题。 选择返回未命名结果的环境时，出现此问题，导致无法访问产品详细信息。 (TGT-53007)
* 修复了在选择某些产品时导致[!UICONTROL Catalog Search]页面崩溃并显示空白屏幕的问题。 (TGT-53087)
* 修复了用户无法在[!DNL Recommendation]用户界面中编辑site_cart_z1 [!DNL Target]活动的问题。 尝试打开活动在[!UICONTROL Overview]页面上触发了一个错误，阻止了对编辑器的访问。 (TGT-53221)

+++

**报表**

+++查看详细信息
* 修复了在将报告源从[!DNL Customer Journey Analytics]或[!DNL Analytics]切换到[!DNL Target]时未清除活动数据库中的沙盒字段的问题。 以前，UI正确发送沙盒：null，但后端忽略此值，保留过时的沙盒数据。 现在，在收到null时，后端可正确清除沙盒字段。 (TGT-52798)
* 在Target后端中重新实施了已删除的选项持久层，以支持[!UICONTROL Automated Personalization] (AP)活动中的准确历史报告。 以前，删除选项时，会丢失其名称，从而难以解释过去的性能数据。

  **关键改进**：

   * 现在使用现有`RemovedCampaignElements`和`RemovedOptionInfo`基础结构跟踪已删除的选项。
   * 从AP活动中删除某个选项时，将保留其元数据（例如ID和名称）。
   * 报表UI现在可以将原始选项名称（例如，`Option Name [Deleted]`）与历史量度一起显示，从而提高清晰度和可用性。

  此更新可确保一致且有意义的报告，即使在从活动中移除选项之后也是如此。 (TGT-52986)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* 修复了VEC中的一个问题：将修改应用于视图会导致重复并触发“用户输入无效”错误。 (TGT-52886)
* 修复了在VEC中配置图像选件时，[!UICONTROL Undo]和[!UICONTROL Insert Before]选项的[!UICONTROL Insert After]功能存在的问题。

  以前，在图像选件上撤消[!UICONTROL Insert Before]或[!UICONTROL Insert After]操作会导致不一致的行为或无法正确还原修改，尤其是在旧版[!DNL Target] UI中创建的活动中。 此问题已得到解决，以确保撤消操作现在能够可靠地用于这些修改。 (TGT-52809)

* 修复了`contentEditable`属性意外设置为true并保留在保存的HTML内容中的问题。 此更新可确保输出更干净的预期HTML，而不会出现意外编辑行为。 (TGT-52319)
* 为了防止已删除选项永久丢失，并确保服务间行为一致，已对UI和相关微服务中的选项实施了软删除功能。

  **键更改**：

   * 选项不再永久删除。 相反，它们会在参数XML对象中使用新的已删除标记： true标志。
   * 此标记仅由更新的[!DNL Target] UI用于从呈现中排除已删除的选项，并阻止将它们发送到边缘服务。
   * 删除的选项在编辑期间仍保留在活动有效负载的一部分，从而确保可跟踪性，同时避免将不存在的选项交付给客户。

  此更新改进了数据完整性，并符合管理分布式系统中删除操作的最佳实践。 (TGT-52726)

+++

**工作区**

+++查看详细信息
* 修复了将活动从非默认工作区复制到默认工作区或非默认工作区之间的问题。 现在，通过增强的跟踪和命名功能来复制选件以防止冲突。

  **关键改进**：
   * 将在目标工作区中使用更新后的ID和元数据重新创建选件。
   * 复制的选件会使用以下格式重命名：“选件名称复制”以及随机数字或时间戳以确保唯一性。
   * 系统将更新选件和活动状态以反映新的ID。
   * 此功能可防止重复复制操作期间因多个相同的“选件副本”名称而导致的错误。
   * 选件可能不会立即显示在目标工作区的选件列表中，而是会进行相应处理和显示。

  此更新提高了跨多个工作区管理选件时的可靠性和可跟踪性。 (TGT-53080)

+++

## [!DNL Target Standard/Premium] 25.7.2（2025年7月18日）

由于最近发现的问题（主要与复杂的客户自定义相关），此版本包含以下修复和更新：

**活动**

+++查看详细信息
* 在取消具有未保存更改的活动编辑时添加了额外的确认警告：“是否确实要保存此活动？ 如果不保存，您的所有更改都将丢失。” 此消息有助于防止意外数据丢失。 (TGT-52865)
* 已将[!UICONTROL Priority]中的旧版功能恢复到[!UICONTROL Goals & Settings]滑块，允许客户直接输入数值，如旧版UI中所支持。 （TGT-53185 和 TGT-53219）

+++

**受众**

+++查看详细信息
* 修复了阻止保存或编辑包含自定义受众的活动的问题。 客户遇到错误消息“我们无法完成您的请求。 如果问题仍然存在，请联系[!DNL Adobe Client Care]。” 尝试保存对特定活动的更改，甚至不保存任何更改时。 (TGT-53189)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++查看详细信息
* 修复了客户在[!UICONTROL Goals & Settings]页面上查看特定活动的报表时，[!UICONTROL View in Analytics]链接错误地指向QA环境而不是生产环境的问题。 (TGT-53163)

+++

**[!UICONTROL Experiences]和[!UICONTROL Offers]**

+++查看详细信息
* 修复了通过自定义代码调用`triggerView`导致无限循环的问题。 (TGT-52885)
* 修复了导致为活动定义的`LocalIds`与在体验定义中使用的那些`LocalIds`之间不匹配的问题。 (TGT-52669)
* 修复了活动[!UICONTROL Overview]页面上缺少量度名称的问题，该问题仅显示“选件”而不是正确的量度名称。 (TGT-53054)

+++

**Form-Based Experience Composer（基于表单的体验编辑器）**

+++查看详细信息
* 修复了[!UICONTROL Form-Based Experience Composer]中阻止活动保存并触发错误消息“无法读取未定义的属性（读取&#39;map&#39;）”的问题。 (TGT-53145)

+++

**推荐**

+++查看详细信息
* 修复了单击[!UICONTROL Catalog Search]中的产品时显示“无法检索产品详细信息”错误并在没有关闭选项的情况下打开模式窗口的问题。 (TGT-53082)
* 修复了在更改收藏集或促销活动时，[活动中作为选件的](/help/main/c-recommendations/recommendations-as-an-offer.md)推荐[!UICONTROL A/B Test]未正确更新的问题。 (TGT-52884)
* 修复了生产环境中，在更新的UI中单击实体时显示错误：“无法检索产品详细信息”的问题。 如果此问题仍然存在，请联系[!DNL Adobe Client Care]。” (TGT-53071)

+++

**报表**

+++查看详细信息
* 修复了将订单详细信息保存到CSV文件导致文件空的问题。 (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++查看详细信息
* 解决了[!UICONTROL Goals & Settings]页面上的问题：在多个体验中使用的选择器无法一致地高亮显示为选定选定项。 (TGT-53062)
* 修复了阻止活动编辑的问题并触发错误消息：“无法读取未定义的属性（读取&#39;map&#39;）”。 (TGT-53161)

+++

**工作区**

+++查看详细信息
* 改进了在切换工作区时对ad-hoc选件的处理。
   * 现在，从默认工作区切换到非默认工作区（或非默认工作区）时，可以正确复制临时选件。 在初始化过程中，会更新工作区上下文，并为选件分配一个新ID以确保唯一性。
   * 在同一个工作区中停留时不会发生任何更改。 (TGT-53079)
* 修复了阻止客户[在不同工作区之间复制活动的问题](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)。 （TGT-52753 和 TGT-47094）
* 修复了在工作区之间更改属性时出现的问题。
   * 在默认工作区与非默认工作区之间切换时，如果目标工作区中存在当前属性，则保留该属性。
   * 如果[!UICONTROL Properties]列表显示警告（可能表示某些属性可能不兼容），并且客户单击[!UICONTROL Add]或[!UICONTROL Remove]然后单击[!UICONTROL Save]，则将删除目标工作区之外的所有属性。 如果客户单击[!UICONTROL Cancel]，则所有属性都将保留，即使目标工作区中不存在这些属性。 (TGT-47094)
   * 如果保留在同一个工作区中，或从非默认工作区切换到默认工作区或其他工作区，则所有内容将保持不变。 (TGT-53078)
* 更新了实体验证逻辑以遵循活动的原始工作区上下文。 诸如[!UICONTROL Experience Fragments] (XF)之类的实体现在已根据最初创建该活动的工作区进行验证。 例如，如果默认工作区中存在XF，并且活动从工作区X复制到工作区Y，则只要XF在原始（默认）工作区中有效，验证仍会传递。 (TGT-53196)
* 在活动复制期间对复制临时受众的增强支持。
   * 临时受众（包括量度、报表、页面和仅限该活动的类型）现在会在以下场景中自动复制：
      * 将活动从默认工作区复制到非默认工作区时。
      * 在同一工作区中复制活动时。 (TGT-53197)

+++

## [!DNL Target Standard/Premium] 25.7.1（2025年7月11日）

由于最近发现的问题（主要与复杂的客户自定义相关），此版本包含以下修复和更新：

**活动**

+++查看详细信息
* 修复了[!UICONTROL Activity QA] URL包含不必要查询参数的问题： `at_preview_evaluate_as_true_audience_ids`。 (TGT-52907)
* 修复了预览URL错误地包含用户明确键入的受众以外的其他受众的问题。 已更正此行为，以确保在生成QA或预览链接时仅应用指定的受众。 (TGT-52912)
* 修复了一个问题，如果在流量分配设置期间首先选择[!UICONTROL Auto-Target] (AA)，则该问题阻止用户创建[!UICONTROL Auto-Allocate] (AT)活动。 此问题会导致后端验证错误，并阻止保存活动。 (TGT-53096)

+++

**受众**

+++查看详细信息
* 修复了具有[!UICONTROL Approver]角色的用户无法添加或保存仅限该活动的受众细化的问题。 尝试这样做会导致403禁止错误，表明需要“[编辑者]”权限，即使用户具有足够的权限来批准和管理活动。 (TGT-52984)
* 修复了使用[!UICONTROL Remove Audience Refinement]选项删除特定于活动的受众时，该受众不再出现在受众列表中以供在同一活动中重新选择的问题。 除非从头开始重新创建受众，否则此行为会阻止用户重新添加相同的受众。 (TGT-52979)
* 修复了以下问题：从位置中删除后，甚至在保存活动之前，仅限该活动的受众细化都会立即从UI中消失。 此行为与预期功能和工具提示指导相冲突，该指导会指出：“保存活动后，将删除此库中所有未使用的受众。” (TGT-52982)
* 修复了尝试将[!UICONTROL All Visitors]以外的受众分配给活动时的问题。 保存后，显示以下错误消息：“我们无法完成您的请求。 如果问题仍然存在，请联系[!UICONTROL Adobe Client Care]。” (TGT-53008)
* 修复了在活动编辑器中创建和分配新受众后阻止保存活动的问题。 显示的错误消息为：“我们无法完成您的请求。 如果问题仍然存在，请联系[!UICONTROL Adobe Client Care]。” (TGT-52977)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++查看详细信息
* 修复了复制现有活动并将报表源更改为[!DNL Adobe Analytics] (A4T)会导致“用户输入无效”错误的问题。 当某些与[!DNL Analytics]报表不兼容的度量操作（如`restart_same_experience`、`restart_random_experience`和`restart_new_experience`）从原始活动中保留时触发了该错误。 (TGT-52900)
* 修复了一个问题，在[!DNL Adobe Analytics]步骤中选择[!UICONTROL Goals & Settings] (A4T)作为报表源时，该问题阻止客户创建或保存活动。 选择[!UICONTROL Custom Event]量度（例如，“自定义事件16”）时具体出现问题，导致以下错误：“用户输入无效。” (TGT-52910)
* 修复了单击“[!UICONTROL View in Analytics]”链接会将用户重定向到主页而非预期的[!DNL Analytics]仪表板的问题。 （TGT-53092 和 TGT-53093）
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* 修复了在更新的[!DNL Recommendations] UI中查看[!UICONTROL Overview]活动时，选择[!UICONTROL Goals & Settings] (A4T)作为报表源时无法加载[!DNL Adobe Analytics]部分的问题。 显示以下错误消息：“出现错误。 我们无法完成您的请求。 如果问题仍然存在，请联系 Adobe 客户关怀部门。“(TGT-52999)

+++

**[!UICONTROL Experiences]和[!UICONTROL Offers]**

+++查看详细信息
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* 修复了在删除所有内容选项后，[!UICONTROL Manage Content]功能无法正确验证位置状态的问题。 在尝试保存或继续进行活动配置时，此问题可能会导致不一致的行为或错误。 (TGT-52801)
* 修复了用户在添加新页面和删除不同体验中的特定元素时遇到“输入无效”错误的问题。 在元素操作期间，特别是在体验之间切换和修改共享页面结构时，通过生成重复的`LocalIds`触发了该错误。 (TGT-52720)
* 修复了使用[!UICONTROL Generate Adhoc Offer]功能导致[!UICONTROL Manage Content]面板中出现未定义位置的问题。 （TGT-53076 和 TGT-53070）
* 阐明了在客户处发生的行为，即从[!UICONTROL Targeting]步骤导航到[!UICONTROL Experiences]时，可能缺少使用HTML选件所做的修改。 对于此客户，受影响的网站会动态生成多个DOM选择器，这些选择器会随着每次页面加载而发生更改。 因此，在重新打开编辑器时，无法找到最初用于修改的选择器，从而导致修改丢失或无效。 此方案按设计要求运行。 为确保修改在编辑器中持久保留，建议客户端使用稳定、一致且不会因页面重新加载而更改的选取器。 (TGT-52874)
* 修复了以下问题：尝试删除或停用作为已排除体验一部分的选件会触发“用户输入无效”错误。 即使未在包含的体验中主动使用选件，也会发生此问题。 (TGT-52917)

+++

**Form-Based Experience Composer（基于表单的体验编辑器）**

+++查看详细信息
* 修复了在基于表单的活动中，复制体验并编辑其中一个复制的体验中的自定义代码会无意间将这些更改应用于所有复制的体验的问题。 现在，每个体验在复制后可独立保留其自定义代码。 (TGT-51600)

+++

**本地化**

+++查看详细信息
* 更新了新UI中法语(fr_FR)、德语(de_DE)、意大利语(it_IT)、朝鲜语(ko_KO)和简体中文(zh_CN)的本地化字符串。

+++

**[!DNL Recommendations]**

+++查看详细信息
* 已添加新的[!DNL Recommendations]信息源[状态](/help/main/c-recommendations/c-products/feeds.md#status)： [!UICONTROL Partial Import Failed]。 (KB-2215)
* 修复了在使用[!DNL Recommendations]添加[!UICONTROL promotions]时影响活动创建工作流的问题。 当用户选择“[!UICONTROL Promote by Attribute]”并添加筛选规则（例如[!UICONTROL Parameter Matching]）时，在保存和重新编辑活动后未保留所选规则类型和操作数值。 重新打开时，筛选规则类型将意外更改，并且缺少操作数值。 (TGT-53059)
* 修复了[!DNL Recommendations] UI中的一个问题：使用单个规则创建的任何促销活动被错误地解释并显示为“项目列表”促销类型，而不管该规则的逻辑如何。 (TGT-53063)
* 修复了在使用更新的[!UICONTROL Overview]UI时，包含[!UICONTROL Download Recommendations Data]的[!UICONTROL Experience Targeting] (XT)活动缺少“[!DNL Recommendations]”按钮的问题。 （TGT-52730 和 TGT-52756）
* 以前，推荐UI仅显示从信息源成功导入的实体数。 但是，后端消息格式包括格式为`# of entities imported / # of total entities`的导入实体数和实体总数。 由于此差异，用户在UI中只能看到第一个值（导入计数），这会导致混淆。 现在，UI会显示这两个数字。 (TGT-53073)
* 修复了在包含推荐的基于表单的A/B活动中配置“[!UICONTROL Promote by attribute]”促销活动时，客户无法保存筛选规则的问题。 保存并重新打开活动后，缺少筛选规则，无法成功保存活动。 (TGT-53057)

+++

**报表**

+++查看详细信息
* 修复了从[!UICONTROL Export order details to CSV]页面中选择“[!UICONTROL Reports]”导致下载空文件的问题。 即使活动中存在有效的订单数据，也会发生此问题。 (TGT-52225)
* 修复了在创建和分配新报表受众后尝试保存活动时的问题。 返回的错误消息为：“访问被拒绝。 要执行此操作，需要以下所有权限： [编辑器]。” 尽管用户具有审批者级别的访问权限，但还是出现了此问题。 (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++查看详细信息
* 解决了以下问题：将修改应用于视图会导致视图被重复并且活动返回“无效用户输入”错误。 此修复可确保正确应用视图修改，而不会触发复制或验证错误。 (TGT-52886)
* 修复了自定义代码修改因错误体验而被错误显示的问题。 具体而言，针对某个体验所做的更改显示在不同的体验中，从而导致实时活动的混乱和潜在错误配置。 (TGT-52776)
* 修复了一个问题，该问题阻止在新的VEC UI中编辑或保存自定义代码修改。 具体来说：

   * 在编辑自定义代码块并保存之后，更改未反映在UI或QA预览中。
   * 在某些情况下，除非关闭并重新打开活动，否则无法删除修改。
   * 作为解决方法，用户必须复制代码，删除修改，然后使用更新的内容手动重新创建它。 (TGT-53072)

* 修复了编辑和保存自定义代码导致[!UICONTROL Modifications]面板无响应的问题。 (TGT-53075)
* 修复了对变量体验中的自定义代码所做的修改意外地反映在[!UICONTROL Control]体验中的问题。 这会导致投放行为发生意外更改。 现在，[!UICONTROL Control]体验仍然与对其他体验所做的自定义代码编辑隔离。 (TGT-52413)
* 修复了在编辑器完全加载之前用户单击了第二个体验（体验A）时，对某个体验（例如，体验B）所做的修改无意间复制到另一个体验（体验A）的问题。 如果最初选择的体验没有发生更改，此行为还可能导致修改丢失。 (TGT-52597)
* 修复了在活动创建的[!UICONTROL Modifications]步骤中所做的更改无法一致保存的问题。 在某些情况下，完成所有步骤并单击[!UICONTROL Save]后，添加到[!UICONTROL Modifications]部分中的自定义脚本将不会在实时站点上反映，尽管在保存过程中没有可见错误。 (TGT-52661)
* 修复了以下问题：自定义代码更改无法正确保存，并且在同一活动中的多个体验间无意中进行了镜像。 此外，用户在打开或刷新某些活动时遇到访问问题，导致屏幕空白。 这些问题现已得到解决，以确保稳定的活动编辑和准确的体验隔离。 (TGT-52594)
* 修复了用户在[!UICONTROL Browse Mode]中无法浏览到其他URL的问题。 这会阻止测试人员和编辑人员验证或预览同一活动会话中的替代页面。 (TGT-53052)
* 修复了在活动创建期间同时打开多个[!UICONTROL Visual Experience Composer] (VEC)实例的问题。 当用户在[!UICONTROL Enhanced Experience Composer]步骤中禁用[!UICONTROL Page Delivery] (EEC)并从网站URL中删除结尾斜杠时，会发生此问题。 (TGT-52782)
* 修复了以下问题：[!UICONTROL Revenue]步骤中的[!UICONTROL Goals & Settings]量度下拉列表错误地默认为[!UICONTROL Revenue per Visit] (RPVISIT)，即使用户选择了其他量度也是如此。  折叠和重新展开指标配置面板时出现问题，导致重置之前选择的值。 （TGT-52811 和 TGT-52878）
* 修复了活动创建工作流中与[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Multivariate Testing] (MVT)活动中的选件命名和内容翻译相关的几个问题：

  解决的关键问题：

   * 创建具有相同名称（例如，“Experience”）的多个HTML选件会触发“不允许使用重复的选件名称”错误，但UI不会明确指示导致冲突的选件。
   * 通过右侧面板重命名选件更新了UI中的名称，但更改未反映在[!UICONTROL Manage Content]选项卡或[!UICONTROL Offers]选项卡中，从而导致持续验证错误。
   * 在MVT活动中，尽管在重命名后重复名称错误并未持续存在，但UI仍无法以一致的方式在各个选项卡反映更新的选件名称。 (TGT-52933)

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
