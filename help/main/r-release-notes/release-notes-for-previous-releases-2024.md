---
keywords: 发行说明；预发行说明；未来增强；未来修复；未来功能；即将发布的版本
description: 查看 Adobe Target 早期版本中包括的功能、增强和修补的列表。
title: 早期版本中包括什么功能？
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 15%
---
# 以前版本的发行说明

以前 [!DNL Adobe Target] 版本的发行说明，包括 [!DNL Target Standard/Premium]、[!DNL Target] 平台和 [!DNL Target] JavaScript 库 (at.js) 的发行说明。

发行说明按发布年月以降序列出。

>[!NOTE]
>
>请参阅 [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A)，以了解有关当月 Target 发行版本（平台和 Target Standard/Premium）的信息。

## 发行说明 - 2024

### [!DNL Adobe Experience Platform Web SDK] `__view__`范围优化（2024年10月22日）

在2024年7月22日至2024年8月15日期间，[!DNL Target]团队优化了`__view__`范围，从而提高活动展示、访问和访客报表的准确性。 此优化旨在自动捕获自动呈现的建议的报告数据，并且对于大多数帐户应该是透明的。

所有新[!DNL Adobe Experience Platform Web SDK]客户都将启用此优化。 但是，如果客户是从at.js迁移而来，并且没有执行下面的实施步骤，则会禁用该优化。 我们敦促这些客户在2025年2月3日之前审查其实施。 在此日期之后，我们将为所有客户启用优化。 如果到时未审查和调整实施，则可能会影响报表，如下所述。 如果您需要确认您的实施是否受到影响，或者需要更多时间来调整实施，请联系[!DNL Adobe Customer Care]。

>[!IMPORTANT]
>
>如果您无法在2025年2月3日之前完成实施审查并解决任何问题，则可以请求延长一次，为期6个月。 确保您的请求在2025年1月31日之前提交。 Adobe将审核您的请求并做出决定。

若要在手动呈现建议时受益于此优化，请查看您的[[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}，以确保在手动呈现体验后或使用`applyPropositions`方法（或相应的[!DNL Launch]操作作为助手）呈现体验时发送通知。

手动呈现体验时最常见的情况包括：

* 使用JSON选件
* 在[[!UICONTROL 基于表单的体验编辑器]](/help/main/c-experiences/form-experience-composer.md)中创建的活动中使用自定义决策范围
* 在获取使用全局`__view__`作用域、基于[!UICONTROL 表单的体验编辑器]创建的活动时不使用`renderDecisions: true`

如果未按照&#x200B;*数据收集*&#x200B;指南中的[呈现个性化内容](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank}中的说明实施通知，则[!DNL Target]和[Analytics for Target报表](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)中可能缺少报表数据。 在某些情况下，您可能会注意到不正确的流量分摊，因为未捕获报表数据。 或者，在其他情况下，重复报告同一事件。

根据您的实施，检查[!DNL Analytics]和A4T报表影响。

[!DNL Platform Web SDK]支持两种呈现体验和个性化的实现类型：

* **单个个性化和测量调用。**

  最初建议，[!DNL Platform Web SDK]的单次呼叫方法被计划弃用，支持拆分呼叫方法。 Adobe建议所有新实施都使用新的拆分调用方法，并建议现有客户也转换为拆分调用方法。

  如果继续使用单调用方法，您可能会在[!DNL Analytics]报表中注意到以下意外更改：

  * 跳出率下降。
  * A4T和[!UICONTROL 页面视图]点击未拼合在一起，因此使用[!DNL Analytics]个eVar和事件在A4T报表中执行某些划分和关联比较困难。

* **拆分调用（也称为页面事件的顶部和底部）。**

  此实现类型是[!DNL Adobe]推荐的新[拆分调用实现方法](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank}。 使用此方法时，新的优化不会影响[!DNL Analytics]或A4T报表。

如有疑问，请联系[Adobe客户关怀](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C)。 (KB-2179)

### at.js版本2.11.6（2024年9月29日）

* 修复了一个问题，该问题阻止[!DNL Target]在[!UICONTROL 可视化体验编辑器] (VEC)或[!UICONTROL 基于表单的体验编辑器]中使用重定向选件正确运行。

有关at.js版本的更多信息，请参阅&#x200B;*Adobe Target开发人员指南*&#x200B;中的[at.js版本详细信息](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}。

### [!DNL Target]在[!DNL Adobe Customer Journey Analytics]中报告（2024年5月8日）

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank}与[!DNL Target]之间的集成为您的优化程序提供了强大的分析和省时的工具。

