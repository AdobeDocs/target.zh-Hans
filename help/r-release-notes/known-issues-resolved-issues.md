---
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
description: 有关此 Adobe Target 版本的已知问题的信息。此外，还包括有关已解决问题的信息。
title: Adobe Target 中的已知问题和已解决的问题
feature: known issues
translation-type: tm+mt
source-git-commit: 729bf757b0072cf57e89fdfc42e6a3db4422341e
workflow-type: tm+mt
source-wordcount: '4296'
ht-degree: 70%

---


# 已知问题和已解决的问题

有关已知问题的信 [!DNL Adobe Target]息。 此外，还包括有关已解决问题的信息。

>[!NOTE]
>
>括号中的问题编号供 Adobe 内部使用。

## 已知问题 {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

下面部分列出了 [!DNL Target] 的已知问题：

### 自动分配和自动目标活动的目标(A4T)分析指标

UI中存在当前已知问题，该问题允 [!DNL Target] 许用户选择不受支持的参与和收入指标作为您在自动分配和自动目标活动 [!UICONTROL 中进行] 优化的  主要目标指标。 支持转化指标；不支持参与和收 *入指标* 。 如果您选择参与或收入目标指标，则不会构建优化模型(即使UI当前允许您 [!DNL Target] 选择不受支持的目标指标)。

有关受支持和不受支持的目标量度的列表，请参 [阅创建](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)*将Analytics用作报告源的活动中支持的目标量度*。 (TNT-38409)

### 页面交付 {#page-delivery}

如果添加模板规则，如[页面交付](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md)中包含的 URL (/checkout、/cart)，则会在规则前添加额外的空格。这是一个外观问题，不影响受众定义的创建和选件交付。(TGT-35920)

### QA预览链接

如果帐户中保存的活动过多，则可能无法加载已保存活动的活动 QA 预览链接。重试预览链接应该有效。将已保存的活动存档，不再主动用于防止此问题继续发生。 (TNT-37294)

### Recommendations活动的QA模式

如果预览中使用的标准基于项目或基于类别，则已知问题会阻止活动。 (TNT-37455)

### 重定向选件 {#redirect}

以下是重定向选件存在的已知问题：

* 在一些情况下，当在配置了 Analytics for Target (A4T) 的活动中使用重定向选件时，有限数量的客户报告流量分配差异程度增大。Adobe 工程师当前正在努力解决此问题。
* at.js 实施中的重定向活动可能会导致预览 URL 进入循环（重复提供该选件）。您可以改为使用 [QA 模式](/help/c-activities/c-activity-qa/activity-qa.md)来执行预览和 QA。此问题不会影响选件的实际交付。(TGT-23019)

### 在 VEC 中取消页面加载 {#cancel}

* 在包含重定向 URL 的 VEC 中取消加载 [!UICONTROL A/B 测试]或[!UICONTROL 体验定位] (XT) 活动时，当前存在以下已知问题。

   在 VEC 的三步引导式工作流的第一步中，当您取消页面加载时，将显示 VEC 中的[!UICONTROL 修改]面板，并将对体验（例如，“体验 B”）应用“重定向到 URL”模板。在进入第二步或第三步后，再返回到第一步时，会出现以下情况。

   在“体验 B”中，默认情况下会呈现已取消的网站加载模板，并且[!UICONTROL 修改]面板将可访问，但不应该出现这种情况，因为此体验已经应用了“重定向到 URL”模板。应显示“重定向到 URL”模板。

   要在 VEC 中显示正确的体验状态，请执行以下操作：

   如果您在切换到其他体验后，再切换回“体验 B”，[!DNL Target] 将显示应用于此体验的“重定向到 URL”模板，并且[!UICONTROL 修改]面板将无法访问。(TGT-32138)

* 对于单页应用程序 (SPA) 网站，取消加载将禁止在[!UICONTROL 修改]面板下编辑操作。

### Recommendations

以下是 Recommendations 活动存在的已知问题：

