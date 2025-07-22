---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 15%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年7月22日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.7.3（2025年7月24日）

由于最近发现的问题（主要与复杂的客户自定义相关），此版本包含以下修复和更新：

**活动**

+++查看详细信息
* 修复了Builder类中的`buildViews`方法不正确地将`viewMaxLocalId`设置为视图总计数而不是分配的最高值`viewLocalId`的问题。 (TGT-53207)
* 引入了一个新的API端点，该端点允许用户从辅助数据库恢复以前删除的活动选项。 此功能利用`RemovedCampaignElements`和`RemovedOptionInfo`类提供的现有基础结构，确保已删除的选项无缝地重新整合到活动中。 (TGT-52903)
* 修复了更新的[!DNL Target] UI中的一个问题，该问题导致[!UICONTROL Automated Personalization] (AP)活动中删除的选件显示为`Deleted option with ID: X`，而不是其原始名称（例如，旧版UI中显示的`Offer Name [Deleted]`）。 此修复恢复了已删除选件的有意义的标签设置，提高了清晰度并使报告更准确、更便于用户使用。 (TGT-52921)
* 修复了后端持久层中的一个问题：已删除的选项已正确存储，但无法通过现有API端点访问。 因此，前端应用程序无法为已删除的选项检索有意义的名称，从而影响历史报表视图。 此修复程序现在确保保留的已删除选项数据能够在UI中正确显示。 (TGT-52973)
* 修复了由于之前修复了同步错误，导致从Target前端迁移到Target Central的某些活动的量度配置不一致的问题。 具体而言，最初使用转化量度且后来更新为基于Analytics的量度的活动在`primaryMetricType`和`successCriteria`字段中保留过时的值。 (TGT-52643)

+++

**Form-Based Experience Composer（基于表单的体验编辑器）**

+++查看详细信息
* 修复了在创建或编辑[!UICONTROL Form-Based Experience Composer] (AP)活动时，在&#x200B;**[!UICONTROL Manage Content]**&#x200B;中单击![图标（ ](/help/main/assets/icons/Experience.svg)管理内容图标[!UICONTROL Automated Personalization]）后导致编辑器崩溃的问题。 (TGT-53047)

+++

**推荐**

+++查看详细信息
* 修复了一个问题，该问题导致[!UICONTROL Catalog Search]在滚动到列表底部时无法加载其他结果，从而恢复与旧版UI一致的行为。 (TGT-53088)
* 修复了在更新的[!UICONTROL Number of Products] UI中[!UICONTROL Collections]页面中缺少[!DNL Target]列的问题。 列现在可正确显示，并恢复预期的功能。 (TGT-53168)
* 修复了[!UICONTROL Collection]规则未根据规则正确过滤的问题。 (TGT-53254)
* 修复了阻止从[!UICONTROL Criteria Details]对话框中删除项目的问题。 (TGT-53245)
* 修复了导致无法打开或无法与无名称的产品交互的问题。 选择返回未命名结果的环境时，出现此问题，导致无法访问产品详细信息。 (TGT-53007)
* 修复了在选择某些产品时导致[!UICONTROL Catalog Search]页面崩溃并显示空白屏幕的问题。 (TGT-53087)
* 修复了由于API限制而无法打开或编辑度量名称长度超过25个字符的[!DNL Recommendations]活动的问题。 此修复确保与超出字符限制的量度名称兼容，从而恢复对受影响活动的完全访问权限。 (TGT-52839)
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

* 实施了一个新的迁移终结点，以支持将已删除的活动选项从基于JCR的活动传输到[!DNL Target]中心。 此功能支持跨系统的一致跟踪和报告。 此功能可确保在[!DNL Target]前端和后端之间保留并同步已删除的选项，从而提高历史报表和数据完整性。 (TGT-53217)

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

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
