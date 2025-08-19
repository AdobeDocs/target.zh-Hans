---
keywords: qa；qa模式；活动qa；qa url；qa url；预览url；预览url
description: 了解如何使用Adobe [!DNL Target] QA URL来执行简单的端到端活动QA，它提供了永不变更的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。
title: 如何QA活动？
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1658'
ht-degree: 27%

---

# 活动 QA

使用[!DNL Adobe Target]中的QA URL来执行简单的端到端活动QA，它提供了永不变更的预览链接、可选的受众定位以及从实时活动数据中分段的QA报表。

[!UICONTROL Activity QA]允许您在启动[!DNL Target]活动之前对其进行完全测试。 [!UICONTROL Activity QA]功能包括：

* 与团队成员共享的链接，无论对体验或活动进行了何种更新，这些链接都不会更改或需要重新生成。 利用此功能，您可以在整个用户历程中全面测试您的活动。
* 可选择遵守受众条件，在对体验外观进行 QA 时，营销人员可以选择测试定位标准或忽略定位标准，而不一定非要满足受众条件.
* 可捕获 QA 报表，以便营销人员能够确认量度可按预期递增，并且 QA 报表数据可与生产报表（对于非 A4T 报表）分开保存。
* 能够单独预览体验，或同时预览其他满足投放标准（页面/[!DNL Target]请求/受众）的已上线活动。
* 能够对整个用户历程进行 QA。在活动 QA 过程中，只需使用 QA 链接访问网站一次，即可浏览整个网站。在结束会话或使用[QA Target书签](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)强制自己退出[!UICONTROL Activity QA]之前，您将一直保留在活动QA中。 如果您的活动跨多个网页，则此功能非常有用。

  >[!NOTE]
  >
  >此功能适用于版本2中的at.js实施。*x*&#x200B;或更高版本。 对于at.js 1.*x*&#x200B;实施，仅当访客的浏览器不阻止第三方Cookie时，此功能才为true。

## 访问和共享 QA URL {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. 从活动的[!UICONTROL Overview]页面，单击&#x200B;**[!UICONTROL Activity QA]**。

1. 配置以下设置：

   * **[!UICONTROL Match audience rules to see experiences]：**&#x200B;有时，您需要确认受众匹配是否有效。 其他时候，您需要检查活动的外观。 如果将此设置切换到“开”位置，则测试人员必须满足定位要求，才有资格查看体验。对于体验定位 (XT) 活动，只提供了一个活动 URL。您所看到的体验取决于您符合哪一个定位规则。

     如果将此设置切换到“关”位置，则单击链接即可查看体验，而不论您是否符合相应条件。执行 QA 时，您可以在要求遵守受众定位条件或不要求遵守受众定位条件之间来回切换。

   * **为所有其他活动显示默认内容：**&#x200B;如果此选项切换到“开”位置，则为所有其他活动显示默认内容。 例如，单独显示预览，而不考虑同一页面/[!DNL Target]请求上的所有其他实时活动。

     如果将此设置切换到“关”位置，请考虑以下几点：

      * 如果正在测试的活动与其他实时活动之间存在冲突，则应用[普通优先级规则](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)。 由于发生冲突，您可能无法看到您打算进行QA的活动。
      * 量度会在已查看的活动中递增，但这仅限于 QA 报表环境。

1. 单击&#x200B;**[!UICONTROL Done]**&#x200B;保存更改。
1. 与组织成员共享活动链接URL以进行测试。

   活动链接永不过期，如果有人更改了活动或体验，则无需重新发送链接。 但是，如果您应用与[!UICONTROL Audience Library]不同的受众，而不是简单地编辑活动，则会生成一个您必须再次共享的新链接。

   通过每个活动链接URL（适用于体验A、体验B等），您可以从相应的体验开始用户历程。 单击为体验生成的URL，然后继续正常网站浏览，以查看多个页面上的体验（如果存在多个页面）。 每个体验仅生成一个URL，即使该体验跨多个页面（模板测试或多页面测试）也是如此。

   您可以导航站点以查看其他页面，因为[!UICONTROL Activity QA]模式具有粘性。 这种情况适用于版本2中的at.js实施。*x*&#x200B;或更高版本。 对于at.js 1.*x*&#x200B;实施，仅当访客的浏览器不阻止第三方Cookie时，才会出现这种情况。

