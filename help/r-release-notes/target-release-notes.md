---
description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
keywords: 发行说明
seo-description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
seo-title: Adobe Target发行说明(预发行版)
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 72a1048a94e363cb5c367942d69231e4de9bd202

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新日期：2019 年 7 月 31 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发行日期、功能和其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## 公告

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. 这有助于跨团队实现优化的优化程序缩放。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* 您可以选择可将集成应用到的工作区
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

此更新将支持以下使用案例：

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* 授予Adobe I/集成访问权限以选择具有适当角色的工作区，以允许中央团队只在几个工作区中进行API驱动的更改。
* 每当团队准备好探索API并相应地选择角色时，每个拥有其工作空间的团队都决定拥有自己的集成。
* 混合和匹配以上任意场景。

**需要的操作**：当前，在所有工作区中利用API针对资源(活动、受众、优惠和报告)运用API的客户需要授予其现有的Adobe I/集成访问所有工作区的权限，以根据其用例使用所需的角色。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. 您现在可以选择所需的角色。

This action *must* be performed before September 4, 2019 to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 按照上述准则提前设置集成不会产生任何负面反应。这一变化越快，就越好。根据单位中的工作区数量，设置此设置需要花费较少的时间。此过程只需单击几次，即可将现有的集成添加到具有所需角色的工作区中。

##  Target Standard/Premium 19.8.1（2019 年 8 月 20 日）{#tgt-19-8-1}

此维护版本包含以下增强功能：

* 多个安全修复，包括在Visual Experience Composer(CMS)中对富文本编辑器(RTE)的安全更新。(TGT-35383)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
