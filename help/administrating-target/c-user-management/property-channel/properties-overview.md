---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: 此信息介绍了向 Adobe Target 实施添加用户，创建工作区、用户组和属性，更新 Target 实施以包含 at_property 参数，以及指定角色和权限时需要执行的任务。
title: 配置企业权限
subtopic: Getting Started
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 70%

---


# ![PREMIUM](/help/assets/premium.png) 配置企业权限{#configure-enterprise-permissions}

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>本主题中的信息已更新，可在Target Standard/高级版20.6.1版本（2020年7月）即将发布的UI更改中抢先登峰造极。 本主题中显示的大多数信息适用于当前UI; 但是，选项可能位于稍有不同的位置。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

下表列出了在创建属性以及分配用户角色和权限时应当执行的任务。有关每项任务的更多信息，请参阅以下部分。

| 任务 | 执行位置 |
|--- |--- |
| 1. 添加用户（可选） | [!DNL Adobe Admin Console for Enterprise] |
| 2. 创建工作区（产品配置文件） | [!DNL Adobe Admin Console for Enterprise] |
| 3. 创建用户组（可选） | [!DNL Adobe Admin Console for Enterprise] |
| 4. 创建属性 | [!DNL Target] 用户界面 |
| 5：更新您的实施以包含 `at_property` 参数 | [!DNL Target] UI、at.js 函数、[!DNL Adobe Launch] 或 [!DNL Dynamic Tag Management] |
| 6. 指定角色和权限 | [!DNL Adobe Admin Console for Enterprise] |

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. 在Adobe Target中，单 **[!UICONTROL 击“管理]** ”>“ **[!UICONTROL 属性]** ” **[!UICONTROL >“]**&#x200B;将属性分配到工作区”。

   或

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. （视情况而定）如果您可以访问多个组织的 [!DNL Admin Console for Enterprise]，请单击右上角或顶部导航栏中的用户头像，然后选择所需组织。

## 步骤 1. Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

当您开始使用新的[!UICONTROL 属性]功能时，必须在 [!DNL Adobe Admin Console for Enterprise] 中执行所有用户管理。但是，[!DNL Target] 中的所有现有用户都将从 [!DNL Target] 迁移到 [!DNL Admin Console for Enterprise]。

1. [在 Admin Console 中](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)，单击页面顶部的&#x200B;**[!UICONTROL 用户]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL 添加用户]**，以创建新用户或编辑现有用户。
1. 按照《企业用户指南》**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/enterprise/help/users.html)中的说明进行操作。

## 步骤 2. Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

工作区(产品用户档案)允许组织将一组特定用户分配给一组特定属性。 工作区在许多方面与 [!DNL Analytics] 中的报表包相似。

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the &quot;Default Workspace&quot; configuration to these newer, limited-access workspaces.

客户可以使用这些工作区按地区、业务部门、网站区域或通过他们选择的任何其他方法，将访问权限划分给不同的团队。

用户可以包含在多个工作区中，甚至可以在每个工作区拥有不同的角色。

