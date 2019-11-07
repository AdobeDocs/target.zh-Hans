---
keywords: 帐户首选项;首选项;网站详细信息;自定义 mbox 名称;用于报表的 Experience Cloud 解决方案;显示预计收入提升;CSS 选择器;使用元素类;默认的可视化体验编辑器 URL;启用增强型体验编辑器;生成体验快照;移动设备视区配置;垂直行业;筛选不兼容的标准
description: 可设置您的帐户首选项以配置 Adobe Target Standard 或 Target Premium，从而使用您的帐户正常运行它们。
title: 首选项
subtopic: 入门指南
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 首选项{#preferences}

可设置您的帐户首选项以配置 [!DNL Target Standard] 或 [!DNL Target Premium]，从而使用您的帐户正常运行它们。

要设置帐户首选项，请单击&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 首选项]**，根据需要配置首选项，然后单击&#x200B;**[!UICONTROL 提交]**。

下图显示了“[!UICONTROL 帐户首选项]”页面上的可用设置。

![“首选项”页面](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>其中某些首选项仅当您具有 [Target Premium](/help/c-intro/intro.md#premium) 时才可用。

## 网站详细信息 {#section_04A3340FC29B46978DB77058259F4EE0}

指定网站的配置方式。

### 自定义全局 Mbox

选择您用来交付 [!DNL Target] 活动的可选自定义 mbox 名称。此全局 mbox 必须为空，这表示它没有任何默认内容。仅当您的网站上安装了更新的 [!DNL at.js] 或 [!DNL mbox.js] 文件后，才应保存此设置。

>[!CAUTION]
>
>如果此设置配置不正确，现有活动可能会发生中断。

## 结果和报表 {#section_47C887AABD704A96BCD1C00BEABF4BCE}

设置相应选项，以确定用于结果和报表的数据。

| 选项 | 描述 |
|--- |--- |
| 用于报表的 Experience Cloud 解决方案 | 选择活动的报表源（[!DNL Target] 或 Adobe Analytics）。您也可以选择为每个活动分别选择报表源。选择报表源时，请考虑以下信息：<ul><li>无论选择何种报表源，都允许执行以下操作：[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化] (AP) 活动创建、激活和停用。当您选择[将 Adobe Analytics 作为 Adobe Target (A4T) 的报表源](/help/c-integrating-target-with-mac/a4t/a4t.md)时，这些活动类型不受支持。即使您将 Analytics 指定为报表源，[!DNL Target] 也会用作这些活动类型的报表源。</li><li>如果将此处的报表源设置为“Analytics”，则将不允许激活使用 [!DNL Target] 作为报表源的活动（将每个活动的报表源指定为 Target）。您必须在活动中将报表源更改为“Analytics”，或在“设置”&gt;“首选项”中将报表引擎更改为“为每个活动选择”。</li><li>如果将此处的报表来源设置为“[!DNL Target]”，则将不允许激活使用“Analytics”作为报表源的活动。您必须在活动中将报表源更改为“[!DNL Target]”，或在“设置”&gt;“首选项”中将报表源更改为“为每个活动选择”。</li><li>如果将此处的报表源设置为“为每个活动选择”，则可以创建、激活和停用所选报表源支持的活动。有关受支持活动的矩阵，请参阅[](/help/c-integrating-target-with-mac/a4t/a4t.md)将 Adobe Analytic 作为 Adobe Target (A4T) 的报表源。</li><li>当您从 A/B 手动切换到[!UICONTROL 自动分配]或[!UICONTROL 自动定位]时，如果[!UICONTROL 自动分配]或[!UICONTROL 自动定位]活动中不支持 A/B 手动活动的报表源，则所有量度和报表受众都将会丢失。</li></ul> |
| 显示预计收入提升 | 如果您为目标输入货币值，则还可以选择显示预计收入提升。[!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。<br>只有 Experience Cloud 管理员用户可以启用或禁用此功能。如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。<br>有关详细信息，请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。 |
| 启用细粒度优先级 | 允许使用 0 至 999 之间的优先级数字条目。<br>根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。<br>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。 |

## CSS 选择器 {#section_8155EDBF449E4198863235F94D1EA872}

指定 [!DNL Target] 生成 CSS 选择器的方式。

以下选项有助于 [!DNL Target] 了解您的网站结构，从而生成更适用于内容交付的 CSS 选择器。默认情况下，[!DNL Target] 会根据页面上的元素 ID 生成选择器。如果您的网站使用很少的 ID，或在同一页面上使用重复的 ID，则使用类可能是更好的选择。

您可以选择下列任一选项或两个选项都选择：

| 选项 | 描述 |
|--- |--- |
| 使用元素 ID | 如果多个元素使用同一个 ID，或元素 ID 在页面加载时可能会发生更改，请取消选择此选项。 |
| 使用元素类 | 默认情况下，[!DNL Target] 仅使用元素 ID。但是，如果您的页面设计为使用类来标识元素（例如通过 [!DNL Adobe Experience Manager] 构建的页面），则您还应当选择[!UICONTROL 使用元素类]。<br>**注意**：虽然已采取各种措施来确保准确性，但请注意，使用类仍可能会导致出现错误。如果您未选择任何选项，准确性也会受到影响。准确性由高到低的顺序为：选择 ID &gt; 选择类 &gt; 未选择任何选项。请务必测试页面，以确保选择器正确无误。<br>您可以为每个活动覆盖此设置（单击“设置”齿轮图标，然后选择 [!UICONTROL CSS 选择器]）。如果您使用不同的方式配置了多个网站，此操作会特别有用。<br>**注意**：在[!UICONTROL 自动个性化]和[!UICONROL 多变量测试]活动中，无法为每个活动覆盖此设置。请参阅[可视化体验编辑器中使用的元素选择器](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)，以了解更多有关选择器的信息。 |

## 可视化体验编辑器 {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| 选项 | 描述 |
|--- |--- |
| 默认的可视化体验编辑器 URL | 选择[!UICONTROL 可视化体验编辑器]使用的默认 URL。这是您每当为各个新活动设置体验时所使用的默认页面（例如主页）。如果未设置默认的 URL，您在创建各个活动时必须为活动输入 URL。 |
| 启用增强型体验编辑器 | 允许在防 iFrame 嵌套网站和具有混合内容的网站上进行编辑。有些网站可能与增强版本不兼容。取消选中此选项可还原到原先使用的体验编辑器。所做的这一选择不会对网站上的活动交付造成任何影响。<br>有关更多信息，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。<br>**注意**：您还可以在活动级别启用增强型体验编辑器。 |
| 加载混合内容 | 在使用增强型体验编辑器 (EEC) 打开网站时启用混合内容。启用此选项可避免通过 Target 代理服务器加载静态资源所产生的额外开销。<br>如果您的内容安全策略 (CSP) 标头允许在启用 EEC 的情况下，无需使用代理服务器即可加载混合内容，则此选项将很有帮助。<br>此外，如果因为在 EEC 中通过代理加载 JavaScript、图像及其他内容所需的时间较长，而导致您的 HTTP 网站加载时间延长，则此选项也将很有帮助。 |
| 生成体验快照 | 启用体验快照后，活动工作流程图中会生成体验的缩览图。但对于某些用户而言，禁用体验快照可能会提高性能。 |

## 移动设备视区配置 {#section_42176D062BCE4A28ADBB784CC4BEF84D}

您可以添加预览体验时要使用的设备。每个设备都有一个关联的受众。

| 选项 | 描述 |
|--- |--- |
| ![Premium 徽章](/help/assets/premium.png) 新增 | 单击[!UICONTROL 新增]，为移动设备视区指定描述性名称以及宽度和高度，选择所需的操作系统，然后单击[!UICONTROL 保存]。有关如何添加移动设备视区的信息，请参阅[移动设备视区配置](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)。 |

## 培训视频：帐户首选项 (7:33)

以下视频包含有关帐户首选项的信息。

* 介绍 [!DNL Target Standard] 中可用的帐户设置

>[!VIDEO](https://video.tv.adobe.com/v/17379?captions=chi_hans)