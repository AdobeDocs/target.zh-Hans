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
ht-degree: 33%
---
# [!DNL Target]简介


>[!CONTEXTUALHELP]
>id="target_sample_size_ab_daily_traffic"
>title="每日流量"
>abstract="每天有多少用户进入您的试验。 如果您不知道自己的每日流量，请选择上面的“流量”，计算机将使用您的其他输入值来为您求解。"

>[!CONTEXTUALHELP]
>id="target_sample_size_setup"
>title="设置测试"
>abstract="这些字段定义了A/B测试、您预期看到的内容以及您在结果中需要有多大的信心。 绑定到上面所选内容的字段将自动解析。 其余部分填入您的预期值。"

>[!CONTEXTUALHELP]
>id="target_sample_size_number_experiences"
>title="体验数量"
>abstract="试验中的变体数量，包括对照组。 A/B测试有两只手臂。 五个变量加上一个控制等于6。 为了维持统计能力，更多的武器需要相应更多的运输量。"

>[!CONTEXTUALHELP]
>id="target_sample_size_duration"
>title="A/B测试持续时间"
>abstract="您的试验将运行多少天。 较长的持续时间可让您的试验有更多的时间收集数据，从而可靠地检测更小的影响。 较短的持续时间需要较大的效果或更多的每日流量才能获得可靠的结果。"

>[!CONTEXTUALHELP]
>id="target_sample_size_minimum_detectable_effect"
>title="最小可检测效果"
>abstract="值得检测的最小改进，即您可以执行操作的最小量度变化。 这是提升度的大小，以百分比点表示，而不是相对于基线的百分比变化。 例如，如果您的基线是5%，并且提升1个百分点很重要，请输入1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_expected_improvement"
>title="预期改进"
>abstract="您预期试验将产生的改进。"

>[!CONTEXTUALHELP]
>id="target_sample_size_variance"
>title="变量"
>abstract="您的量度值是如何分布的，而不是其平均值。 点击率等量度（大多为0和1）具有低方差，而像每用户收入这样的量度（少数高消费者，许多低消费者）可能会具有高得多的方差。 如果不确定，则保留默认值1。"

>[!CONTEXTUALHELP]
>id="target_sample_size_confidence_level"
>title="置信度"
>abstract="你在多大程度上需要相信，结果在称之为真实之前并非只是随机的，这是统计显着性的临界值。 95%的置信水平意味着误报的概率至多为5%。 值越高，误报率越低，但需要的数据越多。"

>[!CONTEXTUALHELP]
>id="target_sample_size_statistical_power"
>title="统计功效"
>abstract="如果确实存在一种效应，则检测这种效应的概率，实验灵敏度。 80%的功率意味着有80%的机会发现实际效果。 较高的功率可减少误报，但需要更多的流量或较长的运行时间。"

>[!CONTEXTUALHELP]
>id="target_sample_size_traffic_mode"
>title="流量模式"
>abstract="用户如何进入您的试验。 连续：在实验持续时间内，用户每天进入。 当结果出现时，流量会自动转向性能更好的变体。"

>[!CONTEXTUALHELP]
>id="target_sample_size_metric_type"
>title="量度类型"
>abstract="您正在测量哪种量度。 百分比：将此用于单击或转化等二进制结果，其中每个用户既可以执行操作也可以不执行操作。 数字：将此用于收入或页面查看次数等量度，这些量度的值会因用户而有很大的差异。"

>[!CONTEXTUALHELP]
>id="target_sample_size_auto_daily_traffic"
>title="每日流量"
>abstract="每天有多少用户进入您的试验。 用于持续运行多天的连续实验，随着结果的传入，流量会自动转向性能更好的变量。"

>[!CONTEXTUALHELP]
>id="target_sample_size_baseline_metric_rate"
>title="基线度量速率"
>abstract="在试验开始前您当前的性能，控制臂平均值。 始终是必需的。 对于百分比量度，输入百分比：如果5%的访客点击了今天购买，请输入5。 对于计数量度，输入原始小数值。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="主要量度"
>abstract="主要指标将自动从报表设置中提取。 要进行更改，请修改目标和设置下的目标量度。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="假设验证"
>abstract="假设是您定义的声明，它解释了试验的预期结果。 包括所更改的内容和位置的描述，然后指明预计更改哪个量度以及如何更改。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_insights"
>title="分析"
>abstract="试验洞察是 AI 在试验数据达到统计显著性后得出的学习结果。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="机会"
>abstract="实验机会是人工智能建议的治疗想法，基于在您的实验屏幕截图和结果中找到的模式AI。"

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="处理详细信息"
>abstract="处理详细信息显示了用户符合某个处理条件时该处理条件的图像。 您可以查看这些图像以进行所有实验。 某些实验可能会要求您确认图像，或者在需要时替换图像。"

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

>[!VIDEO](https://video.tv.adobe.com/v/30323?captions=chi_hans)


