---
description: 发行说明，提供有关最新或即将发布的[!DNL Adobe Target]版本的功能、增强和修复的信息。
keywords: 发行说明
seo-description: 发行说明，提供有关最新或即将发布的[!DNL Adobe Target]版本的功能、增强和修复的信息。
seo-title: Adobe Target 发行说明（预发行版本）
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d675c6875c8474ba490956ea395076eef5b9e58f

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新日期：2019 年 9 月 24 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>括号中的问题编号供 [!DNL Adobe] 内部使用。

## 公告

**July 31, 2019**

[!UICONTROL Enterprise Permissions] allows [!DNL Target] customers to use a single organization, but divide it into workspaces for different teams or workflows. The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although this feature was available in the  UI, the Admin APIs lacked the corresponding support until the  February 2019 release. [!DNL Target][!DNL Target]Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

在即将发布的2019 [!DNL Target] 年9月版本中， [!UICONTROL 企业权限] 将为客户提供以下访问控制：

* 您可以选择可应用集成的工作区
* 您可以将角色应用于Adobe I/O集成：审 [!UICONTROL 批人]、编 [!UICONTROL 辑者]或观 [!UICONTROL 察者]。

**需要操作**:当前正在所有工作区中利用API进行CRUD操作（活动、受众、优惠和报告）的客户需要授予其现有的Adobe I/O集成访问权限，以访问具有所需角色的所有工作区。 Prior to the September release, all integrations operated using Approver access, regardless of the role selected from the Product Role drop-down list. 在即将发布的版本中，您现在可以选择所需的角色。

此操作应于2019年8月 **执行**。 2019年9 [!DNL Target] 月发布后，访问控制将激活，如果您当前是这样设置的，您将仅看到对默认工作区的访问。 预先设置集成角色不会产生任何不良后果。

有关分步说明和更多信息，请参阅授 [予Adobe I/O集成对工作区的访问权限并分配角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。

## Target Standard/Premium 19.9.2（2019 年 9 月 30 日） 

This maintenance release includes the following enhancement:

* 几个安全修复，包括对Visual Experience Composer(VEC)中富文本编辑器(RTE)的安全更新。 (TGT-35383)

## Target Standard/Premium 19.9.1（2019 年 9 月 10 日） 

| 功能/增强 | 描述 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) Enterprise权限 | 在Target 2019年9月版本中，企业权限为客户提供了以下访问控制：<UL><li>您可以选择可应用集成的工作区。</li><li>您可以将角色应用于Adobe I/O集成：批准者、编辑者或观察者。</li></ul>For step-by-step instructions and more information, see Grant Adobe I/O integrations access to workspaces and assign roles.[](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md) |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
