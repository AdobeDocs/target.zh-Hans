---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新、当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f034aba7fe4f54b937dee0846140af140052694c
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 32%

---

# [!DNL Target]发行说明（当前版本）

这些发行说明提供关于每个 [!DNL Adobe Target Standard] 和 [!DNL Target Premium] 版本的功能、增强和修复的信息。此外，在适用的情况下，还包括 [!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js 的发行说明以及其他平台变更。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!UICONTROL Offers Library]用户界面更新（2025年1月9日）

为了增强[!DNL Adobe Target]用户的用户体验，此版本更新了[!UICONTROL Offers Library]用户界面。 此更新使用最新的[!DNL Adobe Spectrum]设计系统，标准化了不一致的设计模式并引入了新的增强功能，包括以下功能：

* **批量选件管理**：同时选择并删除或移动多个选件。

* **[!UICONTROL Code Editor]升级**：使用语法突出显示和行编号刷新HTML和JSON编辑器。

* **已改进优惠卡**：已增强快速信息和详细信息卡，以便更轻松地访问信息。

* **持久搜索和筛选器**：添加会话持久搜索和筛选器选项。

有关详细信息，请参阅本节中的[选件](/help/main/c-experiences/c-manage-content/manage-content.md)和子文章。

以下是一段简短视频，重点介绍此版本中的更改：

![选件UI刷新视频](/help/main/r-release-notes/assets/offers-video-v2.gif)

## [!DNL Adobe Experience Platform Web SDK] `__view__`范围优化（2024年10月22日）

在2024年7月22日至2024年8月15日期间，[!DNL Target]团队优化了`__view__`范围，从而提高活动展示、访问和访客报表的准确性。 此优化旨在自动捕获自动呈现的建议的报告数据，并且对于大多数帐户应该是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客户都将启用此优化。 但是，如果客户是从at.js迁移而来，并且没有执行下面的实施步骤，则会禁用该优化。 我们敦促这些客户在2025年2月3日之前审查其实施。 在此日期之后，我们将为所有客户启用优化。 如果到时未审查和调整实施，则可能会影响报表，如下所述。 如果您需要确认您的实施是否受到影响，或者需要更多时间来调整实施，请联系[!DNL Adobe Customer Care]。

>[!IMPORTANT]
>
>如果您无法在2025年2月3日之前完成实施审查并解决任何问题，则可以请求延长一次，为期6个月。 确保您的请求在2025年1月31日之前提交。 Adobe将审核并决定您的请求。

若要在手动呈现建议时受益于此优化，请查看您的[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}，以确保在手动呈现体验后或使用`applyPropositions`方法（或相应的[!DNL Launch]操作作为助手）呈现体验时发送通知。

手动呈现体验时最常见的情况包括：

* 使用JSON选件
* 在[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)中创建的活动中使用自定义决策范围
* 在获取使用使用全局`__view__`作用域的[!UICONTROL Form-Based Experience Composer]创建的活动时不使用`renderDecisions: true`

如果未按照&#x200B;*数据收集*&#x200B;指南中的[渲染个性化内容](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank}中的说明实施通知，则[!DNL Target]和[Analytics for Target报表](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)中可能缺少报表数据。 在某些情况下，您可能会注意到不正确的流量分摊，因为未捕获报表数据。 或者，在其他情况下，重复报告同一事件。

根据您的实施，检查[!DNL Analytics]和A4T报表影响。

[!DNL Platform Web SDK]支持两种呈现体验和个性化的实现类型：

* **单个个性化和测量调用。**

  最初建议，[!DNL Platform Web SDK]的单次呼叫方法被计划弃用，支持拆分呼叫方法。 Adobe建议所有新实施都使用新的拆分调用方法，并建议现有客户也转换为拆分调用方法。

  如果继续使用单调用方法，您可能会在[!DNL Analytics]报表中注意到以下意外更改：

   * 跳出率下降。
   * A4T和[!UICONTROL Page View]点击未拼合在一起，因此使用[!DNL Analytics]个eVar和事件执行A4T报表的某些划分和关联比较困难。

* **拆分调用（也称为页面事件的顶部和底部）。**

  此实现类型是[!DNL Adobe]推荐的新[拆分调用实现方法](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank}。 使用此方法时，新的优化不会影响[!DNL Analytics]或A4T报表。

如有疑问，请联系[Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C)。 (KB-2179)

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
| [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
