---
keywords: Target Standard;推荐;Target Premium;自动个性化;自动定位;自动定位;权限;adobe target 是什么;
description: 了解 Adobe [!DNL Target] Standard 和 Adobe [!DNL Target] Premium 的基础知识。[!DNL Target] Premium 包含标准产品中不提供的高级功能。
landing-page-description: 使您的客户体验个性化以尽可能提高您的网站和移动网站、应用程序、社交媒体和其他数字渠道的收入。
short-description: 个性化客户体验以最大限度地提升网站和移动站点、应用程序、社交媒体和其他数字渠道的收入。
title: 什么是 Target？
feature: Overview
exl-id: 0e729c71-618b-4ab8-93a3-d37e73ec2740
TQID: https://experienceleague.adobe.com/Mr8fwY1FNfJShSezC50YX1QeBagmuovUySsQUO8jPqo
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 2cecb1f8ae52fd6c47e543710bb14e00503c06ef
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 70%
---
# [!DNL Target]简介


>[!CONTEXTUALHELP]
>id="target_sample_size_ab_daily_traffic"
>title="每日流量"
>abstract="每天参与试验的用户数量。 如果您不清楚每日流量，请在上方选择“流量”，计算器将根据您输入的其他值自动计算每日流量。"

>[!CONTEXTUALHELP]
>id="target_sample_size_setup"
>title="设置测试"
>abstract="这些字段用于定义 A/B 测试、预期结果以及所需的结果置信度。 系统将自动计算与您在上方所选项目对应的字段值。 请在其余字段中填写预期值。"

>[!CONTEXTUALHELP]
>id="target_sample_size_number_experiences"
>title="体验数量"
>abstract="试验中的变体数量，包括对照组。 A/B 测试包含 2 个试验组。 5 个变体加上 1 个对照组，共计 6 个试验组。 试验组越多，所需流量也越大，且需按比例增加，以维持统计功效。"

>[!CONTEXTUALHELP]
>id="target_sample_size_duration"
>title="A/B 测试持续时间"
>abstract="试验将运行的天数。 持续时间越长，试验收集数据的时间就越充足，从而能够可靠地检测出更小的效应。 持续时间较短时，需要更大的效应或更多的每日流量，才能得出可靠的结果。"

>[!CONTEXTUALHELP]
>id="target_sample_size_minimum_detectable_effect"
>title="最小可检测效应"
>abstract="值得检测的最小提升幅度，即足以促使您采取行动的最小量度变化幅度。 此处指以百分点表示的提升幅度，而非相对于基准值的百分比变化。 例如，如果基准值为 5%，且提升 1 个百分点就有实际意义，请输入 1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_expected_improvement"
>title="预期提升幅度"
>abstract="您预期试验带来的提升幅度。"

>[!CONTEXTUALHELP]
>id="target_sample_size_variance"
>title="变量"
>abstract="量度值的离散程度，而非其平均值。 点进率这类量度（取值主要为 0 和 1）的变量较小，而每用户收入这类量度（少数用户消费金额高，多数用户消费金额低）的变量则可能大得多。 如果不确定，请保留默认值 1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_confidence_level"
>title="置信度"
>abstract="在认定结果反映真实效应之前，您需要多大程度的把握来确认该结果并非偶然产生，即统计显著性的判定阈值。 95% 的置信度意味着出现假阳性结果的概率不超过 5%。 置信度越高，出现假阳性结果的概率就越低，但所需的数据也越多。"

>[!CONTEXTUALHELP]
>id="target_sample_size_statistical_power"
>title="统计功效"
>abstract="当效应确实存在时检测出该效应的概率，即试验的灵敏度。 80% 的统计功效意味着有 80% 的概率检测出真实存在的效应。 统计功效越高，出现假阴性结果的概率就越低，但需要更多流量或更长的运行时间。"

>[!CONTEXTUALHELP]
>id="target_sample_size_traffic_mode"
>title="流量模式"
>abstract="用户参与试验的方式。 持续：在试验运行期间，每天都有用户参与试验。 随着试验结果不断产生，流量会自动向表现更好的变体倾斜。"

