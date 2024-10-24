---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: a708699926bd6cc89adc5c72d88be1ca4f0f0495
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 26%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2024年10月22日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Adobe Experience Platform Web SDK] `__view__`范围优化（2024年10月22日）

在2024年7月22日至2024年8月15日期间，[!DNL Target]团队优化了`__view__`范围，从而提高活动展示、访问和访客报表的准确性。 此优化旨在自动捕获自动呈现的建议的报告数据，并且对于大多数帐户应该是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客户都将启用此优化。 但是，如果客户是从at.js迁移而来，并且没有执行下面的实施步骤，则会禁用该优化。 我们敦促这些客户在2025年2月3日之前审查其实施。 在此日期之后，我们将为所有客户启用优化。 如果到时未审查和调整实施，则可能会影响报表，如下所述。 如果您需要确认您的实施是否受到影响，或者需要更多时间来调整实施，请联系[!DNL Adobe Customer Care]。

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

## [!DNL Target Standard/Premium] 24.10.2（2024年10月21日）

此版本包含以下修复：

* 修复了导致[!UICONTROL Recommendations]活动无法在[!UICONTROL Compose]和[!UICONTROL Browse]模式下加载的问题。 (TGT-50709)
* 修复了新的[[!DNL Google Chrome] [!UICONTROL Visual Editing Helper]扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)的问题，该问题在单击“取消”后导致从[!UICONTROL Visual Experience Composer] (VEC)重定向到[!UICONTROL Activities Library]。 在此修复之前，客户需要刷新[!UICONTROL Activities Library]才能创建新活动。 (TGT-49980)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
