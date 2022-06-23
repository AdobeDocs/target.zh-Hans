---
keywords: 全局mbox；自定义全局mbox；编辑at.js;at.js；实施at.js
description: 了解如何在Adobe Target的“管理实施”页面上自定义at.js的全局mbox。
title: 如何自定义全局mbox?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 17%

---

# 自定义全局 mbox

可帮助您自定义 [!DNL Adobe Target] 适用于at.js的全局mbox。

1. 单击&#x200B;**[!UICONTROL “管理”]**>**[!UICONTROL “实现”]**。

1. 禁用 **[!UICONTROL 启用页面加载（自动创建全局mbox）]**，然后添加要用于从交付活动的自定义全局mbox的名称 [!DNL Target].

   >[!IMPORTANT]
   >
   >当您选择其他全局mbox时，将自动保存更改。

   此自定义全局 mbox 还用于点击跟踪。

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. 实施 [!DNL at.js] 库。

   请参阅 [如何部署at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/) 以了解更多信息。

1. 在您的版本中安排进行转换。

   准备好 [!DNL Target] 要开始将全局mbox用于将来的所有活动，您可以继续执行此步骤。

   更新自定义全局 mbox 的名称，以使其匹配上面步骤 2 中所使用的名称。

   >[!IMPORTANT]
   >
   >您帐户中的所有活动均与此mbox同步。 确保您的网站上存在全局mbox，以便活动可以继续运行。 请务必编辑并重新保存之前通过与此mbox同步的可视化体验编辑器(VEC)创建的受影响活动。 无需重新保存在基于表单的体验编辑器中或通过API创建的活动。

