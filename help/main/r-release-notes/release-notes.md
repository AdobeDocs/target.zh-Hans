---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 550fa1e8d4127babe02403708b73862505bf8c99
workflow-type: tm+mt
source-wordcount: '1772'
ht-degree: 15%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 26.1.1（2026年1月18日）

**活动**

+++查看详细信息

* **无法复制活动 — 用户输入无效。**&#x200B;已修复在复制活动时导致用户看到无帮助的“用户输入无效”错误的问题。 以前，在复制活动时，不会保留其特定于工作区的属性分配，从而导致后端拒绝保存请求，因为ABActivity至少需要一个属于非默认工作区的属性。 这种不匹配在UI中触发了常规错误，使用户没有指南。 此修复程序可确保在复制操作期间正确地保留工作区分配，使用户能够保存复制的活动而不进行修改，并防止出现误导性的验证错误。 (TGT-54282)
* **启用Web编辑器选件的Workspace列。**&#x200B;此更新解决了Web编辑器中的其他工作区中出现[!UICONTROL Default Workspace]中的选件所造成的客户混淆。 尽管此行为按预期工作，但在所有工作区中均可刻意看到[!UICONTROL Default Workspace]选件，但客户报告UI未明确工作区来源，尤其是在非默认工作区（如“审批者”）中创建活动时更是如此。 为了提高清晰度，Web编辑器的选件列表中现已启用[!UICONTROL Workspace]列，允许用户轻松区分每个选件属于哪个工作区，并防止误解显示的其他选件。 (TGT-54138)
* 在新选项卡中打开具有target=&quot;_blank&quot;的&#x200B;**链接。**&#x200B;此修复解决了以下问题：在~模式下单击时，包含具有~target=&quot;_blank&quot;[!UICONTROL Browse]的链接的已创作网站将在新的浏览器选项卡中打开，从而中断编辑器内预览体验。 出现此行为是因为创作页面的本机链接属性未被扩展插入的JavaScript截获，这与旧版UI不同，在旧版UI中，锚点元素会进行转换并覆盖其目标以保留在编辑器中导航。 此更新现在确保在Web编辑器中正确处理使用~target=&quot;_blank&quot;~的链接，以便在创作过程中不再打开外部选项卡。 (TGT-54134)
* **取消选择属性警告。**&#x200B;此更新引入了一个可视警告，当用户在活动编辑器中取消选择自动检测到的属性时，该警告会明确通知用户。 以前，删除自动检测到的属性不会指示该属性将被永久删除，这可能会导致意外丢失定位配置。 此修复程序会添加一个警告图标（与旧版UI中的行为一致），以通知用户取消选择资产会将其从活动中移除。 (TGT-54121)
* **[!UICONTROL Workspaces]下拉列表在[!UICONTROL Users]部分中限制为20个。**&#x200B;此修复解决了[!UICONTROL Workspaces] > [!UICONTROL Administration]部分中的[!UICONTROL Users]下拉列表仅显示20个工作区的问题，即使用户有权访问更多工作区也是如此。 `licenseGroups`的基础GraphQL调用也被限制为20个结果，这会导致UI显示不完整的列表，尽管用户有权访问组织中的更多工作区。 更新会移除此硬限制，以便现在可以正确返回并显示整组可用工作区。 (TGT-53820)
* **修复了选件模式不显示Workspace列的问题。**&#x200B;修复了选件模式在更新的UI中不显示workspace列的问题。 这会给客户带来困惑，因为[!UICONTROL Default Workspace]中的选件与所选工作区中的选件一起显示，但未指明它们的来源。 工作区列现在已启用，以便客户可以清楚地识别每个选件属于哪个工作区。 (TGT-52320)

+++

**属性**

+++查看详细信息
* **如果已删除，Activity Edit则不应添加自动检测到的属性。**&#x200B;此修复程序解决了以下问题：编辑活动会自动重新引入用户之前删除的自动检测属性。 重新打开活动进行编辑时，系统错误地还原了已删除的属性，导致[!UICONTROL Properties List]中的行为不一致并混淆。 此更新可确保在删除自动检测到的属性后，该属性会在所有后续编辑期间保持被删除状态，并且除非用户明确将其添加回来，否则该属性不会重新出现。 (TGT-54182)
* **如果已经删除，请不要添加自动检测到的属性。**&#x200B;此修复程序可确保，一旦用户手动从活动中删除了自动检测到的属性，系统在活动编辑器中的后续导航期间将不再重新引入该属性。 以前，如果用户取消选择自动检测的属性，移至[!UICONTROL Targeting]步骤，然后返回到[!UICONTROL Experiences]，则编辑器将根据活动编辑器状态切片中存储的自动检测列表重新填充移除的属性。 更新后的逻辑现在将自动检测到的属性与~ActivityState~切片中的当前属性进行比较，并阻止重新添加用户已删除的任何自动检测到的属性。 这会导致各步骤之间出现一致的行为并尊重用户意图。 (TGT-54181)
* **将自动检测到的文本添加到属性列表。**&#x200B;此增强功能更新[!UICONTROL Properties List]以明确标记系统自动检测的任何属性。 当用户可见的[!UICONTROL Properties List]中也存在自动检测到的属性时，该属性现在会使用存储在~ActivityEditorSlice~状态中的值，在其名称旁边显示“（自动检测）”文本。 这反映了旧版UI的行为，并帮助用户轻松区分手动选择的属性和自动识别的属性。 (TGT-54120)
* **将自动检测到的[!UICONTROL Properties]添加到状态。**&#x200B;此更新确保~ActivityEditorSlice.ExperienceEditor~状态一致地维护所有自动检测到的属性ID的最新列表，这些属性ID从Web编辑器传递到Activity [!UICONTROL Experiences]选项卡。 每次用户导航到[!UICONTROL Experiences]选项卡时，都会使用任何新检测到的属性刷新状态，同时会防止出现重复项，从而确保准确跟踪和可靠的下游行为。 (TGT-54119)