1. 要查看从活动链接URL生成的报表，请单击活动的&#x200B;**[!UICONTROL Reports]**&#x200B;页面，单击&#x200B;**[!UICONTROL Settings]**&#x200B;图标(![icon_gear image](assets/icon_gear.png))，然后从&#x200B;**[!UICONTROL QA Mode Traffic]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Environment]**。

## 正在从QA模式中释放您自己

[!UICONTROL Activity QA]为粘性。 在[!UICONTROL Activity QA]中浏览网站后，[!DNL Target]会话必须过期或必须从[!DNL Target]中释放[!UICONTROL Activity QA]，然后才能像普通访客一样查看您的网站。

### at.js 2.*x*

如果您的网站具有at.js 2.*x*&#x200B;已部署，请使用[Target QA书签](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)强制自己退出[!UICONTROL Activity QA]。 在网站上加载具有空值的页面（如下一个项目符号中所述），在at.js 2.*的情况下，*&#x200B;不会从浏览器中删除QA Cookie。*x* 已部署。

### at.js 1.*x*

如果您的网站具有at.js 1.*x*&#x200B;已部署，除了使用[Target QA书签](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)之外，您还可以通过在网站上加载参数为空值的`at_preview_token`页面来手动强制自己退出。 例如：

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

如果您的网站部署了[[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}，则可以通过在网站上使用具有空值的`at_qa_mode`参数加载页面来手动强制自己退出。 例如：

`https://www.mysite.com/?at_qa_mode=`

## 注意事项 {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* 由于活动QA现在可用于所有[!DNL Target]活动类型，因此不再需要“使用体验预览URL预览Automated Personalization活动”功能。
* 如果帐户中保存的活动过多，则可能无法加载已保存活动的[!UICONTROL Activity QA]预览链接。 重试预览链接应该有效。 为防止这种情况继续发生，请存档不再主动使用的已保存活动。
* [!UICONTROL Activity QA] URL可用于将[Analytics作为报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)的活动。 使用[!UICONTROL Activity QA]执行QA时生成的点击量流向与活动数据流相同的报表包，即使活动已上线。
* [!UICONTROL Activity QA]不显示已存档活动或超过其结束日期的活动内容。 如果您停用已结束的活动，则必须再次保存该活动以便[!UICONTROL Activity QA]正常工作。
* 导入到[!DNL Target Standard/Premium]（例如，从[!DNL Target Classic]）中的活动不支持QA URL。
* 在[!UICONTROL Auto-Allocate]和[!UICONTROL Recommendations]活动中，模型不受[!UICONTROL Activity QA]中捕获的访问的影响。
* 如果在创建活动[时指定了“URL is”基于表单的编辑器中的细化](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)或可视化体验编辑器中的[页面交付选项)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)，则QA URL不起作用，因为[!UICONTROL Activity QA]会附加URL参数。 要解决此问题，请单击 QA URL 以转到您的网站，并从该 URL 中删除附加的参数，然后再加载新的 URL。
* 如果您有at.js 1.如果您使用Safari或其他阻止第三方Cookie的浏览器，则&#x200B;*x*，[!UICONTROL Activity QA]模式无粘性。 在这些情况下，您必须将预览参数添加到您导航到的每个URL。 如果您实施了[CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}，则同样如此。
* 如果活动使用多个体验受众（例如，同一活动中同时包含一个美国网站和一个英国网站），则不会为这四种组合（体验A/美国网站、体验A/英国网站、体验B/美国网站、体验B/英国网站）生成QA链接。 而是只会创建两个 QA 链接（体验 A 和体验 B），且用户必须符合相应受众条件才能看到相应的页面。英国QA人员看不到美国网站。
* 所有 `at_preview` 参数和值均已进行 URL 编码。大多数时候，一切都会按预期运行。 但是，有些客户必须加载均衡器或Web服务器，以尝试对查询字符串参数再次进行编码。

  由于此双重编码过程，当[!DNL Target]尝试对`at_preview_token`进行解码时，[!DNL Target]无法提取正确的令牌值，从而导致预览无法正常工作。

  列入允许列表 [!DNL Adobe]建议您与IT团队联系，以确保所有预览参数均被转换，以便这些值不会发生任何形式的转换。

  下表列出了可在域中列入允许列表的参数：

  | 参数 | 类型 | 值 | 描述 |
  |--- |--- |--- |--- |
  | `at_preview_token` | 加密的字符串 | 必填；没有默认值 | 加密实体，其中包含可以在QA模式下执行的营销活动ID列表。 |
  | `at_preview_index` | 字符串 | 留空 | 参数格式为`<campaignIndex>`或`<campaignIndex>_< experienceIndex>`<br>两个索引均以1开头。 |
  | `at_preview_listed_activities_only` | 布尔 (true/false) | 默认值：false | 如果为“true”，则会处理 `at_preview_index` 参数中指定的所有营销活动。<br>如果为“false”，则会处理页面中的所有营销活动，即使未在预览令牌中指定这些营销活动也是如此。 |
  | `at_preview_evaluate_as_true_audience_ids` | 字符串 | 留空 | 应始终（在定位和报告级别）在[!DNL Target]请求的范围内评估为“true”的segmentId-s的下划线分隔(“_”)列表。 |
  | `_AT_Debug` | 字符串 | 窗口或控制台 | 控制台日志记录或新窗口。 |
  | `adobe_mc_ref` |  |  | 可将默认页面的引荐 URL 传递到新页面。如果使用了 `AppMeasurement.js` 版本 2.1（或更高版本），则 [!DNL Adobe Analytics] 会将此参数值用作新页面上的引荐 URL。 |
  | `adobe_mc_sdid` |  |  | 将[!DNL Supplemental Data Id] (SDID)和[!DNL Experience Cloud Org Id]从默认页面传递到新页面。 传递这些ID可允许[!UICONTROL Analytics for Target] (A4T)将默认页面上的[!DNL Target]请求与新页面上的[!DNL Analytics]请求“拼合”在一起。 |

