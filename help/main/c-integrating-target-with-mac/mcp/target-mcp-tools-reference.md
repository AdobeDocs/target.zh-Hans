---
solution: Target
product: target
title: Adobe Target MCP服务器工具参考
description: Adobe Target MCP服务器公开的所有21种只读工具的完整参数引用。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# [!DNL Adobe Target] MCP服务器工具参考 {#target-mcp-tools-reference}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP服务器可用于&#x200B;**公共Beta**&#x200B;中的所有客户。 当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中支持它。

此页面是[!DNL Adobe Target] MCP服务器公开的所有只读工具的完整参考。 对于每个工具，您都可以找到描述、参数详细信息、返回值以及自然语言提示示例。 有关设置说明和用例，请参阅[入门](target-mcp-get-started.md)和[用例和演练](target-mcp-use-cases.md)。

>[!IMPORTANT]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置，客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 先决条件 {#tools-prerequisites}

您的[!DNL Adobe Target]角色决定了您可用的工具：

* **观察者**&#x200B;角色或更高版本：访问所有读取工具
* **编辑者**&#x200B;角色：访问读写（创建）工具
* **审批者**&#x200B;角色：访问读取、写入和激活/停用工具

有关完整的设置说明，请参阅[开始使用](target-mcp-get-started.md)。

## 活动工具 {#tools-activities}

+++列出活动

**工具：** `list_target_activities`

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

+++获取A/B活动

**工具：** `get_ab_activity`

获取有关A/B活动的详细信息。

检索特定A/B测试的完整配置，包括体验、位置、量度和定位规则。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据（名称、状态、优先级、日期）、体验、位置和选件、目标和量度，以及定位规则。

**示例提示：**“获取A/B活动12345的详细信息”。

+++

+++获取体验定位活动

**工具：** `get_xt_activity`

获取有关体验定位(XT)活动的详细信息。

检索特定XT活动的完整配置，包括受众体验映射、位置和量度。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据、具有受众映射的体验、位置和选件以及目标和量度。

**示例提示：**“获取体验定位活动12345的详细信息”。

+++

+++获取Automated Personalization活动

**工具：** `get_abt_activity`

获取有关Automated Personalization (AP)活动的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | AP活动的唯一标识符 |

**返回：**&#x200B;完整的活动详细信息，包括元数据、体验、位置和算法设置。

**示例提示：**“获取自动Personalization活动12345的详细信息”。

+++

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

## 优惠工具 {#tools-offers}

+++列出优惠

**工具：** `list_target_offers`

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

+++获取优惠

**工具：** `get_target_offer`

获取有关特定选件的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `offer_id` | 整数 | 是 | 优惠的唯一标识符 |

**返回：**&#x200B;完整的选件详细信息，包括`id`、`name`、`type`、`content`、`workspace`和`modifiedAt`。

**示例提示：**“获取选件67890的详细信息”。

+++

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

## 受众工具 {#tools-audiences}

+++列出受众

**工具：** `list_target_audiences`

列出[!DNL Target]租户中的所有受众。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `limit` | 整数 | 否 | 要返回的最大受众数 |
| `offset` | 整数 | 否 | 为分页而跳过的受众数量 |

**返回：**&#x200B;包含`audiences`的JSON对象（对象列表，包括`id`、`name`、`description`、`origin`、`modifiedAt`）和`total`。

**示例提示：**“列出所有受众”。

+++

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

## Mbox工具 {#tools-mboxes}

+++列表mbox

**工具：** `list_target_mboxes`

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

+++获取mbox

**工具：** `get_target_mbox`

获取有关特定mbox的详细信息。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `mbox_name` | 字符串 | 是 | mbox的名称 |

**返回：** Mbox详细信息，包括`name`、`status`以及使用mbox的活动列表。

**示例提示：**“获取mbox &#39;homepage-hero&#39;的详细信息。”

+++

+++列出mbox配置文件属性

**工具：** `list_target_mbox_profile_attributes`

列出所有可用于定位的mbox配置文件属性。

无需参数。

**返回：**&#x200B;配置文件属性对象的JSON数组。

**示例提示：**“哪些配置文件属性可用于定位？”

+++

## 资产工具 {#tools-properties}

+++列表属性

**工具：** `list_target_properties`

列出[!DNL Target]租户中的所有属性。

属性可组织活动并控制访问权限。

无需参数。

**返回：**&#x200B;属性对象列表，包括`id`、`name`、`description`和`channel`。

**示例提示：**“列出所有Target属性”。

+++

## 报告工具 {#tools-reporting}

+++获取A/B性能报表

**工具：** `get_ab_performance_report`

获取A/B活动的性能报表。

检索转化率、提升度和置信度级别。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时段（例如`last7days`、`last30days`或自定义日期范围） |

**返回：**&#x200B;体验级别的量度（访客数、转化率、转化率）、提升度计算、统计置信水平和收入量度（如果已配置）。

**示例提示：**“显示过去30天的A/B测试12345性能报告。”

+++

+++获取A/B订单报表

**工具：** `get_ab_orders_report`

获取A/B活动的订单/收入报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | A/B活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;订单计数、收入和平均订单值（按体验）。

**示例提示：**“获取活动12345的订单报告”。

+++

+++获取体验定位性能报表

**工具：** `get_xt_performance_report`

获取体验定位活动的性能报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;体验级别的绩效指标。

**示例提示：**“显示我的体验定位活动54321的性能”。

+++

+++获取体验定位订单报表

**工具：** `get_xt_orders_report`

获取体验定位活动的订单/收入报表。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `activity_id` | 整数 | 是 | XT活动的唯一标识符 |
| `report_interval` | 字符串 | 否 | 报告的时间段 |

**返回：**&#x200B;按体验排序的量度。

**示例提示：**“获取XT活动54321的订单数据”。

+++

+++按活动名称获取性能报表

**工具：** `get_activity_report_by_name`

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

+++预览活动

**工具：** `preview_activity`

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

+++列出响应令牌

**工具：** `list_target_response_tokens`

列出[!DNL Target]租户中的所有响应令牌。

检索所有已配置的响应令牌，包括内置和自定义响应令牌。

无需参数。

**返回：**&#x200B;响应令牌对象的JSON数组，状态为`name`、`type`和`enabled`。

**示例提示：**“列出所有响应令牌”。

+++

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

## 修订版工具 {#tools-revisions}

+++获取审核日志

**工具：** `get_target_revisions`

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

+++获取特定实体的修订

**工具：** `get_target_entity_revisions`

按ID获取特定实体的所有修订。

| 参数 | 类型 | 必需 | 描述 |
|---|---|---|---|
| `revision_resource_type` | 字符串 | 是 | 资源类型： `activity`、`offer`或`audience` |
| `entity_id` | 整数 | 是 | 实体的唯一标识符 |

**返回指定实体的所有修订的** JSON数组。

**示例提示：**“向我显示对活动12345所做的所有更改。”

+++

## 模板工具 {#tools-templates}

+++列出可用模板

**工具：** `list_target_templates`

列出用于创建活动和选件的可用MCP资源和模板。

无需参数。

**返回：** JSON对象列出了可用的模板和资源。

**示例提示：**“哪些模板可用于创建活动？”

+++

## 工具摘要 {#tools-summary}

| 类别 | 计数 | 工具 |
|---|---|---|
| 活动 | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| 产品建议 | 2 | `list_target_offers`, `get_target_offer` |
| 受众 | 1 | `list_target_audiences` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| 属性 | 1 | `list_target_properties` |
| 报表 | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| 预览 | 1 | `preview_activity` |
| 响应令牌 | 1 | `list_target_response_tokens` |
| 修订 | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| 模板 | 1 | `list_target_templates` |
| **合计** | **21** | |

## 相关资源 {#tools-related}

* [使用MCP客户端](target-mcp.md)
* [[!DNL Adobe Target]管理员API引用](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
