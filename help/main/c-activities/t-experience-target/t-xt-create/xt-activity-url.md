---
keywords: 体验定位；XT；活动URL；URL
description: 了解如何指定[!UICONTROL Activity URL]来确定测试中使用的页面，以及在使用[!UICONTROL Experience Targeting]设计 [!DNL Adobe Target]活动时打开的页面。
title: '[!UICONTROL Activity URL] (XT)活动中的[!UICONTROL Experience Targeting]是什么？'
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 38%

---

# [!UICONTROL Experience Targeting] (XT)活动中的活动URL

[!UICONTROL Activity URL]确定[!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)活动中使用的页面。 这是设计活动时在[!UICONTROL Visual Experience Composer] (VEC)或[!UICONTROL Form-Based Experience Composer]中打开的页面。

1. 在[创建 XT 活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)时，如果出现提示，请指定活动 URL。键入完整的URL（包括`https://`），然后单击&#x200B;**[!UICONTROL Create Activity]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`]和[!DNL `http://www.adobe.com`]都匹配。
   >
   >默认情况下，VEC或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)会打开[可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。
   >
   >如果您指定的URL所对应的网站不包含[[!DNL Target] at.js JavaScript库或 [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}，则您将无法选择页面元素。

1. （视情况而定）要在VEC打开后显示其他页面，请单击&#x200B;**[!UICONTROL Configure]**，选择&#x200B;**[!UICONTROL Page Delivery]**，然后在[!UICONTROL URL]字段中指定URL。

   >[!NOTE]
   >
   >在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。

1. （视情况而定）单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;以向活动添加更多页面或部分。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL Save]**。
