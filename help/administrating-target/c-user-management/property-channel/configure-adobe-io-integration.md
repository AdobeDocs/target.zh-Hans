---
description: 有关授予Adobe I/集成功能的信息，可访问具有所需角色的所有工作区。
keywords: 集成；角色；用户权限；Admin Console
seo-description: 有关授予现有Adobe I/集成的信息，请访问Adobe Target中具有所需角色的所有工作区
seo-title: 在Adobe Target中授予Adobe I/集成功能访问工作区并分配角色
solution: Target
subtopic: 入门指南
title: 授予Adobe I/集成功能访问工作区和分配角色
translation-type: tm+mt
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

---


# ![高级](/help/assets/premium.png) 授予Adobe I/集成功能访问工作区并分配角色

[!UICONTROL Enterprise Permissions] 允许 [!DNL Target] 客户使用单个组织，但将其划分为不同团队或工作流程的工作区。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

[!UICONTROL 企业权限] 功能有助于跨团队有效扩展优化程序。Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* 您可以选择可将集成应用到的工作区
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

此更新支持以下用例：

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* 授予Adobe I/集成访问权限以选择具有适当角色的工作区，以允许中央团队只在几个工作区中进行API驱动的更改。
* 当团队准备好探索API并相应地选择角色时，允许每个拥有自己的工作空间的团队拥有自己的集成。
* 混合和匹配以上任意场景。

**需要的操作**：当前，在所有工作区中利用API针对资源(活动、受众、优惠和报告)运用API的客户需要授予其现有的Adobe I/集成访问所有工作区的权限，以根据其用例使用所需的角色。You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. 您现在可以选择所需的角色。

This action should be performed during the month of **August 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. 对设置集成没有负面反应。这一变化越快，就越好。根据单位中的工作区数量，设置此设置需要花费较少的时间。此过程只需单击几次，即可将现有的集成添加到具有所需角色的工作区中。

**要授予Adobe I/集成集成权限，请访问工作区并分配角色：**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![在Adobe Admin Console中选择产品](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 选择所需的工作区(产品配置文件)。

   ![选择产品配置文件](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![集成选项卡](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click **[!UICONTROL Add Integration]**, select the desired integration, then click **[!UICONTROL Save]**.

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   * [!UICONTROL 审批者]
   * [!UICONTROL 编辑者]
   * [!UICONTROL 观察者]
   ![选择产品配置文件角色](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
