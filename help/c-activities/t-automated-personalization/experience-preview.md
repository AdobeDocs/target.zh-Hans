---
keywords: experience preview;experience urls;generate urls;view experience urls
description: 可以为Target自动个性化活动生成体验预览URL，以便在活动实时进行预览和QA之前直接在您的站点上查看体验内容。 体验预览URL绕过定位，以强制查看特定体验。
title: 使用体验预览URL预览自动个性化活动
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
translation-type: tm+mt
source-git-commit: 4ab572a0466381854d70eb47e0fc0b4a2874b833

---


# ![PREMIUM](/help/assets/premium.png) Preview使用体验预览URL自动个性化活动{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

可以为Target自动个性化活动生成体验预览URL，以便在活动实时进行预览和QA之前直接在您的站点上查看体验内容。 体验预览URL绕过定位，以强制查看特定体验。

>[!NOTE]
>
>“自动个性化”的体验预览URL与“活动QA”模式不同。 在“活动 QA”模式下，您可以为其他类型的活动创建活动 URL。有关更多信息，请参阅[活动 QA](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)。。
>
>仅当使用at.js 1.x时，AP活动的体验预览URL才可用。at.js 2.x当前不支持AP活动的体验预览URL。

使用体验预览URL与团队成员共享体验，并跨浏览器和环境提供QA体验，无需创建单独的QA活动。 如果网站很复杂，或者您的安全策略不允许在模拟器中查看网站，则此功能将特别有用。

1. 创建[自动个性化活动](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)，或单击相应的活动以将其打开。

   无需激活活动，即可预览体验。
1. 在活动摘要页面上，单击三个垂直排列的圆点图标，然后单击&#x200B;**[!UICONTROL 查看体验 URL]**。
1. 查看和/或指定 URL。

   * 如果您使用的是可视化体验编辑器，则会自动输入您为活动指定的默认 URL，且会为活动中的每个体验各生成一个链接。如有需要，您可以更改此 URL，并添加其他 URL。
   * 如果您使用的是基于表单的体验编辑器，则不会自动输入默认 URL。If you haven&#39;t previously created experience preview URLs, click **Add New URL**. 您必须指定所有要预览的 URL，并指定每个 URL 的名称。
   您可以添加多个 URL，如果您在运行一个多页面测试或模板测试，并且想要在多个页面上预览活动，则需要使用多个 URL。

   模态窗口会显示指向您网站上的体验的链接，以获取体验在 Target 可视化体验编辑器之外的“真实预览”。您必须通过共享消息中的链接来共享预览。如果单击链接，然后从页面复制生成的 URL，则不会起作用，因为 URL 包含只有在从消息中的链接访问页面时才会正确显示页面的参数。应当采取的正确操作是，复制模态窗口中的文本，然后通过电子邮件将整个文本发送给您的团队。
1. 单击&#x200B;**[!UICONTROL 生成所有]**，然后单击每个体验以进行预览。

   If you then make changes to the experience, make sure to generate new preview links for your team by returning to the modal window and clicking **Renew Links** to get new links.

   **注意：**&#x200B;预览链接会在新的选项卡中打开，并且您浏览器中的弹出窗口阻止程序会被禁用。

1. 单击每个体验名称以预览活动。

   页面随即会打开，并显示活动。
1. 单击&#x200B;**[!UICONTROL 完成]**&#x200B;以返回到活动摘要。

## 注意事项 {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**生成体验预览URL**

* 体验预览URL不受体验之间流量划分的影响。
* 在受众级别进行定位不会影响预览。
* 您可以为每个活动自动生成最多 300 个体验 URL。超过该限制后，必须手动生成 URL。
* 您可以为每个活动自动生成最多 300 个体验 URL。超过该限制后，必须手动生成 URL。
* 根据体验的数量，生成 URL 最多可能需要五分钟。请勿关闭对话框，否则生成的 URL 将会丢失。
* 生成的预览链接在两个月内有效。两个月后，您必须重新生成预览 URL。
* 只要体验发生了更改，您都必须重新生成预览 URL。

**共享体验预览URL**

* 即使您不是目标受众的成员，您也能够预览体验。
* 您可以与无权访问Adobe target的同事共享体验预览URL。

**使用体验预览URL查看体验**

* 只要页面未发生更改，便可预览任何已保存的活动。
* 无论活动处于活动状态还是非活动状态，都可以使用体验预览URL。
* 无法预览处于“草稿”状态的体验。
* 查看体验预览URL不会影响报表。

**体验预览URL疑难解答**

* 如果您无法在新选项卡中查看预览（由于浏览器缓存问题），请尝试刷新两三次，或者复制链接，然后在其他浏览器、新的会话或私密浏览器模式中打开该链接。
