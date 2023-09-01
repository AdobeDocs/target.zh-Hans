---
keywords: 环境；故障诊断；最佳实践；ubox；重定向；重定向；白名单；黑名单；；阻止列表 列入允许列表
description: 了解如何在Adobe中使用环境 [!DNL Target] 组织您的站点和预生产环境，以便轻松管理和分隔报表。
title: 什么是环境？如何使用环境？
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 43291a102dee4cf03a3a427a4f29fe75d2c11221
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 56%

---

# 环境

可组织您的网站和预生产环境，以便轻松管理和分隔报表。

为方便管理，可将多个主机捆绑在一起并将其放置到环境中。例如，您可以将数十个主机分组到两个或三个环境中。预设环境包括 [!UICONTROL 生产]， [!UICONTROL 暂存]、和 [!UICONTROL 开发]. 您可以根据需要添加新环境，以及对环境进行重命名。

已预先命名默认环境 [!UICONTROL 生产]. 此默认环境无法删除，即使您将其重命名也是如此。[!DNL Target] 将此环境视为您将在其中提供批准的最终活动和测试的位置。

当 [!DNL Target] 从新网站或域收到请求后，这些新域将始终显示在 [!UICONTROL 生产] 环境。 此 [!UICONTROL 生产] 环境无法更改其设置，因此未知站点或新站点保证只能看到处于活动状态并准备好的内容。 通过主机管理，您在激活测试和开发环境中的新活动和内容之前，还可以轻松地确保这些活动和内容的质量。

要管理环境，请单击 **[!UICONTROL 管理]** > **[!UICONTROL 环境]**.

![“环境”列表](/help/main/administrating-target/assets/environments.png)

## 添加环境 {#section_32097D0993724DF3A202D164D3F18674}

1. 从 [!UICONTROL 环境] 列表，单击 **[!UICONTROL 添加环境]**.
1. 为环境指定一个描述性名称。
1. 为环境指定所需的活跃模式：“[!UICONTROL 活跃活动]”或“[!UICONTROL 活跃和不活跃的活动]”。

   如果您指定 [!UICONTROL 活跃和不活跃的活动]，此环境中的主机还会显示不活动的活动。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 设置默认报表环境 {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以选择要用于所有活动报表的默认环境。

如果您使用 [!UICONTROL 生产] 默认情况下，所有未知主机都会自动添加到此处，并且其中的报表数据会包含在默认报表视图中。 而创建“精简”环境则可确保仅包含您的核心网站/域。

要为报表设置默认环境，请执行以下操作：

1. 从 [!UICONTROL 环境] 列表中，单击星形图标

>[!NOTE]
>
>[!DNL Recommendations]如果主机变换主机组，则 用户必须重建自己的行为数据库和产品数据库。
>
>如果您指定 [Adobe Experience Platform数据流中的默认环境](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}，此环境将覆盖中的设置 [!DNL Target Recommendations].

## 更改环境的名称 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. 从 [!UICONTROL 环境] 列表，单击 **[!UICONTROL 编辑]** 图标。
1. 更改环境名称。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 删除环境 {#section_737F8869612047868D03FC755B1223D3}

如果您不再需要某个环境，您可以删除该环境。

1. 从 [!UICONTROL 环境] 列表，单击 **[!UICONTROL 删除]** 图标。
1. 单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

>[!NOTE]
>
>您无法删除 [!UICONTROL 生产] 环境，但您可以对其进行重命名。

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"}

您可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

{{premium-note}}

环境可用于为不同用途而分隔目录中的可用项。 例如，您可以将主机组用于 [!UICONTROL 开发] 和 [!UICONTROL 生产] 环境、不同品牌或不同地理位置。 默认情况下，“目录搜索”、“收藏集”和“排除项”中的预览结果均基于默认的主机组。（也可以使用“环境”筛选器来选择要预览结果的不同主机组。）默认情况下，新添加的项目在所有主机组中都可用，除非在创建或更新项目时指定了环境 ID。

>[!NOTE]
>
>交付的推荐取决于请求中指定的主机组或环境ID。


如果您看不到产品，请确保您使用的是正确的主机组。例如，如果您将推荐设置为使用测试环境并将您的主机组设置为“测试”，则您可能需要在测试环境中重新创建收藏集，之后才会显示产品。要查看每个环境中提供了哪些产品，请在每个环境中使用“目录搜索”。您还可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

>[!NOTE]
>更改选定的环境后，必须单击“搜索”以更新返回的结果。

此 [!UICONTROL 环境] 筛选器可从Target UI中的以下位置访问：

* 目录搜索（[!UICONTROL 推荐 > 目录搜索]）
* “创建收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 新建]）
* “更新收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 编辑]）
* “创建排除项”对话框（[!UICONTROL 推荐 > 排除项 > 新建]）
* “更新排除项”对话框（[!UICONTROL 推荐 > 排除项 > 编辑]）
