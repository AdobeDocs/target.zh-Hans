---
keywords: Adobe Target；Co-worker；AI；技能；试验；推荐
title: Adobe Target的同事技能
description: 了解可用于Adobe Target的同事技能，包括活动发现、测试创建、分析、受众构成和建议疑难解答。
feature: Overview
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: 4b90f47050b63c7e1e6ac5019d45a7b99b3a33b8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%
---

# Adobe Target的同事技能 {#coworker-skills}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解可用于Adobe Target的同事技能，包括探索活动和受众、创建和配置测试、分析性能、撰写受众和管理推荐的技能。

>[!ENDSHADEBOX]

同事技能可帮助Adobe Target从业人员使用自然语言探索其测试和个性化计划、创建和配置活动、分析结果以及解决交付问题。 描述您想在同事聊天中做什么，然后在采取行动之前查看返回的推荐、配置或分析。

[!DNL Adobe Target] MCP工具和协同工作将单独进行记录，并提供不同的功能：

* [目标MCP](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md)记录直接MCP服务器公开的各个工具，包括其支持的活动类型、参数、权限以及读取或写入范围。
* [Co-worker](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/overview#target-activities-and-audiences)提供了一个单独的自然语言编排层，可以组合功能并应用其他工作流。

下表是对相关功能的高层次比较。

| 功能 | 目标MCP | Coworker |
| --- | --- | --- |
| 列出正在运行的实验、受众、选件或最近更改的项目 | 是 | 是 |
| 创建 Automated Personalization 活动 | 否 | 否 |
| 创建Target观众 | 是 | 是 |
| 创建Target VEC活动、体验定位活动或A/B测试 | 是 | 是 |
| 创建Target“推荐”活动 | 是 | 是 |
| 在Target中创建HTML或JSON选件 | 是 | 是 |
| 在Target活动中使用AEM内容片段 | 否 | 是 |
| 推荐正在使用的功能以及下一步要测试的功能 | 无建议或一般建议 | 是 |


## Target插件

**Target**&#x200B;插件下提供了以下技能：

* **目标浏览**

  提供Target实体（包括活动、受众、选件和相关配置）的只读发现、检查和计数功能。

>[!BEGINSHADEBOX]

*示例提示：*

* “列出我的活跃活动。”
* “当前运行着多少活动？”
* “显示此活动使用的受众和选件。”

>[!ENDSHADEBOX]

* **Target活动裁决**

  使用重要性计算和配置检查来确定活动是否已准备就绪、应等待更多数据、应停止还是需要修复。

>[!BEGINSHADEBOX]

*示例提示：*

* “我应该送出这个测试吗？”
* “此活动是否已准备好停止？”
* “当前活动配置是否有任何问题？”

>[!ENDSHADEBOX]

* **目标设计**

  创建和配置活动和选件，生成QA URL，以及创作或优化选件内容。

>[!BEGINSHADEBOX]

*示例提示：*

* “为主页创建A/B测试。”
* “为回访访客体验创建选件。”
* “为此活动生成QA URL。”

>[!ENDSHADEBOX]

* **目标VEC**

  创建和编辑可视化体验编辑器活动及其页面交付受众。

>[!BEGINSHADEBOX]

*示例提示：*

* “为主页创建VEC A/B测试。”
* “编辑我的VEC活动中的主页标题。”
* “为此VEC活动创建页面交付受众。”

>[!ENDSHADEBOX]

* **目标设置**

  指南完成A/B、体验定位或可视化体验编辑器活动创建，包括先决条件、计划、QA和激活。

>[!BEGINSHADEBOX]

    *示例提示：*
    
    *“帮助我创建第一个测试。”
    *“创建体验定位活动之前我需要什么？”
    *“指导我完成计划、QA和激活此活动。”

>[!ENDSHADEBOX]

* **Target Intelligence**

  审核Target项目中的风险、冲突、配置错误、卫生问题和快速入门。

>[!BEGINSHADEBOX]

*示例提示：*

* “审核我的Target活动。”
* “查找我的活动中的冲突或配置风险。”
* “哪些快速入选可以改善我的Target程序的运行状况？”

>[!ENDSHADEBOX]

* **目标策略专家**

  分析历史Target数据以了解入选模式，并推荐未来的测试。

>[!BEGINSHADEBOX]

*示例提示：*

* “我接下来应该根据过去的结果测试哪些内容？”
* “在我表现最好的测试中会出现哪些模式？”
* “根据此活动的结果建议后续测试。”

>[!ENDSHADEBOX]

* **目标测试计算器**

  规划A/B/n样本量、持续时间和可检测的转化和收入量度提升，并对多个比较进行Bonferroni校正。

>[!BEGINSHADEBOX]

*示例提示：*

* “我需要什么样本量？”
* “为了检测到5%的提升，我应该运行此A/B测试多长时间？”
* “我可以使用这种流量测量哪些可检测到的提升度？”

>[!ENDSHADEBOX]

* **目标Portfolio报表**

  提供只读、项目范围的性能汇总以及活动趋势和动因分析。

>[!BEGINSHADEBOX]

*示例提示：*

* “我的最好和最差的测试是什么？”
* “显示我的活动中的性能趋势。”
* “最近哪些活动获得了增长或失去了增长动力？”

>[!ENDSHADEBOX]

* **目标受众编辑器**

  根据自然语言描述或显式规则创建或编辑Target本地受众。

>[!BEGINSHADEBOX]

*示例提示：*

* “为回访移动访客创建受众。”
* “编辑此受众以包含来自自然搜索的访客。”
* “为查看定价页面的访客创建Target受众。”

>[!ENDSHADEBOX]

* **目标推荐**

  管理和使用Target Recommendations活动和配置。

>[!BEGINSHADEBOX]

*示例提示：*

* “创建‘推荐’活动。”
* “显示我的‘推荐’活动和配置。”
* “更新此‘推荐’活动的设置。”

>[!ENDSHADEBOX]

* **目标推荐诊断**

  诊断“推荐”交付、配置、目录和馈送问题。

>[!BEGINSHADEBOX]

*示例提示：*

* “为什么我的推荐没有显示？”
* “诊断此‘推荐’活动的信息源和目录配置。”
* “投放或配置问题是否会影响我的推荐？”

>[!ENDSHADEBOX]
