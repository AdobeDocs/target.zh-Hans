---
keywords: 可视化体验编辑器；vec；wysiwyg
description: 了解在Adobe Target中使用可视化体验编辑器(VEC)的基础知识。 VEC是一个WYSIWYG编辑器，可让您轻松创建个性化体验。
title: 如何使用可视化体验编辑器(VEC)？
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 3f5b198ad08d85caa9c859171e78b710083e44fb
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 43%

---

# [!UICONTROL Visual Experience Composer] (VEC)

[!DNL Adobe Target]中的[!UICONTROL Visual Experience Composer] (VEC)是一个WYSIWYG编辑器，它允许客户直接在其网站或移动网页上创建和测试个性化体验，而无需编辑代码。

>[!NOTE]
>
>[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）版本包含VEC的更新版本。 有关更新的VEC与先前版本有何不同的信息，请参阅[可视化体验编辑器更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)。 有关更新的VEC中各种选项的概述，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

通过VEC，可在站点上下文中轻松创建和测试个性化体验和选件。 您可以通过拖放、交换和修改网页（或选件）或移动网页的布局和内容来为[!DNL Target]活动创建体验和选件。

VEC 是 [!DNL Target] 的主要功能之一。通过 VEC，营销人员和设计人员可以使用可视化界面创建和更改内容。无需直接编辑代码，便可进行多种设计选择。使用编辑器提供的编辑选项也可以编辑 HTML 和 JavaScript。

在[!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;选项卡上，您可以输入默认[!UICONTROL Visual Experience Composer] URL。

此 URL 可确定您打开 VEC 时的起始位置。如果不输入默认URL，则在打开编辑器时，将从空白页开始，然后可以指定URL。

![VEC 高亮显示](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>如果页面包含混合内容（例如，安全站点中的非安全页面），某些浏览器（如[!DNL Firefox]）可能会阻止页面在VEC中显示。 如果您的页面未显示，请单击浏览器地址栏中URL旁边的图标，然后单击&#x200B;**[!UICONTROL Disable protection on this page]**。 此问题不会影响向网站访客显示页面。

无法在 VEC 中修改页面上 iframe 中的内容。要编辑iframe中的内容，请确保iframe文档已启用[!DNL Target]，然后在VEC中加载该iframe URL。

您可以使用[!UICONTROL Experiences]边栏中的选项卡查看页面，查看页面对不同受众或不同体验的外观。 您可以为每个体验提供一个名称。 例如，如果您在导航栏中测试“主页”链接的位置，则可能会为首先显示“主页”链接的体验命名。 例如，“Home link”可让您更轻松地识别列表中的体验。

>[!NOTE]
>
>如果对页面结构所做的更改会影响在该页面上创建的活动中所使用的位置，则可能会导致编辑体验时出现问题。 如果在VEC之外更改了某个位置，[!DNL Target]可能无法找到内容被更改的位置。

当您在页面上移动鼠标时，上下文相关的框会跟随光标，高亮显示页面上的元素。

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

单击高亮显示的元素可查看可用于该元素类型的选项菜单。 例如，您可以单击某个图像并选择&#x200B;**[!UICONTROL Change Image]**&#x200B;将该图像更改为其他图像。 或者单击按钮并更改文本颜色。

您还可以单击&#x200B;**[!UICONTROL Browse]**，然后导航到可从主页面访问的某个页面（如送货页面或购物车），然后测试该页面上的更改。 您也可以访问悬停鼠标时显示的页面元素，例如弹出菜单和迷你购物车。浏览到页面后，单击&#x200B;**[!UICONTROL Design]**&#x200B;编辑体验。 例如，您可能想要更改购物车下拉列表或一组图像的设计。

>[!NOTE]
>
>如果悬停状态依赖于JavaScript，请确保未选择&#x200B;**[!UICONTROL Disable JavaScript]**。 必须启用 JavaScript 才能编辑 JavaScript 元素。

有关 VEC 中可用选项的信息，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

您可以在页面加载时（或在页面加载失败后）对页面执行某些修改，也可以在 VEC 中取消页面加载。有关详细信息，请参阅：

* [在页面加载时或页面加载失败后编辑页面](#loading)
* [在VEC中取消页面加载](#cancel-loading)

## 在页面加载时或页面加载失败后编辑页面 {#loading}

在 VEC 中加载页面之前，或者即使页面无法完全加载（例如，自定义代码不再可操作），您可以执行许多操。

在 VEC 中加载页面或页面加载失败后，您想要访问或编辑页面的一些原因：

* 要对页面进行简单的修改，例如添加自定义代码或更改体验名称
* 要从无法再访问的页面中复制现有的自定义代码
* 在知晓页面不会在 VEC 中加载的情况下，仍想要进行简单的编辑

在页面加载时（或页面加载失败后），[!UICONTROL Experiences]边栏、[!UICONTROL Components]边栏和[!UICONTROL Configure]选项可访问。

## 在VEC中取消页面加载 {#cancel-loading}

您可以在 VEC 中取消页面加载以解锁活动的编辑，而无需等待页面加载完成。此功能可节省时间，并且可帮助您更有效地进行简单的编辑或插入自定义代码，而无需等待 VEC 中的页面加载完成。

可能需要在 VEC 中取消页面加载的一些原因包括：

* 要对现有修改进行细微编辑
* 要删除一个或多个现有修改
* 要插入或编辑自定义代码
* 不适当地输入了错误的页面 URL
* 要在 VEC 中加载页面之前，启用或禁用 JavaScript
* 想要向[!UICONTROL Page Delivery]条件添加更多模板测试规则
* 要在通过EEC或仅限iframe加载页面时覆盖全局[!UICONTROL Enhanced Experience Composer] (EEC)切换开关

如果在VEC中取消页面加载，则可以在活动中的体验之间切换，而无需等待页面加载完成。 若要再次查看VEC中的页面，必须单击&#x200B;**[!UICONTROL Reload]**&#x200B;按钮。

>[!IMPORTANT]
>
>请注意，当通过选择在 VEC 中取消加载来编辑自定义代码或进行任何修改时，必须确保编码或更改已正确完成。确保执行正确的 QA，以保证您的自定义代码和任何其他修改可以按预期交付。

要在VEC中取消页面加载，请在页面加载时单击&#x200B;**[!UICONTROL Cancel Loading]**&#x200B;按钮。 在当前编辑会话期间，页面不会在此活动的 VEC 中加载。

要继续管理当前活动中的体验或添加新的修改，必须单击&#x200B;**[!UICONTROL Reload]**&#x200B;按钮。
