---
keywords: at.js；非生产；非生产；部署
description: 了解旧版mbox.js的Adobe Target实现。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 如何将at.js部署到非生产环境?
feature: at.js
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# 将at.js部署到非生产环境

有关将 at.js 安全地部署到非生产环境的技术信息。

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
