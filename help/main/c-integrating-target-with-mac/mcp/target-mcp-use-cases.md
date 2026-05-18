---
solution: Target
product: target
title: Adobe Target MCP服务器 — 用例和演练
description: 探索Adobe Target MCP服务器的常见用例和分步提示演练。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 53dc7056ca62339a682756fe1b39e6af349f3ae6
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---

# [!DNL Adobe Target] MCP服务器 — 用例和演练 {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器可用于&#x200B;**公共Beta**&#x200B;中的所有客户。 当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支持它。

本页显示了使用自然语言提示通过[!DNL Adobe Target] MCP服务器可以实现的目标，从快速查找到多步骤分析和报告任务。

>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 用例 {#mcp-use-cases}

以下示例显示如何使用自然语言与[!DNL Adobe Target] MCP服务器交互：

| 目标 | 示例提示 |
|---|---|
| **试验状态审核** | “当前在主页上有哪些A/B测试处于活动状态？ 向我显示状态、流量分配，以及每个流量已运行的时长。” |
| **绩效审核** | “向我显示所有已达到统计意义的活动测试 — 哪些体验入选？” |
| **收入分析** | “获取活动AT4821的订单和收入报表，并总结哪个体验为每位访客带来了最大的收入。” |
| **A4T报告** | “提取A4T报告用于我的签出优化测试，并汇总Analytics端转化数据。” |
| **活动分析** | “了解我的‘夏季促销横幅’测试 — 性能是什么样的，是否存在任何异常？” |
| **受众管理** | “列出所有以移动用户为目标的受众，并向我展示他们关联的活动。” |
| **QA和预览** | “为活动12345生成QA预览URL，以便我可以在激活之前查看所有变体。” |
<!-- | **Recommendations review** | "List all Recommendations criteria configured in this account and summarize the algorithm types in use." | -->
| **实施审核** |“配置了什么版本的at.js，哪些响应令牌当前处于活动状态？” |
| **更改审核** | “向我显示过去30天内对活动98765所做的所有更改以及谁进行了更改。” |

## 用例演练 {#mcp-use-case-walkthroughs}

以下演练说明如何在[!DNL Adobe Target] MCP服务器上使用自然语言提示完成常见任务。

<!--
+++Creating an A/B test

**Prompt:**
"Create an A/B test called 'Homepage Hero Image Test' with two experiences: 'Control' showing the current hero and 'Variant' showing a new summer-themed hero image. Target the homepage mbox."

The AI assistant uses the `create_ab_activity` tool to create the activity with the configuration you described. The tool returns the new activity ID and a confirmation of the created experiences.

+++
-->

+++检查活动性能

**提示：**
“向我显示过去30天内我的‘签出流优化’活动的性能量度。”

AI助手使用`get_ab_performance_report`或`get_xt_performance_report`（取决于活动类型）检索指定时间范围的转化率、访客计数和其他量度。

+++

<!--
+++Managing offers

**Prompt:**
"Create an HTML offer called 'Summer Sale Banner' with a promotional banner that says '20% off all summer items'."

The AI assistant uses the `create_target_offer` tool to create the offer with your specified HTML content and returns a confirmation with the new offer ID.

+++

+++Building an audience

**Prompt:**
"Create an audience called 'Mobile Visitors from California' that targets users on mobile devices located in California."

The AI assistant uses the `create_target_audience` tool with the appropriate targeting rules derived from your description.

+++
-->

+++生成QA预览链接

**提示：**
“为活动12345生成预览URL，以便我测试每个体验。”

AI助手使用`preview_activity`工具生成绕过受众定位的可点击URL，从而让您直接在浏览器中查看每个体验。

+++

<!--
+++Creating an Experience Targeting activity

**Prompt:**
"Create an Experience Targeting activity called 'Geo Personalization' that shows different hero banners to visitors from different regions."

The AI assistant uses `create_xt_activity` to build the activity with audience-based experience mapping according to the regions you describe.

+++

+++Scheduling an activity

**Prompt:**
"Update the schedule for activity 12345 to start on May 1st and end on May 31st."

The AI assistant uses the `update_activity_schedule` tool to apply the new start and end dates to the activity.

+++
-->

## 相关资源 {#mcp-use-cases-related}

* [概述](target-mcp.md)
* [快速入门](target-mcp-get-started.md)
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
