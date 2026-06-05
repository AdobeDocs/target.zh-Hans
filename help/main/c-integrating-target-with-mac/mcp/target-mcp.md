---
solution: Target
product: target
title: Adobe Target MCP服务器概述
description: 了解Adobe Target MCP服务器是什么、其关键功能以及它如何连接到AI助手。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 40e87a3a70d51ccda99f046609ba9633719ea540
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 0%

---

# [!DNL Adobe Target] MCP服务器 {#target-mcp}

[!DNL Adobe Target] MCP集成允许您直接从AI助手检查、分析和管理A/B测试和个性化活动。 将[!DNL Target]的试验数据和个性化数据转换为纯语言的工作流 — 审核您的试验组合、审查性能报表、浏览受众和选件、创建活动并进行更新，而无需导航UI或编写API调用。

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器可用于&#x200B;**公共Beta**&#x200B;中的所有客户。 当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支持它。 未来版本中将增加对其他MCP兼容应用程序的支持。


## 什么是模型上下文协议？ {#mcp-overview}

营销和优化团队越来越依赖基于聊天的应用程序和开发人员工具（如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）来简化日常工作。 这些应用程序支持&#x200B;**模型上下文协议(MCP)**，这是一个开放标准，允许应用程序以统一的方式向大型语言模型(LLM)公开后端工具。

[!DNL Adobe Target]现在提供了一个MCP服务器，该服务器直接在任何与MCP兼容的应用程序中呈现实验和个性化操作。 [!DNL Adobe Target]充当决策和执行层，而AI助手处理推理和解释，使团队无需导航多个产品屏幕或针对[!DNL Adobe Target] REST API编写查询，即可更快地访问优化见解。


>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 主要功能 {#mcp-capabilities}

[!DNL Adobe Target] MCP服务器提供对活动、受众、选件和实施配置的读写访问权限。 通过集成，您可以：

* **检查和审核实验** — 获取任何活动的状态、性能、更改历史记录和QA预览链接，而无需浏览UI。
* **分析结果** — 检索A/B、XT、AP和自动定位活动的性能、收入和A4T报表。
* **浏览活动** — 列出、检查和分析A/B和XT活动。
* **创建和更新活动** — 创建新的A/B和体验定位活动、更新配置、管理流量拆分、添加或删除变体以及控制活动状态（激活、暂停、停用）。
* **浏览和管理受众和选件** — 列出、检查、创建和更新受众、HTML选件和JSON选件。
<!-- * **Explore Recommendations criteria** - List and inspect criteria and cart-based algorithms. -->
* **审核实施** — 查看at.js设置、响应令牌和每个实体的修订历史记录。

[!DNL Adobe Target] MCP服务器公开跨10个类别的41个工具 — 从活动创建和报告到受众管理和QA预览。 有关完整的参数引用，请参阅[MCP服务器工具引用](target-mcp-tools-reference.md)。

要了解您可以使用[!DNL Adobe Target] MCP服务器做什么 — 包括逐步提示演练 — 请参阅[用例和演练](target-mcp-use-cases.md)。

要将[!DNL Adobe Target] MCP服务器连接到AI助手（包括先决条件、特定于客户端的配置以及疑难解答），请参阅[入门](target-mcp-get-started.md)。

## 常见问题解答 {#mcp-faq}

+++支持哪些MCP客户端？

[!DNL Adobe Target] MCP服务器当前可用于&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**。 未来版本中可能会添加对其他MCP兼容应用程序的支持。
+++

+++我可以通过MCP访问哪些[!DNL Adobe Target]对象？

您可以访问和管理活动(A/B、XT、AP)、受众、选件、属性、mbox、响应令牌、at.js配置、A4T报告和实体修订历史记录。 MCP服务器公开了41种工具，包括读取和写入操作。
+++

+++MCP服务器是否可以创建或修改活动？

是. MCP服务器支持写入操作，包括创建A/B活动和体验定位活动、更新活动配置、管理流量拆分、添加或删除变体、激活、暂停和停用活动。 写入操作需要编辑器角色或更高版本；激活和停用操作需要审批者角色。
+++

+++要使用MCP服务器，是否需要开发人员访问权限？

否. MCP服务器专为营销和技术人员而设计。 营销人员可以在任何受支持的MCP客户端中使用自然语言提示与其交互，而开发人员可以在克劳德代码或光标等工具中使用它。
+++

+++我的[!DNL Adobe Target]数据是否已发送到MCP客户端提供程序？

当您提交提示时，MCP客户端可能会将相关上下文（包括MCP服务器返回的[!DNL Adobe Target]数据）发送到其模型以供处理。 在连接到生产数据之前，请查看MCP客户端提供商的隐私和数据处理策略。 Adobe的数据处理受[Adobe隐私政策](https://www.adobe.com/privacy.html)和[数据保护条款](https://www.adobe.com/go/dpt-ww)管辖。
+++

+++写入操作能否对实时活动造成意外更改？

编写工具包括安全注释和确认审核，这样无需明确的用户确认即不会执行任何状态更改操作。 Adobe建议先在沙盒环境中测试集成，然后再在生产中使用写入工具，并且在确认集成之前仔细查看所有MCP启动的操作。
+++

+++我需要在[!DNL Adobe Target]中拥有哪些权限？

**观察者**&#x200B;角色或更高角色授予对所有只读工具的访问权限。 写入工具（创建、更新）需要&#x200B;**编辑者**&#x200B;角色或更高版本。 状态更改工具（激活、停用）需要&#x200B;**审批者**&#x200B;角色。 如果您不确定当前的访问级别，请联系您的[!DNL Adobe Target]管理员。
+++

+++我是否可以在多个Target组织或属性中使用MCP服务器？

MCP服务器将操作范围限定于与您的已验证Adobe IMS凭据关联的组织。 如果您有权访问该组织内的多个属性，则可以使用`list_target_properties`工具按属性进行查询并相应地筛选后续请求。
+++

## 相关资源 {#mcp-related}

* [快速入门](target-mcp-get-started.md)
* [用例和演练](target-mcp-use-cases.md)
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [光标文档](https://docs.cursor.com/){target="_blank"}
