---
description: 默认情况下，Target Standard 会创建一个名为 target-global-mbox 的全局 mbox，它可用于运行在 Target Standard 中创建的活动。但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 Target Standard 活动。
keywords: 全局 mbox;Target Classic;使用来自 Target Classic 的全局 mbox
seo-description: 默认情况下，Target Standard 会创建一个名为 target-global-mbox 的全局 mbox，它可用于运行在 Target Standard 中创建的活动。但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 Target Standard 活动。
seo-title: 使用旧版实施中的全局 mbox
solution: Target
subtopic: 入门指南
title: 使用旧版实施中的全局 mbox
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 使用旧版实施中的全局 mbox{#use-a-global-mbox-from-a-legacy-implementation}

默认情况下，Target Standard 会创建一个名为 target-global-mbox 的全局 mbox，它可用于运行在 Target Standard 中创建的活动。但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 Target Standard 活动。

>[!NOTE]
>
>您的每一个帐户只能有一个全局 mbox。

要将现有的全局 mbox 用于 [!DNL Target Standard] 和旧版实施，您必须设置一些参数。

1. 转到 [!DNL Target Standard]，然后单击**[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]**。

   默认情况下，[!UICONTROL 自动创建全局 mbox] 处于启用状态，且自定义的全局 mbox 被命名为 `target-global-mbox`。
1. 如果您要使用现有的 mbox，请禁用[!UICONTROL 自动创建全局 mbox]，然后在[!UICONTROL 自定义全局 mbox] 字段中指定之前创建的全局 mbox 的名称。

   “[!UICONTROL 自定义全局 Mbox]”下拉列表列出了您帐户中的所有 mbox。如果您要使用尚不存在的 mbox，请在 Target Classic 中创建该 mbox。
1. 单击**[!UICONTROL 保存]**。

   您的帐户中的 mbox.js 设置已更新。
1. 下载新的 mbox.js 文件，并在您的网站中引用它。

   使用新的 mbox.js 文件更新您的生产网站后，您便可以设置首选项。
1. 单击**[!UICONTROL 设置]** &gt; **[!UICONTROL 首选项]**。
1. 在[!UICONTROL 自定义全局 mbox] 字段中，指定在实施页面中选择的全局 mbox 的名称。
1. 单击**[!UICONTROL 提交]**。

   所有现有的活动均已更新为使用指定的全局 mbox，包括之前已创建和实施的活动。
   **全局 Mbox 实施故障诊断***为何全局 mbox 未加载？或为何页面加载时全局 mbox 的加载有所延迟？*

请确保 mbox.js 引用是页面上的第一个 JavaScript 调用。有关此问题的其他解决方案，请参阅 [Mbox.js 实施](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420)。
