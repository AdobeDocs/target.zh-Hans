---
keywords: 体验定位；XT；活动URL;URL
description: 了解如何指定活动URL，以确定测试中使用的页面以及在使用Adobe Target设计体验定位活动时打开的页面。
title: 体验定位(XT)活动中的活动URL是什么？
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# 体验定位(XT)活动中的活动URL

的 [!UICONTROL 活动URL] 确定 [!DNL Adobe Target] [!UICONTROL 体验定位] (XT)活动，且在 [!UICONTROL 可视化体验编辑器] (VEC)或 [!UICONTROL 基于表单的体验编辑器] 设计活动时。

1. 在[创建 XT 活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)时，如果出现提示，请指定活动 URL。应键入完整的 URL（包括 `https://`），然后单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。
   >
   >默认情况下，VEC或基于表单的体验编辑器会打开您在 [可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md). 在活动创建过程中，您可以指定其他页面。
   >
   >如果您指定的 URL 所对应的网站不包含 Target Standard JavaScript 代码，则您将无法选择页面元素。

1. （视情况而定）要在 VEC 打开后显示其他页面，请单击&#x200B;**[!UICONTROL 配置]**，选择&#x200B;**[!UICONTROL 页面交付]**，然后在“[!UICONTROL URL]”字段中指定 URL。

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
