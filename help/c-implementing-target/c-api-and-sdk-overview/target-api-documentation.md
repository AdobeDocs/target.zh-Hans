---
keywords: api;adobe i/o
description: 此信息可帮助您从 Target 旧版 API 迁移到 Adobe I/O 上的新版 API。
title: 从 Target 旧版 API 迁移到 Adobe I/O
feature: server-side
topic: Standard
uuid: f8a0ab54-5840-4430-b9be-19e689b1c09a
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 93%

---


# 从 Target 旧版 API 迁移到 Adobe I/O{#transition-from-target-legacy-apis-to-adobe-i-o}

此信息可帮助您从 Target 旧版 API 迁移到 Adobe I/O 上的新版 API。

Adobe Target Classic 停用后，与 Target Classic 帐户关联的 API 也无法使用。本文档将帮助您从基于旧版 API 的集成迁移到由 Adobe I/O 提供支持的 Target API。

有关 Target API 文档的更多信息，请参阅 [Target API 和 NodeJS SDK](../../c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6)。

## 术语 {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| 术语 | 描述 |
|--- |--- |
| 旧版 API | 与 Target Classic 帐户关联的 API。这些 API 调用以基于用户名和密码的身份验证为基础，且使用主机名 `testandtarget.omniture.com`。如果您的 API 调用包含请求 URL 中的用户名和密码，则必须将其转换为 Adobe I/O API。 |
| Adobe I/O | Adobe I/O 是 Target API 的新网关。这些 API 与 Target Standard/Premium 帐户相关联。Adobe I/O 上的 Target API 使用基于 JWT 的身份验证，这是确保企业 API 安全的行业标准。 |

## 时间表 {#section_A478EBF637554A2DB5A31661955121ED}

Target Classic 停用后，旧版 API 也会随之停用：

| 日期 | 详细信息 |
|--- |--- |
| 2017 年 10 月 17 日 | 所有执行写入操作的 API 方法（`saveCampaign`、`copyCampaign`、`saveHTMLOfferContent` 和 `setCampaignState`）都已停用。<br>在这一天，所有 Target Classic 用户帐户都设为只读状态。 |
| 2017 年 11 月 14 日 | 其余 API 都停用。在这一天，Target Classic 用户界面停用。 |

上述时间表不会影响 Recommendations Classic API。

## 等效方法 {#section_DDB42CCC172545B09CB728D794CC466B}

下表列出了各旧版 API 方法所对应的新版 Target API 等效方法。旧版 API 返回 XML 响应，而新版 API 则返回 JSON。

新版 API 方法可链接到 API 文档网站中的相应部分。每个 API 方法都提供有相关示例。您还可以使用 Admin Postman Collection，其中包含 Adobe I/O 上所有新版 Adobe API 方法的示例 API 调用。

| 分组 | 旧版 API 方法 | 新版 API 方法 | 注释 |
|--- |--- |--- |--- |
| 营销活动/活动 | 营销活动创建 | [创建 AB 活动](http://developers.adobetarget.com/api/#create-ab-activity)<br>[创建 XT 活动](http://developers.adobetarget.com/api/#create-xt-activity) | 新版 API 为 AB 活动和 XT 活动提供了不同的创建方法。 |
|  | 营销活动更新 | [更新 AB 活动](http://developers.adobetarget.com/api/#update-ab-activity)<br>[更新 XT 活动](http://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | 复制营销活动 | 不适用 | 使用活动创建 API。 |
|  | 营销活动列表 | [列出活动](http://developers.adobetarget.com/api/#list-activities) |  |
|  | 营销活动状态 | [更新活动状态](http://developers.adobetarget.com/api/#update-activity-state) |  |
|  | 营销活动查看 | [按 ID 获取 AB 活动](http://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[按 ID 获取 XT 活动](http://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | 第三方营销活动 ID | 不适用 | 如果您使用的是 thirdpartyID，则可以使用相关的活动方法。 |
| 选件 | 选件创建 | [创建选件](http://developers.adobetarget.com/api/#create-offer) |  |
|  | 选件获取 | [按 ID 获取选件](http://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | 选件列表 | [列出选件](http://developers.adobetarget.com/api/#list-offers) |  |
|  | 文件夹列表 | 不适用 | Target Standard/Premium 不支持文件夹。 |
| 报表 | 营销活动性能报表 | [获取 AB 性能报表](http://developers.adobetarget.com/api/#get-ab-performance-report)<br>[获取 XT 性能报表](http://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | 审计报表 | [获取审计报表](http://developers.adobetarget.com/api/#get-audit-report) |  |
|  | 1-1 内容报表 | [获取 AP 性能报表](http://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| 帐户设置 | 获取主机组 | [列出环境](http://developers.adobetarget.com/api/#list-environments) |  |

## 例外 {#section_09CF9A0E289149279783B4801D1B6D4C}

如果您需要设置例外，请联系您的客户成功经理。

## 帮助 {#section_591F850E2B7A4342B1C233693425415C}

如果您在迁移到 Adobe I/O 上的新版 Target API 时遇到任何问题或需要任何帮助，请联系 Adobe Target 客户关怀团队 (tt-support@adobe.com)。
