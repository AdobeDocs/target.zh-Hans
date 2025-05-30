---
keywords: 集成;角色;用户权限;Admin Console
description: 了解如何授予现有Adobe I/O集成使用Adobe Target中的所需角色访问所有工作区的权限。
title: 如何授予Adobe I/O访问工作区的权限并分配角色？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 59%

---

# 授予 Adobe I/O 集成访问工作区的权限并分配角色

[!UICONTROL Enterprise Permissions]允许[!DNL Target]客户使用单个组织，但会根据其不同的团队或工作流程将其划分为多个工作区。

>[!NOTE]
>
>“属性和权限”功能作为 [Target Premium](/help/main/c-intro/intro.md#premium) 解决方案的一部分提供。如果没有 [!DNL Target Premium] 许可证，它们将无法在 [!DNL Target Standard] 中使用。

[!UICONTROL Enterprise Permissions]功能有助于跨团队高效地扩展优化程序。 尽管该功能在 [!DNL Target] UI 中可用，但直到 2019 年年初管理员 API 一直缺少相应的支持。在 [!DNL Target] 2019 年 2 月版中，Adobe 更新了管理员 API，以便您可以使用集成帐户访问组织中创建的所有工作区。因此，尽管在以前版本中，管理员API限制为仅访问默认工作区，但是2019年2月的更新版授予了使用[!UICONTROL Approver]访问权限访问所有工作区的访问权限。

在[!DNL Target] 2019年9月版中，[!DNL Target] [!UICONTROL Enterprise Permissions]为客户提供以下访问控制：

* 您可以选择可将集成应用到的工作空间
* 您可以将角色应用于Adobe I/O集成： [!UICONTROL Approver]、[!UICONTROL Editor]或[!UICONTROL Observer]。

更新版支持以下用例：

* 授予Adobe I/O集成使用[!UICONTROL Observer]角色访问所有工作区的权限以进行报告，但无权创建或编辑资源。
* 授予 Adobe I/O 集成使用适当的角色来选择工作区的权限，以允许中心团队仅在少数几个工作区中进行基于 API 的更改。
* 当团队准备好探索 API 并选择相应的角色时，允许各个团队自行创建工作区以便拥有他们自己的集成。
* 混合并匹配以上任意场景。

**所需操作**：当前正在利用 API 对所有工作区中的资源（活动、受众、选件和报表）执行 CRUD 操作的客户，需要根据用例要求，授予其现有 Adobe I/O 集成使用所需的角色访问所有工作区的权限。您可以通过选择[!DNL Adobe Admin Console]中的每个[!DNL Target] [!UICONTROL Product Profile]并在[!UICONTROL Integration]选项卡中添加集成来执行此操作。 在9月版之前，无论从[!UICONTROL Product Role]下拉列表中进行任何选择，所有集成操作都使用[!UICONTROL Approver]访问权限来进行。 现在，您可以选择所需的角色。

>[!NOTE]
>
>如果未执行这项操作，则在 [!DNL Target] 2019 年 9 月版发布之后，访问控制将会激活，而且如果您当前设置为仅访问默认工作区，那么您将看到激活后也只能访问默认工作区。预先设置集成不会产生不良影响。越早完成更改越好。根据组织中的工作区数量，此过程只需单击几次，即可使用所需的角色将现有集成添加到工作区中。

**要授予 Adobe I/O 集成访问工作区的权限并分配角色，请执行以下操作：**

1. 打开&#x200B;**[Adobe Admin Console](https://adminconsole.adobe.com)**。

1. 单击&#x200B;**[!UICONTROL Products]**&#x200B;选项卡，然后选择所需产品的名称。

   ![在 Adobe Admin Console 中选择产品](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. 选择所需的工作区（产品配置文件）。

   ![选择产品配置文件](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. 单击&#x200B;**[!UICONTROL Integrations]**&#x200B;选项卡。

   ![“集成”选项卡](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. （视情况而定）要添加新集成，请单击&#x200B;**[!UICONTROL Add Integration]**，选择所需的集成，然后单击&#x200B;**[!UICONTROL Save]**。

1. 从&#x200B;**[!UICONTROL Product Role]**&#x200B;下拉列表中，为该工作区选择所需的角色：

   | 角色 | 描述 |
   |--- |--- |
   | 审批者 | 可以创建、编辑，以及激活或停止活动。 |
   | 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
   | 观察者 | 可以查看活动，但不能创建或编辑活动。 |
   | 发布者 | 类似于观察者角色（可查看活动，但无法创建或编辑活动）。但是，发布者角色另有激活活动的权限。 |