+++

**推荐**

+++查看详细信息
* **[!UICONTROL Environment]下拉列表仅显示100个结果。**&#x200B;此修复解决了具有超过100个环境的客户在[!UICONTROL Environment]内的[!UICONTROL Recommendations]下拉列表中只能看到前100个条目的限制。 基础GraphQL查询(~getEnvironmentsV2~)采用硬编码页面大小100分页，导致UI仅显示部分列表，即使有其他页面可用。 对于拥有超过100个环境的客户，此问题会导致缺少选项和不完整的选择体验。 更新将提高限制，以便返回并显示所有环境，从而确保完全可见，无论环境计数是多少。 (TGT-53903)

+++

**报表**

+++查看详细信息

* **修复了[!UICONTROL Reports]箭头未明确指示可展开列的问题。**&#x200B;修复了报表表未明确显示其他列可以在更新后的UI中展开的问题。 向列标题附近的[!UICONTROL Reports]箭头添加了消失的工具提示，以帮助客户了解更多列可用。

+++

**查看次数**

+++查看详细信息

* **无法删除应用于视图的修改。**&#x200B;此修复解决了用户无法删除活动中的修改的问题，除非修改已首先重新应用于其他视图。 在编辑活动(例如，活动ID 302467)时，尝试删除任何修改不会产生任何效果，从而阻止用户删除不需要的更改。 但是，使用“应用于更多视图”重新应用修改并分配给`Page Load`事件后，删除操作会突然按预期运行。 (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++查看详细信息
* **[!UICONTROL Experience Fragment]名称在新的VEC UI**&#x200B;中被截断(TGT-54312)
* **无法为[!UICONTROL Advanced Settings]量度使用[!UICONTROL Revenue]。**&#x200B;此修复解决了在[!UICONTROL Advanced Settings]中为[!UICONTROL Revenue]量度配置[!UICONTROL Goals & Settings]时，用户遇到403“访问被拒绝”错误的问题。 添加与主目标关联的依赖项条件时，出现问题；后端错误地要求编辑者权限，即使用户已有足够的权限创建和编辑活动。 因此，尽管配置有效，但保存活动失败。 更新更正了权限检查，以便具有适当访问权限的用户可以成功添加收入量度依赖关系，而不会触发禁止的资源错误。 (TGT-54092)
* **修复了“添加”按钮未应用于选定图像的问题。**&#x200B;修复了在活动创建过程中选择或更新图像时阻止客户添加某些图像的问题。 例如，当客户搜索特定资产时，如果在搜索“ipp”时返回图像，则单击[!UICONTROL Add]按钮不会应用选定的图像，并且不会创建任何修改。 选择其他图像（如`Homepage-banner-1-moz.jpg`）可继续按预期工作。 此更新确保所有有效图像都可以在更新后的UI中一致应用。 (TGT-53610)
* **修复了删除URL条件会重置目标量度配置的问题。**&#x200B;修复了删除[!UICONTROL Goal]量度中的单个URL条件导致整个配置在更新的UI中重置的问题。 当客户尝试删除[!UICONTROL Conversion] > [!UICONTROL Viewed a Page]下保存的URL条件时，目标类型意外切换到[!UICONTROL Viewed an Mbox]，并且已删除所有之前配置的设置。 此更新确保仅删除选定的URL条件，并且所有剩余的目标设置保持不变。 (TGT-53271)
* **修复了搜索未查看子文件夹的问题。**&#x200B;修复了在更新的UI中搜索优惠时未返回子文件夹结果的问题。 客户只有在手动导航到存储选件的文件夹时，才能找到该选件，这使得搜索行为与API功能不一致。 搜索功能现在支持递归查看文件夹，因此客户可以找到选件，而无需单独打开每个文件夹。 (TGT-51954)

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
