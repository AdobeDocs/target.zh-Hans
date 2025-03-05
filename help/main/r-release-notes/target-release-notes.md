---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 82e10bdecbaff95e16c34ae5b4b0acad9f2b6e5e
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 12%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年3月5日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.3.2（2025年3月6日）

此版本包含以下修复和更新：

* 修复了复制仅包含活动受众的活动时无法创建新活动，从而错误地使用原始活动的受众的问题。 (TGT-51855)
* 修复了阻止编辑具有仅限该活动的受众的[!UICONTROL Experience Targeting] (XT)活动的问题。 (TGT-51846)
* 修复了[!UICONTROL Visual Experience Composer] (VEC)在首次编辑时无法正确将修改应用于体验的问题。 (TGT-51843)
* 修复了单击VEC中的某些元素时触发“ID”错误的问题。 (TGT-51814)
* 在活动创建期间更新了VEC中的错误处理。 (TGT-51759)
* 修复了在保存活动时，[!UICONTROL Modifications]面板中缺少视图导致“无效用户输入”错误的问题。 (TGT-51827)
* 修复了阻止创建推荐标准的问题。 (TGT-51834)
* 在重定向到其他URL之前添加了确认消息。 (TGT-51703)
* 修复了选件和文件夹中的GraphQL集成测试问题。 (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1（2025年3月3日）

此版本包含以下修复和更新：

* 组合受众可以包括子组，每个子组包含多个受众。 此版本修复了导致子组受众无法在[!UICONTROL Rules]对话框中显示的问题。 (TGT-51813)
* 解决了在打开旧版活动时，某些体验受众被替换为[!UICONTROL All Visitors]的问题。 (TGT-51812)
* 解决了阻止编辑仅具有活动受众的活动的问题。 (TGT-51807)
* 解决了阻止在更新的[!DNL Target] UI中编辑页面标题修改的问题。 (TGT-51797)
* 解决了在复制体验、删除其他体验然后尝试保存活动时发生的空错误。 (TGT-51796)
* 解决了在创建活动的[!UICONTROL Targeting]步骤期间，受众信息面板中无法显示受众排除规则的问题。 (TGT-51579)
* 更新了韩语本地化的错误消息。 （TGT-51701 和 TGT-51699）

## [!DNL Target Standard/Premium] 25.2.3（2025年2月26日）

此版本包括以下更新：

* 解决了在[!DNL Target] 25.2.1版本之后无法对某些活动进行活动更新的问题。 (TGT-51781)
* 解决了在取消活动创建流程（选择[!UICONTROL Cancel]而不是[!UICONTROL Add Audience]）时删除所有状态中受众更改的问题。 （TGT-51769 和 TGT-51770）
* 解决了无法为某些活动加载[!UICONTROL Visual Experience Composer] (VEC)的问题，特别是当使用了自定义代码时。  问题导致VEC显示空白屏幕或[!DNL Target] UI恢复到其旧版本。 (TGT-51758)
* 解决了在编辑受众的页面交付后丢弃修改的问题。 (TGT-51756)
* 解决了更改[!UICONTROL Goals & Settings]页面上的量度类型时，从活动中删除所有非量度受众（页面和体验受众）的问题。 (TGT-51753)
* 解决了在编辑活动时单击[!UICONTROL Cancel]将Target UI导航到[!UICONTROL Activities List]而不是[!UICONTROL Activity Details]页面的问题。 (TGT-51731)
* 解决了阻止客户通过[!UICONTROL Export Reports to CSV]选项下载报表的问题。 (TGT-51708)
* 解决了在基于表单的体验编辑器中将[!DNL Target Standard]客户错误地显示为使用[!DNL Target Premium]功能[!UICONTROL Properties]的问题。 (TGT-51678)
* 修复了在创建新优惠时阻止显示[!DNL Adobe Experience Platform]属性的问题。 (TGT-51665)
* 已将[!DNL Recommendations]清单的所有活动筛选器移动到快速搜索，将UI与[!UICONTROL Catalog Search]而不是[!UICONTROL Filter]边栏对齐。 (TGT-50723)

## at.js版本2.11.7（2025年2月26日）

此版本包括以下更新：

* 修复了`localStorage`不可用时的遥测日志记录。 遥测导致某些客户在其浏览器中禁用`localStorage`时出现问题。

有关此版本及以前版本的at.js的信息，请参阅[at.js版本详细信息](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}。

## [!DNL Target Standard/Premium] 25.2.1（2025年2月17日）

此版本包括以下更新：

* [!UICONTROL Activities]用户界面更新
* [!DNL Recommendations]用户界面更新

### [!UICONTROL Activities]用户界面更新

随着[!DNL Adobe Target] UI现代化工作的继续，我们很高兴地宣布已正式提供更新的[!UICONTROL Activities]用户界面。

>[!NOTE]
>
>从2月17日开始，客户将逐步获得访问新[!UICONTROL Activities] UI的权限。 为确保为所有客户无缝部署，此版本将分阶段部署。 第一阶段会将初始的[!DNL Target]客户组升级到新的[!UICONTROL Activities] UI。 后续阶段将升级剩余客户。

此更新基于最新的[!DNL Adobe Spectrum]设计系统，标准化了以前不一致的设计模式，同时添加了新的增强功能，例如：

* [重新设计了报表](/help/main/administrating-target/reporting.md)，以便更好地了解活动结果。
* [[!UICONTROL Updated Change Log]](/help/main/c-activities/change-log.md)页面，现在从[[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank}获取实时分析的信息。
* [可自定义的列表视图](/help/main/c-activities/activities.md)，以便在不同的团队需求之间提供更好的灵活性。
* [增强的快速信息和详细信息屏幕](/help/main/c-activities/activities.md)，以便更轻松地访问信息。
* [会话持久搜索和筛选器选项](/help/main/c-activities/activities.md)。
* 完全[重新生成了[!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)，支持浏览器提供商的最新安全更新以及新式用户界面。

  有关更新的VEC与先前版本有何不同的信息，请参阅：

   * [可视化体验编辑器更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
   * [可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [已更新 [!DNL Chrome] 扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)，该扩展支持清单V3以提高安全性并改进对第一方Cookie的支持。

![活动刷新](/help/main/r-release-notes/assets/activities-refresh.png)

### [!DNL Recommendations]用户界面更新

随着[!DNL Adobe Target] UI现代化工作的继续，我们很高兴地宣布已正式提供更新的[!DNL Recommendations]用户界面。

>[!NOTE]
>
>从2月17日开始，客户将逐步获得访问新[!UICONTROL Recommendations] UI的权限。 为确保为所有客户无缝部署，此版本将分阶段部署。 第一阶段会将初始的[!DNL Target]客户组升级到新的[!UICONTROL Activities] UI。 后续阶段将升级剩余客户。

此更新基于最新的[!DNL Adobe Spectrum]设计系统，标准化了以前不一致的设计模式，同时添加了新的增强功能，例如：

* [产品目录搜索](/help/main/c-recommendations/c-products/catalog-search.md)现在具有更新的数据库，允许实时同步产品。
* 通过API创建的[!UICONTROL Recommendations]对象（[!UICONTROL Criteria]、[!UICONTROL Designs]、[!UICONTROL Collections]和[!UICONTROL Exclusions]）[现在可在UI](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md)中使用。
* [推荐设置](/help/main/administrating-target/recommendations-settings.md)已合并到[!UICONTROL Administration]部分下。
* 可自定义的列表视图，可跨不同的团队需求提供更好的灵活性。
* 已使用[语法突出显示和行编号](/help/main/c-experiences/c-manage-content/create-json-offer.md)刷新HTML和JSON代码编辑器。
* 增强的快速信息和详细信息屏幕，可更轻松地访问信息。
* 会话持久搜索和过滤器选项。

![推荐UI刷新](/help/main/r-release-notes/assets/recs-ui-refresh.png)

## [!DNL Target Standard/Premium] 25.1.1（2025年1月9日）

此版本包括以下更新：

### [!UICONTROL Offers Library]用户界面更新

为了增强[!DNL Adobe Target]用户的用户体验，此版本更新了[!UICONTROL Offers Library]用户界面。

>[!NOTE]
>
>为确保为所有客户无缝部署，此版本将分阶段部署。 第一阶段将最初的一组Target客户升级到新的Offers UI。 后续阶段将升级剩余客户。

此更新使用最新的[!DNL Adobe Spectrum]设计系统，标准化了不一致的设计模式并引入了新的增强功能，包括以下功能：

* **批量选件管理**：同时选择并删除或移动多个选件。

* **[!UICONTROL Code Editor]升级**：使用语法突出显示和行编号刷新了HTML和JSON编辑器。

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
>如果您无法在2025年2月3日之前完成实施审查并解决任何问题，则可以请求延长一次，为期6个月。 确保您的请求在2025年1月31日之前提交。 Adobe将审核您的请求并做出决定。

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

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
