---
keywords: 全局 mbox;Target Classic;使用来自 Target Classic 的全局 mbox
description: 了解如何将旧版全局mbox用于Adobe [!DNL Target] 活动。
title: 我能否使用旧版实施中的全局mbox?
feature: at.js
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 36%

---

# 使用旧版实施中的全局mbox

默认情况下， [!DNL Target] 会创建名为target-global-mbox的全局mbox，该mbox用于运行在 [!DNL Target]. 但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 [!DNL Target] 活动。

>[!NOTE]
>
>您的每一个帐户只能有一个全局 mbox。

要将现有的全局 mbox 用于 [!DNL Target] 和旧版实施，您必须设置一些参数。

1. 转到 [!DNL Target]，然后单击 **[!UICONTROL 管理]** > **[!UICONTROL 实施]**.

   默认情况下， **[!UICONTROL 启用页面加载（自动创建全局mbox）]** 启用，且自定义全局mbox名为 `target-global-mbox`.

1. 如果要使用现有的mbox，请禁用 **[!UICONTROL 启用页面加载（自动创建全局mbox）]**，并在 **[!UICONTROL 全局Mbox]** 字段。

   的 [!UICONTROL 全局Mbox] 下拉列表列出了您帐户中的所有mbox。 如果您要使用尚不存在的mbox，请创建该mbox。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您的帐户中的 设置已更新。

1. 下载新的at.js文件，并在您的网站上引用它。

   所有现有的活动均已更新为使用指定的全局 mbox，包括之前已创建和实施的活动。

## 全局mbox实施疑难解答

以下常见问题解答可用于对全局mbox实施进行故障诊断：

### 为何全局 mbox 未加载？或为何页面加载时全局 mbox 的加载有所延迟？

确保at.js引用是页面上的首次JavaScript调用。 有关此问题的其他解决方案，请参阅 [全局mbox常见问题解答](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
