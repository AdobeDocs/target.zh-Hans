---
keywords: 体验定位；XT；活动URL；URL
description: 了解如何指定 [!UICONTROL 活动URL] 确定测试中使用的页面，以及在 [!UICONTROL 体验定位] 活动设计使用 [!DNL Adobe Target].
title: 什么是 [!UICONTROL 活动URL] 在 [!UICONTROL 体验定位] (XT)活动？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 48%

---

# 中的活动URL [!UICONTROL 体验定位] (XT)活动

此 [!UICONTROL 活动URL] 确定在中使用的页面 [!DNL Adobe Target] [!UICONTROL 体验定位] (XT)活动。 这是在中打开的页面 [!UICONTROL 可视化体验编辑器] (VEC)或 [!UICONTROL 基于表单的体验编辑器] （在设计活动时）。

1. 在[创建 XT 活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)时，如果出现提示，请指定活动 URL。应键入完整的 URL（包括 `https://`），然后单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。
   >
   >默认情况下，VEC或 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 打开中指定的页面 [可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md). 在活动创建过程中，您可以指定其他页面。
   >
   >如果您指定的URL所对应的网站不包含 [[!DNL Target] at.js JavaScript库或 [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}中，您无法选择页面元素。

1. （视情况而定）要在VEC打开后显示其他页面，请单击 **[!UICONTROL 配置]**，选择 **[!UICONTROL 页面交付]**，然后在 [!UICONTROL URL] 字段。

   ![“页面交付”对话框](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。

1. （视情况而定）单击&#x200B;**[!UICONTROL 添加模板规则]**，为活动添加更多页面或部分。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。
