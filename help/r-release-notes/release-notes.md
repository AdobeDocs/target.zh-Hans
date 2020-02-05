---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e7a866c01b03815a2e167612d4c7922cef54a5c0

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含Target API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!IMPORTANT]
>
>从2020年3月1日开始，Target将禁用对TLS 1.1和TLS 1.0加密的支持。 传输层安全性 (TLS) 是当前使用的部署最广泛的安全协议，可用于 Web 浏览器和其他需要通过网络安全交换数据的应用程序。需要进行此更改以符合TLS 1.2或更高版本的公认安全合规标准。 检查您当前使用的TLS版本。 如果您的版本低于1.2，请在2020年3月1日之前实施所需的更改，以便继续按预期使用Target。
>
> 有关可能的影响以及更新实施时可能需要采取的步骤的详细信息，请参阅 [TLS（传输层安全）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。

括号中的问题编号供 [!DNL Adobe] 内部使用。

## Target Standard/Premium 20.1.1（2020 年 2 月 4 日） 

Target Standard/Premium 20.1.1版本是维护版本，包括后端增强和改进。 此外，还包含以下修复：

* 修复了导致Adobe Analytics跟踪服务器字段在现有Adobe for Target(A4T)活动的“目标和设置”页面上为空的问题。 (TGT-35960)
* 修复了用户界面中的一个问题，该问题导致在创建类别亲和度的受众时，第二个下拉列表中的选择无法显示。 (TGT-36098)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明——目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [发行说明——目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe Target的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关Adobe Target at.js javaScript库各版本中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参 [阅Experience cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
