---
keywords: 添加用户;项目;用户组;属性;工作区;管理属性;属性;at_property;角色;权限
description: 了解如何将用户添加到Adobe Target；创建工作区、用户组和属性；更新您的实施；以及指定角色和权限。
title: 如何配置企业权限？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Administration & Configuration
role: Admin
exl-id: 6494fc86-d2d3-4382-9d2e-63be435ba935
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 55%

---

# 配置企业权限

此信息介绍了向[!DNL Target]实施添加用户，创建工作区、用户组和属性，更新[!DNL Target]实施以包含`at_property`参数，以及指定角色和权限时需要执行的任务。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/main/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

下表列出了在创建属性以及分配用户角色和权限时应当执行的任务。有关每项任务的更多信息，请参阅以下部分。

| 任务 | 执行位置 |
|--- |--- |
| 1.添加用户（可选） | [!DNL Adobe Admin Console for Enterprise] |
| 2.创建工作区（产品配置文件） | [!DNL Adobe Admin Console for Enterprise] |
| 3.创建用户组（可选） | [!DNL Adobe Admin Console for Enterprise] |
| 4.创建资产 | [!DNL Target] 用户界面 |
| 5：更新您的实施以包含`at_property`参数 | [!DNL Adobe Experience Platform]中的[!DNL Target] UI、at.js函数或标记 |
| 6. 指定角色和权限 | [!DNL Adobe Admin Console for Enterprise] |

对于在[!DNL Adobe Admin Console for Enterprise]中执行的那些任务，请按以下步骤访问该控制台：

1. 在Adobe Target中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Properties]** > **[!UICONTROL Assign Properties to Workspaces]**。

   或

   如果您尚未登录，请转到[https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/)，然后使用您的Adobe ID登录。


1. （视情况而定）如果您可以访问多个组织的 [!DNL Admin Console for Enterprise]，请单击右上角或顶部导航栏中的用户头像，然后选择所需组织。

## 步骤 1. 添加用户（可选） {#section_A92AF0F921B743FEB9E9033433BD816A}

当您开始使用新的[!UICONTROL Properties]功能时，必须在[!DNL Adobe Admin Console for Enterprise]中执行所有用户管理。 但是，[!DNL Target] 中的所有现有用户都将从 [!DNL Target] 迁移到 [!DNL Admin Console for Enterprise]。

1. [在Admin Console](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE)中，单击页面顶部的&#x200B;**[!UICONTROL Users]**&#x200B;选项卡> **[!UICONTROL Add Users]**&#x200B;以创建新用户或编辑现有用户。
1. 按照企业用户指南&#x200B;**&#x200B;的[在 Experience Cloud 中管理用户和组](https://helpx.adobe.com/cn/enterprise/help/users.html)中的说明进行操作。

## 步骤 2. 创建工作区（产品配置文件） {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

工作区（产品配置文件）允许组织为一组特定用户分配一组特定属性。 工作区在许多方面与 [!DNL Analytics] 中的报表包相似。

组织可以通过以下方式开始利用企业权限功能：在[!DNL Admin Console]内创建新工作区，将[!DNL Target]属性分配给这些工作区，并将用户从“默认Workspace”配置移动到这些新的访问受限工作区。

客户可以使用这些工作区按地区、业务部门、网站区域或通过他们选择的任何其他方法，将访问权限划分给不同的团队。

用户可以包含在多个工作区中，甚至可以在每个工作区拥有不同的角色。

