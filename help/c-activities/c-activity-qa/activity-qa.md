---
keywords: qa;qa模式；活动QA;QA URL;QA URL
description: 了解如何使用Adobe [!DNL Target] QA URL来执行简单的端到端活动QA，它提供了永不更改的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。
title: 如何进行QA活动？
feature: 活动
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: b8002e951eb524df8c5fa3caed61ed30951ce85a
workflow-type: tm+mt
source-wordcount: '1586'
ht-degree: 38%

---

# 活动 QA

使用[!DNL Adobe Target]中的QA URL来执行简单的端到端活动QA，它提供了永不更改的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。

[!UICONTROL 活动] QA允许您在启动活动 [!DNL Target] 之前对其进行全面测试。[!UICONTROL 活动QA]功能包括：

* 可与团队成员共享链接，不论体验或活动是否进行了更新，这些链接永远不会更改，也不需要重新生成. 此功能允许您在整个用户历程中全面测试您的活动。
* 可选择遵守受众条件，在对体验外观进行 QA 时，营销人员可以选择测试定位标准或忽略定位标准，而不一定非要满足受众条件.
* 可捕获 QA 报表，以便营销人员能够确认量度可按预期递增，并且 QA 报表数据可与生产报表（对于非 A4T 报表）分开保存。
* 能够单独预览体验，或预览符合交付标准（页面/Target请求/受众）的其他实时活动。
* 能够对整个用户历程进行 QA。在活动 QA 过程中，只需使用 QA 链接访问网站一次，即可浏览整个网站。您可以一直停留在“活动 QA”模式中，直到您结束会话或使用  [Target QA书](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) 签强制自己退出 [!UICONTROL 活动QA]。如果您的活动跨多个网页，则此功能非常有用。

   >[!NOTE]
   >
   >对于使用版本2的at.js实施，此功能是正确的。** x或更高版本。对于at.js 1.** ximplementations中，仅当访客的浏览器不阻止第三方Cookie时，此功能才为true。

## 访问和共享 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 在活动的[!UICONTROL 概述]页面中，单击&#x200B;**[!UICONTROL 活动QA]**&#x200B;链接。

   ![“活动 QA”链接](assets/qa_link.png)

