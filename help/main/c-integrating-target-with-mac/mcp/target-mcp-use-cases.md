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
hide: true
source-git-commit: ecb51d828807735b990b8f3a52102feb005bc61b
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# [!DNL Adobe Target] MCP服务器 — 用例和演练 {#target-mcp-use-cases}

>[!BEGINSHADEBOX]

目录：

* [概述](target-mcp.md)
* [快速入门](target-mcp-get-started.md)
* **[用例和演练](target-mcp-use-cases.md)**
* [MCP服务器工具参考](target-mcp-tools-reference.md)

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

本页显示了使用自然语言提示对[!DNL Adobe Target] MCP服务器所能完成的操作，从快速查找到多步骤活动管理任务。

## 用例 {#mcp-use-cases}

以下示例显示如何使用自然语言与[!DNL Adobe Target] MCP服务器交互：

| 目标 | 示例提示 |
|---|---|
| **试验状态审核** | “当前在主页上有哪些A/B测试处于活动状态？ 向我显示状态、流量分配，以及每个流量已运行的时长。” |
| **绩效审核** | “向我显示所有已达到统计意义的活动测试 — 哪些体验入选？” |
| **收入分析** | “获取活动AT4821的订单和收入报表，并总结哪个体验为每位访客带来了最大的收入。” |
| **A4T 报表** | “提取A4T报告用于我的签出优化测试，并汇总Analytics端转化数据。” |
| **活动管理** | “暂停活动98765并将活动的优先级更新11111200。” |
| **活动分析** | “了解我的‘夏季促销横幅’测试 — 性能是什么样的，是否存在任何异常？” |
| **受众管理** | “列出所有以移动用户为目标的受众，并向我展示他们关联的活动。” |
| **QA和预览** | “为活动12345生成QA预览URL，以便我可以在激活之前查看所有变体。” |
| **推荐审核** | “列出此帐户中配置的所有推荐标准，并汇总正在使用的算法类型。” |
| **实施审核** | “配置的at.js版本以及当前活动的响应令牌是什么？” |
| **更改审核** | “向我显示过去30天内对活动98765所做的所有更改以及谁进行了更改。” |

## 用例演练 {#mcp-use-case-walkthroughs}

以下演练说明如何在[!DNL Adobe Target] MCP服务器上使用自然语言提示完成常见任务。

+++创建A/B测试

**提示：**
“使用两种体验创建名为‘主页主页主页主页主页图像测试’的A/B测试：‘控制’显示当前主页，而‘变量’显示新的夏季主题主页图像。 定位主页mbox。”

AI助手使用`create_ab_activity`工具创建具有您描述的配置的活动。 该工具会返回新活动ID和对已创建体验的确认。

+++

+++检查活动性能

**提示：**
“向我显示过去30天内我的‘签出流优化’活动的性能量度。”

AI助手使用`get_ab_performance_report`或`get_xt_performance_report`（取决于活动类型）检索指定时间范围的转化率、访客计数和其他量度。

+++

+++管理优惠

**提示：**
“创建一个名为‘夏季促销横幅’的HTML优惠，该优惠的促销横幅上写着‘所有夏季商品20%的折扣’。”

AI助手使用`create_target_offer`工具创建具有您指定的HTML内容的选件，并返回具有新选件ID的确认。

+++

+++构建受众

**提示：**
“创建一个名为‘来自加利福尼亚的移动访客’的受众，该受众定位位于加利福尼亚的移动设备上的用户。”

AI助手使用`create_target_audience`工具以及从您的描述派生的相应定位规则。

+++

+++生成QA预览链接

**提示：**
“为活动12345生成预览URL，以便我测试每个体验。”

AI助手使用`preview_activity`工具生成绕过受众定位的可点击URL，从而让您直接在浏览器中查看每个体验。

+++

+++创建体验定位活动

**提示：**
“创建一个名为‘地域Personalization’的体验定位活动，向来自不同地区的访客显示不同的主页横幅。”

AI助手使用`create_xt_activity`根据您描述的区域，通过基于受众的体验映射来构建活动。

+++

+++计划活动

**提示：**
“更新活动12345的时间表，从5月1日开始，到5月31日结束。”

AI助手使用`update_activity_schedule`工具将新的开始日期和结束日期应用于活动。

+++

## 相关资源 {#mcp-use-cases-related}

* [概述](target-mcp.md)
* [快速入门](target-mcp-get-started.md)
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
