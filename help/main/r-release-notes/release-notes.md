---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d6d58e94f4d4745b0783321671025d9cdd07f57f
workflow-type: tm+mt
source-wordcount: '3287'
ht-degree: 12%

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

**[!UICONTROL Analytics for Target] (A4T)**

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

**[!UICONTROL Visual Experience Composer] (VEC)**

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

**[!UICONTROL Analytics for Target] (A4T)**

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

**[!UICONTROL Visual Experience Composer] (VEC)**

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
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
