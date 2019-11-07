---
description: 有关在 Adobe Target 中使用可视化体验编辑器 (VEC) 的信息。
title: Adobe Target 可视化体验编辑器 (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 可视化体验编辑器 (VEC){#visual-experience-composer-vec}

有关使用可视化体验编辑器 (VEC) 的信息。

VEC 是 WYSIWYG 用户界面，可让您轻松地在站点环境中创建和测试个性化体验和选件。您可以通过拖放、交换和修改网页（或选件）或移动网页的布局和内容来为 Target 活动创建体验和选件。

VEC 是 [!DNL Adobe Target] 的主要功能之一。通过 VEC，营销人员和设计人员可以使用可视化界面创建和更改内容。无需直接编辑代码，便可进行多种设计选择。使用编辑器提供的编辑选项也可以编辑 HTML 和 JavaScript。

在 Target 的&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 首选项]**&#x200B;选项卡上，您可以输入默认可视化体验编辑器 URL。

![默认 VEC URL 设置](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

此 URL 可确定您打开 VEC 时的起始位置。如果您没有输入默认 URL，则当您打开编辑器时，首先会打开一个空白页面，然后需指定一个 URL。

>[!NOTE]
>
>如果页面包含混合内容（例如，安全网站中的非安全页面），某些浏览器（如 Firefox）可能会阻止页面在 VEC 中显示。如果您的页面未显示，请单击浏览器地址栏中 URL 旁边的图标，然后再单击&#x200B;**[!UICONTROL 在此页面上禁用保护]**。此问题不会影响向网站访客显示页面。

无法在 VEC 中修改页面上 iframe 中的内容。要编辑 iframe 中的内容，请确保 iframe 文档已启用 Target，然后在 VEC 中加载该 iframe URL。

您可以使用页面顶部的下拉菜单来查看您的页面，因为它会显示给不同的受众或具有不同的体验。您可以在第二个下拉列表中为每个体验提供一个名称。例如，如果您要测试导航栏中主页链接的位置，则可以将主页链接显示在最前面的体验命名为诸如“主页链接”之类的名称，以便轻松地在列表中识别体验。

>[!NOTE]
>
>如果对页面结构所做的更改会影响在该页面上创建的活动中所使用的位置，则可能会导致编辑体验时出现问题。如果在 VEC 之外更改了某个位置，则 Target 可能无法找到内容发生了更改的位置。

当您在页面上移动鼠标时，上下文相关的框会跟随光标，高亮显示页面上的元素。

![VEC 高亮显示](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

单击&#x200B;**[!UICONTROL 叠加]**&#x200B;图标可更改高亮显示的方式。例如，你可以选择仅高亮显示图像、链接、区域 mbox、修改或 JavaScript。您可以更改高亮显示的颜色。您还可以指定高亮显示颜色和用于高亮显示不同元素类型的填充类型。

![更改“叠加”设置](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

单击高亮显示的元素可查看可用于该元素类型的选项菜单。例如，您可以单击图像并选择&#x200B;**[!UICONTROL 编辑 &gt; 文本/HTML]** 以更改文本，或单击按钮以更改背景颜色。您可以使用页面左上角的按钮来打开和关闭叠加。

您还可以单击&#x200B;**[!UICONTROL 浏览]**，然后导航到可从主页面访问的某个页面（例如送货页面或购物车），然后测试该页面上的更改。您也可以访问悬停鼠标时显示的页面元素，例如弹出菜单和迷你购物车。浏览到相应的页面后，单击&#x200B;**[!UICONTROL 撰写]可编辑体验。**&#x200B;例如，您可能想要更改购物车下拉列表或一组图像的设计。

>[!NOTE]
>
>如果悬停状态依赖于 JavaScript，请确保未选中&#x200B;**[!UICONTROL 禁用 JavaScript]**。必须启用 JavaScript 才能编辑 JavaScript 元素。

有关 VEC 中可用选项的信息，请参阅[可视化体验编辑器选项](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

您可以在页面加载时（或在页面加载失败后）对页面执行某些修改，也可以在 VEC 中取消页面加载。有关详细信息，请参阅：

* [在页面加载时或页面加载失败后编辑页面](#loading)
* [在 VEC 中取消页面加载](#cancel-loading)

## 在页面加载时或页面加载失败后编辑页面 {#loading}

在 VEC 中加载页面之前，或者即使页面无法完全加载（例如，自定义代码不再可操作），您可以执行许多操。

在 VEC 中加载页面或页面加载失败后，您想要访问或编辑页面的一些原因：

* 要对页面进行简单的修改，例如添加自定义代码或更改体验名称
* 要从无法再访问的页面中复制现有的自定义代码
* 在知晓页面不会在 VEC 中加载的情况下，仍想要进行简单的编辑

在页面加载时（或页面加载失败后），[!UICONTROL 体验]面板、[!UICONTROL 修改]面板，以及体验顶部的设置（叠加、修改、配置等）均可访问。

下图显示，您可以在页面加载时插入自定义代码或执行其他操作：

![页面正在加载](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## 在 VEC 中取消页面加载 {#cancel-loading}

您可以在 VEC 中取消页面加载以解锁活动的编辑，而无需等待页面加载完成。此功能可节省时间，并且可帮助您更有效地进行简单的编辑或插入自定义代码，而无需等待 VEC 中的页面加载完成。

可能需要在 VEC 中取消页面加载的一些原因包括：

* 要对现有修改进行细微编辑
* 要删除一个或多个现有修改
* 要插入或编辑自定义代码
* 不适当地输入了错误的页面 URL
* 要在 VEC 中加载页面之前，启用或禁用 JavaScript
* 要向“页面交付”标准添加更多模板测试规则
* 要在通过 EEC 或仅 iframe 加载页面可能因页面不同而有所不同时，覆盖全局增强型体验编辑器 (EEC) 切换开关

在 VEC 中取消页面加载之后，您可以在活动中的体验之间进行切换，而无需等待页面加载完成。若要再次查看 VEC 中的页面，必须单击&#x200B;**[!UICONTOL 重新加载]**&#x200B;按钮。

>[!IMPORTANT]
>
>请注意，当通过选择在 VEC 中取消加载来编辑自定义代码或进行任何修改时，必须确保编码或更改已正确完成。确保执行正确的 QA，以保证您的自定义代码和任何其他修改可以按预期交付。

要在 VEC 中取消页面加载，请在页面加载时单击&#x200B;**[!UICONTROL 取消加载]**&#x200B;按钮。在当前编辑会话期间，页面不会在此活动的 VEC 中加载。

![“取消加载”按钮](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

要继续管理当前活动中的体验或添加新的修改，则必须单击&#x200B;**[!UICONTROL 重新加载]**&#x200B;按钮。

![“重新加载”按钮](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>此功能当前存在的已知问题将在下一版本中修复。有关更多信息，请参阅[已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#cancel)页面上的“在 VEC 中取消页面加载”。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 可视化体验编辑器（第 1 个，共 2 个）(7:17)

* 更改页面的内容
* 更改页面的布局

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=chi_hans)

### 可视化体验编辑器（第 2 个，共 2 个）(7:29)

* 重命名和复制体验
* 创建重定向体验
* 将活动定位到单个 URL 或一组 URL
* 创建多页面活动
* 预览和构建响应式网站的体验
* 使用叠加高亮显示元素类型

>[!VIDEO](https://video.tv.adobe.com/v/17401?captions=chi_hans)

### 办公时间：可视化体验编辑器

此视频是“[办公时间](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* VEC 如何工作
* 如何避免 VEC 中的常见问题
* 您可用于解决 VEC 问题的做法

>[!VIDEO](https://video.tv.adobe.com/v/20784/?captions=chi_hans)