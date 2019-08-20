---
description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
keywords: 发行说明
seo-description: 提供有关最新或即将推出的[！DNL Adobe Target]版本。
seo-title: Adobe Target 发行说明（预发行版本）
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 3b21fede9df1ef61da194fac55ffb862c037258a

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍 [!DNL Adobe Target] 最新版本或即将发布的版本的功能、增强功能、修复信息和已知问题。

**上次更新日期：2019 年 7 月 31 日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能及其他信息如有更改，恕不另行通知。要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行时间。
>
>括号中的问题编号供 [!DNL Adobe] 内部使用。

## 公告

**2019年月31日**

[!UICONTROL 企业权限] 允许 [!DNL Target] 客户使用单个组织，但将其划分为不同团队或工作流程的工作区。[!UICONTROL 企业权限] 功能有助于跨团队有效扩展优化程序。尽管此功能在 [!DNL Target] UI中可用，但在2019年 [!DNL Target] 月发布之前，管理员API一直缺少相应的支持。Adobe更新了管理员API，以便您可以使用集成帐户访问单位中创建的所有工作区。因此，在早期，Admin API仅限于默认工作区，2019年月更新已授予具有 [!UICONTROL 审批人] 访问权限的所有工作区的访问权限。

在即将 [!DNL Target] 发布的2019年月版本中 [!UICONTROL ，Enterprise Permissions] 将为客户提供以下访问控制：

* 您可以选择可将集成应用到的工作区
* 您可以对Adobe I/集成应用角色： [!UICONTROL 审批人]、 [!UICONTROL 编辑者]或 [!UICONTROL 观察者]。

**需要操作**：当前，在所有工作区中对资源(活动、受众、优惠和报告)利用API进行CRUD操作的客户需要授予其现有的Adobe I/集成访问所需角色的所有工作区。在月发布之前，所有使用 [!UICONTROL 审批人] 访问权限操作的集成，无论从 [!UICONTROL “产品角色”] 下拉列表中选择的角色如何。在即将发布的版本中，您现在可以选择所需的角色。

此操作应在2019 **年月的一个月**&#x200B;内执行。在2019 [!DNL Target] 年月发布之后，访问控制将激活，如果您当前设置了该工作区，则您将仅观察到默认工作区。预先设置集成角色不会产生不利后果。

有关分步说明和更多信息，请参阅 [授予Adobe I/O集成权限以访问工作区和分配角色](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。

## Target Standard/Premium 19.9.1（2019 年 9 月 24 日）

此维护版本包含以下增强功能：

* 多个安全修复，包括在Visual Experience Composer(CMS)中对富文本编辑器(RTE)的安全更新。(TGT-35383)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
