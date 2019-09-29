---
description: 有关授予Adobe I/O集成对具有所需角色的所有工作区的访问权限的信息。
keywords: 集成；角色；用户权限；管理控制台
seo-description: 有关向现有Adobe I/O集成授予对Adobe Target中所需角色的所有工作区的访问权限的信息
seo-title: 授予Adobe I/O集成对工作区的访问权限并在Adobe Target中分配角色
solution: Target
subtopic: 入门指南
title: 授予Adobe I/O集成对工作区的访问权限并分配角色
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) 授予Adobe I/O集成对工作区的访问权限并分配角色

[!UICONTROL “企业权限] ” [!DNL Target] 允许客户使用单个组织，但将其分为不同团队或工作流的工作区。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

“企 [!UICONTROL 业权限] ”功能有助于有效扩展团队中的优化计划。 尽管该功能在UI中可用， [!DNL Target] 但直到2019年早些时候，Admin API还是缺乏相应的支持。 在2019年2 [!DNL Target] 月的版本中，Adobe更新了Admin API，这样您就可以使用集成帐户访问在组织中创建的所有工作区。 因此，虽然之前的版本将Admin API限制为仅使用默认工作区，但2019年2月的更新授予了对所有具有批准者访问权限的工作区 [!UICONTROL 的访] 问权限。

在2019年9 [!DNL Target] 月版本中， [!DNL Target] 企 [!UICONTROL 业权限] (Enterprise Permissions)为客户提供了以下访问控制：

* 您可以选择可应用集成的工作区
* 您可以将角色应用于Adobe I/O集成：审 [!UICONTROL 批人]、编 [!UICONTROL 辑者]或观 [!UICONTROL 察者]。

此更新支持以下用例：

* 授予具有“观察者”角色的所有工作区的Adobe I/O集成访问权限，以用于报告目的，而无权创建或编辑资源。 
* Grant the Adobe I/O integration the access to select workspaces with the appropriate role to allow a central team to make API-driven changes in only a few workspaces.
* 允许拥有其工作区的每个团队在准备好探索API并相应地选择角色时进行自己的集成。
* 混合并匹配以上任一场景。

**需要的操作**:当前在所有工作区中利用API进行CRUD操作（活动、受众、优惠和报告）的客户需要授予其现有Adobe I/O集成访问权限，根据其用例，该访问权限具有所需角色的所有工作区。 您可以通过在中选择每个产 [!DNL Target] 品配 [!UICONTROL 置文件] , [!DNL Adobe Admin Console] 然后在“集成”选项卡中添加 [!UICONTROL 集成] 。 在9月发布之前，所有集成都使用批准者访 [!UICONTROL 问来运行] ，无论从“产品角色  ”下拉列表中做出何种选择。 您现在可以选择所需的角色。

>[!NOTE]
>
>如果未执行此操作，在 [!DNL Target] 2019年9月版本发布后，访问控制将激活，并且您将仅看到对默认工作区的访问（如果您当前是这样设置的）。 预先设置集成没有不良反应。 你越早做出这种改变，就越好。 根据组织中的工作区数量，此过程只需单击几下即可将现有集成添加到具有所需角色的工作区中。

**要授予Adobe I/O集成对工作区的访问权限并分配角色，请执行以下操作：**

1. 打开 **[Adobe Admin Console](https://adminconsole.adobe.com)**。

1. 单击 **[!UICONTROL 产品]** ，然后选择所需产品的名称。

   ![Choose product in Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 选择所需的工作区（产品配置）。

   ![Select the product profile](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Integrations tab](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click Add Integration, select the desired integration, then click Save.********

1. From the Product Role drop-down list, select the desired role for that workspace:****

   * [!UICONTROL 审批者]
   * [!UICONTROL 编辑者]
   * [!UICONTROL 观察者]
   ![Choose Product Profile role](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
