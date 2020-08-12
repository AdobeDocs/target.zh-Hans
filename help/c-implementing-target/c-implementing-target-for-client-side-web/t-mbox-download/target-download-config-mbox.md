---
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
description: Target Standard 和 Premium 使用修改版的 Adobe Target mbox.js 文件。
title: 下载 mbox.js
feature: null
subtopic: Getting Started
topic: Standard
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 94%

---


# 下载 mbox.js{#download-mbox-js}

Target Standard 和 Premium 使用修改版的 Adobe Target mbox.js 文件。

要使用 [!DNL Adobe Target][!UICONTROL  可视化体验编辑器]，您必须在 [!DNL mbox.js] 文件中额外包含一行 JavaScript。

1. 单击 **[!UICONTROL 中的]** “管 **[!UICONTROL 理”]** > [!DNL Target Standard]“实施”。
1. 单击&#x200B;**[!UICONTROL 下载 mbox.js]**，然后根据提示操作，以保存该文件。
1. （视情况而定）如果您使用的是 [!DNL mbox.js] 版本 60 或更高版本，则可以对库进行配置，以便在默认情况下自动隐藏页面内容直到 mbox 加载为止，从而减少响应式网站上出现闪烁情况。

   有关更多信息，请参阅 [mbox.js 高级设置](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)中的“禁止页面加载闪烁”。

1. 在网站上创建 [!DNL mbox.js] 引用。

   从 [!DNL mbox.js] 版本 57 开始，[!DNL mbox.js] 引用可以放置在页面 `<head>` 部分中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本低于 57，则该引用必须是页面 `<head>` 部分中的最后一项。如果 mbox.js 引用不是最后一项，则可能会引发严重的显示或性能问题。请参 [阅mbox.js的用途](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) ，了解更多信息。

1. 将保存的 [!DNL mbox.js] 文件上传到您在代码中指定的托管环境位置。
