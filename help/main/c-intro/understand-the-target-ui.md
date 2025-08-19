---
keywords: target用户界面；用户界面；ui；公告；事件；通知
description: 熟悉用户界面并查找更深入信息的链接，以帮助您充分利用 [!DNL Target]。
title: 如何使用 [!DNL Target] UI？
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 3f7c81654d4f7982acf166b314cc332822cc87a6
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 23%

---

# 了解 [!DNL Target] UI

该用户界面按符合逻辑并且便于用户使用的形式进行排列，以帮助您充分利用 [!DNL Adobe Target]。以下简要概述可帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。

{{updated-ui}}

## [!DNL Target]用户界面标题

[!DNL Target] UI顶部的标题包含选项卡和选项，可帮助您导航解决方案的不同功能。 您还可以切换组织和[!DNL Adobe Experience Cloud]解决方案，如果您是Beta计划的成员，则可以提供反馈，访问AI助手，获取帮助和通知，管理您的[!DNL Adobe]配置文件，以及注销[!DNL Target]。

![Target 标题](/help/main/c-intro/assets/target-header.png)

左侧的选项卡允许您访问[!DNL Target]的各种功能，稍后将对此进行讨论。 在讨论这些选项卡之前，我们先来讨论右侧的选项。

### [!UICONTROL Organization]

*组织*&#x200B;是一个实体，管理员从中可配置组和用户，并控制 [!DNL Adobe Experience Cloud] 中的单点登录。组织的作用类似于一个衔接所有 [!DNL Experience Cloud] 产品和解决方案的登录公司。大多数情况下，组织即是您的公司名称。但是，公司可以具有多个组织。

如果您的公司有多个组织，请从[!UICONTROL Organization]下拉列表中选择所需的组织：

![“组织”下拉列表](/help/main/c-intro/assets/organizations.png)

### [!UICONTROL Beta Feedback]

（视情况而定）如果您是官方[!DNL Target] Beta项目的一部分，则可能会看到[!UICONTROL Beta Feedback]图标。

![Beta反馈图标](/help/main/c-intro/assets/beta-feedback.png)

提供反馈的说明，包括适用的文件或屏幕截图，以及任何其他详细信息（如有必要），然后单击&#x200B;**[!UICONTROL Submit]**。

### [!DNL AI Assistant]

（视情况而定）如果您的组织已授予您使用[!DNL AI Assistant]的权限，请单击[!DNL AI Assistant]图标。

有关详细信息，请参阅[Adobe Experience Platform AI助手概述](/help/main/c-intro/ai-assistant.md)。

### 帮助

单击[!UICONTROL Help]图标（![帮助图标](/help/main/assets/icons/HelpOutline.svg) ）可访问信息、视频、博客等，以帮助您更有效地使用[!DNL Target]。 您可以创建支持工单、查找支持电话号码、通过Twitter提问或提供有关[!DNL Target]的反馈以使我们了解[!DNL Target]团队的情况。

![帮助](/help/main/c-intro/assets/help.png)

### 请求、通知和公告 {#notifications-announcements}

[!UICONTROL Requests]、[!UICONTROL Notifications]和[!UICONTROL Announcements]面板帮助您及时了解[!DNL Adobe Target]的所有最新进展。 主动通知帮助您及时了解[!DNL Adobe Experience Cloud]解决方案和[!DNL Target]事件的状态。 主动公告提醒您发生断电事件和维护事件。

单击标题中的[!UICONTROL Notifications]图标（![通知图标](/help/main/assets/icons/Bell.svg)）以查看通知：

该面板包含[!UICONTROL Requests]、[!UICONTROL Notifications]和[!UICONTROL Announcements]的选项卡。

![通知](assets/notifications.png)

以下部分包含有关每个选项卡以及如何配置通知和公告的信息：

#### [!UICONTROL Requests]

在[!DNL Adobe]面板中接收有关[!UICONTROL Requests]产品和解决方案、您与其他用户的协作以及其他相关更新的重要信息。

