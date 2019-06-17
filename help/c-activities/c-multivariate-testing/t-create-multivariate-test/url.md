---
description: 活动URL决定了在Multivariate Test(MVT)中使用的页面，该页面在Target中设计测试时打开。
keywords: 定位
seo-description: 活动URL决定了在Multivariate Test(MVT)中使用的页面，该页面在Adobe Target中设计测试时打开。
seo-title: 活动 URL
solution: Target
title: 活动 URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 0730d5f8f6aa2b72c2069c81d6e5a0183489e91c

---


# 活动 URL{#activity-url}

活动URL决定了在 [!M更紧密的Test] (MVT)中使用的页面，以及在设计测试时打开的页面 [!DNL Adobe Target]。

[在活动创建过程中提示时](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)，指定活动URL。键入完整的URL(包括 `https://`)，然后单击 **[!UICONTROL 下]** 一步。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。

默认情况下 [!UICONTROL ，Visual Experience Composer] (CMS)会打开 [在帐户首选项中指定的页面](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)。在活动创建过程中，您可以指定其他页面。

要在CMS打开后显示其他页面，请单击 **[!UICONTROL 配置]** 图标，然后选择 **[!UICONTROL 页面传送]**，然后指定URL。

![“页面交付”对话框](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

单击 **[!UICONTROL 添加模板规则]，为活动添加更多页面和部分。**

其他规则可以基于以下任何一项：

* URL
* 域
* 路径
* 话题标签 (#) 片段
* 查询
* 参数

可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

完成后单击 **[!UICONTROL 保存]。**

>[!NOTE]
>
>如果您输入的 URL 所对应的网站不包含 Target Standard JavaScript 代码，则您将无法选择页面元素。

默认情况下，CMS不允许对包含JavaScript的元素(如旋转横幅)进行更改。如果您希望能够使用 **[!UICONTROL 可视化体验编辑器]** 更改这些元素，可以关闭[!UICONTROL 使用 JavaScript 渲染]。

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。