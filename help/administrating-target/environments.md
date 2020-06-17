---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: 可组织您的网站和预生产环境，以便轻松管理和分隔报表。
title: 环境
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 61%

---


# 环境

可组织您的网站和预生产环境，以便轻松管理和分隔报表。

>[!NOTE]
>
>本主题中的信息已更新，可在Target Standard/高级版20.6.1版本（2020年7月）即将发布的UI更改中抢先登峰造极。 本主题中显示的大多数信息适用于当前UI; 但是，选项可能位于稍有不同的位置。

主机管理的主要目标是确保网站上不会意外出现任何不活跃的内容。通过主机管理，您还可以按环境分隔报表数据。

A [host](/help/administrating-target/hosts.md) is any web server (or web domain) from where you serve content during any stage of your project. 提供 mbox 的任何主机都可被识别。

为方便管理，可将多个主机捆绑在一起并将其放置到环境中。例如，您可以将数十个主机分组到两个或三个环境中。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 您可以根据需要添加新环境，以及对环境进行重命名。

One environment, the default environment, is pre-named [!UICONTROL Production]. 此默认环境无法删除，即使您将其重命名也是如此。[!DNL Target] 将此环境视为您将在其中提供批准的最终活动和测试的位置。

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. 通过主机管理，您在激活测试和开发环境中的新活动和内容之前，还可以轻松地确保这些活动和内容的质量。

[!DNL Target] 不限制可以发送和接收mbox的主机，因此当出现新的服务器或域时，它们会自动工作（除非您设置了allowlist或blocklist）。 这也让您能够在不了解或不可预测的各种域中进行广告测试。

要管理环境，请单 **[!UICONTROL 击“管理]** ”> **[!UICONTROL 环境]**。

![环境列表](/help/administrating-target/assets/environments.png)

## 添加环境 {#section_32097D0993724DF3A202D164D3F18674}

1. 在环境 [!UICONTROL 列表] 中，单击 **[!UICONTROL 添加环境]**。
1. 为环境指定一个描述性名称。
1. 为环境指定所需的活跃模式：“[!UICONTROL 活跃活动]”或“[!UICONTROL 活跃和不活跃的活动]”。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

您可以选择要用于所有活动报表的默认环境。

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. 而创建“精简”环境则可确保仅包含您的核心网站/域。

要为报表设置默认环境，请执行以下操作：

1. 在环境 [!UICONTROL 列表] ，单击星形图标

>[!NOTE]
>
>[!DNL Recommendations]如果主机变换主机组，则 用户必须重建自己的行为数据库和产品数据库。

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. From the [!UICONTROL Environment] list, click the **[!UICONTROL Environments]** tab.
1. Click the **[!UICONTROL Edit]** icon.
1. 更改环境名称。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

如果您不再需要某个环境，您可以删除该环境。

1. 在环境  列表中，单 **[!UICONTROL 击删除]** 图标。
1. 单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## 推荐：按环境（主机组）筛选收藏集和排除项

![Premium 徽章](/help/assets/premium.png)

您可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

>[!NOTE]
>Recommendations activities are available as part of the [!DNL Target] Premium solution. 如果没有 [!DNL Target] Premium 许可证，它们将无法在 [!DNL Target] Standard 中使用。

环境可用于将目录中的可用项目分隔为不同用途。 For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. 默认情况下，“目录搜索”、“收藏集”和“排除项”中的预览结果均基于默认的主机组。（也可以使用“环境”筛选器来选择要预览结果的不同主机组。）默认情况下，新添加的项目在所有主机组中都可用，除非在创建或更新项目时指定了环境 ID。交付的“推荐”取决于请求中指定的主机组。

如果您看不到产品，请确保您使用的是正确的主机组。例如，如果您将推荐设置为使用测试环境并将您的主机组设置为“测试”，则您可能需要在测试环境中重新创建收藏集，之后才会显示产品。要查看每个环境中提供了哪些产品，请在每个环境中使用“目录搜索”。您还可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。

>[!NOTE]
>更改选定的环境后，必须单击“搜索”以更新返回的结果。

The [!UICONTROL Environment] filter is available from the following places in the Target UI:

* 目录搜索（[!UICONTROL 推荐 > 目录搜索]）
* “创建收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 新建]）
* “更新收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 编辑]）
* “创建排除项”对话框（[!UICONTROL 推荐 > 排除项 > 新建]）
* “更新排除项”对话框（[!UICONTROL 推荐 > 排除项 > 编辑]）