---
keywords: 体验预览;体验 URL;生成 URL;查看体验 URL
description: 了解如何使用体验预览URL进行Adobe [!DNL Target] Automated Personalization活动，以便在活动开始之前直接在您的网站上查看体验内容。
title: 如何在Automated Personalization活动中使用体验预览URL?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 51%

---

# 用体验预览 URL 预览 Automated Personalization 活动

可以为生成体验预览URL [!DNL Target] [!UICONTROL Automated Personalization] 活动，以便在活动开始之前直接在您的网站上查看体验内容，以进行预览和QA。 体验预览URL会绕过定位，以强制查看特定体验。

>[!NOTE]
>
>您可以为其他类型的 [!DNL Target] 活动。 但是，过程略有不同。 有关更多信息，请参阅[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md#preview)。。

使用体验预览URL与团队成员共享体验，并跨浏览器和环境进行QA体验，而无需创建单独的QA活动。 如果网站很复杂，或者您的安全策略不允许在模拟器中查看网站，则此功能将特别有用。

1. 创建[自动个性化活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)，或单击相应的活动以将其打开。

   无需激活活动，即可预览体验。

1. 在活动概述页面上，单击三个垂直圆点，然后单击 **[!UICONTROL 查看体验URL]**.

1. 查看和/或指定 URL。

   * 如果您使用 [!UICONTROL 可视化体验编辑器] (VEC)，系统会自动输入您为活动指定的默认URL，并为活动中的每个体验生成一个链接。 如有需要，您可以更改此 URL，并添加其他 URL。
   * 如果您使用 [!UICONTROL 基于表单的体验编辑器]，则不会自动输入默认URL。 如果您之前未创建体验预览URL，请单击 **添加新URL**. 您必须指定所有要预览的 URL，并指定每个 URL 的名称。

   您可以添加多个 URL，如果您在运行一个多页面测试或模板测试，并且想要在多个页面上预览活动，则需要使用多个 URL。

   模式窗口会显示指向您网站上的体验的链接，以便在 [!DNL Target] VEC. 您必须通过共享消息中的链接来共享预览。如果单击链接，然后从页面复制生成的 URL，则不会起作用，因为 URL 包含只有在从消息中的链接访问页面时才会正确显示页面的参数。应当采取的正确操作是，复制模态窗口中的文本，然后通过电子邮件将整个文本发送给您的团队。

1. 单击&#x200B;**[!UICONTROL 生成所有]**，然后单击每个体验以进行预览。

   如果您随后更改了体验，请确保通过返回到模式窗口并单击来为团队生成新的预览链接 **续订链接** 以获取新链接。

   >[!NOTE]
   >
   >预览链接会在新选项卡中打开，并要求禁用浏览器上的弹出窗口阻止程序。

1. 单击每个体验名称以预览活动。

   页面随即会打开，并显示活动。

1. 单击&#x200B;**[!UICONTROL 完成]**&#x200B;以返回到活动摘要。

## 注意事项 {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**生成体验预览URL**

* 体验预览URL不受体验之间流量划分的影响。
* 在受众级别进行定位不会影响预览。
* 您可以为每个活动自动生成最多 300 个体验 URL。超过该限制后，必须手动生成 URL。
* 根据体验的数量，生成 URL 最多可能需要五分钟。请勿关闭对话框，否则生成的URL将丢失。
* 生成的预览链接在两个月内有效。两个月后，您必须重新生成预览 URL。
* 只要体验发生了更改，您都必须重新生成预览 URL。

**共享体验预览URL**

* 即使您不是目标受众的成员，您也能够预览体验。
* 您可以与无权访问的同事共享体验预览URL [!DNL Adobe Target].

**使用体验预览URL查看体验**

* 只要页面未发生更改，便可预览任何已保存的活动。
* 无论活动处于活动状态还是处于非活动状态，体验预览URL都可用。
* 您无法预览 [!UICONTROL 草稿] 状态。
* 查看体验预览URL不会对报表产生影响。

**体验预览URL故障诊断**

* 如果您无法在新选项卡中查看预览（由于浏览器缓存问题），请尝试刷新两三次，或者复制链接，然后在其他浏览器、新的会话或私密浏览器模式中打开该链接。
