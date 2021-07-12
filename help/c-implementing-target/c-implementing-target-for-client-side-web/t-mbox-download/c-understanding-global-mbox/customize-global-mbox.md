---
keywords: 全局mbox；自定义全局mbox；编辑at.js;at.js；实施at.js
description: 了解如何在Adobe Target的“管理实施”页面上自定义at.js的全局mbox。
title: 如何自定义全局mbox?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# 自定义全局 mbox

此信息可帮助您自定义适用于at.js的全局mbox。

1. 单击&#x200B;**[!UICONTROL “管理”]**>**[!UICONTROL “实现”]**。

1. 禁用&#x200B;**[!UICONTROL 启用页面加载（自动创建全局mbox）]**，然后添加要用于从[!DNL Target]交付活动的自定义全局mbox的名称。

   >[!IMPORTANT]
   >
   >当您选择其他全局mbox时，将自动保存更改。

   此自定义全局 mbox 还用于点击跟踪。

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 在您的网站上实施[!DNL at.js]库。

   有关更多信息，请参阅[如何部署at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md)。

1. 在您的版本中安排进行转换。

   当您准备好[!DNL Target]以开始将全局mbox用于将来的所有活动时，您可以继续执行此步骤。

   更新自定义全局 mbox 的名称，以使其匹配上面步骤 2 中所使用的名称。

   >[!IMPORTANT]
   >
   >您帐户中的所有活动均与此mbox同步。 如果此mbox不在您的网站上，则所有活动都将停止运行。