当有人向您发送批准对象或授予对象访问权限的请求时，该请求显示在[!UICONTROL Requests]面板中。

#### 通知 {#notifications}

[!DNL Target]事件通知包括以下内容：

* **活动**:批准或停用活动时（手动或达到活动开始或结束日期时），所有活动类型的通知。 通知包含带有活动概述页面链接的活动的名称。

  通知是可配置的，默认情况下由[!DNL Target Premium]帐户的活动工作区中的产品管理员、发布者和批准者接收。 对于[!DNL Target Standard]帐户，所有发布者和批准者都会收到通知。

  通知的格式与以下示例类似：

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **配置文件脚本**：手动或由[!DNL Target]激活或停用配置文件脚本时的通知。

  通知是可配置的，默认情况下由[!DNL Target Premium]和[!DNL Target Standard]帐户的产品管理员和批准者接收。

  通知的格式与以下示例类似：

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Recommendations馈送**：手动或由[!DNL Recommendations]激活或停用[!DNL Target]馈送时的通知。 当[!DNL Recommendations]馈送失败时，也会发送通知。

  通知是可配置的，默认情况下由[!DNL Target Premium]帐户的产品管理员和批准者接收。 [!DNL Recommendations]是[!DNL Target Premium]功能，在[!DNL Target Standard]中不可用。

  通知的格式与以下示例类似：

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

您可以将单个通知标记为已读，方法是将鼠标悬停在所需通知上，然后单击[!UICONTROL Mark as Read] （ ![标记为已读图标](/help/main/assets/icons/CheckmarkCircle.svg) ）图标。 您可以单击面板底部的[!UICONTROL Mark as Read]或[!UICONTROL View All]，将所有通知标记为已读或查看所有通知。

您也可以将鼠标悬停在通知上并单击[!UICONTROL Snooze] （ ![暂停图标](/help/main/assets/icons/Clock.svg) ）图标，以再次设置要通知的提醒。 然后，您可以选择您希望收到通知的时间：5分钟、15分钟、1小时或明天。

#### 公告

主动公告提醒您发生断电事件和维护事件。

