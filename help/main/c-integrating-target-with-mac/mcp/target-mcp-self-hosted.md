---
solution: Target
product: target
title: 自行托管Adobe Target MCP服务器
description: 了解如何使用Python、Docker或本地开发环境运行您自己的Adobe Target MCP服务器实例。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer
level: Experienced
hide: true
source-git-commit: 782256b734068075795d5e9c1f3f552ca48918e6
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 2%

---

# 自托管[!DNL Adobe Target] MCP服务器 {#target-mcp-self-hosted}

>[!BEGINSHADEBOX]

目录：

* [使用MCP客户端](target-mcp.md)
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* **[自行托管MCP服务器](target-mcp-self-hosted.md)**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>自托管部署适用于需要完全控制[!DNL Adobe Target] MCP服务器运行时的开发人员和高级用户。 对于大多数用户，建议使用托管端点(`https://targetmcp.adobe.io/mcp`)。 请参阅[使用MCP客户端](target-mcp.md)。

本页介绍如何克隆、配置和运行您自己的[!DNL Adobe Target] MCP服务器实例。 当您需要本地开发环境、自定义网络配置或希望贡献服务器代码库时，自托管会很有用。

## 先决条件 {#self-hosted-prereqs}

在开始之前，请确保您具备以下条件：

* **Python 3.13或更高版本**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** — 快速Python包和项目管理器

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* 具有Adobe Experience Cloud访问权限的有效[!DNL Adobe Target]许可证
* **Artifactory凭据** （仅限Adobe内部用户） — 安装内部依赖项所需

## 安装 {#self-hosted-install}

**1. 克隆存储库：**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2. 创建并激活虚拟环境：**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3. 配置环境变量：**

```bash
cp env.example .env
```

打开`.env`并将占位符值替换为您的凭据和组织设置。

**4. 安装依赖项：**

```bash
make uv-install
```

**5. 启动服务器：**

选择与您的用例匹配的模式：

| 模式 | Command（命令） | 使用时机 |
|---|---|---|
| StreamableHTTP（API服务器） | `make run-api-server` | 通过HTTP连接MCP客户端 |
| STDIO（本地MCP客户端） | `make run-mcp-stdio` | 使用直接进程通信 |

## 将MCP客户端连接到本地服务器 {#self-hosted-connect}

### 光标

将以下内容添加到Cursor MCP配置中。 将占位符值替换为您的实际IMS令牌和组织ID：

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### Claude码

向指向本地服务器的Claude Code MCP配置文件中添加一个条目：

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>连接到本地服务器时，必须手动传递身份验证标头（如上面的光标示例所示）。 OAuth浏览器流仅适用于托管的`https://targetmcp.adobe.io/mcp`终结点。

## Docker部署 {#self-hosted-docker}

存储库包括用于容器化部署的Docker撰写配置。

**使用Docker撰写运行：**

```bash
make run-dc
```

**直接生成并运行Docker映像：**

```bash
make build
make run-docker
```

## api端点 {#self-hosted-endpoints}

自托管服务器公开以下HTTP端点：

| 终结点 | 描述 |
|---|---|
| `/mcp` | AI客户端的MCP协议端点 |
| `/ping` | 活动检查 — 返回`"Pong"` |
| `/health` | 运行状况检查 — 返回`{"status": "healthy"}` |
| `/validate` | 输入验证端点 |
| `/authorize` | OAuth授权端点 |
| `/token` | OAuth令牌端点 |

**运行状况检查示例：**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## 故障排除 {#self-hosted-troubleshoot}

+++服务器无法启动

1. 验证是否已安装Python 3.13+： `python --version`
1. 确认已激活虚拟环境： `source .venv/bin/activate`
1. 检查`.env`中的所有环境变量是否设置正确。
1. 再次运行`make uv-install`以确保所有依赖项都存在。

+++

+++无法从MCP客户端连接

1. 确认服务器正在运行并且端口可访问： `curl http://localhost:8080/ping`
1. 验证MCP客户端配置中的服务器URL是否与正在运行的服务器地址匹配。
1. 对于游标，请确保`Authorization`标头包含有效的未过期的IMS令牌。

+++

+++依赖项安装失败（Adobe内部用户）

1. 确认已正确配置Artifactory凭据。
1. 检查与内部Artifactory实例的网络连接。
1. 请与团队的DevOps或平台工程联系人联系，以获取有关艺术品的访问权限。

+++

## 相关资源 {#self-hosted-related}

* [使用MCP客户端](target-mcp.md) — 托管终结点设置和工具引用
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
