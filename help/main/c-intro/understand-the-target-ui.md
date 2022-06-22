---
keywords: target 用户界面;用户界面;ui；公告；事件
description: 熟悉用户界面并查找更深入的信息的链接，以帮助您充分利用 [!DNL Target].
title: 如何使用 [!DNL Target] UI？
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 417ed843cd3c9f2598a569f673c8b8515bc90464
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 47%

---

# 了解 [!DNL Target] UI

该用户界面按符合逻辑并且便于用户使用的形式进行排列，以帮助您充分利用 [!DNL Adobe Target]。以下简要概述可帮助您熟悉 [!DNL Target] 和提供了更多详细信息和分步说明的链接。

顶部的标题 [!DNL Target] UI包含一些选项卡和选项，可帮助您导航解决方案的不同功能。 您还可以切换组织和 [!DNL Adobe Experience Cloud] 解决方案，获取帮助和通知，管理 [!DNL Adobe] 配置文件，并注销 [!DNL Target].

![Target 标题](/help/main/c-intro/assets/target-header.png)

使用左侧的选项卡，可访问 [!DNL Target]，稍后将讨论。 在转入这些选项卡之前，我们先来讨论右侧的各个选项。

## 组织

*组织*&#x200B;是一个实体，管理员从中可配置组和用户，并控制 [!DNL Adobe Experience Cloud] 中的单点登录。组织的作用类似于一个衔接所有 [!DNL Experience Cloud] 产品和解决方案的登录公司。大多数情况下，组织即是您的公司名称。但是，公司可以具有多个组织。

如果您的公司有多个组织，请从[!UICONTROL “组织”]下拉列表中选择所需的组织：

![“组织”下拉列表](/help/main/c-intro/assets/organizations.png)

## 应用程序

通过应用程序切换器，可快速访问您有权访问的 [!DNL Adobe Experience Cloud] 解决方案。

![应用程序切换器](/help/main/c-intro/assets/apps.png)

## 帮助

通过“帮助”图标，可访问信息、视频、博客等以帮助您更有效地使用 [!DNL Target]。您可以创建支持票证、查找支持电话号码、通过Twitter提出问题或提供有关 [!DNL Target] 让我们知道 [!DNL Target] 团队在做。

![帮助](/help/main/c-intro/assets/help.png)

## 通知和公告

[!UICONTROL “通知”]和[!UICONTROL “公告”]面板帮助您及时了解 [!DNL Adobe Target] 的所有最新进展。主动通知有助于您及时了解 [!DNL Adobe Experience Cloud] 解决方案和 [!DNL Target] 事件。 主动公告提醒您发生断电事件和维护事件。

>[!NOTE]
>
>有关增强功能的信息 [!UICONTROL 通知和公告] 此部分中的面板当前适用于select [!DNL Target] 客户，并将在未来几个月向所有客户推出。

单击标题中的铃铛图标以查看通知：

![通知和公告的铃铛图标](assets/bell-icon.png)

该面板包含的选项卡适用于 [!UICONTROL 通知] 和 [!UICONTROL 公告].

![通知](assets/notifications.png)

以下部分包含有关每个选项卡以及如何配置通知和公告的信息。

### 通知

[!DNL Target] 事件通知包括以下内容：

