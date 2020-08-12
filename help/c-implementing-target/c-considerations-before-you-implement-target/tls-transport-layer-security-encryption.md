---
keywords: tls;tls 1.0;transport layer security;encryption;tls 1.1;tls 1.2
description: 此信息介绍了对以下方面所做的更改：Adobe 和 Target 如何使用 TLS（传输层安全性）来保持最高安全标准和提高客户数据安全性。
title: TLS（传输层安全性）加密更改
feature: null
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 61%

---


# TLS（传输层安全性）加密更改{#tls-transport-layer-security-encryption-changes}

有关Adobe和Adobe Target如何使用TLS（传输层安全）来维护最高安全标准并提升客户数据安全性的更改的信息。

传输层安全性 (TLS) 是当前使用的部署最广泛的安全协议，可用于 Web 浏览器和其他需要通过网络安全交换数据的应用程序。Adobe 设有安全合规性标准，该标准要求结束旧协议的生命周期，并且强制使用 TLS 1.2，以便使用最新且最安全的版本。

>[!IMPORTANT]
>
>2020年3月1日之后，Adobe Target将不再支持Visual Experience Composer(VEC)、Enhanced Experience Composer(EEC)、Discation Composer(活动投放)、API等的TLS 1.1加密。 请在2020年3月1日之前升级到TLS 1.2，以避免出现任何问题。

我们希望这不会对客户数据或报表产生重大影响。

## 启用增强型体验编辑器 (EEC) 的可视化体验编辑器 (VEC){#section_B374B62DEC3344C194AC7BECC2EE0AA0}

自2020年3月1日起，TLS 1.2为默认值，不再支持TLS 1.1。

Adobe 会分阶段地将客户移到 TLS 1.2。针对域已经符合 1.2 的客户，我们会将其移到 TLS 1.2，而不需要您做出任何更改。大多数客户域已支持TLS 1.2;但是，如果您的域不支持TLS 1.2，我们将像今天一样（2020年3月之前）将这些域保留在TLS 1.1上。

在此迁移阶段，您应该不会遇到任何问题。如果 VEC 停止加载早期运行的某个网站，请[打开客户关怀票证](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)，将此迁移作为可能的原因。

但是，如果您是使用TSL 1.1但不支持TLS 1.2的客户之一，则您应计划将域／基础结构移动到TLS 1.2。我们将继续支持TLS 1.1协议，直到2020年3月1日。 从2020年3月1日开始，目标将不支持要通过增强体验书写器功能用于VEC的TLS 1.1协议。

尽管我们强烈建议大家今后使用 TLS 1.2，但如果您是新客户且确实“不”**&#x200B;支持 TLS 1.2，请联系客户关怀团队，告知他们您需要对增强型体验编辑器使用 TLS 1.1。但是，请计划迁移到TLS 1.2，因为2020年3月1日之后也不支持您。

## Activity delivery {#section_46CA5943E4354B259014C2BF340AECD6}

从2020年3月1日开始，目标服务器将不再支持TLS 1.1。通过此更改，目标服务器将不再接受使用不支持TLS 1.2（或更高版本）的旧设备或Web浏览器的访客的请求。 因此，仅支持 TLS 1.1（或默认支持 TLS 1.1）的旧设备和浏览器将不会收到来自 Adobe Target 的活动内容。网站的默认内容将会呈现出来。

一些将受到影响的旧设备和浏览器包括：

* Google Chrome(Chrome for Android)版本29及更早版本
* Opera Browser(Opera Mobile)12.17及更早版本
* Mozilla Firefox（适用于移动设备的Firefox）版本26及更早版本
* Android 4.3 及更早版本
* Windows 7 及更早版本上的 Internet Explorer 8-10
* Windows Phone 8.0 上的 Internet Explorer 10
* Safari 6.0.4/OS X 10.8.4 及更早版本

