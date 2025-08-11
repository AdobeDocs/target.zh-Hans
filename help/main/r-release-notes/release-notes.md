---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 15%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

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

## [!DNL Target Standard/Premium] 25.8.1（2025年8月7日）

此版本包含以下增强功能和修复：

**活动**

+++查看详细信息
* 修复了更新UI的几个问题，包括由于输入值中的间距而删除页面类型时出现的错误、在工作区之间复制活动不可靠，以及QA环境中的页面交付规则功能不正常。 (TGT-52703)
* 修复了更新的[!DNL Target] UI中，具有[!UICONTROL Editor]角色的用户能够访问和尝试编辑实时活动的问题，应限制该问题。 活动列表和概述屏幕错误地显示了实时活动的编辑选项，从而导致潜在的意外更改。 (TGT-53055)
* 修复了[!UICONTROL Advanced Search] UI中的一个问题：选择“value present”（值存在）或“value not present”（值不存在）运算符会提示用户输入操作数，对于这些条件，该操作数不是必需的。 (TGT-51961)
* 修复了更新后的UI中，即使在沙盒环境中，将活动从暂存复制到生产工作区的尝试也始终失败的问题。 尽管使用有效配置并具有适当的工作区权限，客户仍会遇到各种错误消息，包括“活动已使用的匿名受众”和“无效受众ID”。 (TGT-52394)

+++

**体验片段(XF)**

+++查看详细信息
* 修复了体验片段(XF)内容在[!UICONTROL Visual Experience Composer] (VEC)预览中无法呈现的问题，尽管该内容在内容交付中正常工作。 (TGT-53318)

+++

**本地化**

+++查看详细信息
* 修复了“促销活动”部分中的“添加促销活动”按钮在QA租户的多个语言环境中显示为未本地化的本地化问题。 (TGT-53263)

+++

**产品建议**

+++查看详细信息
* 修复了通过可视化体验编辑器(VEC)编辑现有HTML选件时导致从内容交付中删除所有修改的问题。 更改在修改选项卡中显示为灰色，并且未反映在QA预览中，尽管在旧版UI中正确应用了这些更改。 (TGT-52863)
* 修复了更新的[!DNL Target] UI中的一个问题：在从[!UICONTROL Visual Experience Composer]选项卡导航回[!UICONTROL Targeting]后，在[!UICONTROL Experiences] (VEC)中做出的HTML选件修改无法保留。 (TGT-52874)
* 修复了更新的[!DNL Target] UI中的一个问题：在同一选择器之前和之后插入一个HTML选件会导致不正确的位置生成。 当客户从[!UICONTROL Targeting]选项卡返回到[!UICONTROL Experience]选项卡时，仅保留了一个选择器，从而导致修改丢失和内容投放中断。 此行为与旧版UI不同，旧版UI使用不同的位置标识符正确保留两个修改。 (TGT-52891)
* 修复了更新的[!DNL Target] UI中的一个问题：单击[!UICONTROL Modifications]边栏中的已添加选件会导致右侧[!UICONTROL Configuration]面板间歇性地出现和消失，从而使其难以与选件设置进行交互。 (TGT-53288)
* 修复了添加到活动中特定于受众的变体的HTML选件无法始终在修改部分中保存或显示的问题。 在编辑期间在受众之间切换后，以前应用的选件有时消失或无法呈现，这会中断验证并延迟活动准备工作。 (TGT-53440)
* 修复了复制包含选件的活动会导致在新活动中创建重复选件的问题。 此行为会导致不必要的混乱和混淆，尤其是在工作区之间移动活动时。 此修复程序现在可确保[!DNL Target]选件正确复制到目标工作区中，而不会出现重复情况，从而简化活动管理并提高工作流效率。 (TGT-53454)

+++

**单页应用程序(SPA)**

+++查看详细信息
* 修复了更新后的VEC中阻止客户对[!UICONTROL Single Page Application] (SPA)视图进行修改的问题。 虽然在旧版UI中创建的活动支持特定于视图的定位，但新UI无法检测或允许对这些视图进行编辑，视图切换控件显示为禁用。 (TGT-52556)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* 修复了对[!UICONTROL Visual Experience Composer]中的体验所做的修改不可见或在UI中显示不一致的问题。 (TGT-TGT-53381)
* 修复了更新后的VEC中，[!UICONTROL Manage Content]部分无法显示体验缩略图的替换文本的问题。 此问题使用户难以识别文档，尤其是在文件名较长或截断时。 (TGT-52291)
* 修复了客户在VEC活动中配置[!UICONTROL page delivery]规则时遇到错误验证错误的错误。 具体而言，在输入文本值时，诸如“等于任意”和“不等于任意”之类的运算符会触发“运算符类型的输入无效”，即使应当支持文本也是如此。 (TGT-52629)
* 修复了在使用“选择选件”按钮选择选件时，导致更新UI的[!UICONTROL Modifications]面板中行为不一致的几个问题。 UI未替换现有选件，而是添加了一个重复的选件，并尝试与任一选件交互会导致控制台错误，例如`selectorNotFound`。 此外，某些选件不会显示“选择选件”按钮，只会显示可编辑的属性。 (TGT-53321)
* 修复了更新的[!DNL Target] UI中的一个问题：在活动设置期间进行的HTML代码更改未在变体页面上保留，即使它们是为控制组正确保存也是如此。 尽管进行了多次尝试并在没有页面分组的情况下重新创建测试，但变体页面始终无法保留修改，影响内容交付和QA验证。 (TGT-53436)
* 修复了更新后的VEC中，页面投放规则中的“等于任何”运算符无法接受输入值的问题。 跨所有mbox配置客户参数时，选择此运算符会导致“输入无效”错误，从而阻止创建规则。 (TGT-52623)

+++

**工作区**

+++查看详细信息
* 改进了在不同工作区之间复制活动时的工作流。 在工作区之间复制活动以前会导致因缺少受众和未分配属性而导致同步错误。 此更新引入了一个更智能、更直观的工作流，可确保正确配置复制的活动并准备发布。 (TGT-47094)
* 修复了由于`copyActivityBatchOperations`突变失败，客户无法在工作区之间复制活动的问题。 尝试复制活动会导致服务器错误(500)和响应有效负载为空。 (TGT-52405)
* 修复了在所选工作区中无法访问配置中引用的选件时，活动同步失败的问题。 这会导致发布错误，并使活动处于失败状态。 (TGT-52535)
* 修复了在更新的[!DNL Target] UI中的工作区之间复制活动时的多个问题。 客户遇到与受众访问相关的错误，特别是实时活动，以及权限验证不正确，即使用户在源和目标工作区中均具有“[!UICONTROL Approver]”角色也是如此。 (TGT-53002)
* 修复了更新后的UI中的一个问题：在同一工作区中复制活动时，不必要地会复制关联的选件和受众。 (TGT-53457)
* 修复了一个问题，该问题用于解决以下情况：非默认工作区之间未正确复制临时（匿名）受众，或者未将非默认受众正确复制到默认工作区。 虽然早期的更新确保了在默认到非默认和相同工作区的情况下可以正确复制，但此增强功能侧重于保留跨多个工作区的组合受众配置。 此修复确保所有工作区过渡中的受众行为一致且定位准确。 (TGT-53268)

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