* [!UICONTROL Target QA Mode] UI仅显示多页面活动中体验的第一个URL。 假设您要创建一个历程测试，并从URL1移动到URL2。 但是，如果要单独转到 URL2，请复制针对 URL1 提供的所有 URL 参数，并在放置“?”后将其应用于 URL2，正如 URL1 中所看到的一样。
* 如果帐户中保存的活动过多，则可能无法加载已保存活动的活动 QA 预览链接。重试这些预览链接。存档已保存但不再主动使用的活动，以防继续发生此问题。

## Target JavaScript库[!UICONTROL QA Mode]兼容性 {#compatibility}

[!DNL Target]支持以下JavaScript库：

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html)

下表列出了各种活动类型，并指示每个库是否支持[!UICONTROL Activity QA]模式：

| 活动类型 | at.js 1.x | at.js 2.x | Platform Web SDK |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | 是 | 是 | 是 |
| [!UICONTROL Auto-Allocate] | 是 | 是 | 是 |
| [!UICONTROL Auto-Target] | 是 | 是 | 是 |
| [!UICONTROL Automated Personalization] (AP) | 是 | 是 | 是 |
| [!UICONTROL Experience Targeting] (XT) | 是 | 是 | 是 |
| [!UICONTROL Multivariate Test] (MVT) | 是 | 是 | 是 |
| [!UICONTROL Recommendations] | 是 | 是 | 是 |