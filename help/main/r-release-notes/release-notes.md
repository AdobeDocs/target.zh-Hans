---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
TQID: https://experienceleague.adobe.com/-Unx6cVsw3wch2LJgPtvBYPe-10rdpiJ4v9F7tMSP08
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c74d8b09fba181fcded2f982d99a03f1e7f3a07a
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 29%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## [!DNL Target Standard/Premium] 26.7.4（2026年7月23日）

**报表**

+++查看详细信息

* **转化率图表不适用于特定的移动受众。** 修复了[!UICONTROL 转化率]图形未针对某些移动设备受众呈现的问题。 (TGT-55611)

* 从下拉列表中选择&#x200B;**时，“已查看mbox”转化目标不起作用。** 修复了从[!UICONTROL 目标和设置]中下拉列表为“已查看mbox”转化目标选择mbox时无法正确保存mbox名称，从而无法记录转化的问题。 (TGT-55588)

+++

**受众**

+++查看详细信息

* 受众库页面上的&#x200B;**布局问题。** 修复了在侧面导航折叠时在[!UICONTROL 受众库]页面上启用过滤器时发生的布局问题。 (TGT-55502)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **移动设备版本未正确加载。** 修复了[!UICONTROL 可视化体验编辑器]未提供刷新方式，导致移动设备视图无法正确加载的问题。 (TGT-54408)

* **编辑或删除修改操作不起作用。** 修复了无法从[!UICONTROL 编辑体验]视图编辑或删除修改的问题。 (TGT-55250)

* **活动加载后，浏览模式无响应。** 修复了以下问题：[!UICONTROL 浏览]模式对包含修改的体验无响应，从而阻止进一步的导航和创作。 (TGT-55306)

* **无法选择Salesforce LWC （影子DOM）中的元素。** 修复了[!UICONTROL 可视化体验编辑器]无法选择使用影子DOM嵌套在Salesforce Lightning Web组件中的元素的问题，从而导致“未找到选择器”错误。 (TGT-54956)

* **在[!UICONTROL 可视化体验编辑器]中出现重复的选件。** 修复了在活动创作UI中修改和选件间歇性重复显示的问题。 (TGT-55685)

+++

**管理**

+++查看详细信息

* **已将内容生成助理重命名为[!UICONTROL 生成内容]。** 已将“AI助手”内容生成功能重命名为[!UICONTROL 跨[!DNL Target]用户界面表面]生成内容。 (TGT-55689)

+++

**推荐**

+++查看详细信息

* **使用配置文件属性的基于热门程度的推荐。** [!DNL Target]现在支持按访客个人资料属性（如国家/地区、首选语言或成员级别）动态地对热门程度推荐、“查看次数最多”和“最畅销商品”进行分组。 (TAPER-7614)

* **推荐集合在[!UICONTROL 集合]和活动配置之间不匹配。** 修复了与[!UICONTROL 推荐] > [!UICONTROL 收藏集]视图相比，从活动配置查看时，[!UICONTROL 推荐]收藏集返回了额外的不符合条件的实体的问题。 (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2（2026年7月16日）

**活动**

+++查看详细信息

* **[!UICONTROL 活动概述]页面上的目标信息不正确。** 修复了[!DNL Automated Personalization]活动的[!UICONTROL 活动概述]页面显示其他目标而非优化目标的问题。 (TGT-55553)

* 在[!UICONTROL 浏览]模式下导航页面时，**屏幕无响应。** 修复了在[!UICONTROL 浏览]模式下的页面之间导航时，屏幕无响应的问题。 (TGT-55565)

+++

**主页**

+++查看详细信息

* [!UICONTROL 最佳执行者]和[!UICONTROL 保存]的&#x200B;**UI更改。** 更新了表现最好的UI并保存体验。 (TGT-54975)

+++

**受众**

+++查看详细信息

* **在[!UICONTROL 创建配置文件脚本]对话框中未本地化的字符串。** 修复了[!UICONTROL 创建配置文件脚本]对话框中的字符串未本地化的问题。 (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1（2026年7月9日）

**活动**

+++查看详细信息

* **在[!UICONTROL 活动]、[!UICONTROL 受众]和[!UICONTROL 选件]页面中显示源不一致。** 修复了源在[!UICONTROL 活动]、[!UICONTROL 受众]和[!UICONTROL 选件]页面中显示不一致的问题。 (TGT-55247)

* 通过UI编辑时&#x200B;**活动源更改。** 修复了通过UI编辑活动会更改原始活动源的问题。 (TGT-55248)

+++

**受众**

+++查看详细信息

* **编辑受众时默认工作区不正确。** 修复了在编辑受众后默认工作区不正确的问题。 (TGT-55510)

+++

**报表**

+++查看详细信息

* 5月报告的&#x200B;**CSV下载失败。** 修复了下载5的CSV报表失败的问题。 (TGT-55524)

+++

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

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