* 如果通过信息源或 API 未收到更新达 60 天之后，实体会正确过期；但是，过期后不会从目录搜索索引中删除已过期的实体。(IRI-857)
* 标准和设计的“使用信息”叠加不反映它们在 A/B 活动和体验定位活动中的使用情况 (TGT-34331)
* A/B 活动和体验定位活动中的 Recommendations 选件不显示 Recommendations 栏的可视预览。
* 通过 API 创建的收藏集、排除项、标准和设计在 Target 用户界面中不可见，并且只能通过 API 进行编辑。(TGT-35777)
* 通过 API 创建的 Recommendations 活动可在用户界面中查看，但只能通过 API 进行编辑。
* “标准”列表（卡片）视图中显示的“自定义标准”信息源状态每十分钟刷新一次，在极少情况下可能会超过十分钟。“自定义标准”编辑视图中显示的状态将实时获取并始终保持为最新。(TGT-35896、TGT-36173)
* 标准和设计卡不显示正确数量的活动。 如果在A/B活动中使用标准或设计，则卡可能会错误地显示未使用设计或标准，即使在活动中使用了设计或标准。 (TGT-36621、TGT-37217)

### 多变量测试 (MVT) 活动

在 MVT 活动中查看量度时，表格和图形中显示的入选者不一致。如果用户从摘要视图切换到图形视图，之后又切换回摘要视图，更改量度，然后再切换到图形视图，则会出现此问题。出现此问题时，摘要视图会始终显示正确的入选者。如果用户从未在摘要视图和图形视图之间来回切换多次，则图形视图将显示正确的入选者。

### at.js {#atjs}

以下是 at.js 存在的已知问题：

