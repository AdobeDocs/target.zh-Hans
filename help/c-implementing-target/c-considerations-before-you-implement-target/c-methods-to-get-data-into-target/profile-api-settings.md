---
keywords: implementation;api;profile;profile api settings;authentication token
description: 通过Adobe TargetAPI启用或禁用批量更新的身份验证，并生成用户档案身份验证令牌。
title: 用户档案API设置(在Adobe Target)
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 40%

---


# 配置文件 API 设置

通过Adobe TargetAPI启用或禁用批量更新的身份验证，并生成用户档案身份验证令牌。

[!DNL Adobe Target] 会为每一个用户创建并维护一个配置文件。This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit; however, you can update a profile individually or in bulk via API.

为了提高安全性，您可以要求批量更新 API 调用必须在请求的标头中传递有效的访问令牌。

**使用 Target UI 设置身份验证要求并生成访问令牌：**

1. 单击“ **[!UICONTROL 管理]** ”>“ **[!UICONTROL 实施]**”。
1. 在“ **[!UICONTROL 用户档案]** API **[!UICONTROL ”下]** 滑，“需要身份验证”切换到启用或禁用位置。

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   令牌将根据“[!UICONTROL 到期时间]”框中所列的时间到期。

   您必须具有以下用户权限之一才能生成身份验证令牌：

   * 至少拥 [!UICONTROL 有“编辑] ”权限(或“审 [!UICONTROL 批者]”)

      有关客户的详细 [!DNL Target Standard] 信息，请 [参阅在用户中指定角](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) 色和 *权限*。 有关客户的详细 [!DNL Target Premium] 信息，请参 [阅配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * 工作区／产品用户档案级别上的管理员角色

      工作区仅对客 [!DNL Target Premium] 户可用。 For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * 产品级别的管理权限(Sysadmin [!DNL Adobe Target] 权限)
   >[!NOTE]
   >
   >您也可以通过 API 生成配置文件身份验证令牌。有关更多信息，请参阅 [Adobe Target 开发人员网站](https://developers.adobetarget.com/)上的[配置文件](https://developers.adobetarget.com/api/#profiles)。

1. 复制生成的令牌，并按以下格式将其包含在请求的标头中：&quot;授权&quot; : &quot;持有者&quot;。

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>重置此令牌会导致使用当前令牌的 API 调用失败。这将需要更新使用此令牌的任何脚本或应用程序。
