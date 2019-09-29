---
description: 目录搜索可帮助您在目录中查找产品或内容。
keywords: 目录;搜索
seo-description: Adobe Target中的目录搜索可帮助您在目录中找到产品或内容。
seo-title: Adobe Target中的目录搜索
solution: Target
title: 目录搜索
title-outputclass: premium
topic: Premium
uuid: e0876963-5905-4850-a615-953e435f26e9
badge: premium
translation-type: tm+mt
source-git-commit: afb87e3e23b44133982e55fdc7650250e6bf8b3a

---


# ![PREMIUM](/help/assets/premium.png) 目录搜索 {#catalog-search}

目录搜索可帮助您在目录中查找产品或内容。

To access catalog search, click Recommendations &gt; Catalog Search.********

您可以对搜索进行优化，方式是单击搜索字段中的向下箭头，然后从显示的选项菜单中选择搜索选项。

![](assets/searchproductsmenu.png)

搜索选项包括：

* ALL
* 名称
* 品牌
* 类别
* ID
* 消息

**[!UICONTROL 所有]**&#x200B;选项会使用 OR 逻辑搜索所有其他搜索标准所产生的结果。

在搜索结果中，单击&#x200B;**[!UICONTROL 环境]**&#x200B;筛选器可指定要显示哪个生产主机组环境的目录。[](/help/administrating-target/hosts.md)您还可以滚动浏览搜索结果中的项目，以查看缩览图和其他产品信息。

“产品”旁边显示的数字表示指定环境的可用产品总数中与搜索词相匹配的产品数量。

当通过源文件、API或mbox更新收到更新时，目录会自动刷新。 Updates are usually completed in an hour. 如果更新正在进行中，则显示最近更新开始的时间。 如果未进行更新，则显示最近更新开始和完成的时间。

## 根据高级搜索创建集合或排除

You can create [collections](/help/c-recommendations/c-products/collections.md) or [exclusions](/help/c-recommendations/c-products/exclusions.md) using Advanced Search on the Catalog Search page ([!UICONTROL Recommendations] &gt; [!UICONTROL Catalog Search] &gt; [!UICONTROL Advanced Search]).

![Save as](/help/c-recommendations/c-products/assets/save-as.png)

例如，在使用“ID”&gt;“包含”创建搜索后，您可以单击[!UICONTROL 另存为] &gt; [!UICONTROL 收藏集或排除项]。

>[!IMPORTANT]
>
>“高级搜索”功能不区分大小写；但在进行产品交付时，会根据区分大小写的搜索来返回产品。这种不匹配可能会导致产生混淆。因此，在基于使用“高级搜索”功能搜索到的结果创建收藏集或排除项时，请务必考虑大小写问题。例如，如果您搜索“Holiday”，初始搜索会列出包含“Holiday”和“holiday”的结果。如果您随后创建一个目录，以用于返回包含“holiday”的产品，则只会返回包含“holiday”的产品，而不会返回包含“Holiday”的产品。可以采用类似的方式处理排除项。
