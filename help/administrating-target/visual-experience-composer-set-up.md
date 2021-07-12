---
keywords: 可视化体验编辑器；VEC；默认URL；增强型体验编辑器；EEC；混合内容；体验快照；移动设备视区；CSS;CSS选择器
description: 了解如何通过指定Adobe的常规设置、移动设备视区配置和CSS选择器来配置体验 [!DNL Target] 可视化体验编辑器(VEC)。
title: 如何配置可视化体验编辑器(VEC)?
feature: 管理和配置
role: Admin
exl-id: cf6c9ece-6745-477e-81ac-a3e9a9fddb09
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 50%

---

# 配置可视体验编辑器

通过指定[!DNL Adobe Target] [!UICONTROL 可视化体验编辑器](VEC)的常规设置、移动设备视区配置和CSS选择器来配置 。

要访问[!UICONTROL 可视化体验编辑器]配置页面，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]。**

>[!NOTE]
>
>请注意，此页面上的设置适用于整个[!DNL Target]帐户。

![可视化体验编辑器配置页面](/help/administrating-target/assets/vec.png)

## 一般设置

您可以为可视化体验编辑器指定常规设置。

![“常规设置”部分](/help/administrating-target/assets/general-settings.png)

以下设置可供使用：

### 默认URL

选择[!UICONTROL 可视化体验编辑器]使用的默认 URL。这是您每当为各个新活动设置体验时所使用的默认页面（例如主页）。如果未设置默认的 URL，您在创建各个活动时必须为活动输入 URL。

### 启用增强型体验编辑器 {#eec}

允许在防 iFrame 嵌套网站和具有混合内容的网站上进行编辑。某些网站可能与增强版本不兼容。 取消选中此选项可还原到原始的[!UICONTROL 可视化体验编辑器]。 所做的这一选择不会对网站上的活动交付造成任何影响。

有关更多信息，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

您还可以在活动级别启用[!UICONTROL 增强型体验编辑器]。

### 加载混合内容

使用[!UICONTROL 增强型体验编辑器](EEC)打开网站时启用混合内容。 启用此选项可避免通过[!DNL Target]代理服务器加载静态资源所产生的额外开销。

例如，如果：

* 您的内容安全策略(CSP)标头允许在启用EEC的情况下，无需使用代理服务器即可加载混合内容。
* 在EEC中，您的HTTP网站加载时间会增加，其中通过代理加载JavaScript、图像等所需的时间会更长。

### 在活动流程图中生成体验快照

启用体验快照后，活动工作流程图中会生成体验的缩览图。但对于某些用户而言，禁用体验快照可能会提高性能。

## ![Premium徽章移](/help/assets/premium.png) 动设备视区配置

您可以添加预览体验时要使用的设备。每个设备都有一个关联的受众。

![移动设备视区配置部分](/help/administrating-target/assets/mobile-viewport-configuration.png)

单击&#x200B;**[!UICONTROL 添加]**，为移动设备视区指定描述性名称，指定宽度和高度，选择所需的操作系统，然后单击[!UICONTROL 保存]。

有关如何添加移动设备视区的信息，请参阅[移动设备视区配置](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

## CSS 选择器 {#css}

指定 [!DNL Target] 生成 CSS 选择器的方式。

![CSS选择器部分](/help/administrating-target/assets/css-selectors.png)

以下选项有助于 [!DNL Target] 了解您的网站结构，从而生成更适用于内容交付的 CSS 选择器。默认情况下，[!DNL Target] 会根据页面上的元素 ID 生成选择器。如果您的网站使用很少的 ID，或在同一页面上使用重复的 ID，则使用类可能是更好的选择。

您可以选择下列任一选项或两个选项都选择：

### 使用元素 ID

如果多个元素使用同一个 ID，或元素 ID 在页面加载时可能会发生更改，请取消选择此选项。

### 使用元素类

默认情况下，[!DNL Target] 仅使用元素 ID。但是，如果您的页面设计为使用类来标识元素（例如通过 [!DNL Adobe Experience Manager] 构建的页面），则您还应当选择[!UICONTROL 使用元素类]。

>[!NOTE]
>
>尽管已采取各种措施来确保准确性，但请注意，使用类可能会导致错误。 如果您未选择任何选项，准确性也会受到影响。准确性由高到低的顺序为：选择 ID > 选择类 > 未选择任何选项。请务必测试页面，以确保选择器正确无误。

您可以为每个活动覆盖此设置（单击“设置”齿轮图标，然后选择 [!UICONTROL CSS 选择器]）。如果您使用不同的方式配置了多个网站，此操作会特别有用。

>[!NOTE]
>
>在[!UICONTROL Automated Personalization]和[!UICONTROL Multivariate Testing]活动中，无法为每个活动覆盖该设置。  请参阅[可视化体验编辑器中使用的元素选择器](/help/c-experiences/c-visual-experience-composer/vec-selectors.md)，以了解更多有关选择器的信息。

## 培训视频：帐户首选项(7:33) ![概述徽章](/help/assets/overview.png)

以下视频包含有关帐户首选项的信息。

* 介绍 [!DNL Target Standard] 中可用的帐户设置

>[!NOTE]
>
>[!DNL Target] [!UICONTROL 管理]菜单UI（以前称为[!UICONTROL 设置]）经过重新设计，可提供更高的性能、减少发布新功能时所需的维护时间，并改善整个产品的用户体验。 以下视频中的信息通常正确；但是，选项的位置可能略有不同。 更新的视频将很快发布。

>[!VIDEO](https://video.tv.adobe.com/v/17379)