1. 在 中[!DNL Admin Console]，单击&#x200B;**[!UICONTROL 产品]**，然后选择所需产品的名称。

   ![工作区](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 创建所需的工作区（产品配置文件）：

   * **默认访问：**&#x200B;所有现有活动都将合并到一个名为“默认访问”的项目中。这不会对客户产生任何影响。所有用户角色和功能都将与此更改之前完全相同。

      通过 [!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] 和 [!DNL Target Classic] 创建的所有活动也将包含在“默认访问”工作区中。当前无法将“默认访问”中的项目移动到其他项目。

   * **新工作区（产品配置文件）：**&#x200B;您可以通过执行以下操作来开始利用新的权限功能：

      * 在 [!DNL Admin Console for Enterprise] 中创建新工作区。
      * 将 Target 属性分配到工作区。

   您可以使用这些工作区按地区、业务部门、网站区域或通过您选择的任何其他方法，将访问权限划分给不同的团队。用户可以包含在多个工作区中，也可以在每个工作区拥有不同的角色。

1. 按照《企业用户指南》**&#x200B;的[创建和管理产品配置](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)中的说明进行操作。

>[!NOTE]
>请观看下面的视频，以了解有关配置工作区的更多信息。

### Obtain your workspace ID {#workspace-id}

您需要传递工作区 ID 才能使用 [Target API](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) 中的企业权限。

1. 在 [Adobe Admin Console](https://adminconsole.adobe.com) 中，单击[!UICONTROL 产品]选项卡，然后单击左侧菜单中的产品以显示 PLC（工作区）列表。
1. 单击所需的 PLC（工作区），然后在 URL 中找到“配置文件”ID，如下所示。

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 步骤 3. Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

您可以创建用户组（例如开发人员、分析师、营销人员、管理人员等），然后为其分配多个 Adobe 产品和工作区中的相应权限。为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

1. 在 Admin Console 中，单击页面顶部的&#x200B;**[!UICONTROL 用户]**&#x200B;选项卡 > **[!UICONTROL 用户组]**，以创建新用户组或对现有用户组进行编辑。
1. 按照《企业用户指南》**&#x200B;的[管理产品配置的用户和组](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html)中的说明进行操作。

## 步骤 4. Create properties {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

通过添加特定名称／值对作为参数来启用属性，该参数包含任何调用(目标调用、api调用等) 可以启用属性。

属性属于特定的渠道（Web、移动设备、电子邮件和 API/其他）。

**提示**：请观看下方的视频，以了解有关如何创建属性的更多信息。

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. 单击&#x200B;**创建属性**。

   ![“新建属性”对话框](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   填写以下字段：

   * **属性名称（必需）:** 指定属性的描述性名称。
   * **描述：**&#x200B;为属性指定可选描述。
   * **渠道：**&#x200B;为属性选择所需的渠道：Web、移动设备应用程序、电子邮件或其他/API（例如机顶盒或 PlayStation 游戏机）。

1. Click **[!UICONTROL Copy]** to copy the code to your clipboard that you&#39;ll use while performing the steps in [5: Update Your Implementation to Include the at_property Parameter](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. 完成后单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>请观看下面的视频，以了解有关创建属性的更多信息。

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**获取`at_property`参数代码：**

1. （视情况而定）使用您在执行 [4. 创建属性](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)中的步骤时生成并保存到剪贴板的实施代码，继续执行步骤 2。

   或

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. 将鼠标指针悬停在要显示的所需属性的“[!UICONTROL 上次更新]”列上，然后单击“[!UICONTROL 代码]”图标。

      ![属性悬停代码](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 右键单击高亮显示的实施代码以将其复制到剪贴板。

      ![属性代码](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   您可以通过多种方法来更新 [!DNL Target] 实施。例如，对于网页，可以使用以下方法：

   * **通过[!DNL Adobe Launch]中的“全局参数”：**

      For more information, see [Add Global Target Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **通过[!DNL Dynamic Tag Management]中的“全局参数”：**

      ![](assets/property_token_2.png)

      有关更多信息，请参阅“动态标签管理产品文档”**&#x200B;中的[全局参数 - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target)。

   * **通过 targetPageParams() 函数：**&#x200B;将以下代码置于 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 标记中 at.js 或 mbox.js 引用的上方。

      ![](assets/property_token_1.png)

      有关如何使用 at.js 完成此操作的更多信息，请参阅 [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。

   * **通过 mboxCreate() 函数：**

      ![](assets/property_token_3.png)

      有关如何使用 at.js 完成此操作的更多信息，请参阅 [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) 和 [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)。

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. 在 Admin Console 中，单击&#x200B;****&#x200B;产品，然后选择所需产品的名称。

   ![工作区](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 单击所需用户档案的名称（例如，默认工作区）。

   ![默认工作区](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 单击&#x200B;**[!UICONTROL 用户]**。

   [!UICONTROL 用户]选项卡会显示该工作区中的所有用户。

   ![配置用户](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![产品角色下拉式列表](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |
   | 发布者 | 与“观察者”角色类似(可以视图活动，但不能创建或编辑它们)。 但是，“发布者”角色具有激活活动的其他权限。 |

   有关更多信息，请参阅《企业用户指南》**&#x200B;中的[在 Admin Console 中管理产品权限和角色](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html)。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 如何配置 Target 工作区 (6:55) ![教程徽章](/help/assets/tutorial.png)

以下视频说明了如何创建工作区。

* 从 Adobe Target 界面访问 Adobe Admin Console（3 种方式）
* 在 Adobe Admin Console 中配置工作区

   * 向工作区添加用户
   * 向工作区添加属性

* 了解默认工作区

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* 如何在 [!DNL Adobe Target] 界面中创建属性
* 如何生成要包含在属性实施中的属性令牌
* 熟悉三种实施方法：

   * Web
   * 移动设备应用程序
   * 电子邮件、机顶盒或 API 调用

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
