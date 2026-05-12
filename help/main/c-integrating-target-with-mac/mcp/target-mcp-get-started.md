---
solution: Target
product: target
title: Adobe Target MCP服务器入门
description: 了解如何将Adobe Target MCP服务器连接到AI助手，包括先决条件、客户端配置和疑难解答。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 开始使用[!DNL Adobe Target] MCP服务器 {#target-mcp-get-started}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器可用于&#x200B;**公共Beta**&#x200B;中的所有客户。 当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支持它。

此页面将指导您完成将[!DNL Adobe Target] MCP服务器连接到AI助手并验证设置所需的一切。

>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 先决条件 {#mcp-prerequisites}

在将[!DNL Adobe Target] MCP服务器连接到MCP客户端之前，请确保：

* 您拥有一个Adobe Experience Platform组织的有效[!DNL Adobe Target]许可证（Adobe Experience Cloud订阅）。
* 您有一个受支持的MCP兼容应用程序（当前为Claude Web 、 Claude Desktop 、 Claude Code 、 Cursor或ChatGPT ）。
* 您在Adobe Admin Console中配置了[!DNL Adobe Target]权限：
   * **观察者**&#x200B;角色：只读工具
   * **编辑者**&#x200B;角色：读取+创建工具
   * **审批者**&#x200B;角色：读取+创建+激活/停用工具

## 连接[!DNL Adobe Target] MCP服务器 {#mcp-connect}

>[!NOTE]
>
>[!DNL Adobe Target] MCP服务器使用OAuth 2.0进行身份验证。 首次使用Target MCP工具时，您会被重定向到Adobe Experience Cloud以登录、选择您的组织并授予所请求的权限。 不需要静态凭据。

**从Claude Desktop或Claude Web连接：**

1. 打开MCP客户端设置并添加新的MCP服务器。
1. 输入服务器URL： `https://targetmcp.adobe.io/mcp`
1. 出现提示时，使用您的Adobe Experience Cloud凭据完成Adobe IMS OAuth登录。
1. 一旦通过身份验证，所有工具即可立即使用。 尝试“列出所有活动的Target活动”以验证连接。

**从克劳德代码连接：**

将以下代码添加到您的克劳德代码MCP配置中：

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

在首次使用出现提示时，完成OAuth浏览器流程。

**从游标连接：**

1. 打开&#x200B;**Cursor**&#x200B;并导航到&#x200B;**设置** → **MCP** → **添加新全局MCP服务器**。
1. 添加以下配置：

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. 保存配置。 [!DNL Target] MCP服务器将显示在可用的MCP服务器中。

>[!TIP]
>
>如果显示了来自错误组织的活动或数据，请完全注销Adobe Experience Cloud，重新连接MCP服务器，并在重新身份验证期间仔细选择正确的组织。

## 故障排除 {#mcp-troubleshooting}

+++OAuth流失败或重定向不正确

1. 完全注销Adobe Experience Cloud。
1. 清除adobe.com域的浏览器Cookie。
1. 重试身份验证流程。
1. 确保在出现提示时选择正确的组织。
+++

+++出现来自错误组织的活动或数据

1. 完全注销Adobe Experience Cloud。
1. 在客户端设置中，断开并重新连接MCP服务器。
1. 在重新验证期间仔细选择正确的组织。
+++

+++工具返回错误消息

1. 验证您是否在[!DNL Adobe Target]中拥有该操作所需的权限（请参阅[先决条件](#mcp-prerequisites)）。
1. 检查引用的资源（活动、选件、受众）是否存在于您的组织中。
1. 确认活动ID和其他标识符正确无误。
+++

+++无法连接到MCP服务器

1. 验证互联网连接。
1. 检查在客户端配置中是否正确输入了MCP服务器URL。
1. 请尝试在MCP客户端设置中删除并重新添加服务器。
+++

## 安全性和权限 {#mcp-security}

[!DNL Adobe Target] MCP服务器只能访问您的Adobe用户帐户有权查看或修改的数据。 所有操作都尊重您的[!DNL Target]角色分配和工作区权限。

服务器请求以下OAuth作用域：

* `AdobeID` — 基本Adobe标识
* `openid` — OpenID Connect身份验证
* `additional_info.projectedProductContext` — 租户发现
* `read_organizations` — 组织级别的操作
* `additional_info.roles` — 基于角色的访问控制

OAuth令牌会在每个请求中根据Adobe IMS进行验证，不会由MCP服务器永久存储，并且所有通信都使用HTTPS。

## 相关资源 {#mcp-get-started-related}

* [概述](target-mcp.md)
* [用例和演练](target-mcp-use-cases.md)
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
