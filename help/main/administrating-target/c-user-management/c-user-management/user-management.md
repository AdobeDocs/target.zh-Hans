---
keywords: 添加用户;管理用户;用户权限
description: 了解如何使用 Adobe Admin Console 管理用户及其在 Adobe Target 中的权限和权利。
title: 如何添加用户和管理权限？
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: ht
source-wordcount: '911'
ht-degree: 100%

---

# 用户

在 [!DNL Adobe Admin Console] 中添加用户和管理权限。

>[!NOTE]
>
>[!UICONTROL 属性]和[!UICONTROL 权限]功能作为 [!DNL Target] Premium 解决方案的一部分提供。如果没有 [!DNL Target] Premium 许可证，它们将无法在 [!DNL Target] Standard 中使用。
>您可以在 [!DNL Target] UI 的顶部单击[!UICONTROL 管理]链接，确定组织使用的是 Standard 还是 Premium 许可。
>
>* **[!DNL Target]Standard 客户**：如果您看到[!UICONTROL 用户]选项卡（[!UICONTROL 管理 > 用户]）（而不是&#x200B;**[!UICONTROL 属性]**&#x200B;选项卡），则组织具有 [!DNL Target] Standard 许可。[!DNL Target] Standard 客户应按照本文中的相关说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。
>
>* **[!DNL Target]Premium 客户**：如果您看到[!UICONTROL 用户]选项卡和[!UICONTROL 属性]选项卡（[!UICONTROL 管理 > 属性]），则组织具有 [!DNL Target] Premium 许可。[!DNL Target] Premium 客户应按照[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)和[配置企业权限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。
>
>有关如何管理用户和权限的详细信息，请参阅企业和团队用户指南&#x200B;**&#x200B;中的[管理产品和配置文件](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

开始使用 [!DNL Adobe Target] 时，您会发现自己的 [!DNL Adobe Experience Cloud] 帐户中预先填充了一些 ID（以 Adobe.com 结尾）。这些 ID 是 [!DNL Adobe] 团队的成员，因此在您需要帮助时，可以协助您的新帐户以及 [!DNL Adobe Target] 的使用。要获取帮助，请按常规方式联系 Adobe 团队。

只有在用户登录其 [!DNL Adobe Experience Cloud] 帐户并随后登录到 [!DNL Target Standard/Premium] 中时，您才会看到新用户在[!UICONTROL 用户]页面中列出。

默认情况下，所有 [!DNL Target] 用户最初都拥有观察者权限。

管理员用户在[!UICONTROL 用户]列表中标识。如果您的访问权限级别更改，请联系一位系统管理员用户。

## 在 Target 中查看用户信息

您可以直接在 Target 中查看 Target 环境中当前用户的列表，包括他们在各个工作区中的角色以及电子邮件地址。

要查看“用户”页面，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用户]**。

![Target 中的用户列表](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>要管理现有用户或者添加新用户，您必须使用 [!UICONTROL Adobe Admin Console]，如下所示。

## 访问 Adobe Admin Console {#access}

对于在 Adobe Admin Console 中执行的任务，请按以下步骤访问该控制台：

1. 在 [!DNL Target] 中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用户]** > **[!UICONTROL 用户管理]**。

   或

   如果您尚未登录，请转到 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然后使用您的 Adobe ID 登录。

1. （视情况而定）如果您可以访问多个组织的 [!DNL Admin Console for Enterprise]，请单击右上角或顶部导航栏中的用户头像，然后选择所需组织。

## 添加用户 {#add-users}

必须在 [!DNL Adobe Admin Console for Enterprise] 中执行所有用户管理。但是，[!DNL Target] 中的所有现有用户都将从 [!DNL Target] 迁移到 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console 中](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户]**&#x200B;以创建新用户或者编辑现有用户。
1. 按照企业用户指南&#x200B;**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 创建用户组 {#user-groups}

您可以创建用户组（例如开发人员、分析师、营销人员、管理人员等），然后为其分配多个 Adobe 产品和工作区中的相应权限。为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

1. [在 Admin Console 中](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**&#x200B;以创建新用户组或者编辑现有用户组。
1. 按照企业用户指南&#x200B;**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 指定角色和权限 {#roles-permissions}

只有系统管理员才能在 [!DNL Target] 中设置用户角色。例如，Standard 审批者用户如果没有 [!DNL Experience Cloud] 管理权限，无法将观察者更改为审批者。

系统管理员用户必须将用户添加到系统中。系统不会自动添加用户。[!DNL Experience Cloud] 向他们发送电子邮件来邀请，并且用户必须先确认其电子邮件地址，然后才能注册帐户。

1. [在 Admin Console 中](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 产品]**，然后选择所需产品的名称。

   ![“产品”选项卡](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 单击所需工作区（例如，默认工作区）。

   ![默认工作区](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL 用户]选项卡会显示该工作区中的所有用户。

   ![配置用户](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用每个用户在[!UICONTROL 产品角色]列中的下拉列表为其选择所需的权限角色（审批者、编辑者或观察者）。

   ![“产品角色”下拉列表](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |
   | 发布者 | 类似于观察者角色（可查看活动，但无法创建或编辑活动）。但是，发布者角色另有激活活动的权限。 |

有关更多信息，请参阅企业用户指南&#x200B;**&#x200B;中的[在 Admin Console 中管理产品权限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培训视频：如何配置 Adobe Target 工作区 ![“教程”徽章](/help/main/assets/tutorial.png)

学习目标：

* 从 Adobe Target 界面访问 Adobe Admin Console（三种方式）
* 在 Adobe Admin Console 中配置工作区
   * 向工作区添加用户
   * 向工作区添加属性
* 了解默认工作区

>[!NOTE]
>
>[!DNL Target][!UICONTROL 管理] 菜单 UI（以前的[!UICONTROL 设置]）经过重新设计，以提供更好的性能、减少发布新功能时所需的维护时间并改善整个产品的用户体验。以下视频中的信息通常正确，但是，选项可能位于不同的位置。更新后的视频很快就会发布。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