将 [!DNL Customer Journey Analytics] 用作 [!DNL Target] 的报告源主要有以下好处：

* 营销人员可以随时将 [!DNL Customer Journey Analytics] 成功量度动态应用到 [!DNL Target] 活动报表。 在运行活动之前什么都不需要指定。
* 营销人员可以利用[!DNL Customer Journey Analytics]功能（如[试验面板](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}）来进一步分析其网站个性化。

有关详细信息，请参阅Adobe Customer Journey Analytics中的[目标报表](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)。

### [!UICONTROL 可视化体验编辑器]助手扩展（2024年4月23日）

旧版[!DNL Target]可视化体验编辑器助手扩展是使用清单V2创建的。 [!DNL Google]宣布从2024年6月起，将不再允许使用清单V2创建的扩展。 有关详细信息，请参阅[[!UICONTROL 可视化体验编辑器]帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

[!DNL Adobe]建议客户尽快迁移到较新的[可视化编辑帮助程序扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

### [!UICONTROL 浏览器]受众属性中`Browser:iPad`和`Browser:iPhone`的更新（2024年4月30日）

| 更新 | 详细信息 |
|--- |--- |
| [!UICONTROL 浏览器:iPad]和[!UICONTROL 浏览器:iPhone]已在创建受众时使用的[浏览器属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)中更新。 | [!DNL Adobe Target]允许您[定位多个类别属性中的任意一个](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括访问您的页面时使用特定[浏览器或浏览器选项](/help/main/c-target/c-audiences/c-target-rules/browser.md)的访客。<P>从[!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）开始，将更新使用Target UI创建的内置受众，例如`Browser:iPad`和`Browser:iPhone`，以使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`为[!DNL iPad]和[!DNL iPhone]执行正确的定位。<P>客户无需对此更新执行任何操作。<p><B>重要信息</b>：若要让客户在配置文件脚本（和JavaScript区段）中对[!DNL iPad]和[!DNL iPhone]执行正确的定位，客户必须在&#x200B;**2024年4月30日**&#x200B;之前手动进行更改。 有关必须手动更改的备用设置示例，请参阅[!UICONTROL 浏览器]受众属性[&#128279;](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates)中的更新 [!DNL iPad] 和 [!DNL iPhone] 。 |

### [!UICONTROL 可视化编辑帮助程序]扩展（2024年3月14日）

此版本包含针对[!DNL Google Chrome]的[[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)扩展的以下增强功能和修复：

* 增强了在客户网站中执行创作时的iFrame加载机制。
* 修复了在[!UICONTROL 可视化体验编辑器] (VEC)中执行创作时导致扩展重复Cookie的问题。

### [!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）

此版本包含以下增强和修复：

* 修复了计算活动中唯一选择器数量的逻辑。 (TGT-47878)
* 修复了导致使用[!UICONTROL Analytics for Target] (A4T)报表配置的[!UICONTROL 多变量] (MVT)活动无法正确显示的问题。 (TGT-47490)
* 改进了在将无流量的体验用作控制体验时报表中显示的警告消息。 (TGT-47537)
* 添加了许多后端和本地化修复。

### [!DNL Target] Standard/Premium 24.1.1（2024 年 1 月 22 日、23 日和 25 日）

此版本包含以下增强和修复：

* 具有收入目标指标的[!UICONTROL Analytics for Target] (A4T)活动未显示“收入”作为列名称，并且收入指标未在报表中以($)格式显示。 这是一个已经解决的外观问题。 (TGT-46995)
* 修复了一个问题，该问题导致报告日期间隔不起作用。 (TGT-47396)
* 修复了在客户使用[!UICONTROL 更多操作]图标激活或停用活动后，导致[!UICONTROL 所有活动]页面上显示错误状态的问题。 (TGT-47367)
* 修复了导致[!UICONTROL 重要属性]报表不针对单个客户显示的问题。 (TGT-47272)
* 修复了一个问题，该问题导致在单个客户尝试启用“需要身份验证”时显示“负载无效”消息。 (TGT-47195)
* 更新了 [!DNL Target] UI 中的大量本地化字符串。
