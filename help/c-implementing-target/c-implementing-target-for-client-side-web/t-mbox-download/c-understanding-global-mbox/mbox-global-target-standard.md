---
keywords: global mbox;target classic;use global mbox from target classic
description: 默认情况下，Target Standard 会创建一个名为 target-global-mbox 的全局 mbox，它可用于运行在 Target Standard 中创建的活动。但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 Target Standard 活动。
title: 使用旧版实施中的全局 mbox
feature: null
subtopic: Getting Started
topic: Standard
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 45%

---


# 使用旧版实施中的全局 mbox{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. 但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 [!DNL Target] 活动。

>[!NOTE]
>
>您的每一个帐户只能有一个全局 mbox。

要将现有的全局 mbox 用于 [!DNL Target] 和旧版实施，您必须设置一些参数。

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. 如果要使用尚不存在的mbox，请创建mbox。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您的帐户中的 mbox.js 设置已更新。

1. 下载新的at.js文件并在您的网站上引用它。

   所有现有的活动均已更新为使用指定的全局 mbox，包括之前已创建和实施的活动。

## 全局mbox实施疑难解答

以下常见问题解答可用于解决您的全局mbox实施问题：

### 为什么不加载全局mbox，或者为什么在加载页面时加载全局mbox时存在延迟？*

确保at.js引用是页面上的第一个JavaScript调用。 有关此问题的其他解决方案，请参 [阅全局mbox常见问题](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)。