有关更深入的信息，请参阅[Adobe状态](https://status.adobe.com/)页面。

### 配置通知和公告

要编辑通知首选项，请执行以下操作：

1. 单击[!UICONTROL Edit Preferences] （![编辑首选项图标](/help/main/assets/icons/Setting.svg) ）图标，然后单击左边栏中的&#x200B;**[!UICONTROL Notifications]**。
1. 在&#x200B;**[!UICONTROL Target]**&#x200B;下，选择要如何接收通知：

   * [!UICONTROL In-app]
   * [!UICONTROL Email]
   * [!DNL Slack]

1. 选择您希望视为高优先级的类别。

   >[!NOTE]
   >
   >“[!UICONTROL New releases]”和“[!UICONTROL Updates on content]”是仅适用于[!DNL Target]的通知类别。 其他类别适用于其他[!DNL Adobe]解决方案。

1. 选择您希望在浏览器中显示警报的通知。

   这些警报会出现在浏览器的右上角几秒钟。 您可以选择查看高优先级类别、所有类别或隐藏所有通知弹出窗口。 您还可以配置是否希望通知保持可见状态，直到关闭它们，或者可以配置通知持续时间。

1. 选择您希望接收通知电子邮件的频率：

   * [!UICONTROL Don't send emails]
   * [!UICONTROL Instant notifications]
   * [!UICONTROL Daily digest]
   * [!UICONTROL Weekly digest]

1. 为工作区配置Slack通知。

### 应用程序切换器

通过应用程序切换器，可快速访问您有权访问的 [!DNL Adobe Experience Cloud] 解决方案。

![应用程序切换器](/help/main/c-intro/assets/apps.png)

### Profile

单击您的个人档案头像以编辑您的 [!DNL Adobe Experience Cloud] 首选项或退出 [!DNL Target]。还可访问或编辑您的 [!DNL Adobe] 个人档案。

![个人档案头像](/help/main/c-intro/assets/change-language.png)

现在，让我们讨论[!DNL Target]标题左侧的选项卡。

## 活动

打开&#x200B;**[!UICONTROL Activities]**&#x200B;时，[!DNL Target]列表是默认视图。 您可以从此页面创建活动并管理现有活动。

有关[中可用的活动类型的深入信息以及要详细了解](/help/main/c-activities/activities.md)列表的用户界面，请参阅[!DNL Target]活动[!UICONTROL Activity]。

## 受众

单击“**[!UICONTROL Audiences]**”选项卡以显示[!UICONTROL Audiences]列表，从中可创建受众和管理现有受众。

受众是指一组看到定位活动的相似活动参加者。 受众是具有相同特征的一组人员，例如新访客、回访访客或来自中西部的回访访客。 通过[!UICONTROL Audience]功能，可将不同的内容和体验定位到特定的受众，即在适当的时间向适当的人员展示恰当的信息，从而优化您的数字营销。 如果将访客视为目标受众的一部分，则 [!DNL Target] 根据在活动创建期间定义的标准决定要显示何种体验。

有关[中受众类型的深入信息以及要详细了解](/help/main/c-target/c-audiences/create-audience.md)列表的用户界面，请参阅[!DNL Target]创建受众[!UICONTROL Audience]。

## 产品建议

单击“**[!UICONTROL Offers]**”选项卡以显示[!UICONTROL Offers]列表，从中可创建体验和选件以及管理现有体验和选件。

体验可以是一个页面、整个网页、可能形成购买漏斗的一组页面或一些其他逻辑序列的页面上的一个产品建议、图像、文本、按钮、视频，以及这些不同元素的组合。它还可以是语音助手的回复、客户服务脚本，甚至是饮料机中提供的独特口味。您可以在 [!DNL Target] 活动中测试或个性化体验。

有关[中选件类型的深入信息以及要详细了解](/help/main/c-experiences/c-manage-content/manage-content.md)列表的用户界面，请参阅[!DNL Target]选件[!UICONTROL Offer]。

## 推荐

单击&#x200B;**[!UICONTROL Recommendations]**&#x200B;选项卡以访问[!DNL Target Recommendations]。

>[!NOTE]
>
>[!UICONTROL Recommendations] 活动作为 [!DNL Target Premium] 解决方案的一部分提供。在没有[!UICONTROL Recommendations]许可证的[!DNL Target Standard]中，[!DNL Target Premium]活动不可用。 有关详细信息，请参阅“Target 简介”**&#x200B;中的 [Target Premium](/help/main/c-intro/intro.md#premium)。

[!UICONTROL Recommendations]活动可根据以往用户活动或其他算法自动显示客户可能感兴趣的产品或内容。 “推荐”有助于引导客户查看在其他情况下他们可能不知道的相关项目。

有关[中有关](/help/main/c-recommendations/recommendations.md)的深入信息以及要详细了解[!UICONTROL Recommendations]用户界面的，请参阅[!DNL Target]推荐[!UICONTROL Recommendations]。

## 管理

单击&#x200B;**[!UICONTROL Administration]**&#x200B;选项卡以访问[!UICONTROL Administration]页面。

通过[!UICONTROL Administration]页面可管理[!DNL Target]，包括[!UICONTROL Visual Experience Composer] (VEC)、报表、[!DNL Scene7]配置、实现、主机、环境、响应令牌、用户和推荐的配置设置。

有关更深入的信息以及要详细了解用户界面的，请参阅[管理 Target 概述](/help/main/administrating-target/administrating-target.md)。

## 可视化体验编辑器 (VEC)

除了[!DNL Target] UI之外，您还应熟悉VEC UI。 有关详细信息，请参阅[[!DNL Visual Experience Composer] 选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。
