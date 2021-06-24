---
keywords: 实施;Mbox;mbox.js;下载 mbox.js;配置 mbox.js
description: 了解旧版mbox.js的Adobe Target实施。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 如何下载 [!DNL Target] mbox.js库？
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# 下载 mbox.js

Target Standard 和 Premium 使用修改版的 Adobe Target mbox.js 文件。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都将失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的网站出现任何潜在问题。 有关详细信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

要使用 [!DNL Adobe Target][!UICONTROL  可视化体验编辑器]，您必须在 [!DNL mbox.js] 文件中额外包含一行 JavaScript。

1. 单击&#x200B;****>**[!UICONTROL [!DNL Target Standard]中的实施]**。
1. 单击&#x200B;**[!UICONTROL 下载 mbox.js]**，然后根据提示操作，以保存该文件。
1. （视情况而定）如果您使用的是 [!DNL mbox.js] 版本 60 或更高版本，则可以对库进行配置，以便在默认情况下自动隐藏页面内容直到 mbox 加载为止，从而减少响应式网站上出现闪烁情况。

1. 在网站上创建 [!DNL mbox.js] 引用。

   从 [!DNL mbox.js] 版本 57 开始，[!DNL mbox.js] 引用可以放置在页面 `<head>` 部分中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本低于 57，则该引用必须是页面 `<head>` 部分中的最后一项。如果 mbox.js 引用不是最后一项，则可能会引发严重的显示或性能问题。

1. 将保存的 [!DNL mbox.js] 文件上传到您在代码中指定的托管环境位置。
