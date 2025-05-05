---
keywords: 环境；疑难解答；最佳做法；复选框；重定向；重定向；白名单；黑名单；阻止列表；允许列表
description: 了解如何使用Adobe [!DNL Target] 中的环境来整理站点和生产前环境，以便轻松管理和独立报告。
title: 什么是环境？如何使用环境？
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 47%

---

# 环境

可组织您的网站和预生产环境，以便轻松管理和分隔报表。

为方便管理，可将多个主机捆绑在一起并将其放置到环境中。例如，您可以将数十个主机分组到两个或三个环境中。预设环境包括[!UICONTROL Production]、[!UICONTROL Staging]和[!UICONTROL Development]。 您可以根据需要添加新环境，以及对环境进行重命名。

一个环境（默认环境）已预命名为[!UICONTROL Production]。 此默认环境无法删除，即使您将其重命名也是如此。[!DNL Target] 将此环境视为您将在其中提供批准的最终活动和测试的位置。

从新网站或域收到[!DNL Target]请求时，这些新域始终显示在[!UICONTROL Production]环境中。 [!UICONTROL Production]环境无法更改其设置，因此可确保未知站点或新站点仅查看处于活动状态且准备就绪的内容。 通过主机管理，您在激活测试和开发环境中的新活动和内容之前，还可以轻松地确保这些活动和内容的质量。

{{permissions-update}}

要管理环境，请单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Environments]**。

## 添加环境 {#section_32097D0993724DF3A202D164D3F18674}

1. 从[!UICONTROL Environments]列表中，单击&#x200B;**[!UICONTROL Add Environment]**。
1. 为环境指定一个描述性名称。
1. 为环境指定所需的活动模式： [!UICONTROL Active Activities]或[!UICONTROL Active and Inactive Activities]。

   如果指定[!UICONTROL Active and Inactive Activities]，此环境中的主机也会显示非活动活动。

1. 单击 **[!UICONTROL Save]**。

## 设置报告的默认环境 {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以选择要用于所有活动报表的默认环境。

如果使用[!UICONTROL Production]作为默认值，则所有未知主机都会自动添加到此处，并且默认报告视图中将包含来自这些主机的报告数据。 而创建“精简”环境则可确保仅包含您的核心网站/域。

要为报表设置默认环境，请执行以下操作：

1. 从[!UICONTROL Environments]列表中，单击星形图标

>[!NOTE]
>
>[!DNL Recommendations]如果主机变换主机组，则 用户必须重建自己的行为数据库和产品数据库。
>
>如果在 [!DNL Adobe Experience Platform] 数据流[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans#target){target=_blank}中指定了默认环境，则此设置将覆盖[!DNL Target]中的设置。

## 更改环境的名称 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 从[!UICONTROL Environment]列表中，单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标。
1. 更改环境名称。
1. 单击 **[!UICONTROL Save]**。

## 删除环境 {#section_737F8869612047868D03FC755B1223D3}

如果您不再需要某个环境，您可以删除该环境。

1. 从[!UICONTROL Environment]列表中，单击&#x200B;**[!UICONTROL Delete]**&#x200B;图标。
1. 单击&#x200B;**[!UICONTROL Delete]**&#x200B;以确认删除。

>[!NOTE]
>
>您无法删除[!UICONTROL Production]环境，但可以对其进行重命名。

## [!BADGE 高级]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="了解Target Premium中包含的内容。"}

您可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

{{premium-note}}

可使用一种环境将目录中的可用项目隔开，以供不同用途。 例如，您可以为[!UICONTROL Development]和[!UICONTROL Production]环境、不同品牌或不同地理区域使用主机组。 默认情况下，“目录搜索”、“收藏集”和“排除项”中的预览结果均基于默认的主机组。（也可以使用“环境”过滤器选择其他主机组来预览结果。） 默认情况下，新添加的项目在所有主机组中均可用，除非在创建或更新项目时指定了环境ID。

>[!NOTE]
>
>提供的建议取决于请求中指定的主机组或环境ID。


如果您看不到产品，请确保您使用的是正确的主机组。例如，如果您将推荐设置为使用测试环境并将您的主机组设置为“测试”，则您可能需要在测试环境中重新创建收藏集，之后才会显示产品。要查看每个环境中提供了哪些产品，请在每个环境中使用“目录搜索”。您还可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

>[!NOTE]
>更改选定的环境后，必须单击“搜索”以更新返回的结果。

[!UICONTROL Environment]筛选器可从Target UI中的以下位置访问：

* 目录搜索([!UICONTROL Recommendations > Catalog Search])
* “创建收藏夹”对话框([!UICONTROL Recommendations > Collections > Create New])
* 更新集合对话框([!UICONTROL Recommendations > Collections > Edit])
* “创建排除”对话框([!UICONTROL Recommendations > Exclusions > Create New])
* “更新排除”对话框([!UICONTROL Recommendations > Exclusions > Edit])
