---
description: 有关使用可视化体验编辑器 (VEC) 的信息。
seo-description: 有关在 Adobe Target 中使用可视化体验编辑器 (VEC) 的信息。
seo-title: Adobe Target 可视化体验编辑器 (VEC)
title: 可视化体验编辑器 (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# 可视化体验编辑器 (VEC){#visual-experience-composer-vec}

有关使用可视化体验编辑器 (VEC) 的信息。

CMS是其中的主要功能 [!DNL Adobe Target]之一。CMS是一个编辑器，营销人员和设计人员使用可视界面创建和更改内容。无需直接编辑代码，便可进行多种设计选择。使用编辑器提供的编辑选项也可以编辑 HTML 和 JavaScript。

在 Target 的**[!UICONTROL 设置]** &gt; **[!UICONTROL 首选项]**选项卡上，您可以输入默认可视化体验编辑器 URL。

![默认的CMS URL设置](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

此URL确定打开CMS时开始的位置。如果您没有输入默认 URL，则当您打开编辑器时，首先会打开一个空白页面，然后需指定一个 URL。

>[!NOTE]
>
>如果页面包含混合内容(例如安全站点中的非安全页面)，某些浏览器(如Firefox)可能阻止页面在CMS中显示。如果未显示您的页面，请单击浏览器地址栏中URL旁边的图标，然后单击 **[!UICONTROL 此页面上的禁用保护]**。此问题不会影响向网站访客显示页面。

不能在CMS中修改页面上iframe内的内容。要编辑iframe中的内容，请确保iframe文档已启用Target，然后在CMS中加载该iframe URL。

您可以使用页面顶部的下拉菜单来查看您的页面，因为它会显示给不同的受众或具有不同的体验。您可以在第二个下拉列表中为每个体验提供一个名称。例如，如果您要测试导航栏中主页链接的位置，则可以将主页链接显示在最前面的体验命名为诸如“主页链接”之类的名称，以便轻松地在列表中识别体验。

>[!NOTE]
>
>如果对页面结构所做的更改会影响在该页面上创建的活动中所使用的位置，则可能会导致编辑体验时出现问题。如果在CMS之外更改了位置，Target可能无法找到内容所在的位置。

当您在页面上移动鼠标时，上下文相关的框会跟随光标，高亮显示页面上的元素。

![CMS高亮显示](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

单击 **[!UICONTROL “叠加]** ”图标以更改突出显示显示的方式。例如，您可以选择仅突出显示图像、链接、区域mbox、修改或JavaScript。您可以更改突出显示的颜色。您还可以指定高亮显示颜色和用于高亮显示不同元素类型的填充类型。

![更改叠加设置](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

单击高亮显示的元素以获取该元素类型可用的选项菜单，例如，可以单击某个图像，选择 **[!UICONTROL “编辑”&gt;“文本/HTML]** ”更改文本，或单击按钮并更改背景颜色。您可以使用页面左上角的按钮来打开和关闭叠加。

您还可以单击**[!UICONTROL 浏览]**，然后导航到可从主页面访问的某个页面（例如送货页面或购物车），然后测试该页面上的更改。您也可以访问悬停鼠标时显示的页面元素，例如弹出菜单和迷你购物车。浏览到相应的页面后，单击**[!UICONTROL 撰写]可编辑体验。**例如，您可能想要更改购物车下拉列表或一组图像的设计。

>[!NOTE]
>
>如果悬停状态依赖于 JavaScript，请确保未选中**[!UICONTROL 禁用 JavaScript]**。必须启用 JavaScript 才能编辑 JavaScript 元素。

有关CMS中可用选项的信息，请参阅 [视觉体验书写器选项](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

您可以在页面加载时对页面执行一些修改(或在页面加载失败后)，也可以取消CMS中的页面加载。有关详细信息，请参阅：

* [在页面加载或页面加载失败后编辑页面](#loading)
* [取消在CMS内的页面加载](#cancel-loading)

## 在页面加载或页面加载失败后编辑页面 {#loading}

在 VEC 中加载页面之前，或者即使页面无法完全加载（例如，自定义代码不再可操作），您可以执行许多操。

某些原因可能希望在页面加载到CMS中或在加载失败后对页面进行编辑或编辑：

* 您要对页面进行简单修改，例如添加自定义代码或更改体验的名称
* 您希望从不再可访问的页面复制现有的自定义代码
* 您知道页面不会在CMS内加载，但您仍希望进行简单的编辑

当页面加载(或在加载失败后)、“ [!UICONTROL 体验] ”面板、 [!UICONTROL “修改] ”面板以及体验顶部的设置均可访问时，体验(叠加、修改、配置等)均可访问。

下图显示了在页面仍在加载时，您可以插入自定义代码或执行其他操作：

![页面加载](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## 取消在CMS内的页面加载 {#cancel-loading}

您可以取消CMS中的页面载入以解锁活动的编辑，而无需等待页面加载。此功能可节省时间并帮助您更高效地进行编辑或插入自定义代码，而无需等待页面加载到CMS中。

您可能希望取消CMS中加载页面的一些原因包括：

* 您希望对现有修改做细微编辑
* 您要删除一个或多个现有修改
* 您要插入或编辑自定义代码
* 您错误地输入了错误的页面URL
* 在CMS中加载页面之前，您需要启用或禁用JavaScript
* 您希望将更多模板测试规则添加到页面交付条件
* 您希望覆盖全局增强体验书写器(EEC)切换页面时，通过EEC或iframe-only可能会将页面更改为页面

在CMS中取消页面后，您可以在活动中的体验之间切换，而无需等待页面加载。要再次在CMS中查看页面，您必须单击 **[!UICONTOL “重新加载]** ”按钮。

>[!IMPORTANT]
>
>请注意，当自定义代码或进行任何修改时，通过选择取消在CMS内的加载，您必须确保编码或更改正常完成。确保您执行正确的QA以确保您的自定义代码和任何其他修改均按预期提供。

要取消在CMS中的页面加载，请在加载页面时单击 **[!UICONTROL “取消正在加载]** ”按钮。在当前编辑会话期间，此页面不会在此活动的CMS中加载。

![“取消加载”按钮](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

要继续管理当前活动中的体验或添加新修改，您必须单击 **[!UICONTROL “重新加载]** ”按钮。

![“重新加载”按钮](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>下一个发行版中将修复此功能的当前已知问题。有关详细信息，请参阅“取消在CMS内加载页面”问题 [和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#cancel) 页面。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 可视化体验编辑器 (7:17)

以下视频提供了有关使用可视化体验编辑器选项的信息。

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### 可视化体验编辑器（第 1 个，共 2 个）(7:17)

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### 可视化体验编辑器（第 2 个，共 2 个）(7:29)

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### 办公时间：可视化体验编辑器

此视频是“[办公时间](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* VEC 如何工作
* 如何避免 VEC 中的常见问题
* 您可用于解决 VEC 问题的做法

>[!VIDEO](https://video.tv.adobe.com/v/20784/)