>[!CONTEXTUALHELP]
>id="target_sample_size_metric_type"
>title="量度类型"
>abstract="您要衡量的量度类型。 百分比：适用于点击或转化等二元结果，即每位用户只有执行或未执行某项操作两种情况。 数值：适用于收入或页面浏览量等量度，这类量度的值可能因用户而异，差异较大。"

>[!CONTEXTUALHELP]
>id="target_sample_size_auto_daily_traffic"
>title="每日流量"
>abstract="每天参与试验的用户数量。 适用于持续运行多天的试验。在此类试验中，随着试验结果不断产生，流量会自动向表现更好的变体倾斜。"

>[!CONTEXTUALHELP]
>id="target_sample_size_baseline_metric_rate"
>title="基准量度值"
>abstract="试验开始前的当前表现，即对照组的平均值。 此字段始终为必填项。 对于百分比量度，请输入百分数：例如，如果目前有 5% 的访客点击“立即购买”，请输入 5。 对于计数量度，请直接输入原始数值（可含小数）。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="主要量度"
>abstract="主要量度会自动从报表设置中获取。 如需更改，请修改“目标和设置”中的目标量度。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="假设验证"
>abstract="假设是您定义的一项陈述，用于说明试验的预期结果。 请描述要更改的内容及其位置，然后说明您预期哪个量度会发生变化，以及具体如何变化。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_insights"
>title="分析"
>abstract="试验洞察是指在试验数据达到统计显著性后，AI 从中发现的有价值的信息。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="机会"
>abstract="试验机会是指 AI 根据在试验屏幕截图和结果中发现的规律，提出的试验处理方案构想。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="试验处理方案详情"
>abstract="试验处理方案详情通过图像展示用户符合方案适用条件时所看到的实际效果。 您可以查看所有试验的这些图像。 某些试验可能会要求您确认图像，或在必要时进行替换。"

作为[!DNL Adobe Experience Cloud]的一部分，[!DNL Adobe Target]提供全面的工具，以个性化跨Web、移动站点、应用程序、社交媒体和其他数字渠道的客户体验。

[!DNL Target]有助于最大限度地增加收入，并且可以许可为[!DNL Target Standard]或[!DNL Target Premium]。

## [!UICONTROL Target Standard] {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard]是[!DNL Adobe Target]的前端，支持可视创建和管理A/B测试以及基于规则的定位活动。 [!DNL Target]支持在[[!UICONTROL 可视化体验编辑器]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)工作流内外的自定义代码插入。 [!DNL Target Standard]为您的数字财产提供简化的实施策略，每个页面上有一行代码管理您的网站与[!DNL Target]之间的所有通信。

行业最佳实践已集成到[!DNL Target Standard]中，因此既适合新用户，也适用于经验丰富的用户。 您可以使用[!DNL Adobe Experience Cloud]轻松地与团队成员共享数据、结果和协作。

## [!DNL Target Premium] {#premium}

[!BADGE 高级]{type=Positive}

[!DNL Target Premium]是高级产品，需要许可证才能向[!DNL Target Standard]添加高级功能。 [!DNL Target]指南中的所有[!DNL Target Premium]文章都在每个页面的顶部或受影响文本附近的内联包含[!UICONTROL Premium]徽章。 [!UICONTROL Premium]徽章可点击，且链接至此部分。

**[!DNL Target Premium]包括以下功能：**

### [!UICONTROL 自动个性化]

[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) (AP)使用高级机器学习算法来提供个性化体验并提高数字交互的转化率。

AP记录访客活动，生成配置文件以将内容定位到类似的访客。 AP跟踪个人和群体对内容的响应，使用复杂的建模根据关于访客的所有已知信息自动定位每个访客。

AP是完全自动化的，以最少的人工分析持续学习。 它构建各种模型以确定访客可能对哪些产品感兴趣，并收集和存储访客配置文件中的信息。 多个算法可确保为系统提供最佳模型。

### [!UICONTROL Auto-Target（自动定位）]

[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)使用高级机器学习识别营销人员定义的高性能体验。 然后，它根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验。 [!UICONTROL 自动定位]有助于使内容个性化并促进转化。

### 推荐

