---
description: 下列发行说明将介绍 Target 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。
keywords: 发行说明
seo-description: 下列发行说明将介绍 Adobe Target 最新版本或即将发布的版本的功能、增强功能、修复和已知问题
seo-title: Adobe Target发行说明(预发行版)
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: de5d1a5852c7c6b59521e8d89493d48959a5b377

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新时间：2019 年 6 月 25 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发行日期、功能和其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1（2019 年 6 月 26 日）{#tgt-19-6-1}

此版本包括以下新增功能和增强功能：

| 功能 / 增强功能 | 描述 |
| --- | --- |
| 可视化体验编辑器 (VEC) | **新的CMS菜单选项**：单击CMS中的页面元素时，菜单会显示可用于该元素类型的选项。<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>See *Styles* in [Visual Experience Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#styles).<br>**单击跟踪改进**：我们改进了在CMS和单页应用程序(SPA) CMS中配置点击跟踪的过程。<ul><li>选择要在单击跟踪中使用的元素时，所有可用元素的名称都会显示在右侧的“修改”面板中，从而可以快速、轻松地选择所需元素。</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. 您可以将鼠标悬停在此数字上，查看所有选定元素的名称。(TGT-33878)</li></ul>See [Click tracking](/help/c-activities/r-success-metrics/click-tracking.md). |
| 单页应用程序 Visual Experience Composer (SPA VEC) | **引导工作流程**：新的向导式工作流程可帮助您了解页面交付规则设置如何配置为为单页应用程序成功执行和运行活动。(TGT-33718)<br> See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md#page-delivery-settings).<br>**克隆修改**：您现在可以使用SPA CMS定义修改，然后克隆该修改以在单页应用程序中的其他视图中使用。(TGT-33882)<br>See [Single Page App (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md). |
| 移动设备可视化体验编辑器 | **多个应用程序版本**：您现在可以为移动应用程序的多个版本创作活动。这在版本类似时节省了时间和精力，您无需显著更改应用程序的UI。(TGT-34231)<br>See &quot;Manage multiple app versions&quot; in [Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#using-the-mobile-vec). |
| ![Premium徽章](/help/assets/premium.png) 自动个性化(AP)和自动定位 | **特定体验作为控制**：您可以选择要在创建AP或自动Target活动时用作控件的体验。此功能允许您根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。然后，您可以根据控制流量来评估个性化流量的绩效报告。当前控制选项(随机提供的体验)将继续可用。(TGT-32801, TGT-26572, &amp; TGT-26571)<br>See [Select the control for your Automated Personalization or Auto-Target Activity](/help/c-activities/t-automated-personalization/experience-as-control.md). Note that there is a [current known issue](/help/r-release-notes/known-issues-resolved-issues.md) with this feature.<br>**个性化洞察报告**：当访客在特定位置看到特定内容时，针对属性的营销人员友好命名提供更有意义的信息。(TGT-33421 &amp; TGT-34957)<br>See [Data collection for the Target personalization algorithms](/help/c-activities/t-automated-personalization/ap-data.md). |
| ![高级徽章](/help/assets/premium.png) 推荐 | 在创建“最近查看的项目”逻辑时，您可以使用“推荐以前购买的项目”切换。(TGT-34030)<br>有关详细信息，请参阅 [“创建标准”](/help/c-recommendations/c-algorithms/create-new-algorithm.md#previously-purchased) 中最近查看的项目。 |
| Google Chrome SameSite Cookie策略 | Google最近宣布从Chrome76(针对2019年月30日的版本)开始，开发人员必须明确指定哪些cookie可以跨网站工作以及哪些cookie可以跟踪用户。<br>随着行业努力为消费者创建更加安全的Web，Target绝对致力于在会议期间提供个性化体验并超越访客的隐私期望。<br>请参阅 [Google Chrome SameSite Cookie策略](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要收到有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的高级通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
