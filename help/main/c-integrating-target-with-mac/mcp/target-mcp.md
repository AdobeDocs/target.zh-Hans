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
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 0%

---

# [!DNL Adobe Target] MCP服务器 {#target-mcp}

[!DNL Adobe Target] MCP集成允许您直接从AI助手检查、分析和管理A/B测试、个性化活动和推荐标准。 将[!DNL Target]的读取和写入API转换为纯语言工作流 — 审核您的试验组合、审查性能报告、管理受众和选件，以及执行可控操作，而无需导航UI或编写API调用。

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器可用于&#x200B;**公共Beta**&#x200B;中的所有客户。 当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支持它。 未来版本中将增加对其他MCP兼容应用程序的支持。


## 什么是模型上下文协议？ {#mcp-overview}

营销和优化团队越来越依赖基于聊天的应用程序和开发人员工具（如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）来简化日常工作。 这些应用程序支持&#x200B;**模型上下文协议(MCP)**，这是一个开放标准，允许应用程序以统一的方式向大型语言模型(LLM)公开后端工具。

[!DNL Adobe Target]现在提供了一个MCP服务器，它可以在任何与MCP兼容的应用程序中直接显示实验、个性化和推荐操作。 [!DNL Adobe Target]充当决策和执行层，而AI助手处理推理和解释，使团队无需导航多个产品屏幕或针对[!DNL Adobe Target] REST API编写查询，即可更快地访问优化见解。


>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 主要功能 {#mcp-capabilities}

[!DNL Adobe Target] MCP服务器提供对活动、受众、选件、推荐和实施配置的读写访问权限。 通过集成，您可以：

* **检查和审核实验** — 获取任何活动的状态、性能、更改历史记录和QA预览链接，而无需浏览UI。
* **分析结果** — 检索A/B、XT、AP和自动定位活动的性能、收入和A4T报表。
* **管理活动** — 创建、更新和激活A/B和XT活动；调整流量分摊、变体、时间表和优先级。
* **管理受众和选件** — 列出、检查和创建受众、HTML选件和JSON选件。
* **浏览推荐标准** — 列出并检查标准和基于购物车的算法。
* **审核实施** — 查看at.js设置、响应令牌和每个实体的修订历史记录。

>[!NOTE]
>
>写入操作（创建、更新、激活、停用）包括安全注释。 未经明确的用户确认不会执行任何更改。

[!DNL Adobe Target] MCP服务器公开跨10个类别的52个工具 — 从活动管理和报告到受众创建和QA预览。 有关完整的参数引用，请参阅[MCP服务器工具引用](target-mcp-tools-reference.md)。

要了解您可以使用[!DNL Adobe Target] MCP服务器做什么 — 包括逐步提示演练 — 请参阅[用例和演练](target-mcp-use-cases.md)。

要将[!DNL Adobe Target] MCP服务器连接到AI助手（包括先决条件、特定于客户端的配置以及疑难解答），请参阅[入门](target-mcp-get-started.md)。

## 常见问题解答 {#mcp-faq}

+++支持哪些MCP客户端？

[!DNL Adobe Target] MCP服务器当前可用于&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**。 未来版本中可能会添加对其他MCP兼容应用程序的支持。
+++

+++我可以通过MCP访问哪些[!DNL Adobe Target]对象？

您可以访问活动(A/B、XT、AP)、受众、选件、属性、mbox、推荐标准、响应令牌、at.js配置、A4T报表和实体修订历史记录。 读取和写入操作在52种工具中均受支持 — 写入操作需要适当的角色和明确的确认。
+++

+++MCP服务器是否可以创建或修改活动？

是. 除了读取操作之外，服务器还会公开允许您创建活动、暂停活动、更新优先级、调整流量拆分等操作的写入操作。 写操作遵循与[!DNL Adobe Target] UI相同的权限模型 — 您需要适当的角色才能进行更改，并且在没有明确的用户确认的情况下不会执行任何操作。
+++

+++要使用MCP服务器，是否需要开发人员访问权限？

否. MCP服务器专为营销和技术人员而设计。 营销人员可以在任何受支持的MCP客户端中使用自然语言提示与其交互，而开发人员可以在克劳德代码或光标等工具中使用它。
+++

+++我的[!DNL Adobe Target]数据是否已发送到MCP客户端提供程序？

当您提交提示时，MCP客户端可能会将相关上下文（包括MCP服务器返回的[!DNL Adobe Target]数据）发送到其模型以供处理。 在连接到生产数据之前，请查看MCP客户端提供商的隐私和数据处理策略。 Adobe的数据处理受[Adobe隐私政策](https://www.adobe.com/privacy.html)和[数据保护条款](https://www.adobe.com/go/dpt-ww)管辖。
+++

+++写入操作能否对实时活动造成意外更改？

编写工具包括安全注释和确认审核。 在任何状态更改操作（如激活活动、更改优先级或更新流量分配）之前，服务器都会显示一个结构化确认，其中显示受影响的对象、预计的流量影响以及所需的明确批准步骤。 在确认之前，不会进行任何更改。
+++

+++我需要在[!DNL Adobe Target]中拥有哪些权限？

**观察者**&#x200B;角色至少授予对所有读取工具的访问权限。 **编辑者**&#x200B;角色允许创建活动、受众和选件。 需要有&#x200B;**审批者**&#x200B;角色才能激活、停用或存档活动。 如果您不确定当前的访问级别，请联系您的[!DNL Adobe Target]管理员。
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