1. 在[!DNL Admin Console]中，单击&#x200B;**[!UICONTROL Products]**，然后选择所需产品的名称。

   ![工作区](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. 创建所需的工作区（产品配置文件）：

   * **默认访问：**&#x200B;所有现有活动都将合并到一个名为“默认访问”的项目中。这不会对客户产生任何影响。所有用户角色和功能都将与此更改之前完全相同。

     通过 [!DNL Adobe Experience Manager] (AEM)、[!DNL Adobe Mobile Services] 和 [!DNL Target Classic] 创建的所有活动也将包含在“默认访问”工作区中。当前无法将“默认访问”中的项目移动到其他项目。

   * **新工作区（产品配置文件）：**&#x200B;您可以通过执行以下操作来开始利用新的权限功能：

      * 在 [!DNL Admin Console for Enterprise] 中创建新工作区。
      * 将 Target 属性分配到工作区。

   您可以使用这些工作区按地区、业务部门、网站区域或通过您选择的任何其他方法，将访问权限划分给不同的团队。用户可以包含在多个工作区中，也可以在每个工作区拥有不同的角色。

1. 按照《企业用户指南》**&#x200B;的[创建和管理产品配置](https://helpx.adobe.com/cn/enterprise/help/manage-products-and-configurations.html)中的说明进行操作。

>[!NOTE]
>请观看下面的视频，以了解有关配置工作区的更多信息。

### 获取工作区ID {#workspace-id}

您需要传递工作区ID才能使用[Target API](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=zh-Hans){target=_blank}中的企业权限。

1. 在[Adobe Admin Console](https://adminconsole.adobe.com)中，单击[!UICONTROL Products]选项卡，然后单击左侧菜单中的产品以显示PLC（工作区）列表。
1. 单击所需的 PLC（工作区），然后在 URL 中找到“配置文件”ID，如下所示。

   ![workspaceID](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## 步骤 3. 创建用户组（可选） {#section_5F5CB9AA7A9F4D26953E22016DA59605}

您可以创建用户组（例如开发人员、分析师、营销人员、管理人员等），然后为其分配多个 Adobe 产品和工作区中的相应权限。为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

1. 在Admin Console中，单击页面顶部的&#x200B;**[!UICONTROL Users]**&#x200B;选项卡> **[!UICONTROL User Groups]**&#x200B;以创建新用户组或编辑现有用户组。
1. 按照《企业用户指南》**&#x200B;的[管理产品配置的用户和组](https://helpx.adobe.com/cn/enterprise/help/manage-products-and-configurations.html)中的说明进行操作。

## 步骤 4. 创建属性 {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

属性是通过在任意调用（Target调用、API调用等）中添加特定名称/值对作为参数来启用的 可以启用属性。

属性属于特定的渠道（Web、移动设备、电子邮件和 API/其他）。

**提示**：请观看下方的视频，以了解有关如何创建属性的更多信息。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Properties]**&#x200B;以显示[!UICONTROL Properties]列表。
1. 单击&#x200B;**创建属性**。

   填写以下字段：

   * **属性名称（必需）：**&#x200B;为属性指定一个描述性名称。
   * **描述：**&#x200B;为属性指定可选描述。
   * **渠道：**&#x200B;为属性选择所需的渠道：Web、移动设备应用程序、电子邮件或其他/API（例如机顶盒或 PlayStation 游戏机）。

1. 单击&#x200B;**[!UICONTROL Copy]**&#x200B;将代码复制到剪贴板，在执行[5：更新您的实现以包含at_property参数](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8)中的步骤时将使用该代码。
1. 完成后单击&#x200B;**[!UICONTROL Save]**。

>[!NOTE]
>请观看下面的视频，以了解有关创建属性的更多信息。

## 步骤5：更新您的实施以包含at_property参数 {#section_9B17A59807A94712BE642942442EBBC8}

要使用[!DNL Target]用户权限功能，您必须将`at_property`参数添加到任何点击[!DNL Target]的调用（Target调用、API调用等）中。

**获取 `at_property` 参数代码：**

1. （视情况而定）使用您在执行 [4. 创建属性](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD)中的步骤时生成并保存到剪贴板的实施代码，继续执行步骤 2。

   或

   在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Properties]**&#x200B;以显示[!UICONTROL Properties]列表。

   1. 将鼠标指针悬停在要显示的所需属性的[!UICONTROL Last Updated]列上，然后单击[!UICONTROL Code]图标。

      ![属性悬停代码](/help/main/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. 右键单击高亮显示的实施代码以将其复制到剪贴板。

1. 使用在上一步中获取的实施代码更新您的[!DNL Target]实施。

   您可以通过多种方法来更新 [!DNL Target] 实施。例如，对于网页，可以使用以下方法：

   * **通过[!DNL Adobe Experience Platform]内标记中的“自定义参数”：**

     有关详细信息，请参阅&#x200B;*标记概述*&#x200B;文档中的[添加Mbox参数](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=zh-Hans#add-mbox-params)。

   * **通过targetPageParamsAll()函数：**&#x200B;将以下代码置于`<head>`标记中的at.js引用上方。

     ```javascript
     <script>
      function targetPageParamsAll() {
       return {
        "at_property": "5f8bd98b-1456-a84c-2a96-11s9b8e2b112"
       };
      }
     </script>
     ```

     有关如何使用at.js完成此操作的更多信息，请参阅[targetPageParamsAll](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparamsall.html?lang=zh-Hans){target=_blank}。

## 步骤6：指定角色和权限 {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. 在Admin Console中，单击&#x200B;**[!UICONTROL Products]**，然后选择所需产品的名称。

   ![工作区](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. 单击所需配置文件的名称(例如，默认Workspace)。

   ![默认工作区](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. 单击 **[!UICONTROL Users]**。

   [!UICONTROL Users]选项卡会显示该工作区中的所有用户。

   ![配置用户](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. 使用[!UICONTROL Product Role]列中每个用户的下拉列表选择所需的权限角色（审批者、编辑者、观察者或发布者）。

   ![“产品角色”下拉列表](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |
   | 发布者 | 类似于观察者角色（可查看活动，但无法创建或编辑活动）。但是，发布者角色另有激活活动的权限。 |

   有关更多信息，请参阅企业用户指南&#x200B;**&#x200B;中的[在 Admin Console 中管理产品权限和角色](https://helpx.adobe.com/cn/enterprise/help/manage-permissions-and-roles.html)。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

>[!NOTE]
>
>[!DNL Target] [!UICONTROL Administration]菜单UI（以前为[!UICONTROL Setup]）已重新设计，以提供更好的性能、缩短发布新功能时所需的维护时间并改善整个产品的用户体验。 以下视频中的信息通常正确；但是，选项可能位于不同的位置。 更新后的视频很快就会发布。

### 如何配置Adobe Target工作区(6:55) ![教程徽章](/help/main/assets/tutorial.png)

以下视频说明了如何创建工作区。

* 从 Adobe Target 界面访问 Adobe Admin Console（3 种方式）
* 在 Adobe Admin Console 中配置工作区

   * 向工作区添加用户
   * 向工作区添加属性

* 了解默认工作区

>[!VIDEO](https://video.tv.adobe.com/v/3421729?captions=chi_hans)

### 如何在Adobe Target中创建属性(3:05) ![教程徽章](/help/main/assets/tutorial.png)

* 如何在 [!DNL Adobe Target] 界面中创建属性
* 如何生成要包含在属性实施中的属性令牌
* 熟悉三种实施方法：

   * Web
   * 移动设备应用程序
   * 电子邮件、机顶盒或API调用

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
