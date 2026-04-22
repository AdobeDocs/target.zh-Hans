---
solution: Target
product: target
title: Adobe Target MCP服务器工具参考
description: Adobe Target MCP服务器公开的所有39种公共工具的完整参数引用。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
hide: true
source-git-commit: 6e7fa766f3da76f3e9d1f4527bfe50b9e703db4e
workflow-type: tm+mt
source-wordcount: '2782'
ht-degree: 14%

---

# [!DNL Adobe Target] MCP服务器工具参考 {#target-mcp-tools-reference}

>[!BEGINSHADEBOX]

目录：

* [使用MCP客户端](target-mcp.md)
* **[MCP服务器工具引用](target-mcp-tools-reference.md)**

>[!ENDSHADEBOX]

此页面是[!DNL Adobe Target] MCP服务器公开的所有公共工具的完整参考。 对于每个工具，您都可以找到描述、参数详细信息、返回值以及自然语言提示示例。 有关设置说明和使用案例，请参阅[使用MCP客户端](target-mcp.md)。

>[!NOTE]
>
>读取工具可用于具有&#x200B;**观察者**&#x200B;或更高角色的所有连接用户；写入工具需要&#x200B;**编辑者**&#x200B;或&#x200B;**审批者**&#x200B;角色。

>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 活动工具 {#tools-activities}

+++list_target_activities

列出具有服务器端过滤和排序的[!DNL Adobe Target]活动。

检索分页的活动列表。 所有筛选器都通过[!DNL Target]管理员API在服务器端应用。 服务器每页最多返回200个活动。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `limit` | 整数 | 否 | 要返回的最大活动数（服务器最大数量：200） |
| `offset` | 整数 | 否 | 为分页而跳过的活动数 |
| `sort_by` | 字符串 | 否 | 要作为排序依据的字段。 前缀为`-`表示降序（例如，`-modifiedAt`）。 选项： `id`、`name`、`state`、`priority`、`startsAt`、`endsAt`、`lifetimeStart`、`lifetimeEnd`、`createdAt`、`createdBy`、`modifiedAt`、`modifiedBy`、`type`、`thirdPartyId` |
| `state` | 字符串 | 否 | 按活动状态筛选： `approved` （实时/活动）、`deactivated` （非活动）、`paused`、`saved` （草稿） |
| `activity_type` | 字符串 | 否 | 按类型筛选： `ab` （A/B测试）、`xt` （体验定位）、`abt` (Automated Personalization) |
| `name_contains` | 字符串 | 否 | 筛选名称包含此字符串（不区分大小写）的活动 |
| `starts_after` | 字符串 | 否 | ISO 8601日期 — 在此日期之后开始的活动 |
| `starts_before` | 字符串 | 否 | ISO 8601日期 — 在此日期之前开始的活动 |
| `modified_after` | 字符串 | 否 | ISO 8601日期 — 在此日期之后修改的活动 |
| `ends_after` | 字符串 | 否 | ISO 8601日期 — 在此日期之后结束的活动 |
| `ends_before` | 字符串 | 否 | ISO 8601日期 — 在此日期之前结束的活动 |
| `workspace` | 字符串 | 否 | 按工作区ID筛选 |
| `segment_id` | 字符串 | 否 | 按受众区段ID过滤 |
| `profile_attribute_id` | 字符串 | 否 | 按配置文件属性ID筛选 |
| `priority` | 整数 | 否 | 按准确的优先级值筛选(0-999) |
| `mbox` | 字符串 | 否 | 按mbox/位置名称筛选 |
| `offer_id` | 字符串 | 否 | 按优惠ID筛选 |
| `view_id` | 字符串 | 否 | 按SPA视图ID筛选 |

**返回：** JSON对象，带有`activities` （对象列表包括`id`、`name`、`state`、`type`、`priority`、`modifiedAt`、`startsAt`、`endsAt`）和`total` （总计数，可能会超过返回的页面大小）。

**示例提示：**“列出按最近修改排序的所有活动A/B测试。”

+++

+++get_ab_activity

获取有关A/B活动的详细信息。

检索特定A/B测试的完整配置，包括体验、位置、量度和定位规则。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据（名称、状态、优先级、日期）、体验、位置和选件、目标和量度，以及定位规则。

**示例提示：**“获取A/B活动12345的详细信息”。

+++

+++get_xt_activity

获取有关体验定位(XT)活动的详细信息。

检索特定XT活动的完整配置，包括受众体验映射、位置和量度。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据、具有受众映射的体验、位置和选件以及目标和量度。

**示例提示：**“获取体验定位活动12345的详细信息”。

+++

+++get_abt_activity

获取有关Automated Personalization (AP)活动的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | AP活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据、体验、位置和算法设置。

**示例提示：**“获取自动Personalization活动12345的详细信息”。

+++

+++create_ab_activity

创建新的A/B测试活动。

使用指定配置（包括体验、选件和定位）创建新的A/B测试。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `name` | 字符串 | 是 | 活动的名称 |
| `state` | 字符串 | 否 | 初始状态： `approved`、`deactivated`或`saved` （默认值： `saved`） |
| `priority` | 整数 | 否 | 活动优先级（0-999，默认值： 0） |
| `starts_at` | 字符串 | 否 | 活动开始日期(ISO 8601) |
| `ends_at` | 字符串 | 否 | 活动结束日期(ISO 8601) |
| `experiences` | 数组 | 是 | 体验配置列表 |
| `locations` | 数组 | 是 | 位置/mbox配置列表 |
| `goals` | 对象 | 否 | 主要和次要目标指标 |
| `audiences` | 数组 | 否 | 目标受众配置 |
| `workspace_id` | 字符串 | 否 | 活动的Workspace ID |

**返回：**&#x200B;创建的活动对象及其分配的ID。

**示例提示：**“创建名为‘主页主页主页主页主页主页测试’的A/B测试，该测试包含两个体验，分别测试主页主页主页主页主页上的不同主页图像。”

+++

+++create_xt_activity

创建新的体验定位(XT)活动。

创建一个XT活动，该活动根据定位规则向不同受众提供不同的体验。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `name` | 字符串 | 是 | 活动的名称 |
| `state` | 字符串 | 否 | 初始状态： `approved`、`deactivated`或`saved` （默认值： `saved`） |
| `priority` | 整数 | 否 | 活动优先级（0-999，默认值： 0） |
| `starts_at` | 字符串 | 否 | 活动开始日期(ISO 8601) |
| `ends_at` | 字符串 | 否 | 活动结束日期(ISO 8601) |
| `experiences` | 数组 | 是 | 包含受众映射的体验配置列表 |
| `locations` | 数组 | 是 | 位置/mbox配置列表 |
| `goals` | 对象 | 否 | 主要和次要目标指标 |
| `workspace_id` | 字符串 | 否 | 活动的Workspace ID |

**返回：**&#x200B;创建的活动对象及其分配的ID。

**示例提示：**“创建一个名为‘地域Personalization’的体验定位活动，向来自不同地区的访客显示不同的内容。”

+++

+++update_ab活动

更新现有A/B活动。

使用读 — 修改 — 写模式：获取当前状态，合并更改，验证并发送更新。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要更新的活动的唯一标识符 |
| `activity` | 对象 | 是 | 要更新的字段（名称、优先级、体验、位置、目标等） |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“更新活动12345以将流量分配更改为70/30。”

+++

+++update_xt活动

更新现有的体验定位活动。

使用读 — 修改 — 写模式。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要更新的XT活动的唯一标识符 |
| `activity` | 对象 | 是 | 要更新的字段 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“更新XT活动12345以为移动访客添加新体验”。

+++

+++update_abt_activity

更新现有的Automated Personalization活动。

使用读 — 修改 — 写模式。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要更新的AP活动的唯一标识符 |
| `activity` | 对象 | 是 | 要更新的字段 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“更新自动Personalization活动12345以更改优化目标”。

+++

+++update_activity_schedule

更新活动的开始和结束日期。

在不修改其他设置的情况下更新活动的计划。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 活动的唯一标识符 |
| `activity_type` | 字符串 | 是 | 活动类型： `ab`、`xt`或`abt` |
| `starts_at` | 字符串 | 否 | 新的开始日期(ISO 8601) |
| `ends_at` | 字符串 | 否 | 新结束日期(ISO 8601) |

**返回：**&#x200B;计划更新的确认。

**示例提示：**“更新A/B活动计划12345于5月1日至5月31日运行。”

+++

+++update_active_state

更改活动状态（激活、停用或暂停）。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 活动的唯一标识符 |
| `state` | 字符串 | 是 | 新状态： `approved` （实时/活动）、`deactivated` （非活动）、`paused`或`saved` （草稿） |

**返回：**&#x200B;更新的活动状态。

**示例提示：**“激活活动12345”或“暂停主页主页主页主页主页测试”。

+++

+++update_activity_name

重命名活动。

仅更新名称，而不修改完整配置。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 活动的唯一标识符 |
| `name` | 字符串 | 是 | 新活动名称 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“将活动12345重命名为‘Summer Campaign主页测试’。”

+++

+++更新活动优先级

更改活动优先级。

当多个活动针对同一位置时，优先级较高的活动优先。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 活动的唯一标识符 |
| `priority` | 整数 | 是 | 新优先级值（0-999；更高=更高的优先级） |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“将活动12345的优先级设置为100。”

+++

+++add_activity_variant

向活动添加新体验/变体。

处理所有结构协调，包括创建选项、映射到位置和重新平衡流量。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要修改的活动的ID |
| `activity_type` | 字符串 | 是 | 活动类型： `ab`、`xt`或`abt` |
| `variant_name` | 字符串 | 是 | 新体验/变体的名称 |
| `offer_id` | 整数 | 否 | （基于表单）要使用的现有优惠ID |
| `offer_content` | 字符串 | 否 | （基于表单）适用于新内联选件的HTML内容 |
| `traffic_percentage` | 整数 | 否 | 新变体的流量% (1-99)。 如果忽略，则流量将平均重新平衡 |
| `audience_id` | 整数 | 否 | 变体的受众ID（XT活动） |
| `modifications` | 数组 | 否 | (VEC)基于CSS选择器的修改列表 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“使用选件67890向A/B活动12345添加名为‘假日主题’的新变体。”

+++

+++update_traffic_split

更新变量之间的流量分配。

百分比的总和必须为100。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要修改的活动的ID |
| `activity_type` | 字符串 | 是 | 活动类型： `ab`或`abt` （不支持XT — 面向受众） |
| `splits` | 对象 | 是 | 字典将体验名称映射到百分比。 必须包括所有体验，总和必须为100 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“将活动12345的流量分摊更改为控制占70%，变体A占30%。”

+++

+++update_variant_offer

更改特定变体的选件。

适用于基于表单的活动（使用`offer_id`）和VEC活动（使用`modifications`）。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要修改的活动的ID |
| `activity_type` | 字符串 | 是 | 活动类型： `ab`、`xt`或`abt` |
| `variant_name` | 字符串 | 是 | 要更新的体验/变体的名称 |
| `offer_id` | 整数 | 否 | （基于表单）新优惠ID |
| `offer_content` | 字符串 | 否 | （基于表单）适用于新内联选件的HTML内容 |
| `modifications` | 数组 | 否 | (VEC)基于CSS选择器的修改的新列表 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“更新活动12345中的‘变体A’体验以使用选件99999。”

+++

+++remove_activity_variant

从活动中删除体验/变体。

删除体验，清除孤立的选项，并在剩余变体之间平均重新平衡流量。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要修改的活动的ID |
| `activity_type` | 字符串 | 是 | 活动类型： `ab`、`xt`或`abt` |
| `variant_name` | 字符串 | 是 | 要移除的体验/变体的名称 |

**返回：**&#x200B;更新的活动对象。

**示例提示：**“从A/B activity 12345中删除‘测试变体’体验”。

+++

## 优惠工具 {#tools-offers}

+++list_target_offers

列出[!DNL Target]租户中的所有优惠。

检索包含可选过滤功能的内容选件分页列表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `limit` | 整数 | 否 | 要返回的最大优惠数量 |
| `offset` | 整数 | 否 | 跳出进行分页的优惠数量 |
| `type` | 字符串 | 否 | 按选件类型筛选： `content` (HTML)、`json`或`redirect` |
| `name` | 字符串 | 否 | 按选件名称筛选（部分匹配） |

**返回：**&#x200B;包含`offers`的JSON对象（对象列表，包括`id`、`name`、`type`、`content`、`modifiedAt`）和`total`。

**示例提示：**“列出所有JSON选件”。

+++

+++get_target_offer

获取有关特定选件的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `offer_id` | 整数 | 是 | 优惠的唯一标识符 |

**返回：**&#x200B;完整的选件详细信息，包括`id`、`name`、`type`、`content`、`workspace`和`modifiedAt`。

**示例提示：**“获取选件67890的详细信息”。

+++

+++create_target_offer

创建新的HTML内容选件。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `name` | 字符串 | 是 | 优惠的名称 |
| `content` | 字符串 | 是 | 选件的HTML或文本内容 |
| `workspace_id` | 字符串 | 否 | 选件的Workspace ID |

**返回：**&#x200B;创建的选件及其分配的ID。

**示例提示：**“使用促销横幅创建名为‘夏季促销横幅’的HTML优惠。”

+++

+++create_target_json_offer

创建新的JSON选件来交付结构化数据。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `name` | 字符串 | 是 | 优惠的名称 |
| `content` | 对象 | 是 | 选件的JSON内容 |
| `workspace_id` | 字符串 | 否 | 选件的Workspace ID |

**返回：**&#x200B;创建的选件及其分配的ID。

**示例提示：**“使用功能切换设置创建一个名为‘功能标志配置’的JSON选件。”

+++

+++update_target_offer

更新现有选件。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `offer_id` | 整数 | 是 | 要更新的优惠的唯一标识符 |
| `name` | 字符串 | 否 | 已更新优惠名称 |
| `content` | 字符串或对象 | 否 | 更新的优惠内容 |

**返回：**&#x200B;更新的选件对象。

**示例提示：**“使用新的促销内容更新优惠67890。”

+++

## 受众工具 {#tools-audiences}

+++list_target_audiences

列出[!DNL Target]租户中的所有受众。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `limit` | 整数 | 否 | 要返回的最大受众数 |
| `offset` | 整数 | 否 | 为分页而跳过的受众数量 |

**返回：**&#x200B;包含`audiences`的JSON对象（对象列表，包括`id`、`name`、`description`、`origin`、`modifiedAt`）和`total`。

**示例提示：**“列出所有受众”。

+++

+++create_target_audience

使用定位规则创建新受众。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `name` | 字符串 | 是 | 受众的名称 |
| `description` | 字符串 | 否 | 受众描述 |
| `targetRule` | 对象 | 否 | 定位规则（地域、浏览器、自定义属性等） |
| `workspace_id` | 字符串 | 否 | 受众的Workspace ID |

**返回：**&#x200B;创建的受众及其分配的ID。

**示例提示：**“创建名为‘来自加利福尼亚州的移动访客’的受众，目标为CA中的移动用户。”

+++

## Mbox工具 {#tools-mboxes}

+++list_target_mboxes

列出您[!DNL Target]租户中的所有mbox。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `limit` | 整数 | 否 | 要返回的最大mbox数 |
| `offset` | 整数 | 否 | 要跳过以进行分页的mbox数量 |
| `name` | 字符串 | 否 | 按mbox名称筛选（部分匹配） |
| `status` | 字符串 | 否 | 按状态筛选 |

**返回：**&#x200B;包含`mboxes`的JSON对象（对象列表，包括`name`、`status`、`lastRequestTime`）和`total`。

**示例提示：**“列出所有包含&#39;homepage&#39;的mbox。”

+++

+++get_target_mbox

获取有关特定mbox的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `mbox_name` | 字符串 | 是 | mbox的名称 |

**返回：** Mbox详细信息，包括`name`、`status`以及使用mbox的活动列表。

**示例提示：**“获取mbox &#39;homepage-hero&#39;的详细信息。”

+++

+++list_target_mbox_profile_attributes

列出所有可用于定位的mbox配置文件属性。

无需参数。

**返回：**&#x200B;配置文件属性对象的JSON数组。

**示例提示：**“哪些配置文件属性可用于定位？”

+++

## 资产工具 {#tools-properties}

+++list_target_properties

列出[!DNL Target]租户中的所有属性。

属性可组织活动并控制访问权限。

无需参数。

**返回：**&#x200B;属性对象列表，包括`id`、`name`、`description`和`channel`。

**示例提示：**“列出所有Target属性”。

+++

## 报告工具 {#tools-reporting}

+++get_ab_performance_report

获取A/B活动的性能报表。

检索转化率、提升度和置信度级别。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时段（例如`last7days`、`last30days`或自定义日期范围） |

**返回：**&#x200B;体验级别的量度（访客数、转化率、转化率）、提升度计算、统计置信水平和收入量度（如果已配置）。

**示例提示：**“显示过去30天的A/B测试12345性能报告。”

+++

+++get_ab_orders_report

获取A/B活动的订单/收入报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;订单计数、收入和平均订单值（按体验）。

**示例提示：**“获取活动12345的订单报告”。

+++

+++get_xt_performance_report

获取体验定位活动的性能报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;体验级别的绩效指标。

**示例提示：**“显示我的体验定位活动54321的性能”。

+++

+++get_xt_orders_report

获取体验定位活动的订单/收入报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;按体验排序的量度。

**示例提示：**“获取XT活动54321的订单数据”。

+++

+++get_activity_report_by_name

按名称搜索活动并获取其性能报表。

当您知道活动名称但不知道其ID时，此变量将非常有用。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_name` | 字符串 | 是 | 要搜索的活动名称 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;活动详细信息和性能度量。

**示例提示：**“获取我的‘主页主页主页主页测试’活动的性能报告。”

+++

## 预览工具 {#tools-preview}

+++preview_activity

为[!DNL Target]活动生成浏览器QA预览URL。

创建可单击的预览链接，以强制显示特定体验，并绕过受众定位规则。 适用于A/B、XT和Automated Personalization活动。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | 要预览的[!DNL Target]活动标识 |
| `experience_index` | 整数 | 否 | 基于0的体验索引。 如果忽略，则返回所有体验的URL |
| `url` | 字符串 | 否 | 用于预览的页面URL。 对于基于表单的活动，此为必需字段。 对于VEC活动，会覆盖创作位置（如果提供） |

**返回：**&#x200B;活动信息（名称、类型、状态）、每个体验的预览URL以及体验名称和索引。

**示例提示：**“为活动12345生成预览URL，以便我可以在浏览器中测试每个体验。”

+++

## 响应令牌工具 {#tools-response-tokens}

+++list_target_response_tokens

列出[!DNL Target]租户中的所有响应令牌。

检索所有已配置的响应令牌，包括内置和自定义响应令牌。

无需参数。

**返回：**&#x200B;响应令牌对象的JSON数组，状态为`name`、`type`和`enabled`。

**示例提示：**“列出所有响应令牌”。

+++

+++create_target_response_token

创建新的自定义响应令牌以在[!DNL Target]响应中收集其他数据。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `token_name` | 字符串 | 是 | 响应令牌的名称 |
| `token_type` | 字符串 | 是 | 令牌类型： `SCRIPT`、`ACTIVITY`、`MBOX`、`GEO`或`CRS` |

**返回：**&#x200B;创建的响应令牌对象。

**示例提示：**“创建名为‘campaign_id’的ACTIVITY类型的自定义响应令牌。”

+++

## 修订版工具 {#tools-revisions}

+++get_target_revisions

获取资源类型的审核日志。

通过作者可选的筛选，检索对[!DNL Target]资源所做的更改。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `revision_resource_type` | 字符串 | 是 | 资源类型： `activity`、`offer`或`audience` |
| `modified_by` | 字符串 | 否 | 按进行更改的用户筛选 |
| `limit` | 整数 | 否 | 要返回的最大修订数量 |
| `offset` | 整数 | 否 | 为分页而跳过的修订数量 |

**返回：**&#x200B;修订历史记录，包含时间戳、用户和更改描述。

**示例提示：**“显示活动更改的审核日志”。

+++

+++get_target_entity_revisions

按ID获取特定实体的所有修订。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `revision_resource_type` | 字符串 | 是 | 资源类型： `activity`、`offer`或`audience` |
| `entity_id` | 整数 | 是 | 实体的唯一标识符 |

**返回指定实体的所有修订的** JSON数组。

**示例提示：**“向我显示对活动12345所做的所有更改。”

+++

## 模板工具 {#tools-templates}

+++list_target_templates

列出用于创建活动和选件的可用MCP资源和模板。

无需参数。

**返回：** JSON对象列出了可用的模板和资源。

**示例提示：**“哪些模板可用于创建活动？”

+++

## 工具摘要 {#tools-summary}

| 类别 | 计数 | 工具 |
|---|---|---|
| 活动 | 17 | `list_target_activities`、`get_ab_activity`、`get_xt_activity`、`get_abt_activity`、`create_ab_activity`、`create_xt_activity`、`update_ab_activity`、`update_xt_activity`、`update_abt_activity`、`update_activity_schedule`、`update_activity_state`、`update_activity_name`、`update_activity_priority`、`add_activity_variant`、`update_traffic_split`、`update_variant_offer`、`remove_activity_variant` |
| 产品建议 | 5 | `list_target_offers`、`get_target_offer`、`create_target_offer`、`create_target_json_offer`、`update_target_offer` |
| 受众 | 2 | `list_target_audiences`, `create_target_audience` |
| Mbox | 3 | `list_target_mboxes`，`get_target_mbox`，`list_target_mbox_profile_attributes` |
| 属性 | 1 | `list_target_properties` |
| 报表 | 5 | `get_ab_performance_report`、`get_ab_orders_report`、`get_xt_performance_report`、`get_xt_orders_report`、`get_activity_report_by_name` |
| 预览 | 1 | `preview_activity` |
| 响应令牌 | 2 | `list_target_response_tokens`, `create_target_response_token` |
| 修订 | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| 模板 | 1 | `list_target_templates` |
| **合计** | **39** | |

## 相关资源 {#tools-related}

* [使用MCP客户端](target-mcp.md)
* [[!DNL Adobe Target] 管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}