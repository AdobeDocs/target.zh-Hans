---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: 帮助您为at.js自定义全局mbox的信息。
title: 自定义全局 mbox
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# 自定义全局 mbox{#customize-a-global-mbox}

帮助您为at.js自定义全局mbox的信息。

1. 单击“ **[!UICONTROL 管理]** ”>“ **[!UICONTROL 实施]**”。

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   此自定义全局 mbox 还用于点击跟踪。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 完成后，单击&#x200B;**[!UICONTROL 保存]**。

1. Implement the [!DNL at.js] library on your site.

   请参 [阅如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) ，以了解更多信息。

1. 在您的版本中安排进行转换。

   在您准备好 [!DNL Target] 以开始将全局 mbox 用于所有活动后，您便可以立即开始执行此步骤。

   更新自定义全局 mbox 的名称，以使其匹配上面步骤 2 中所使用的名称。

   >[!IMPORTANT]
   >
   >保存后，您帐户中的所有活动都会与此 mbox 同步。如果此 mbox 不在您的网站上，则所有活动都将停止运行。

