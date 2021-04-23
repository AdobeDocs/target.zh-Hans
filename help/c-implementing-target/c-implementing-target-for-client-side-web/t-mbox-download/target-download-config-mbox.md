---
keywords: 实施;Mbox;mbox.js;下载 mbox.js;配置 mbox.js
description: 了解旧版mbox.js的Adobe Target实现。 迁移到Adobe Experience Platform Web SDK(AEP Web SDK)或at.js的最新版本。
title: 如何下载 [!DNL Target] mbox.js库？
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 58%

---

# 下载 mbox.js

Target Standard 和 Premium 使用修改版的 Adobe Target mbox.js 文件。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。
>
>我们建议所有客户在此日期前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

要使用 [!DNL Adobe Target][!UICONTROL  可视化体验编辑器]，您必须在 [!DNL mbox.js] 文件中额外包含一行 JavaScript。

1. 单击[!DNL Target Standard]中的&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。
1. 单击&#x200B;**[!UICONTROL 下载 mbox.js]**，然后根据提示操作，以保存该文件。
1. （视情况而定）如果您使用的是 [!DNL mbox.js] 版本 60 或更高版本，则可以对库进行配置，以便在默认情况下自动隐藏页面内容直到 mbox 加载为止，从而减少响应式网站上出现闪烁情况。

   有关更多信息，请参阅 [mbox.js 高级设置](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C)中的“禁止页面加载闪烁”。

1. 在网站上创建 [!DNL mbox.js] 引用。

   从 [!DNL mbox.js] 版本 57 开始，[!DNL mbox.js] 引用可以放置在页面 `<head>` 部分中的任意位置。

   >[!IMPORTANT]
   >
   >如果您使用的 [!DNL mbox.js] 版本低于 57，则该引用必须是页面 `<head>` 部分中的最后一项。如果 mbox.js 引用不是最后一项，则可能会引发严重的显示或性能问题。有关详细信息，请参阅[mbox.js的功能](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md)。

1. 将保存的 [!DNL mbox.js] 文件上传到您在代码中指定的托管环境位置。
