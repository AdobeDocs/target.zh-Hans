---
keywords: global mbox;target classic;use global mbox from target classic
description: 默认情况下，Target Standard 会创建一个名为 target-global-mbox 的全局 mbox，它可用于运行在 Target Standard 中创建的活动。但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 Target Standard 活动。
title: 使用旧版实施中的全局 mbox
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# 使用旧版实施中的全局 mbox{#use-a-global-mbox-from-a-legacy-implementation}

默认情况下，[!DNL Target]会创建一个名为目标-global-mbox的全局mbox，它用于运行在[!DNL Target]中创建的活动。 但是，如果您已经针对旧版实施在页面上创建了一个全局 mbox，则可将该 mbox 用于您的 [!DNL Target] 活动。

>[!NOTE]
>
>您的每一个帐户只能有一个全局 mbox。

要将现有的全局 mbox 用于 [!DNL Target] 和旧版实施，您必须设置一些参数。

1. 转至[!DNL Target]，然后单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。

   默认情况下，**[!UICONTROL 页面加载处于启用状态(启用自动创建全局mbox]**，而自定义全局mbox的名称为`target-global-mbox`。

1. 如果要使用现有mbox，请禁用&#x200B;**[!UICONTROL 启用页面加载（自动创建全局mbox]**），并在&#x200B;**[!UICONTROL 全局Mbox]**&#x200B;字段中指定先前创建的全局mbox的名称。

   [!UICONTROL 全局Mbox]下拉框将列表您帐户中的所有mbox。 如果要使用尚不存在的mbox，请创建mbox。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   您的帐户中的 mbox.js 设置已更新。

1. 下载新的at.js文件并在您的网站上引用它。

   所有现有的活动均已更新为使用指定的全局 mbox，包括之前已创建和实施的活动。

## 全局mbox实施疑难解答

以下常见问题解答可用于解决您的全局mbox实施问题：

### 为何全局 mbox 未加载？或为何页面加载时全局 mbox 的加载有所延迟？

确保at.js引用是页面上的第一个JavaScript调用。 有关此问题的其他解决方案，请参阅[全局mbox常见问题](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)。
