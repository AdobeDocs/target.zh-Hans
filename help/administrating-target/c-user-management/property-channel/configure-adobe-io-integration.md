---
description: 有关授予Adobe I/集成功能的信息，可访问具有所需角色的所有工作区。
keywords: 集成；角色；用户权限；Admin Console
seo-description: 有关授予现有Adobe I/集成的信息，请访问Adobe Target中具有所需角色的所有工作区
seo-title: 在Adobe Target中授予Adobe I/集成功能访问工作区并分配角色
solution: Target
subtopic: 入门指南
title: 授予Adobe I/集成功能访问工作区和分配角色
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![高级](/help/assets/premium.png) 授予Adobe I/集成功能访问工作区并分配角色

[!UICONTROL Enterprise Permissions] 允许 [!DNL Target] 客户使用单个组织，但将其划分为不同团队或工作流程的工作区。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

[!UICONTROL 企业权限] 功能有助于跨团队有效扩展优化程序。尽管该功能在 [!DNL Target] UI中可用，但管理员API在2019年之前一直缺少相应的支持。在2019 [!DNL Target] 年月版本中，Adobe更新了管理员API，以便您可以使用集成帐户访问单位中创建的所有工作区。因此，虽然以前，管理员API仅限于默认工作区，但在2019年月的更新中，已授予 [!UICONTROL 具有审批人] 访问权限的所有工作区的访问权限。

在2019 [!DNL Target] 年月版中 [!DNL Target][!UICONTROL ，Enterprise Permissions] 为客户提供以下访问控制：

* 您可以选择可将集成应用到的工作区
* 您可以对Adobe I/集成应用角色： [!UICONTROL 审批人]、 [!UICONTROL 编辑者]或 [!UICONTROL 观察者]。

此更新支持以下用例：

* 授予Adobe I/Ominteration Access对所有工作区具有 [!UICONTROL “观察者”] 角色的集成权限，没有权限创建或编辑资源。
* 授予Adobe I/集成访问权限以选择具有适当角色的工作区，以允许中央团队只在几个工作区中进行API驱动的更改。
* 当团队准备好探索API并相应地选择角色时，允许每个拥有自己的工作空间的团队拥有自己的集成。
* 混合和匹配以上任意场景。

**需要的操作**：当前，在所有工作区中利用API针对资源(活动、受众、优惠和报告)运用API的客户需要授予其现有的Adobe I/集成访问所有工作区的权限，以根据其用例使用所需的角色。您可以通过选择中的每个 [!DNL Target][!UICONTROL 产品配置文件] 并在 [!DNL Adobe Admin Console][!UICONTROL “集成] ”选项卡中添加集成来执行此操作。在月发布之前，所有使用 [!UICONTROL 审批人] 访问权限操作的集成，无论 [!UICONTROL 从“产品角色”] 下拉列表中进行了什么选择。您现在可以选择所需的角色。

>[!NOTE]
>
>如果未执行此操作，则在2019 [!DNL Target] 年月发布之后，访问控制将会激活，如果您当前设置了该工作区，则您将仅观察到默认工作区。对设置集成没有负面反应。这一变化越快，就越好。根据单位中的工作区数量，此过程只需单击几次即可将现有的集成添加到具有所需角色的工作区中。

**要授予Adobe I/集成集成权限，请访问工作区并分配角色：**

1. 打开 **[Adobe Admin Console](https://adminconsole.adobe.com)**。

1. 单击 **[!UICONTROL “产品]** ”选项卡，然后选择所需产品的名称。

   ![在Adobe Admin Console中选择产品](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 选择所需的工作区(产品配置文件)。

   ![选择产品配置文件](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![集成选项卡](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (具有条件)要添加新集成，请单击 **[!UICONTROL 添加集成]**，选择所需的集成，然后单击 **[!UICONTROL 保存]**。

1. 从 **[!UICONTROL 产品角色]** 下拉列表中，为该工作区选择所需的角色：

   * [!UICONTROL 审批者]
   * [!UICONTROL 编辑者]
   * [!UICONTROL 观察者]
   ![选择产品配置文件角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
