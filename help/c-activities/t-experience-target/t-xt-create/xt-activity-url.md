---
description: 活动URL决定了在体验定位活动中使用的页面，该页面在设计活动时在Visual Experience Composer(CMS)或基于表单的Experience Composer中打开。
keywords: 定位
seo-description: 活动URL决定了在体验定位活动中使用的页面，该页面在设计活动时在Adobe Target Visual Experience Composer(CMS)或基于表单的Experience Composer中打开。
seo-title: 活动 URL
solution: Target
title: 活动 URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 活动 URL{#activity-url}

活动URL决定了在体验定位(XT)活动中使用的页面，该页面在设计活动时在Visual Experience Composer(CMS)或基于表单的Experience Composer中打开。

1. [在创建XT活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md)时提示您，指定活动URL。应键入完整的 URL（包括 `https://`），然后单击&#x200B;**[!UICONTROL 创建活动]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). 在活动创建过程中，您可以指定其他页面。
   >
   >如果为不包含Target标准JavaScript代码的站点指定URL，则无法选择页面元素。

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![“页面交付”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数
   可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL 保存]。**