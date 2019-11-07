---
keywords: 集成;角色;用户权限;Admin Console
description: 有关授予现有 Adobe I/O 集成使用 Adobe Target 中的所需角色访问所有工作区的权限的信息。
title: 在 Adobe Target 中授予 Adobe I/O 集成访问工作区的权限并分配角色
subtopic: 入门指南
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) 授予 Adobe I/O 集成访问工作区的权限并分配角色

[!UICONTROL 企业权限]允许 [!DNL Target] 客户使用单个组织，但会根据其不同的团队或工作流程将其划分为多个工作区。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

[!UICONTROL 企业权限]功能有助于跨团队高效地扩展优化程序。尽管该功能在 [!DNL Target] UI 中可用，但直到 2019 年年初管理员 API 一直缺少相应的支持。在 [!DNL Target] 2019 年 2 月版中，Adobe 更新了管理员 API，以便您可以使用集成帐户访问组织中创建的所有工作区。因此，尽管在以前版本中，管理员 API 限制为仅访问默认工作区，但是 2019 年 2 月的更新版授予了使用[!UICONTROL 审批者]访问权限访问所有工作区的访问权限。

With the [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] provides customers with the following access controls:

* 您可以选择可将集成应用到的工作空间
* 您可以对 Adobe I/O 集成应用以下角色：[!UICONTROL 审批者]、[!UICONTROL 编辑者]或[!UICONTROL 观察者]。

更新版支持以下用例：

* 授予 Adobe I/O 集成使用[!UICONTROL 观察者]角色访问所有工作区的权限以进行报告，但无权创建或编辑资源。
* 授予 Adobe I/O 集成使用适当的角色来选择工作区的权限，以允许中心团队仅在少数几个工作区中进行基于 API 的更改。
* 当团队准备好探索 API 并选择相应的角色时，允许各个团队自行创建工作区以便拥有他们自己的集成。
* 混合并匹配以上任意场景。

**所需操作**：当前正在利用 API 对所有工作区中的资源（活动、受众、选件和报表）执行 CRUD 操作的客户，需要根据用例要求，授予其现有 Adobe I/O 集成使用所需的角色访问所有工作区的权限。您可以通过选择 [!DNL Adobe Admin Console] 中的每个 [!DNL Target] [!UICONTROL 产品配置文件]，并在[!UICONTROL 集成]选项卡中添加集成来执行此操作。在 9 月版之前，无论从[!UICONTROL 产品角色]下拉列表中进行任何选择，所有集成操作都使用[!UICONTROL 审批者]访问权限来进行。现在，您可以选择所需的角色。

>[!NOTE]
>
>如果未执行这项操作，则在 [!DNL Target] 2019 年 9 月版发布之后，访问控制将会激活，而且如果您当前设置为仅访问默认工作区，那么您将看到激活后也只能访问默认工作区。预先设置集成不会产生不良影响。越早完成更改越好。根据组织中的工作区数量，此过程只需单击几下即可将现有集成添加到具有所需角色的工作区中。

**要授予 Adobe I/O 集成访问工作区的权限并分配角色，请执行以下操作：**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. 单击&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡，然后选择所需产品的名称。

   ![在 Adobe Admin Console 中选择产品](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 选择所需的工作区（产品配置文件）。

   ![选择产品配置文件](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 单击&#x200B;**[!UICONTROL 集成]**&#x200B;选项卡。

   ![“集成”选项卡](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （条件）要添加新集成，请单击&#x200B;**[!UICONTROL 添加集成]**，选择所需的集成，然后单击&#x200B;**[!UICONTROL 保存]**。

1. 从&#x200B;**[!UICONTROL 产品角色]**&#x200B;下拉列表中，为该工作区选择所需的角色：

   * [!UICONTROL 审批者]
   * [!UICONTROL 编辑者]
   * [!UICONTROL 观察者]
   ![选择产品配置文件角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
