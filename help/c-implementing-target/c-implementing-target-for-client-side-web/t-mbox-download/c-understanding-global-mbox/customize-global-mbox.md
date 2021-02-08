---
keywords: 全局mbox；自定义全局mbox；编辑at.js;at.js;implement at.js
description: 了解如何通过Adobe Target的“管理——实施”页面为at.js自定义全局mbox。
title: 如何自定义全局mbox?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 50%

---


# 自定义全局 mbox

帮助您为at.js自定义全局mbox的信息。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。

1. 禁用&#x200B;**[!UICONTROL 页面加载（自动创建全局mbox）]**，然后添加自定义全局mbox的名称，以用于从[!DNL Target]传送活动。

   此自定义全局 mbox 还用于点击跟踪。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 完成后，单击&#x200B;**[!UICONTROL 保存]**。

1. 在您的站点上实施[!DNL at.js]库。

   有关详细信息，请参阅[如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)。

1. 在您的版本中安排进行转换。

   在您准备好 [!DNL Target] 以开始将全局 mbox 用于所有活动后，您便可以立即开始执行此步骤。

   更新自定义全局 mbox 的名称，以使其匹配上面步骤 2 中所使用的名称。

   >[!IMPORTANT]
   >
   >保存后，您帐户中的所有活动都会与此 mbox 同步。如果此 mbox 不在您的网站上，则所有活动都将停止运行。

