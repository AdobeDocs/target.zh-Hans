---
keywords: 体验定位；xt;活动url;url
description: 活动URL确定在“Adobe Target体验定位”活动中使用的页面，该页面在设计活动时在可视体验书写器(VEC)或基于表单的体验书写器中打开。
title: 活动 URL
feature: Experience Targeting
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 65%

---


# 活动URL在体验定位(XT)活动

[!UICONTROL 活动URL]确定在[!DNL Adobe Target] [!UICONTROL 体验定位](XT)活动中使用的页面，该页面在[!UICONTROL 可视体验书写器](VEC)或[!UICONTROL 基于表单的体验书写器]中打开活动是设计的。

1. 在[创建 XT 活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)时，如果出现提示，请指定活动 URL。应键入完整的 URL（包括 `https://`），然后单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。
   >
   >默认情况下，VEC或基于表单的体验书写器会打开在[可视体验书写器设置](/help/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。
   >
   >如果您指定的 URL 所对应的网站不包含 Target Standard JavaScript 代码，则您将无法选择页面元素。

1. （视情况而定）要在 VEC 打开后显示其他页面，请单击&#x200B;**[!UICONTROL 配置]**，选择&#x200B;**[!UICONTROL 页面交付]**，然后在“[!UICONTROL URL]”字段中指定 URL。

   ![“页面交付”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

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