---
keywords: tls;tls 1.0;transport layer security;encryption
description: 此信息介绍了对以下方面所做的更改：Adobe 和 Target 如何使用 TLS（传输层安全性）来保持最高安全标准和提高客户数据安全性。
title: TLS（传输层安全性）加密更改
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: 1a502cc9c235ee765f24f04acf60b6fd75c369dc

---


# TLS（传输层安全性）加密更改{#tls-transport-layer-security-encryption-changes}

此信息介绍了对以下方面所做的更改：Adobe 和 Target 如何使用 TLS（传输层安全性）来保持最高安全标准和提高客户数据安全性。

传输层安全性 (TLS) 是当前使用的部署最广泛的安全协议，可用于 Web 浏览器和其他需要通过网络安全交换数据的应用程序。[!DNL Adobe] 设有安全合规性标准，该标准要求结束旧协议的生命周期，并且强制使用 TLS 1.2，以便使用最新且最安全的版本。

>[!IMPORTANT]
>
>2020年2月之后，Adobe Target将不再支持针对Visual Experience Composer(VEC)、Enhanced Experience Composer(EEC)、活动交付和API等的TLS 1.1加密。 请在2002年2月之前升级到TLS 1.2以避免任何问题。

我们希望这不会对客户数据或报表产生重大影响。

## 启用增强型体验编辑器 (EEC) 的可视化体验编辑器 (VEC){#section_B374B62DEC3344C194AC7BECC2EE0AA0}

到目前为止，Adobe Target 的[增强型体验编辑器](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) (EEC) 默认会使用 TLS 1.0。在2020年2月之后，默认情况下，Target将转向TLS 1.2。

Adobe 会分阶段地将客户移到 TLS 1.2。针对域已经符合 1.2 的客户，我们会将其移到 TLS 1.2，而不需要您做出任何更改。大多数客户域已经支持 TLS 1.2，但是，如果您的域不支持 TLS 1.2，我们仍会像目前一样将这些域保留在 TLS 1.0（直至 2020 年 2 月）。

在此迁移阶段，您应该不会遇到任何问题。如果 VEC 停止加载早期运行的某个网站，请[打开客户关怀票证](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，将此迁移作为可能的原因。

但是，如果您是使用 TSL 1.0 且不支持 TLS 1.2 的客户，则应规划将您的域/基础设施迁移到 TLS 1.2。我们会继续支持 TLS 1.0 协议，直至 2020 年 2 月。从 2020 年 2 月开始，Target 将不再支持通过增强型体验编辑器功能对 VEC 使用 TLS 1.0。

尽管我们强烈建议大家今后使用 TLS 1.2，但如果您是新客户且确实“不”**&#x200B;支持 TLS 1.2，请联系客户关怀团队，告知他们您需要对增强型体验编辑器使用 TLS 1.0。但是，请制定转移到 TLS 1.2 的计划，因为 2020 年 2 月之后也将不再为您提供支持。

## Activity delivery {#section_46CA5943E4354B259014C2BF340AECD6}

从 2020 年 2 月开始，Target 服务器将不再支持 TLS 1.0。伴随着这项更改，Target 服务器将不再接受最终用户使用不支持 TLS 1.1 或更高版本的旧设备或 Web 浏览器发送的请求。因此，仅支持 TLS 1.0（或默认支持 TLS 1.0）的旧设备和浏览器将不会收到来自 Adobe Target 的活动内容。网站的默认内容将会呈现出来。

一些将受到影响的旧设备和浏览器包括：

* Android 4.3 及更早版本
* Windows 7 及更早版本上的 Internet Explorer 8-10
* Windows Phone 8.0 上的 Internet Explorer 10
* Safari 6.0.4/OS X 10.8.4 及更早版本

在您针对这项更改进行规划时，需考虑以下事项（请注意，2020 年 2 月这一截止日期会影响所有这些项目）：

* 您必须确保默认网站已按照可用于兼容设备和浏览器的方法准备就绪。
* 请注意，Target 报表中的访客数量可能会显示略微降低。
* 您可能需要更改专门针对不支持 TLS 1.0 的旧设备或浏览器创建的受众，否则针对这些设备和浏览器的交付将无法再正常运行。

有关受支持的浏览器及其版本的更多详细信息，请参阅[支持的浏览器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)。

## Adobe Target API {#section_88797FA5434049EC89F908853CC76903}

从 2020 年 2 月开始，Target API 将不再支持 TLS 1.0 加密。访问该 API 的客户应当确认他们不会受到影响。

* 在默认设置下使用 Java 7 的 API 客户端将需要进行修改才能支持 TLS 1.2。有关更多信息，请参阅 Java 网站上的“[更改客户端端点的默认 TLS 协议版本：从 TLS 1.0 到 TLS 1.2](https://www.java.com/en/configure_crypto.html)”。
* 使用 Java 8 的 API 客户端应当不会受到影响，因为其默认设置为 TLS 1.2。
* 使用其他框架的 API 客户端将需要联系各自的供应商来获取有关 TLS 1.2 支持的详细信息。

## Access to Experience Cloud Solutions interfaces {#section_748870ADE77B4CBEB18518DC784E64E5}

由于 Target Standard/Premium 界面已要求使用[现代化的 Web 浏览器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)，因此我们预计不会出现任何问题。如果您无法连接 Target，则应将您的浏览器升级到最新版本。

## How to check which TLS version your browser uses {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

要使用Google Chrome检查您网站上的TLS版本，请执行以下操作：

1. 在Chrome中打开受影响的网站。
1. 从Chrome菜单（三个垂直椭圆）中，单击“更多工具”>“开发人员工具”。

   ![Chrome 开发人员工具](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 打开“安全”选项卡，然后检查“连接：

   ![TLS版本详细信息](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>这些说明在发布时为最新说明，可能会有所更改。 如果这些说明发生更改，Internet快速搜索应会有所帮助。  其他浏览器具有类似的步骤。

## Expected behavior with browsers supporting TLS 1.0 Only {#section_B5DA97A34EF248EB927610A5DA71EF2F}

本节介绍了使用 at.js 或 mbox.js 实施时，仅支持 TLS 1.0 的浏览器预期发生的情况。为便于比较，本节还介绍支持TLS 1.2的浏览器的预期功能。

### 中心端点

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 已启用 TLS 1.0：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li></ul>已启用 TLS 1.2：<ul><li>下载 at.js 文件。</li></ul> |
| mbox.js | 已启用 TLS 1.0：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li></ul>已启用 TLS 1.2：<ul><li>下载 mbox.js 文件。</li></ul> |

### 边端点

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 已启用 TLS 1.0：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li><li>提供了默认内容。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容。</li></ul> |
| mbox.js | 已启用 TLS 1.0：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li><li>提供了默认内容。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容</li></ul> |

### 针对浏览器版受众的活动（Internet Explorer、版本6、7或8）

>[!NOTE]
>
>受众停止工作。

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 版本低于 10 的 Internet Explorer 版本不支持 at.js。 |
| mbox.js | 已启用 TLS 1.0：<ul><li>提供了默认内容。</li><li>没有触发 Target 请求。</li><li>没有显示控制台错误。</li><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容。</li></ul> |