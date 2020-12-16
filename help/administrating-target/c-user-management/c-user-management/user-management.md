---
keywords: add user;manage user;user permissions
description: 您可以将用户添加到Adobe Target并管理他们在Adobe Admin Console的权限。
title: 用户
feature: user management
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 46%

---


# 用户{#users}

您可以在[!DNL Adobe Admin Console]中添加用户并管理其权限。

>[!NOTE]
>
>[!UICONTROL “属性和权限”功能作为 ] Premium 解决方案的一部分提供。[!DNL Target]如果没有 [!DNL Target] Premium 许可证，它们将无法在 [!DNL Target] Standard 中使用。
>单击[!DNL Target] UI顶部的[!UICONTROL 管理]链接，可以判断您的组织是否拥有标准或高级许可证。
>
>* **[!DNL Target]标准客户**:如果您看到“用  户”标[!UICONTROL 签(“管理”>“用户]”)(而非“属性” **** 选项卡)，则您的组织具有“标 [!DNL Target] 准”许可证。[!DNL Target] Standard 客户应按照本文中的相关说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。
   >
   >
* **[!DNL Target]高级客户**:如果您看到“用  户”标  签和“属[!UICONTROL 性”标签(“管理”>“属性]”)，则您的组织具有 [!DNL Target] 高级许可证。[!DNL Target] Premium 客户应按照[企业用户权限](/help/administrating-target/c-user-management/property-channel/property-channel.md)和[配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)中的说明进行操作，以在 [!DNL Adobe Admin Console] 中添加用户和分配权限。
>
>
有关如何管理用户和权限的详细信息，请参阅&#x200B;*企业和团队用户指南*&#x200B;中的[管理产品和用户档案](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)。

开始使用 [!DNL Adobe Target] 时，您会发现自己的 [!DNL Adobe Experience Cloud] 帐户中预先填充了一些 ID（以 Adobe.com 结尾）。这些ID适用于[!DNL Adobe]团队的成员，这样，如果您需要帮助，他们可以帮助您使用新帐户和[!DNL Adobe Target]。 要获取帮助，请按常规方式联系 Adobe 团队。

直到用户使用其[!DNL Adobe Experience Cloud]帐户登录，然后登录到[!DNL Target Standard/Premium]后，才会在[!UICONTROL 用户]页面上显示新用户。

默认情况下，所有 [!DNL Target] 用户最初都拥有观察者权限。

管理员用户在[!UICONTROL 用户]列表中进行标识。 如果您需要更改访问级别，请与某个系统管理员用户联系。

## 视图目标中的用户信息

您可以在目标环境中视图当前用户的列表，包括其每个工作区的角色，以及直接从内部目标发送电子邮件地址。

要视图“用户”页面，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用户]**。

![用户列表自目标](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>要管理现有用户或添加新用户，必须使用[!UICONTROL Adobe Admin Console]，如下所述。

## 访问 Adobe Admin Console {#access}

对于在 Adobe Admin Console 中执行的任务，请按以下步骤访问该控制台：

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用户]** > **[!UICONTROL 用户管理]**。

   或

   转至[https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/)，然后使用您的Adobe ID登录（如果尚未登录）。

1. （视情况而定）如果您可以访问多个组织的 [!DNL Admin Console for Enterprise]，请单击右上角或顶部导航栏中的用户头像，然后选择所需组织。

## 添加用户{#add-users}

必须在 [!DNL Adobe Admin Console for Enterprise] 中执行所有用户管理。但是，[!DNL Target] 中的所有现有用户都将从 [!DNL Target] 迁移到 [!DNL Admin Console for Enterprise]。

1. [在Admin Console中](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单 **[!UICONTROL 击“用]** 户 **** ”>“用户”以创建新用户或编辑现有用户。
1. 按照《企业用户指南》**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 创建用户组{#user-groups}

您可以创建用户组（例如开发人员、分析师、营销人员、管理人员等），然后为其分配多个 Adobe 产品和工作区中的相应权限。为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

1. [在Admin Console中](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击 **[!UICONTROL “用户]**  **[!UICONTROL >]** 用户组”以创建新用户组或编辑现有用户组。
1. 按照《企业用户指南》**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 指定角色和权限{#roles-permissions}

只有系统管理员才能在 [!DNL Target] 中设置用户角色。例如，标准批准者用户不能将观察者更改为审批者，但不具有[!DNL Experience Cloud]管理权限。

系统管理员用户必须将用户添加到系统中。系统不会自动添加用户。他们会收到[!DNL Experience Cloud]的电子邮件邀请，在注册其帐户之前必须确认其电子邮件地址。

1. [](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)在 Admin Console 中，单击&#x200B;**[!UICONTROL 产品]**，然后选择所需产品的名称。

   ![“产品”选项卡](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 单击所需的工作区（例如，默认工作区）。

   ![默认工作区](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   [!UICONTROL 用户]选项卡会显示该工作区中的所有用户。

   ![配置用户](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用每个用户在“[!UICONTROL 产品角色]”列中的下拉列表为其选择所需的权限角色（审批者、编辑者或观察者）。

   ![产品角色下拉式列表](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |
   | 发布者 | 与“观察者”角色类似(可以视图活动，但不能创建或编辑它们)。 但是，“发布者”角色具有激活活动的其他权限。 |

有关更多信息，请参阅《企业用户指南》**&#x200B;中的[在 Admin Console 中管理产品权限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培训视频：如何配置目标工作区![教程标记](/help/assets/tutorial.png)

学习目标：

* 从 Adobe Target 界面访问 Adobe Admin Console（三种方式）
* 在 Adobe Admin Console 中配置工作区
   * 向工作区添加用户
   * 向工作区添加属性
* 了解默认工作区

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]菜单UI（以前称为[!UICONTROL Setup]）已重新设计，可提供改进的性能、减少发布新功能时所需的维护时间并改善整个产品的用户体验。 以下视频中的信息通常是正确的；但是，选项可能位于稍有不同的位置。 更新的视频将很快发布。

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
