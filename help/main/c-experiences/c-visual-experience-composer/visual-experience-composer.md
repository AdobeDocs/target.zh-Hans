---
keywords: 可视化体验编辑器；vec；wysiwyg
description: 了解在Adobe Target中使用可视化体验编辑器(VEC)的基础知识。 VEC是一个WYSIWYG编辑器，可让您轻松创建个性化体验。
title: 如何使用可视化体验编辑器(VEC)？
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL 可视化体验编辑器] (VEC)

[!DNL Adobe Target]中的[!UICONTROL 可视化体验编辑器] (VEC)是一个WYSIWYG编辑器，可直接在网站和移动网页上创建和测试个性化体验，而无需编辑代码。

通过拖放元素、交换内容以及更改页面布局，为[!DNL Target]活动创建体验和选件。 该编辑器还提供了用于编辑HTML和JavaScript的选项。

## 浏览器要求 {#browser-requirements}

[!DNL Adobe Target]接口支持[!DNL Safari]。 您可以在[!DNL Safari]中创建基于表单的活动，并使用除VEC和[!UICONTROL 增强型体验编辑器] (EEC)之外的所有功能。 如果您在[!DNL Safari]中打开可视化体验编辑器，则叠加会提示您切换到[!DNL Google Chrome]以编辑体验。

诸如[!DNL Firefox]之类的浏览器可能会阻止包含混合内容的页面在VEC中显示，例如，安全站点内的非安全页面。 如果页面未显示，请单击浏览器地址栏中URL旁边的图标，然后单击&#x200B;**[!UICONTROL 在此页面上禁用保护]**。 此问题不会影响页面向网站访客显示的方式。

## 打开VEC {#open-the-vec}

要设置默认在VEC中打开的页面，请在[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**&#x200B;选项卡上输入默认的[!UICONTROL 可视化体验编辑器] URL。

如果不设置默认URL，则VEC将打开并显示一个空白页面，您可以在其中指定URL。

![VEC 高亮显示](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## 编辑体验 {#edit-experiences}

### 查看和命名体验 {#view-and-name-experiences}

使用[!UICONTROL 体验]边栏中的选项卡查看您的页面向不同受众或不同体验的显示方式。 为每个体验提供一个描述性名称，以便于在列表中识别。

例如，在导航栏中测试Home链接的位置时，将其显示在首位的体验命名为“Home link first”。

![在体验边栏中重命名体验](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### 选择和修改元素 {#select-and-modify-elements}

将光标移动到页面上以使用上下文相关框突出显示单个元素。

单击高亮显示的元素以显示该元素类型的编辑选项。 例如，选择图像并单击&#x200B;**[!UICONTROL 更改图像源]**&#x200B;以替换该图像，或选择按钮以更改其文本颜色。

![编辑选定元素的选项](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

您无法编辑嵌入到页面中的iframe中的内容。 要编辑该内容，请确保iframe文档已启用[!DNL Target]，然后直接在VEC中加载iframe URL。

在VEC之外更改页面结构可能会影响活动使用的位置。 如果这些位置发生更改，[!DNL Target]可能无法找到您修改的元素，这可能会导致编辑体验时出现问题。

### 浏览和设计 {#browse-and-design}

单击&#x200B;**[!UICONTROL 浏览]**&#x200B;导航到可从当前页面访问的页面，如送货页面或购物车，并在该处测试更改。

VEC中的![浏览模式](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

在“浏览”模式下，您还可以访问悬停鼠标时显示的元素，如弹出菜单和迷你购物车。 当您到达要编辑的页面或元素时，单击&#x200B;**[!UICONTROL 设计]**&#x200B;以编辑体验。

如果悬停状态依赖于JavaScript，请确保未选择&#x200B;**[!UICONTROL 禁用JavaScript]**。 必须启用JavaScript才能编辑依赖它的元素。

有关可用编辑选项的详细信息，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)。

## 管理页面加载 {#manage-page-loading}

在页面加载时或页面加载失败后，某些编辑选项仍然可用。 您还可以取消页面加载以访问这些选项，而无需等待。

### 在页面加载时或页面加载失败后编辑页面 {#loading}

例如，您可以在页面完成VEC中的加载之前或页面加载失败之后进行某些更改，例如，因为自定义代码不再有效。

使用可用的编辑选项可以：

* 进行简单的更改，例如添加自定义代码或重命名体验
* 从无法再访问的页面中复制现有自定义代码
* 对无法在VEC中加载的页面进行简单编辑

在页面加载时或加载失败后，[!UICONTROL 体验]边栏、[!UICONTROL 组件]边栏和[!UICONTROL 配置]选项仍可访问。

### 在VEC中取消页面加载 {#cancel-loading}

在VEC中取消页面加载以编辑活动，而无需等待页面完成加载。

当您需要执行以下操作时，取消页面加载会很有用：

* 对现有修改进行细微编辑
* 删除一个或多个现有修改
* 插入或编辑自定义代码
* 更正错误输入的页面URL
* 在VEC中加载页面之前，启用或禁用JavaScript
* 将模板测试规则添加到[!UICONTROL 页面交付]条件
* 在通过EEC或仅iframe模式下加载页面时，覆盖全局[!UICONTROL 增强型体验编辑器] (EEC)切换开关

取消页面加载后，您可以在活动中的体验之间进行切换，而无需等待页面加载完成。 单击&#x200B;**[!UICONTROL 重新加载]**&#x200B;以再次在VEC中显示页面。

>[!IMPORTANT]
>
>如果在取消页面加载后编辑自定义代码或进行其他修改，请执行质量保证(QA)测试，以验证所做的更改是否按预期交付。

要停止加载页面，请在加载页面时单击&#x200B;**[!UICONTROL 取消加载]**。 在当前编辑会话期间，除非您重新加载页面，否则此活动的页面仍保持卸载状态。

单击&#x200B;**[!UICONTROL 重新加载]**&#x200B;以继续管理当前活动中的体验或添加新修改。
