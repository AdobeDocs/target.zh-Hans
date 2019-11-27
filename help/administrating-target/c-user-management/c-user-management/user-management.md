---
keywords: add user;manage user;user permissions
description: 您可以在 Adobe Admin Console 中添加用户并管理其权限。
title: 用户
subtopic: Getting Started
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: 799085cec9f1a8604f1ac0e9027f7af8b6f5e991

---


# 用户{#users}

您可以在 Adobe Admin Console 中添加用户并管理其权限。

>[!NOTE]
>
>[!UICONTROL “属性和权限”功能作为 ] Premium 解决方案的一部分提供。[!DNL Target]如果没有 [!DNL Target] Premium 许可证，它们将无法在 [!DNL Target] Standard 中使用。
>您可以通过单击 UI 顶部的“[!UICONTROL 设置]”链接来判断贵组织是拥有 Standard 许可证还是拥有 Premium 许可证。[!DNL Target]
>
>**[!DNL Target]Standard 客户：**&#x200B;如果您看到[!UICONTROL 用户]选项卡（[!UICONTROL 设置 &gt; 用户]），则意味着贵组织拥有 [!DNL Target] Standard 许可证。[!DNL Target Standard 客户应按照本文中的相关说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。
>
>**[!DNL Target]Premium 客户：**&#x200B;如果您看到了[!UICONTROL 属性]选项卡（[!UICONTROL 设置 &gt; 属性]），则表明您的组织拥有 [!DNL Target] 许可证。[!DNL Target] Premium 客户应按照[企业用户权限](/help/administrating-target/c-user-management/property-channel/property-channel.md)和[配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。

要管理用户和权限，请参阅《 [企业和团队用户指南](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) 》中的“管理产品和配置”。

开始使用 [!DNL Adobe Target] 时，您会发现自己的 [!DNL Adobe Experience Cloud] 帐户中预先填充了一些 ID（以 Adobe.com 结尾）。这些 ID 是供 Adobe 团队成员使用的，如果您需要帮助，团队成员便可以使用这些 ID 来帮助您解决新帐户问题以及使用 [!DNL Adobe Target] 时遇到的问题。要获取帮助，请按常规方式联系 Adobe 团队。

新用户使用其 Adobe Experience Cloud 帐户登录，接着通过单击 [!UICONTROL  卡片登录到 ] 之后，您才会看到“[!DNL Target Standard/Premium]用户[!DNL Target]”页面上列出该用户。

默认情况下，所有 [!DNL Target] 用户最初都拥有观察者权限。

管理员用户在用户列表中进行标识。 如果您需要更改访问级别，请与某个系统管理员用户联系。

## 访问 Adobe Admin Console {#access}

对于在 Adobe Admin Console 中执行的任务，请按以下步骤访问该控制台：

1. 如果您尚未登录，请转到 [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然后使用您的 Adobe ID 登录。

   或

   如果您已经登录 Experience Cloud，请转到 [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com)，然后单击顶部导航栏中的[!UICONTROL 应用程序]图标，接着单击右侧的&#x200B;**[!UICONTROL 管理员]**。

1. （视情况而定）如果您可以访问多个组织的 [!DNL Admin Console for Enterprise]，请单击右上角或顶部导航栏中的用户头像，然后选择所需组织。

## 添加用户 {#add-users}

必须在 [!DNL Adobe Admin Console for Enterprise] 中执行所有用户管理。但是，[!DNL Target] 中的所有现有用户都将从 [!DNL Target] 迁移到 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 用户]** &gt; **[!UICONTROL 用户]**，以创建新用户或编辑现有用户。
1. 按照《企业用户指南》**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 创建用户组 {#user-groups}

您可以创建用户组（例如开发人员、分析师、营销人员、管理人员等），然后为其分配多个 Adobe 产品和工作区中的相应权限。为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 用户]** &gt; **[!UICONTROL 用户组]**，以创建新用户组或编辑现有用户组。
1. 按照《企业用户指南》**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 指定角色和权限 {#roles-permissions}

只有系统管理员才能在 [!DNL Target] 中设置用户角色。例如，如果没有 Experience Cloud 管理员权限，标准审批者用户将无法将观察者更改为审批者。

系统管理员用户必须将用户添加到系统中。系统不会自动添加用户。需从 Experience Cloud 中通过电子邮件方式邀请用户，且用户必须确认其电子邮件地址，然后才会注册其帐户。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击&#x200B;**[!UICONTROL 产品]**，然后选择所需产品的名称。

   ![“产品”选项卡](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 单击所需的工作区（例如，默认工作区）。

   ![默认工作区](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace.png)

   [!UICONTROL 用户]选项卡会显示该工作区中的所有用户。

   ![配置用户](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. 使用每个用户在“[!UICONTROL 产品角色]”列中的下拉列表为其选择所需的权限角色（审批者、编辑者或观察者）。

   ![产品角色下拉列表](/help/administrating-target/c-user-management/c-user-management/assets/product-role.png)

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |

有关更多信息，请参阅《企业用户指南》**&#x200B;中的[在 Admin Console 中管理产品权限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培训视频：如何配置 Target 工作区

学习目标：

* 从 Adobe Target 界面访问 Adobe Admin Console（三种方式）
* 在 Adobe Admin Console 中配置工作区
   * 向工作区添加用户
   * 向工作区添加属性
* 了解默认工作区

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=chi_hans)
