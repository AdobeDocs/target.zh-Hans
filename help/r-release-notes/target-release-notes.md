---
description: 下列发行说明将介绍最新版本或即将发布的 Target 版本的功能、增强功能、修复信息和已知问题。
keywords: 发行说明
seo-description: 这些发行说明提供有关最新或即将推出的Adobe Target版本的功能、增强、修复和已知问题的信息
seo-title: Adobe Target发行说明(预发行版)
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3a498a99e333acc92651eb94592af87cfc34c6e1

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍最新版本或即将发布的 [!DNL Adobe Target] 版本的功能、增强功能、修复信息和已知问题。

**上次更新时间：2019 年 6 月 6 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发行日期、功能和其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [目标发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行版的时间。
>
>括号中的期刊编号供内部 [!DNL Adobe] 使用。

## Target Standard/Premium 19.6.1（2019 年 6 月 25 日）{#tgt-19-6-1}

此版本包括以下新增功能和增强功能：

### 可视化体验编辑器 (VEC)

* **新的CMS菜单选项**：单击CMS中的页面元素时，菜单会显示可用于该元素类型的选项。

   * **样式&gt;背景**：现在可使用 [!UICONTROL “样式”&gt;“背景] ”选项更改选定元素的背景图像和颜色。(TGT-15001)

   * **[!UICONTROL 替换为&gt; HTML]并[!UICONTROL 替换为&gt;体验片段]**：单击图像后，单击 [!UICONTROL 替换为]，此时将显示两个新选项：

      * **HTML**：您可以使用HTML替换图像，以使您完全控制元素，而无需选择父元素来访问HTML选项。
      * **体验片段**：您可以使用Adobe Experience Manager(AEM) [体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) 替换图像，以便快速插入AEM中在Target活动中创建的元素。(TGT-34097)

* **单击跟踪改进**：我们改进了在CMS和单页应用程序(SPA) CMS中配置点击跟踪的过程。

   * 选择要在单击跟踪中使用的元素时，所有可用元素的名称都会显示在右侧的“修改”面板中，从而可以快速、轻松地选择所需元素。
   * 三部分引导活动工作流的 [!UICONTROL “目标和设置”] 页面显示一个数字，表示单击跟踪的元素数量。您可以将鼠标悬停在此数字上，查看所有选定元素的名称。(TGT-33878)

### SPA CMS

* **引导工作流程**：新的向导式工作流程可帮助您了解页面交付规则设置如何配置为为单页应用程序成功执行和运行活动。(TGT-33718)

* **克隆修改**：您现在可以使用SPA CMS定义修改，然后克隆该修改以在单页应用程序中的其他视图中使用。(TGT-33882)

### 移动CMS

* **多个应用程序版本**：您现在可以为移动应用程序的多个版本创作活动。这在版本类似时节省了时间和精力，您无需显著更改应用程序的UI。(TGT-34231)

### 自动个性化(AP)和Auto-Target ![Premium徽章](/help/assets/premium.png)

* **特定体验作为控制**：您可以选择要在创建AP或自动Target活动时用作控件的体验。此功能允许您根据活动中配置的流量分配百分比，将整个控制流量路由到特定体验。然后，您可以根据控制流量来评估个性化流量的绩效报告。当前控制选项(随机提供的体验)将继续可用。（TGT-32801 和 TGT-26572）

### 其他增强、修复和更改

* `<BODY>` 标记现在显示在DOM路径中，当单击页面上的某个元素时，该路径显示在CMS底部，允许您对标记 `<BODY>` 执行操作。(TGT-33736)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要获得有关Target和其他Adobe Experience Cloud解决方案的即将产品增强的预先通知，请注册Adobe优先产品更新：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