* 使用 2.2.0 之前的 at.js 版本，如果页面元素（如按钮）上没有 Adobe Analytics 代码，则单击跟踪不会报告 Analytics for Target (A4T) 中的转换情况。at.js 2.2.0 已针对此问题进行了修复。如果您遇到此问题，[请升级到最新版本的 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。
* 如果您使用 at.js 2.1.1 或更早版本（例如某个默认体验）创建未进行任何修改的体验，则该体验可能不会计入报告、Analytics for Target (A4T)、Adobe Analytics 或 Google Analytics 中。此外，[ttMeta 插件](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md)可能无法正确工作。

   作为解决方法，请在体验内容中使用空格。(TNT-33366)

   >[!NOTE]
   >
   >at.js 2.2.0 对此问题进行了修复。您应升级到[最新版本的 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)，或者仅对低于 2.2.0 版本的 at.js 使用上述解决方法。

* 将页面加载到可视化体验编辑器 (VEC) 中时，Target 需要确定全局 mbox 设置是处于启用状态还是禁用状态，以及 entityID 或 categoryID 是否存在于用户尝试在 VEC 中应用推荐的位置。标准列表将会根据这些信息进行筛选。默认列表已筛选算法，但[“兼容”复选框](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md)允许您查看完整的算法列表。

   使用 at.js 时，“兼容性”复选框处于隐藏状态，因此您看不到不兼容的算法。

   此问题仅适用于使用 VEC 的 Recommendations 活动。

   **解决方法**：禁用 [!UICONTROL Recommendations > 设置]中的[!UICONTROL 筛选不兼容的标准]选项。禁用此设置后，所有标准（兼容和不兼容）都将显示在标准选择器中。(TGT-25949)

* 由于 at.js 和访客 API 2.2.0 之间的交互，在升级到 at.js 版本 1.0 后不会在 Microsoft Explorer 11 浏览器中触发 Mbox。此问题会影响 at.js 版本 0.9.6 及更高版本。(TNT-27600)
* at.js 可能不适用于 Cordova/Hybrid 应用程序，因为它们当前不支持第一方 Cookie。(TNT-26166)

   **解决方法**：请在启用“仅限 x”选项的情况下配置 at.js，并在调用中传递 `mboxThirdPartyId` 以管理用户。

### 成功量度

将高级选项“计数如何递增”设置为“每次展示时”或“每次展示时（页面刷新除外）”的成功量度不能用作其他量度所依赖的成功量度。

将成功量度设置为每次展示时递增时，Target 会在访客每次访问此成功量度时再次计数该访客。然后，Target 会将成功量度“成员资格”重置为 0，以便在下次展示时再次对其计数。因此，除非其他量度要求先查看此量度，否则 Target 永远不会意识到用户已查看第一个量度。

### Analytics for Target (A4T)

在Analysis Workspace使用目标活动印象和转化时，应用“同一触点”Attribution IQ模型来确保准确计数。 要应用非 [默认归因模型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)，请右键单击度量以修 **改列设置>启用使用非默认归因模型>选择相同接触模型**。 如果不应用此模型，这些指标就会被夸大。

所有当前Analytics包都能添加此模型并包含Attribution IQ。 如果您无权访问Attribution IQ，请在Reports &amp; Analytics中依赖A4T数据。

### Target API

客户无法通过 Adobe I/O 上的 v3 版 A/B 活动 API 对自动分配活动执行 CRUD 操作。

### GEO定位

2020年5月10日，我们更新了GEO提供商文件，这引发了一些不一致。 例如，添加了一些包含逗号的值；但是，现有受众中的值没有逗号。 并非所有投放服务器都受此更改影响。 因此，在2020年5月10日至7月22日之间，使用这些值的受众可能没有达到所有正确访客的要求。

### 报告-可下载。csv报告中的数据与目标UI中显示的报告不一致。 {#csv}

如果活动使用多个度量，则生成的用于下载的。csv文件报告不一致。 可下载的报告仅根据报告设置生成，并考虑使用的任何其他指标的相同值。

真相的来源始终是UI中显示的报 [!DNL Target] 告。

## 已解决的问题 {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

上述已知问题在解决后将会被移至下面部分，并在必要时添加额外的注释。

### 显示“处理”标签的图像优惠

在上传图像后，优惠页面上的图像优惠有时会在数小时内保留“处理”标签。 在大多数情况下，这只是标签的问题：图像优惠仍可用于活动并传送。 (MCUI-10264, TGT-37458)

在Target Standard/Premium 20.10.1版本中已修复此问题。

### Analytics for Target (A4T) 报表

已解决与A4T相关的以下问题：

* 使用目标度量影响A4T活动的 [!DNL Analytics] 问题，该目标度量导致A4T报告显示意外的流量拆分或人为夸大的转换。

   此问题在以下条件下影响A4T报告:

   * 活动是在2020年9月15日至11月5日（太平洋标准时间凌晨4点）之间创建或保存的，并且
   * 活动选择了 [!DNL Analytics] 一个指标作为目标指标。

   [!DNL Target] 在此期间正确分割流量。 但是，活动设置中可能出现50/50拆分，例如，在A4T报告中显示90/10拆分。

   对于受影响的活动，在11月5日（太平洋标准时间凌晨4点）之后，访客首次看到正确的流量拆分。 此时后创建或保存的新活动将正确报告流量拆分。

* 使用目标度量影响A4T活动的 [!DNL Target] 问题，导致A4T报告报告转化率低或无转化。

   >[!NOTE]
   >
   >此问题仅影响A4T报告。 它不影响活动投放。

   此问题在以下条件下影响A4T报告:

   * A4T活动的发布时间为2020年9月22日至11月11日（太平洋标准时间下午2:30），并且
   * 活动选择 [!DNL Target] 了一个指标作为目标指标，
   * 当访客达到活动的目标事件( [!UICONTROL 例如，单击某个元素])时，还有一个与转换事件匹配的低优先级非A4T活动。 如果非A4T活动配置的度量与A4T活动相同，或者配置的度量为“任意mbox”，则可能会发生这种情况。

   此问题影响2020年9月22日至11月11日（太平洋标准时间下午2:30）之间生效的A4T活动的报告。 受影响A4T报告的活动将在此日期范围外正确显示转换。 非A4T活动的报告未受影响。

如果您还有其他问题，请联系您的客户成功经理(CSM)或 [Adobe客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。 (CSO 20201110016)

### 自动目标报告 {#at-metrics}

已解决从9月15日下 [!DNL Adobe Target Premium] 午2 [!UICONTROL :30开始影响用] 户自动目标报告的问题。(PDT)10月6日上午9点25分。(PDT)。 查看受影响转化量度的报告(使用“已查[!UICONTROL 看页面]”或“已[!UICONTROL 单击mbox”选项进行配置])时，转化率会错误报告。 此时不存在已知的投放问题。

要重新同步并更正报告:

1. 复制并保存受影响 [!UICONTROL 的自动目标] 活动。
1. 激活新保存的活动(如果受影响的活动是实时的)。
1. 删除原始（受影响）活动。

(TGT-38522, CSO 20201006007)

### 报表 {#conversions-audiences}

当前转换增量根据使用的受众不同。

例如，对于同一访客，如果转换计数设置为增量“每个进入者一次：”

* 受众:访问级别转换的“所有合格访客”仅增加一次。 这是预期行为。
* 受众:每次访问级别转换的“新访客”都会错误地增加，而不是只增加一次。 这不是预期行为。

如果将转换计数设置为递增“每次印象：”

* 受众:用于访客级转换的“所有合格访客”错误地只增加一次，而不是每次增加一次。 这不是预期行为。
* 受众:“新访客”用于访客级转换，每次都会增加。 这是预期行为。

请注意，此问题仅与 [!DNL Target] 报告相关。 在将Analytics用于目标( [!UICONTROL A4T)] 报告时，这不是问题。

此问题已得到解决。

### 使用Google Chrome 80+版时，不在Visual Experience Composer(VEC)或Enhanced Experience Composer(EEC)中加载页面

此已知问题与Google决定更改没有SameSite属性的Cookie的默认行为有关，从Chrome版本80开始。 在更改之前，Chrome将所有不带SameSite属性的Cookie默认为“SameSite=None”，现在它默认为“SameSite=Lax”，这将更改在GET和POST请求上发送Cookie的方式。 请参 [阅SameSite更新](https://www.chromium.org/updates/same-site)。

有关详细信息和修复，请参阅“最近发布的Google Chrome SameSite cookie实施策略对VEC和EEC有何影响？” in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### 使用自定义体验作为控制时，自动定位活动的图形报表无法呈现

如果所有体验中均没有数据（0 次访问），则自动定位活动的图形报表无法呈现为“差异”模式（“平均提升”和“每日提升”）。如果将控制体验设为自定义，则在活动早期阶段可能会发生这种情况。对于其他模式（“运行平均值（控制和目标）”、“每日（控制和目标）”以及“访问次数”），报表可以正常呈现。当有一些数据（访问次数不为零）时，报表会立即按预期呈现。

已在 Target 19.7.1 版本中修复此问题。

### mbox.js

mbox.js 库不支持客户端模板语言，例如 Handlebars 和 Mustache。at.js 库则&#x200B;**&#x200B;支持这些语言。

**注意**：mbox.js 库将不再开发。所有客户都应该从 mbox.js 迁移到 at.js。有关更多信息，请参阅[从 mbox.js 迁移到 at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)。

### 实施：全局 Mbox 自动创建

On the Implementation tab ([!UICONTROL Administration > Implementation]) the [!UICONTROL Global Mbox Auto Create] field will be &quot;false&quot; by default for a newly provisioned tenant.

在配置后首次下载 mbox.js 时，“[!UICONTROL 全局 Mbox 自动创建]”字段在下载的 mbox.js 文件和 [!DNL Target] 后端中将设置为“true”，但它将继续在 UI 中的“[!UICONTROL 实施]”页面上显示为“false”，直到页面刷新为止（页面刷新后，状态将为“true”）。

对于新配置的租户，在下载的 at.js 中将设置 `global_mbox_autocreate = false`。如果先下载 mbox.js，则 global\_mbox\_autocreate 将设置为“true”，并且在下载的 at.js 中也将设置 `global_mbox_autocreate = true`。(TGT-15929)

### Target API 中的企业权限支持 {#api}

如果使用 GET API 拉取选件列表，则“选件”库中从 Target UI 创建的代码选件将显示在默认工作区中。此问题将在 2019 年 3 月的第一个星期得到修复。完成此修复后，在从 API 拉取时，代码选件将显示在相应的工作区中。此问题&#x200B;*不*&#x200B;会影响从 API 创建的选件。例如，无论是使用 GET API 还是从 Target UI 中获取选件，从 API 创建的代码选件都将显示在创建这些选件的工作区中。

### 报告和极端订单

从2019年11月25日至2020年4月26日，一台目标服务器遇到一个问题，该问题导致极端订单值计入基于收入的报告指标(AOV、RPV)。 从2019年12月19日到2020年4月23日，另一台服务器遇到了同样的问题。 此问题并未影响所有目标服务器或所有目标客户。

在以下情况下 *您* 未受到影响：

* 您的目标实施使用不同的服务器。
* 您的报告未排除极端订单。
* 您使用转化量度来衡量活动。
* 您的目标活动将Analytics用于目标(A4T)。
* 您位于亚太(APAC)地区。

要确定此问题是否影响您的目标报告，请联系客 [户关怀](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。

### Recommendations

* 如果 Recommendations 信息源中的项目与上一次运行中的项目相同，则该信息源索引会显示“正在等待编入索引”。要交付的产品引入不会受到影响。(RECS-6663)

   已在 Target 19.4.2 版本中修复此问题。

* Recommendations 信息源在处理时所花费的时间比预期要长。(COR-2836)

   已在 Target 16.10.1 版本中修复。

* 推荐信息源 UI 无法显示正确的索引状态。后端作业正常运行，但 UI 无法获取并显示当前状态。

   已在 17.10.1 版本中修复此问题。

### 重定向选件

页面上出现的争用情况可能会导致同时计入原始页面和重定向页面上的页面查看次数。我们计划对 at.js 实施进行更新，以确保避免出现这种争用情况。

已现在 at.js 1.6.3 中修复此问题。

### 排除组

* 在创建排除组后应用自动去除重复项功能时，UI 中活动图的计数可能会不正确。
* 在对具有排除组的现有活动进行编辑后，UI 中可能无法正确反映手动包含项。

这些问题已得到解决。

### Target API

Adobe I/O 上的 v1 版选件 API 将通过 Target 创建的所有选件存储在默认工作区中。(TTTEAM-41957)

此问题已得到解决。

### at.js {#at-js-2}

由于 at.js 和访客 API 2.2.0 之间的交互，在升级到 at.js 版本 1.0 后不会在 Microsoft Explorer 11 浏览器中触发 Mbox。此问题会影响 at.js 版本 0.9.6 及更高版本。(TNT-27600)

已在 API 2.3.0 版本或更高版本中修复。

### 地域定位

在创建地域定位受众时，搜索包含特殊字符（例如空格或逗号）的字符串当前无法正常工作。例如，在根据城市、省/自治区/直辖市、国家/地区创建受众时，会出现这个问题。例如，在搜索“纽约”时，不会返回有效结果。

已于 2018 年 11 月版修复。

### at.js {#at-js-3}

如果使用 at.js 版本 1.6.0，但没有活动资格，则会出现 Analytics for Target (A4T) 重定向。

已在 at.js 1.6.2 版中修复。

### 活动、工作区和删除活动 API

默认工作区中通过 API 删除的活动继续显示在 Target UI 中。作为解决方法，请使用 Target UI 删除默认工作区中的所有活动。(TGT-31315)

已于 2018 年 10 月 25 日修复

### 自动个性化 (AP) 选件报表

您在自动个性化 (AP) 活动的报表中单击定位体验以查看选件报表时，当前您会看到空结果、错误消息或旋转的图标。(TNT-30695)

已于 2018 年 9 月 27 日修复。

### 代码编辑器

当您在 Firefox 和 Internet Explorer 中使用代码编辑器时，如果在三步工作流操作指南的第 1 步重新加载 VEC，则“修改”选项卡无法正确呈现，但是这不会影响 VEC 的功能。(TGT-28730)

已在 18.9.1 版本中修复此问题。

### 使用属性促销活动规则的 Recommendations 活动

编辑或复制使用属性促销活动规则的 Recommendations 活动时，如果单击“保存”，则会显示“具有缺失的字段”错误。

已在 17.8.1 版本中修复此问题。

### 备用 Recommendations

备用 Recommendations 会在 Target UI 的“最近查看的项目”卡片上错误地显示“已启用”。(TGT-29308)

已在 18.4.1 版本中修复此问题，以便显示“已禁用”。

### 自动定位活动和报表受众

当自动定位活动中使用的报表受众名称发生更改时，从 Target 对该活动执行的进一步更新可能会失败，并显示一条错误消息。

已在 Target 18.5.1 版本（2018 年 5 月 22 日）中修复此问题。

### at.js {#at-js-4}

at.js 版本 0.9.6 中更改了对保存 Cookie 时应使用的顶级域进行提取的算法。由于进行了这项更改，Cookie 不能保存到使用 IP 的地址中。大多数情况下，使用 IP 地址进行测试，但作为解决方法，您可以使用 DNS 条目，调整本地计算机上的主机文件，或使用 targetGlobalSettings() at.js 函数插入代码段以支持 IP 地址。

此问题已在 at.js 版本 1.2 中纠正。

### Target Premium 的企业用户权限

作为企业权限迁移的一部分，所有 Target Premium 用户管理都已从 Adobe Target UI 迁移到 Adobe Admin Console。

迁移可能会导致出现以下两个应注意的问题：

* 非管理员用户会收到一封电子邮件，指出他们现在可以访问 Adobe Target。这表明已为贵组织完成迁移。可以忽略此电子邮件。
* 迁移后，Adobe Admin Console 中会重新显示之前已禁用用户的一些报表。如果 Adobe Admin Console 中的已禁用用户仍显示在迁移之前 Target 的用户列表中，则对于贵组织来说，这可能会是一个问题。我们建议管理员查看 Admin Console 中的用户列表以验证访问权限。

此问题已于 2017 年 8 月 30 日修复

### 活动创建

17.6.2 版本的问题可能会影响 2017 年 6 月 22 日至 2017 年 6 月 29 日期间创建和/或更新的活动。以下活动会受到影响：

* 在体验定位 (XT) 中重新排列的任何体验都将还原到原始顺序
* 活动本地的任何区段规则（未保存在受众中）都会丢失：组合的受众、位置细化以及与成功量度相关的任何规则。

其他活动不会受到影响。

**重要信息**：此问题不会自动修复。您必须重新保存任何受影响的活动才能修复此问题。

此问题已于 2017 年 6 月 29 日修复

### 基于表单的体验编辑器

使用基于表单的体验编辑器时，已报告会出现以下已知问题：

* 如果您使用基于表单的体验编辑器来编辑 mbox 而不是自动创建全局 mbox (target-global-mbox)，然后选择一个参与度量度作为成功量度，则该量度只会在具有活动中所用 mbox 的页面上递增。例如，如果您的 mbox 为 homepage\_mbox，则“每次访问页数”量度便是该访问期间对 homepage\_mbox 进行点击的次数。(TGT-22789)
* 在流程的步骤 1 中，如果在使用基于表单的体验编辑器时删除体验定位 (XT) 活动中的体验，则会引发 JavaScript 异常。(TGT-24366)

第一个问题已在 Target 17.3.1 版本（2017 年 3 月版）中修复。

第二个问题已在 Target 17.6.1 版本（2017 年 6 月版）中修复。

### at.js {#at-js-5}

自 Target 17.4.1（2017 年 4 月 27 日版）发行以来，使用 at.js 库时，在可视化体验编辑器中执行“插入图像”操作会导致无法交付选件内容。

此问题已在 2017 年 5 月 22 日发行的 at.js 版本 0.9.7 中修复。

### 报表：A/B 活动和体验定位 (XT) 活动

在 4 月 27 日晚上 9 点（太平洋标准时间）到 5 月 5 日早上 6:00（太平洋标准时间）期间，如果创建或编辑了 A/B 活动和 XT 活动，且其中包含任何使用“已查看页面”转化操作的量度（不基于其他量度），则这些活动可能会错误地记录转化次数。此问题现已解决；但是，在受影响的时间段内，有关这些活动的“已查看页面”转化操作的报表可能不准确，且遗憾的是，这些报表无法更正。我们建议，在基于这些活动的“已查看页面”转化操作做出任何决策时，您只应信赖在受影响时间段之前或之后记录的数据。

其他量度的报表数据仍然可用，因为它们没有受到影响。

已在 Target 17.4.3 修补程序中修复。

### 选件：A/B 活动和体验定位 (XT) 活动

在 4 月 28 日星期五（晚上 9 点，太平洋时间）到 5 月 1 日星期一（晚上 9:15，太平洋时间）期间，使用基于表单的体验编辑器创建或编辑的至少具有两个体验的 A/B 活动和 XT 活动的选件在交付和预览时会受到影响。只会显示具有默认内容的选件。

已在 Target 17.4.3 修补程序中修复。

### at.js {#at-js-6}

使用可视化体验编辑器 (VEC) 和 at.js 时，以下操作会导致无法交付选件：移动和重新排列。

已在 at.js 版本 0.9.6 中修复此问题。

### 报表

由于会出现异常行为，已删除 Target 17.3.1 版本（2017 年 3 月 30 日版）中包含的在报表中查看多个量度的功能。即将发行的版本中将再次提供此功能。

Target 17.4.1 版本（2017 年 4 月 27 日版）中包含在报表中查看多个量度的功能。

### 选件

从“图像选件”库（“选件”>“图像选件”）中删除的图像在 UI 中仍可见。在即将发行的版本中，这些已删除的图像将不再显示。在此期间，已删除的图像会显示在 UI 中，但其状态为“已删除”。(TGT-23793)

已在 Target 17.4.1 版本（2017 年 4 月 27 日版）中修复。

### 重定向选件

对于“最近查看的项目”标准，如果未在 mbox 请求中传递 entity.id 参数，则基于实体的动态规则将不会生成推荐。(RECS-6241)

已在发布 Recommendations（2018 年 3 月 22 日）后修复此问题。在发布 Recommendations 后，如果未在 mbox 请求中传递 entity.id，则 Target 会跳过基于实体的动态规则。

### at.js {#at-js-7}

当用户在更新 at.js 设置后尝试从“实施详细信息”页面下载 at.js 时，将会下载 mbox.js 而不是 at.js。(TGT-23069)

已在 Target 17.3.1 版本（2017 年 3 月 30 日版）中修复。

### 全局排除规则

需要 10 到 20 分钟才能将全局排除规则传播到边缘网络以执行 Premium Recommendations。(RECS-5270)

已在 Recommendations 17.2.2.0 版本（2017 年 3 月 6 日版）中修复。

### Analytics for Target (A4T) 报表

切换报表量度时，报表不会更新。这是一个用户界面问题。对报表数据收集或交付没有影响。(TGT-22970)

已在 Target 17.2.2.0 版本（2017 年 2 月 24 日版）中修复。

### CSV 报表

下载的报表不遵循“排除极端订单”设置。(TGT-21871)

已在 Target 17.2.1.0 版本中修复。