* **活动**:批准或停用活动时（手动或达到活动开始或结束日期时），所有活动类型的通知。 通知包含带有活动概述页面链接的活动名称。

   默认情况下，活动工作区中的产品管理员、发布者和批准者可以配置并接收通知，以便 [!DNL Target Premium] 帐户。 对于 [!DNL Target Standard] 帐户、通知由所有发布者和批准者接收。

   通知的格式如下所示：

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **配置文件脚本**:手动或由 [!DNL Target].

   通知是可配置的，默认情况下，产品管理员和批准者会接收这两种通知 [!DNL Target Premium] 和 [!DNL Target Standard] 帐户。

   通知的格式如下所示：

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations信息源**:通知 [!DNL Recommendations] 手动或由 [!DNL Target]. 通知也会在 [!DNL Recommendations] 馈送失败。

   通知是可配置的，默认情况下，产品管理员和批准者会接收通知 [!DNL Target Premium] 帐户。 [!DNL Recommendations] 是 [!DNL Target Premium] 功能，在 [!DNL Target Standard].

   通知的格式如下所示：

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed to import from source`

您可以将所有通知标记为已读，或在面板底部查看所有通知。

### 公告

主动公告提醒您发生断电事件和维护事件。

有关更深入的信息，请参阅 [Adobe 状态](https://status.adobe.com/)页面。

### 配置通知和公告

要编辑通知首选项，请执行以下操作：

1. 单击齿轮图标，然后单击 **[!UICONTROL 通知]**.
1. 在 **[!UICONTROL Target]**，单击 **[!UICONTROL 自定义]**.
1. 选择或取消选择要接收通知的类别：

   * 请求：当有人向您发送请求以批准对象或授予对对象的访问权限时。 您无法取消订阅此类别。
   * 分配给我：当有人为您分配对象时。
   * 提及次数：某人在评论中提及您时。
   * 新版本：当您有权访问的产品或服务有新版本可用时。
   * 与我共享：当某人与您共享对象时。
   * 内容更新：当某人对您创建或跟踪的对象进行编辑、删除或注释时。
   * 其他:

   >[!NOTE]
   >
   >“新版本”和“内容更新”是适用于 [!DNL Target]. 其他类别适用于其他Adobe解决方案。


1. 选择要被视为高优先级的类别。
1. 选择要在浏览器中显示警报的通知。

   这些警报会在浏览器的右上角显示几秒钟。 您可以选择查看高优先级类别、所有类别，或隐藏所有通知弹出窗口。 您还可以配置是希望通知在关闭之前一直保持可见，还是配置通知持续时间。

1. 选择要接收通知电子邮件的频率：

   * 不发送电子邮件
   * 即时通知
   * 每日摘要
   * 每周摘要

## Profile

单击您的个人资料头像以编辑您的 [!DNL Adobe Experience Cloud] 首选项或退出 [!DNL Target]。还可访问或编辑您的 [!DNL Adobe] 个人资料。

![个人资料头像](/help/main/c-intro/assets/change-language.png)

现在我们讨论 [!DNL Target] 标题左侧的选项卡。

## 活动

打开 [!DNL Target] 时，**[!UICONTROL 活动]**&#x200B;列表是默认的视图。您可以从此页面创建活动并管理现有活动。

![Activities list（活动列表）](/help/main/c-intro/assets/activities-list.png)

有关 [!DNL Target] 中提供的活动类型的深入信息以及要详细了解[!UICONTROL “活动”]列表的用户界面，请参阅[活动](/help/main/c-activities/activities.md)。

## 受众

单击 **[!UICONTROL 受众]** 选项卡 [!UICONTROL 受众] 列表，您可以在其中创建受众并管理现有受众。

![“受众”列表](/help/main/c-intro/assets/audience-list.png)

受众是指一组看到定位活动的相似活动参加者。 受众是具有相同特征的人群，例如都是新访客、回访访客或来自中西部的回访访客。通过[!UICONTROL “受众”]功能，可将不同的内容和体验面向特定受众，通过在适当的时间向适当的人显示适当的消息而优化数字营销。如果将访客视为目标受众的一部分，则 [!DNL Target] 根据在活动创建期间定义的标准决定要显示何种体验。

有关 [!DNL Target] 中提供的受众类型的深入信息以及要详细了解[!UICONTROL “受众”]列表的用户界面，请参阅[创建受众](/help/main/c-target/c-audiences/create-audience.md)。

## 选件

单击 **[!UICONTROL 选件]** 选项卡 [!UICONTROL 选件] 列表中列出了您可以创建体验和选件，以及管理现有体验和选件的位置。

![“选件”列表](/help/main/c-intro/assets/offers.png)

体验可以是一个页面、整个网页、可能形成购买漏斗的一组页面或一些其他逻辑序列的页面上的一个选件、图像、文本、按钮、视频，以及这些不同元素的组合。它还可以是语音助手的回复、客户服务脚本，甚至是饮料机中提供的独特口味。您可以在 [!DNL Target] 活动中测试或个性化体验。

有关 [!DNL Target] 中提供的选件类型的深入信息以及要详细了解[!UICONTROL “选件”]列表的用户界面，请参阅[选件](/help/main/c-experiences/c-manage-content/manage-content.md)。

## 推荐

单击&#x200B;**[!UICONTROL “推荐”]**&#x200B;选项卡以访问 [!DNL Target Recommendations]。

>[!NOTE]
>
>“推荐”活动作为 [!DNL Target Premium] 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。有关详细信息，请参阅“Target 简介”**&#x200B;中的 [Target Premium](/help/main/c-intro/intro.md#premium)。

![推荐](/help/main/c-intro/assets/recommendations.png)

“[!UICONTROL 推荐]”活动可根据以往用户活动或其他算法自动显示客户可能感兴趣的产品或内容。Recommendations可帮助将客户引导至他们可能还不知道的相关项目。

有关 [!DNL Target] 中提供的[!UICONTROL 推荐]的深入信息以及要详细了解[!UICONTROL “选件”]的用户界面，请参阅[选件](/help/main/c-recommendations/recommendations.md)。

## 管理

单击&#x200B;**[!UICONTROL “管理”]**&#x200B;选项卡以访问[!UICONTROL “管理”]页面。

![“管理”页面](/help/main/c-intro/assets/administration.png)

通过[!UICONTROL “管理”]页面可管理 [!DNL Target]，包括[!UICONTROL 可视体验编辑器] (VEC)、报表、[!DNL Scene7] 配置、实现、主机、环境、响应令牌和用户的配置设置。

有关更深入的信息以及要详细了解用户界面的，请参阅[管理 Target 概述](/help/main/administrating-target/administrating-target.md)。