1. 配置以下设置：

   ![QA 链接配置选项](assets/qa_link_config.png)

   * **[!UICONTROL 匹配受众规则以查看体验]:** 有时，您可能想要确认受众匹配是否可以正常工作。其他时候，您需要检查活动的外观。 如果将此设置切换到“开”位置，则测试人员必须满足定位要求，才有资格查看体验。对于体验定位 (XT) 活动，只提供了一个活动 URL。您所看到的体验取决于您符合哪一个定位规则。

      如果将此设置切换到“关”位置，则单击链接即可查看体验，而不论您是否符合相应条件。执行 QA 时，您可以在要求遵守受众定位条件或不要求遵守受众定位条件之间来回切换。

   * **显示所有其他活动的默认内容：** 如果将此选项切换到“开”位置，则会显示所有其他活动的默认内容。例如，会单独显示预览，而不考虑同一页面/[!DNL Target]请求上的所有其他实时活动。

      如果将此设置切换到“关”位置，请考虑以下几点：

      * 如果您测试的活动与其他实时活动之间存在冲突，则会应用[常规的优先级规则](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。由于发生冲突，您可能看不到要进行QA的活动。
      * 量度会在已查看的活动中递增，但这仅限于 QA 报表环境。

1. 单击 **[!UICONTROL 完成]**，以保存所做的更改。
1. 与组织成员共享活动链接URL以进行测试。

   活动链接永远不会过期，如果有人更改活动或体验，您无需重新发送链接。 但是，如果您应用的受众与[!UICONTROL 受众库]不同，而不是简单地编辑活动，则会生成一个必须重新共享的新链接。

   每个活动链接URL（体验A、体验B等的活动链接URL）均允许您从相应的体验开始用户历程。 单击为体验生成的URL，然后继续正常的网站浏览，以在多个页面（如果存在多个页面）上查看体验。 每个体验只会生成一个 URL，即使体验涉及多个页面（模板测试或多页面测试）也是如此。

   您可以导航站点以查看其他页面，因为[!UICONTROL 活动QA]模式具有粘滞性。 对于使用版本2的at.js实施，情况是如此。** x或更高版本。对于at.js 1.** ximplementations中，仅当访客的浏览器不阻止第三方Cookie时，才会出现这种情况。

1. 要查看从活动链接URL生成的报表，请单击活动的&#x200B;**[!UICONTROL 报表]**&#x200B;页面，单击&#x200B;**[!UICONTROL 设置]**&#x200B;图标(![](assets/icon_gear.png))，然后从&#x200B;**[!UICONTROL 环境]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL QA模式流量]**。

## 注意事项 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 除[!UICONTROL 自动定位]和[!UICONTROL Automated Personalization](AP)之外，所有活动类型的[!UICONTROL 活动QA]链接都显示在[!UICONTROL 概述]页面上。
* [!UICONTROL 如果帐户中保存的活动过多，则可能无法加载已保存活动的活动 QA 预览链接。]重试预览链接应该有效。 为防止这种情况继续发生，请存档不再积极使用的已保存活动。
* [!UICONTROL 活动 QA URL 适用于将 Analytics 用作报表源 (A4T) 的活动。]使用[!UICONTROL 活动QA]执行QA时生成的点击量会流向同一报表包，即使活动开始后，该报表包中的活动数据也会流向该报表包。
* [!UICONTROL “活动 QA”不会显示已存档活动或已过期活动的内容。]如果停用已结束的活动，则必须再次保存该活动，[!UICONTROL 活动QA]才能正常工作。
* 导入到[!DNL Target Standard/Premium]中的活动（例如从[!DNL Target Classic]导入的活动）不支持QA URL。
* 在[!UICONTROL 自动分配]和[!UICONTROL Recommendations]活动中，模型不受[!UICONTROL 活动QA]中捕获的访问量的影响。
* [!UICONTROL 活动] QA具有粘滞性。在[!UICONTROL 活动QA]中浏览网站后，您的[!DNL Target]会话必须过期，或者您必须让[!DNL Target]从[!UICONTROL 活动QA]中释放您，然后才能像普通访客一样查看您的网站。 使用[Target QA书签](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)强制自己退出[!UICONTROL 活动QA]。

   您也可以手动强制自己退出该模式，方法是在网站上使用具有空值的 `at_preview_token` 参数（例如 `https://www.mysite.com/?at_preview_token=`）来加载页面。

* 如果在创建活动[时指定了“URL is”基于表单的编辑器中的细化](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)或可视化体验编辑器中的[页面交付选项)](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)，则QA URL将不起作用，因为[!UICONTROL 活动QA]会附加URL参数。 要解决此问题，请单击 QA URL 以转到您的网站，并从该 URL 中删除附加的参数，然后再加载新的 URL。
* 如果您有at.js 1.*x*，如果您 [!UICONTROL 使] 用Safari或其他阻止第三方Cookie的浏览器，则活动QA模式不会粘滞。在这些情况下，必须将预览参数添加到您导航到的每个URL。 如果已实施[CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)，则情况相同。
* 如果活动使用多个体验受众（例如同一活动中包含的美国和英国网站），则不会为这四种组合（体验A/美国网站、体验A/英国网站、体验B/美国网站、体验B/英国网站）生成QA链接。 而是只会创建两个 QA 链接（体验 A 和体验 B），且用户必须符合相应受众条件才能看到相应的页面。英国QA人员看不到美国网站。
* 所有 `at_preview` 参数和值均已进行 URL 编码。大多数时候，一切都会按预期运行。 但是，某些客户必须加载平衡器或尝试对查询字符串参数再次进行编码的Web服务器。

   由于此双重编码过程，当[!DNL Target]尝试对`at_preview_token`进行解码时，[!DNL Target]无法提取正确的令牌值，从而导致无法正常预览。

   Adobe建议您与IT团队沟通，以确保所有预列入允许列表览参数，以便这些值不会发生任何形式的改变。

   下表列出了可在域中列入允许列表的参数：

   | 参数 | 类型 | 值 | 描述 |
   |--- |--- |--- |--- |
   | `at_preview_token` | 加密的字符串 | 必填；没有默认值 | 一个加密实体，其中包含可在QA模式下执行的营销活动ID列表。 |
   | `at_preview_index` | 字符串 | 留空 | 参数格式为 `<campaignIndex>` 或 `<campaignIndex>_< experienceIndex>`<br>两个索引均以 1 开头。 |
   | `at_preview_listed_activities_only` | 布尔 (true/false) | 默认值：false | 如果为“true”，则会处理 `at_preview_index` 参数中指定的所有营销活动。<br>如果为“false”，则会处理页面中的所有营销活动，即使未在预览令牌中指定这些营销活动也是如此。 |
   | `at_preview_evaluate_as_true_audience_ids` | 字符串 | 留空 | 在[!DNL Target]请求范围中，应始终（在定位和报告级别）将segmentId-s的下划线分隔(&quot;_&quot;)列表计算为“true”。 |
   | `_AT_Debug` | 字符串 | 窗口或控制台 | 控制台日志记录或新窗口。 |
   | `adobe_mc_ref` |  |  | 可将默认页面的引荐 URL 传递到新页面。如果使用了 `AppMeasurement.js` 版本 2.1（或更高版本），则 [!DNL Adobe Analytics] 会将此参数值用作新页面上的引荐 URL。 |
   | `adobe_mc_sdid` |  |  | 将[!DNL Supplemental Data Id](SDID)和[!DNL Experience Cloud Org Id]从默认页面传递到新页面。 通过传递这些ID，[!UICONTROL Analytics for Target](A4T)可以将默认页面上的[!DNL Target]请求与新页面上的[!DNL Analytics]请求“拼合”到一起。 |

* [!UICONTROL Target QA模式] UI仅显示多页面活动中体验的第一个URL。 假设您要创建历程测试，并从URL1移动到URL2。 但是，如果要单独转到 URL2，请复制针对 URL1 提供的所有 URL 参数，并在放置“?”后将其应用于 URL2，正如 URL1 中所看到的一样。

## Target JavaScript库兼容性

[!DNL Target] 支持以下JavaScript库：

* [at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

下表列出了各种活动类型并指示每个库是否支持[!UICONTROL 活动QA]模式：

| 活动类型 | at.js 1.x | at.js 2.x | 平台Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B 测试] | 是 | 是 | 是 |
| [!UICONTROL 自动分配] | 是 | 是 | 是 |
| [!UICONTROL Auto-Target（自动定位）] | 否 | 否 | 否 |
| [!UICONTROL Automated Personalization] (AP) | 否 | 否 | 否 |
| [!UICONTROL Experience Targeting] (XT) | 是 | 是 | 是 |
| [!UICONTROL 多变量测试] (MVT) | 是 | 是 | 是 |
| [!UICONTROL 推荐] | 是 | 是 | 是 |




