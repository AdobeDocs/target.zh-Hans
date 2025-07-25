---
keywords: 管理;审批者角色;审批者
description: 在收到 [!DNL Adobe Target] 的电子邮件邀请后，执行 [!DNL Adobe Experience Cloud]管理员应该执行的第一个任务。
title: 从何处开始管理 [!DNL Target]？
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 614fd89c9746ce55f502debd5b689c34de400ae5
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 32%

---

# 管理员首要步骤

本文包含收到[!DNL Adobe Target]的电子邮件邀请后，[!DNL Adobe Experience Cloud]管理员应该采取的首要步骤。

## 受邀加入[!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console]中的系统管理员必须通过邀请您加入，将您添加为[!DNL Target]中的用户。 然后，系统管理员应将您添加到一个或多个特定于角色的产品配置文件（用户组）。 这两项任务均在[Adobe Admin Console](https://adminconsole.adobe.com)中执行。

有关详细信息，请参阅[管理用户组](https://helpx.adobe.com/enterprise/using/users.html)。

系统管理员执行这些步骤后，您将会收到一封邀请电子邮件。

## 接受邀请 {#task_24FE66659E634B24AB61DB8497772E17}

收到加入[!DNL Adobe Experience Cloud]的邀请之后，接受邀请、登录并接受[!UICONTROL End User License Agreement] (EULA)。

1. 接受加入 [!DNL Adobe Experience Cloud] 的邀请。
1. 如果您还没有 Adobe ID，系统会提示您创建一个 Adobe ID。

   如果您有Adobe ID，则会识别您的Adobe ID，并提示您登录。
1. 接受[!UICONTROL Terms of Use]。
1. 查看您目前已做工作的摘要，然后单击&#x200B;**[!UICONTROL Continue to Experience Cloud]**。
1. 登录到[!DNL Adobe Experience Cloud]并单击&#x200B;**[!UICONTROL Link Account]**。

   >[!NOTE]
   >
   >如果不关联您的帐户，您将无法访问 [!DNL Target]。

   所有[!UICONTROL Experience Cloud]产品都会显示在链接页面上。 单击`Link Target`并输入您的[!DNL Target]用户名和密码以访问[!DNL Target]。
1. 单击 **[!UICONTROL Continue to Experience Cloud]**。

   此时，您还没有为任何组设置权限以供您关联。
1. 如有需要，请观看介绍 [!DNL Adobe Experience Cloud] 的相关视频。
1. 要查看您的新权限并访问产品，请先注销 [!DNL Adobe Experience Cloud]，然后再重新登录。
1. 继续下一步骤：[为您自己分配“审批者”角色](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 为您自己分配“审批者”角色 {#task_15CAA437A71444E2932B333D5E66A3C7}

接受加入[!DNL Adobe Experience Cloud]的邀请并登录之后，确认[!DNL Target]已添加至您的[!DNL Experience Cloud]帐户，然后为您自己分配[!UICONTROL Approver]的[!DNL Target]角色。

如果贵组织具有 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) 许可证，请参阅&#x200B;*用户*&#x200B;中的[指定角色和权限](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。

如果贵组织具有 [Target Premium](/help/main/c-intro/intro.md#premium) 许可证，请参阅&#x200B;*配置企业权限*&#x200B;中的[步骤 6：指定角色和权限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)。

下一步应该是在[!DNL Target Standard]和[!DNL Target Premium]中设置用户。 有关更多信息，请参阅[用户管理](/help/main/administrating-target/c-user-management/user-management.md)。

## 编辑[!UICONTROL Administration]设置所需的权限 {#admin-permissions}

**在2025年4月22日之前**：在[!UICONTROL Approvers]中拥有[!DNL Adobe Admin Console]权限的用户可以编辑或更改[[!UICONTROL Administration]的](/help/main/administrating-target/administrating-target.md)页面[!DNL Target]页面上的所有设置，而不管他们的[!DNL Target]角色如何。

**自2025年4月22日起生效**：仅[!UICONTROL Product]和[!UICONTROL Solutions]管理员能够更新[[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md)分区中的设置，无论他们在[!DNL Target]工作区中担任什么角色。 没有此权限的用户将具有[!UICONTROL Administration]部分的只读访问权限。

此更新增强了组织对[!DNL Target]实例配置的控制，防止了可能影响不同测试和个性化团队之间活动交付的意外更新。
