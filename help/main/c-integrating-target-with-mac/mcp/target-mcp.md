---
solution: Target
product: target
title: 使用MCP客户端
description: 了解如何使用MCP服务器将Adobe Target连接到MCP客户端
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: a0fbca3156a7d2a1c582ce591112a18b4a122a64
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# 使用MCP客户端 {#target-mcp}

>[!BEGINSHADEBOX]

目录：

* **[使用MCP客户端](target-mcp.md)**
* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [自行托管MCP服务器](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**&#x200B;和&#x200B;**Cursor**&#x200B;中可用。 未来版本中将增加对其他MCP兼容应用程序的支持。

[!DNL Adobe Target] MCP集成允许您直接从AI助手检查、分析和管理A/B测试、个性化活动和推荐标准。 将[!DNL Target]的读取和写入API转换为纯语言工作流 — 审核您的试验组合、审查性能报告、管理受众和选件，以及执行可控操作，而无需导航UI或编写API调用。 此页面介绍集成的工作方式、您可以对其执行的操作以及如何入门。

## 什么是模型上下文协议？ {#mcp-overview}

营销和优化团队越来越依赖基于聊天的应用程序和开发人员工具（如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）来简化日常工作。 这些应用程序支持&#x200B;**模型上下文协议(MCP)**，这是一个开放标准，允许应用程序以统一的方式向大型语言模型(LLM)公开后端工具。

[!DNL Adobe Target]现在提供了一个MCP服务器，它可以在任何与MCP兼容的应用程序中直接显示实验、个性化和推荐操作。 [!DNL Adobe Target]充当决策和执行层，而AI助手处理推理和解释，使团队无需导航多个产品屏幕或针对[!DNL Adobe Target] REST API编写查询，即可更快地访问优化见解。

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

## 可用工具 {#mcp-tools}

[!DNL Adobe Target] MCP服务器公开52个工具。 读取工具适用于所有具有查看权限的连接用户；写入工具需要“编辑者”或“审批者”角色。

### 活动工具 — 读取

| 工具 | 描述 |
|---|---|
| `list_target_activities` | 按状态、类型、名称、日期、优先级、mbox和工作区列出具有服务器端过滤的活动 |
| `list_all_target_activities` | 获取与筛选器匹配的所有活动，在结果中自动分页 |
| `get_ab_activity` | 获取特定A/B活动的完整详细信息 |
| `get_xt_activity` | 获取特定体验定位(XT)活动的完整详细信息 |
| `get_abt_activity` | 获取特定Automated Personalization (AP)活动的完整详细信息 |

### 活动工具 — 写入

| 工具 | 描述 |
|---|---|
| `create_ab_activity` | 创建新的A/B测试活动 |
| `create_xt_activity` | 创建新的体验定位(XT)活动 |
| `create_activity_from_modifications` | 通过JavaScript修改创建XT活动 |
| `update_ab_activity` | 更新现有A/B活动 |
| `update_xt_activity` | 更新现有XT活动 |
| `update_abt_activity` | 更新现有的Automated Personalization活动 |
| `update_activity_state` | 激活、停用、暂停或存档活动 |
| `update_activity_schedule` | 更新活动的开始和结束日期 |
| `update_activity_priority` | 更新活动的优先级 |
| `update_activity_name` | 重命名活动 |
| `add_activity_variant` | 向活动添加新变体（体验） |
| `update_traffic_split` | 更新变量之间的流量分配 |
| `update_variant_offer` | 更改变体的选件或VEC修改 |
| `remove_activity_variant` | 从活动中删除变体 |

### 优惠工具

| 工具 | 描述 |
|---|---|
| `list_target_offers` | 列出具有服务器端过滤和排序的选件 |
| `list_all_target_offers` | 获取与筛选器匹配的所有选件，自动分页 |
| `get_target_offer` | 获取特定优惠的详细信息 |
| `create_target_offer` | 创建新的HTML选件 |
| `create_target_json_offer` | 创建新的JSON选件 |
| `update_target_offer` | 更新现有HTML选件 |

### 受众工具

| 工具 | 描述 |
|---|---|
| `list_target_audiences` | 列出具有服务器端过滤和排序的受众 |
| `create_target_audience` | 使用可选定位规则创建受众 |

### Mbox和定位工具

| 工具 | 描述 |
|---|---|
| `list_target_mboxes` | 具有过滤和排序功能的列表mbox |
| `list_all_target_mboxes` | 获取所有与筛选器匹配的mbox，自动分页 |
| `get_target_mbox` | 按名称获取特定mbox的详细信息 |
| `list_target_mbox_profile_attributes` | 列出与mbox关联的所有配置文件属性 |

### 属性

| 工具 | 描述 |
|---|---|
| `list_target_properties` | 列出所有Target属性 |

### 报告和分析工具

| 工具 | 描述 |
|---|---|
| `get_ab_performance_report` | 获取A/B、自动分配或自动定位活动的性能报表 |
| `get_ab_orders_report` | 获取A/B或自动定位活动的订单和收入报表 |
| `get_xt_performance_report` | 获取XT活动的性能报表 |
| `get_xt_orders_report` | 获取XT活动的订单和收入报表 |
| `get_apt_performance_report` | 获取AP或自动定位活动的性能报表 |
| `get_activity_insights` | 按名称搜索活动并获取详细的性能分析 |
| `get_a4t_report` | 获取活动的Analytics for Target (A4T)报表 |

### 推荐工具

| 工具 | 描述 |
|---|---|
| `list_target_criteria` | 列出所有“推荐”标准 |
| `get_target_criteria` | 获取特定“推荐”标准的详细信息 |
| `update_target_criteria_cart` | 更新基于推荐购物车的标准 |

### 实施和配置工具

| 工具 | 描述 |
|---|---|
| `get_atjs_settings` | 获取AT.js设置和配置 |
| `get_atjs_versions` | 获取可用的AT.js版本 |
| `list_target_response_tokens` | 列出您的Target租户中的所有响应令牌 |
| `create_target_response_token` | 创建新的自定义响应令牌 |

### 审核和修订工具

| 工具 | 描述 |
|---|---|
| `get_target_revisions` | 获取资源类型的审核日志，按作者筛选 |
| `get_target_entity_revisions` | 按ID获取特定实体的所有修订 |

### 实用工具

| 工具 | 描述 |
|---|---|
| `preview_activity` | 为Target活动生成QA预览URL |
| `create_page_delivery_segment` | 为VEC活动定位创建页面投放区段 |
| `list_target_templates` | 列出可用的MCP资源和模板 |
| `debug_token_info` | 检查当前OAuth令牌范围和声明 |

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

## 先决条件 {#mcp-prerequisites}

在将[!DNL Adobe Target] MCP服务器连接到MCP客户端之前，请确保：

* 您拥有一个Adobe Experience Platform组织的有效[!DNL Adobe Target]许可证（Adobe Experience Cloud订阅）。
* 您有一个受支持的MCP兼容应用程序（当前为Claude Web 、 Claude Desktop 、 Claude Code或Cursor ）。
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

## 常见问题解答 {#mcp-faq}

+++支持哪些MCP客户端？

[!DNL Adobe Target] MCP服务器当前可用于&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**&#x200B;和&#x200B;**Cursor**。 未来版本中可能会添加对其他MCP兼容应用程序的支持。
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

当您提交提示时，MCP客户端可能会将相关上下文（包括MCP服务器返回的[!DNL Adobe Target]数据）发送到其模型以供处理。 在连接到生产数据之前，请查看MCP客户端提供商的隐私和数据处理策略。 Adobe的数据处理受[Adobe隐私政策](https://www.adobe.com/cn/privacy.html)和[数据保护条款](https://www.adobe.com/go/dpt-ww)管辖。
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

* [MCP服务器工具参考](target-mcp-tools-reference.md)
* [自托管 [!DNL Adobe Target] MCP服务器](target-mcp-self-hosted.md)
* [模型上下文协议文档](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Cursor文档](https://docs.cursor.com/){target="_blank"}
