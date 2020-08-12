---
description: 有关如何将 at.js 安全地部署到非生产环境的信息。
title: 将 at.js 部署到非生产环境
feature: null
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 92%

---


# Deploy at.js to a non-production environment{#deploy-at-js-to-a-non-production-environment}

有关将 at.js 安全地部署到非生产环境的技术信息。

## 部署到 DTM 测试环境

如果您使用 DTM，则可以轻松地将 at.js 保存到 Adobe Target 工具配置中。

保存该库后，可使用 DTM 切换工具来针对您的生产代码对其进行测试。这还方便 Adobe 顾问为您提供支持。

有关更多信息，请参阅《使用动态标签管理实施 Adobe Target 的最佳实践》**&#x200B;指南中的[选项 3：通过由 DTM 托管的 Target JavaScript 库手动实施 Target](https://docs.adobe.com/content/help/en/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html)。

## 使用“Requestly”Chrome 扩展映射到其他文件

>[!NOTE]
>
>除了以下信息外，您还可以使用适用于 Google Chrome 的 [Adobe Target VEC 助手浏览器扩展](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) 是一个免费的 Chrome 扩展，可使您将请求重定向到替代 URL。

您可以先将 at.js 部署到一个 URL，然后使用 Requestly 将当前的 mbox.js 文件 URL 映射到新的 at.js URL。之后，每当网站尝试加载 mbox.js 时，它都会实际加载 at.js。Adobe 也可以通过此方法更加轻松地为您提供支持。

## 部署到开发环境、测试环境或 QA 环境

如果您在代码库中托管 mbox.js，并且能够方便地更新代码环境，请将 at.js 部署到一个较低级别的环境中。

为了使 Adobe 能够更好地提供支持，请将该文件部署到 Adobe 能够访问的环境中。

## 使用 Charles 或 Fiddler 映射到本地文件

[Charles Web 调试代理](https://www.charlesproxy.com/)是一款适用于 Mac 和 Windows 的应用程序，其“映射本地”功能可用于将您加载的 mbox.js 生产文件映射到 at.js 的本地副本。可在 Mac 和 Windows 中下载此应用程序的免费试用版。

[Fiddler](https://www.telerik.com/fiddler) 是一种类似的工具，可在 Windows 中免费下载。

## 部署到其他标签管理器环境

如果您使用的是其他标签管理器，则该管理器或许可以在不影响您的生产流量的情况下安全部署 at.js。