在计划进行此更改时，请考虑以下事项（请注意，2020年3月1日的截止日期会影响所有这些项目）:

* 您必须确保默认网站已按照可用于兼容设备和浏览器的方法准备就绪。
* 请注意，Target 报表中的访客数量可能会显示略微降低。
* 您可能需要更改专门为目标不支持TLS 1.2的旧设备或浏览器而创建的受众。对这些设备和浏览器的投放将不再有效。

For more details about supported browsers and their versions, see [Supported Browsers](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## Adobe Target API {#section_88797FA5434049EC89F908853CC76903}

从2020年3月1日开始，目标API将不再支持TLS 1.1加密。 访问该 API 的客户应当确认他们不会受到影响。

* 在默认设置下使用 Java 7 的 API 客户端将需要进行修改才能支持 TLS 1.2。有关更多信息，请参阅 Java 网站上的“[更改客户端端点的默认 TLS 协议版本：从 TLS 1.0 到 TLS 1.2](https://www.java.com/en/configure_crypto.html)”。
* 使用 Java 8 的 API 客户端应当不会受到影响，因为其默认设置为 TLS 1.2。
* 使用其他框架的 API 客户端将需要联系各自的供应商来获取有关 TLS 1.2 支持的详细信息。

## Access to Experience Cloud Solutions interfaces {#section_748870ADE77B4CBEB18518DC784E64E5}

由于 Target Standard/Premium 界面已要求使用[现代化的 Web 浏览器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)，因此我们预计不会出现任何问题。如果您无法连接 Target，则应将您的浏览器升级到最新版本。

## How to check which TLS version your browser uses {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

要使用Google Chrome在您的网站上检查TLS版本，请执行以下操作：

1. 在Chrome中打开受影响的网站。
1. 从Chrome菜单（三个垂直椭圆）中，单击“更多工具”>“开发人员工具”。

   ![Chrome 开发人员工具](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 打开“安全”选项卡，然后检查“连接：

   ![TLS版本详细信息](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>这些说明在发布时为最新说明，可能会有更改。 如果这些说明发生更改，快速Internet搜索应会有所帮助。  其他浏览器具有类似的步骤。

## 支持1.2以下TLS版本的浏览器的预期行为 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

本节介绍仅在使用at.js或mbox.js实施时，支持1.2以下TLS版本的浏览器会发生什么情况。 为便于比较，本节还介绍支持TLS 1.2的浏览器的预期。

### 中心端点

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 启用TLS 1.0或TLS 1.1时：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li></ul>已启用 TLS 1.2：<ul><li>下载 at.js 文件。</li></ul> |
| mbox.js | 启用TLS 1.0或TLS 1.1时：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li></ul>已启用 TLS 1.2：<ul><li>下载 mbox.js 文件。</li></ul> |

### 边缘端点

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 启用TLS 1.0或TLS 1.1时：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li><li>提供了默认内容。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容。</li></ul> |
| mbox.js | 启用TLS 1.0或TLS 1.1时：<ul><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li><li>用户会看到“无法安全连接到该页面”的信息。这则信息说明，这种情况可能是由于网站使用过时的或不安全的 TLS 安全设置引起的。</li><li>没有显示控制台错误。</li><li>提供了默认内容。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容</li></ul> |

### 活动针对浏览器版本受众（Internet Explorer、6、7或8版）

>[!NOTE]
>
>受众停止工作。

| Target JavaScript 实施 | 详细信息 |
|--- |--- |
| at.js | 版本低于 10 的 Internet Explorer 版本不支持 at.js。 |
| mbox.js | 启用TLS 1.0或TLS 1.1时：<ul><li>提供了默认内容。</li><li>没有触发 Target 请求。</li><li>没有显示控制台错误。</li><li>使用浏览器开发工具，在“网络”选项卡上，您会看到“200 OK”。这意味着请求已成功。</li></ul>已启用 TLS 1.2：<ul><li>提供了选件内容。</li></ul> |