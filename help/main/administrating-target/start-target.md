---
keywords: 管理;审批者角色;审批者
description: 在收到Adobe Experience Cloud的电子邮件邀请后，执行Adobe Target管理员应该执行的首要任务。
title: 从何处开始管理[!DNL Target]？
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
TQID: 'https://experienceleague.adobe.com/GfadY-knTwzXCB-n1AZ9u3PtoAyJokn1OXu3elRhgXk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 9%
---
# 管理员首要步骤

在通过[!DNL Adobe Experience Cloud]收到加入[!DNL Adobe Target]的邀请后，请完成这些步骤。 当您准备好配置帐户默认设置时，请参阅[如何管理Target？](/help/main/administrating-target/administrating-target.md)。 有关在UI中查找&#x200B;**[!UICONTROL 管理]**&#x200B;的帮助，请参阅[了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)。

**工作流概述**

1. [受邀加入Target](#task_3E0817630774431983FAA3D2CB2E75BD)：系统管理员在[!DNL Adobe Admin Console]中添加您。
1. [接受邀请](#task_24FE66659E634B24AB61DB8497772E17)：登录到[!DNL Experience Cloud]并关联您的[!DNL Target]帐户。
1. [为您自己分配“审批者”角色](#task_15CAA437A71444E2932B333D5E66A3C7)：确认您的许可证类型的访问权限。
1. [用户管理](/help/main/administrating-target/c-user-management/user-management.md)：为[!DNL Target Standard]或[!DNL Target Premium]添加用户和分配角色。

## 受邀加入[!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console]中的系统管理员必须通过邀请您加入，将您添加为[!DNL Target]中的用户。 管理员还应将您添加到一个或多个特定于角色的产品配置文件（用户组）。 这两项任务均在[Adobe Admin Console](https://adminconsole.adobe.com)中完成。

有关分步指南，请参阅Adobe企业文档中的[了解如何管理用户和产品配置文件](https://helpx.adobe.com/enterprise/using/users.html)。

管理员完成这些步骤后，您将收到一封邀请电子邮件。

## 接受邀请 {#task_24FE66659E634B24AB61DB8497772E17}

收到加入[!DNL Adobe Experience Cloud]的邀请后，接受邀请、登录并接受[!UICONTROL 最终用户许可协议] (EULA)。

使用以下步骤接受邀请并将[!DNL Target]链接到您的[!DNL Experience Cloud]帐户：

1. 接受加入 [!DNL Adobe Experience Cloud] 的邀请。
1. 如果您还没有 Adobe ID，系统会提示您创建一个 Adobe ID。

   如果您已有Adobe ID，请在出现提示时登录。

1. 接受[!UICONTROL 使用条款]。

1. 查看您目前已做工作的摘要，然后单击&#x200B;**[!UICONTROL 继续访问Experience Cloud]**。

1. 登录到[!DNL Adobe Experience Cloud]，然后单击&#x200B;**[!UICONTROL 关联帐户]**。

   >[!NOTE]
   >
   >如果不关联您的帐户，则无法访问[!DNL Target]。

   所有[!UICONTROL Experience Cloud]产品都会显示在链接页面上。 单击&#x200B;**[!UICONTROL 链接目标]**，然后输入您的[!DNL Target]用户名和密码。
1. 单击&#x200B;**[!UICONTROL 继续访问Experience Cloud]**。

   此时，您可能还没有有权链接的产品配置文件；您的系统管理员可以在[!DNL Adobe Admin Console]中分配这些配置文件。
1. 或者，观看介绍[!DNL Adobe Experience Cloud]的视频。
1. 要刷新权限并打开产品，请注销[!DNL Adobe Experience Cloud]，然后重新登录。
1. 继续[为您自己分配审批者角色](#task_15CAA437A71444E2932B333D5E66A3C7)。

## 为您自己分配“审批者”角色 {#task_15CAA437A71444E2932B333D5E66A3C7}

接受邀请并登录后，确认[!DNL Target]出现在您的[!DNL Experience Cloud]帐户中，然后为您自己分配[!DNL Target]的[!UICONTROL 审批者]角色。

选择与您的许可证相匹配的指南：

* 如果您的组织具有[Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905)许可证，请参阅[了解如何在&#x200B;*用户*&#x200B;中指定角色和权限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。
* 如果贵组织具有 [Target Premium](/help/main/c-intro/intro.md#premium) 许可证，请参阅&#x200B;*配置企业权限*&#x200B;中的[步骤 6：指定角色和权限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)。

然后，您可以为[!DNL Target Standard]或[!DNL Target Premium]设置用户。 请参阅[用户管理](/help/main/administrating-target/c-user-management/user-management.md)以获取许可证的概述和正确工作流的链接。

## 编辑[!UICONTROL 管理]设置所需的权限 {#admin-permissions}

**在2025年4月22日之前**：在[!DNL Adobe Admin Console]中拥有[!UICONTROL 审批者]权限的用户可以在[!DNL Target]中的[[!UICONTROL 管理]](/help/main/administrating-target/administrating-target.md)页面上编辑或更改所有设置，而不管他们的[!DNL Target]角色如何。

**自2025年4月22日起生效**：仅[!UICONTROL 产品]和[!UICONTROL 解决方案]管理员可以更新[[!UICONTROL 管理]](/help/main/administrating-target/administrating-target.md)部分中的设置，无论其在[!DNL Target]工作区中的角色如何。 没有此权限的用户对[!UICONTROL 管理]部分具有只读访问权限。

此更改加强了组织对[!DNL Target]实例配置的控制，并有助于防止意外更新，这可能会影响测试和个性化团队之间的活动交付。