[“推荐”活动可根据以往用户活动自动显示客户可能感兴趣的产品或内容。](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) [!UICONTROL 推荐]有助于将客户导向到他们可能不知道的相关项目。

推荐可根据客户在网站上的活动来确定向该客户推广产品的方式。 例如：

* 鼓励购买了背包的人也考虑购买登山鞋和登山杖。

  使用“购买了这个项目，也购买了那个项目的人”标准，创建一个推荐来显示通常一起购买的项目。

* 向访客推荐与其当前正在观看的视频内容相似的内容，以增加访客在媒体网站上的停留时间。

  使用“查看了这个项目，也查看了那个项目的人”标准，创建一个推荐来推荐其他视频。

* 建议查看有关银行储蓄计划信息的客户也阅读 IRA 帐户相关信息。

  使用“查看了这个项目，但购买了那个项目的人”标准，显示人们查看某个产品后购买的其他产品，而不显示推荐中的第一个产品。

### “推荐”作为产品建议

[推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)允许您在[!UICONTROL A/B测试]、[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 体验定位] (XT)活动中包含推荐。

此功能提供了几项全新的功能，例如：

* 可在同一活动中测试和锁定推荐和非推荐内容。
* 可轻松尝试在页面上放置推荐内容，包括为多个推荐排序。
* 使用[!UICONTROL 自动分配]自动将流量推送到性能最佳的推荐体验。
* 使用[!UICONTROL 自动定位]根据个人资料动态地为访客分配量身定制的推荐体验。

### 企业用户权限

通过[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838)功能，可创建不同的项目（在 [!DNL Adobe Admin Console for Enterprise] 中称为“产品配置文件”）。 [!UICONTROL 企业用户权限]允许您为单个用户分配不同的权限，这些权限规定该用户对每个项目的访问权限。 这些不同的项目好比 [!DNL Adobe Analytics] 中各个报表包的工作方式。 每个项目都可以拥有其特定用户，而这些用户可以具有适用于一组属性的特定角色。 结果是客户可限制其用户的查看、编辑、批准和发布访问权限。 可根据区域、环境（开发/暂存/生产）、渠道或其他自定义标准限制用户。

## Beta功能 {#beta}

[!BADGE Beta]{type=Informative}

[!DNL Adobe Target]团队经常为选定的客户启用新功能以进行测试和提供反馈。 在测试期结束后，将在未来[!DNL Target Standard/Premium]版本中为所有客户启用这些功能，并在发行说明中宣布。

在介绍Beta功能的[!DNL Target]指南中，文章包括在每页顶部或受影响文本附近的内联Beta徽章。 Beta徽章可单击，并包含指向此部分的链接。

## 经典版推荐 {#section_9554068100054D2DBDB298CBE5A0E413}

>[!IMPORTANT]
>
>[!DNL Recommendations Classic] 是一个旧版产品，不再许可给新客户。 为了获得最佳的 [!DNL Recommendations] 体验，请升级到 [!DNL Adobe Target Premium] 中提供的 [!DNL Recommendations] 活动，如上所述。

[!DNL Recommendations Classic] 可根据网站上以往的用户活动自动显示客户可能感兴趣的产品或内容。 推荐可帮助将用户定向到若没有推荐他们可能无法了解到的项目，从而提高网站所产生的收入。

有关更多信息，请参阅 [Recommendations Classic 文档](/help/main/assets/adobe-recommendations-classic.pdf)。

## Experience League： Adobe [!DNL Target]欢迎套件 {#kit}

用此欢迎套件在 [!DNL Adobe Target] 上构建您的优化和个性化项目。 该欢迎套件包括关键信息、工具和资源，以帮助您准备和启动您的第一个 [!DNL Target] 活动。 该套件包括短期快速入选和长期优化策略的想法。

[Adobe Target欢迎套件](/help/main/c-intro/target-welcome-kit.md)

## 培训视频：活动类型(9:03) ![概述徽章](/help/main/assets/overview.png)

以下视频介绍 [!DNL Target Standard/Premium] 中提供的活动类型以及 [!DNL Target] 三步引导式工作流程可怎样帮助您实现网站目标。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)


