---
keywords: implementation;api;profile;profile api settings;authentication token
description: 通过Adobe TargetAPI启用或禁用批量更新的身份验证，并生成用户档案身份验证令牌。
title: 用户档案API设置(在Adobe Target)
feature: APIs/SDKs
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 40%

---


# 配置文件 API 设置

通过[!DNL Adobe Target] API启用或禁用批量更新的身份验证，并生成用户档案身份验证令牌。

[!DNL Adobe Target] 会为每一个用户创建并维护一个配置文件。此用户档案存储在[!DNL Target]边缘群集上，每次访问后会实时更新；但是，您可以单独或通过API批量更新用户档案。

为了提高安全性，您可以要求批量更新 API 调用必须在请求的标头中传递有效的访问令牌。

**使用 Target UI 设置身份验证要求并生成访问令牌：**

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实施]**。
1. 在&#x200B;**[!UICONTROL 用户档案API]**&#x200B;幻灯片下，**[!UICONTROL 需要身份验证]**&#x200B;切换到启用或禁用位置。

   ![](assets/profile_api_settings.png)

1. （视情况而定）如果启用了身份验证要求，请单击&#x200B;**[!UICONTROL 生成新用户档案身份验证令牌]**。

   ![](assets/profile_api_settings_2.png)

   令牌将根据“[!UICONTROL 到期时间]”框中所列的时间到期。

   您必须具有以下用户权限之一才能生成身份验证令牌：

   * 至少[!UICONTROL Editor]权限（或[!UICONTROL Approver]）

      有关[!DNL Target Standard]客户的详细信息，请参阅&#x200B;*Users*&#x200B;中的[指定角色和权限](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)。 有关[!DNL Target Premium]客户的详细信息，请参阅[配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * 工作区／产品用户档案级别上的管理员角色

      工作区仅对[!DNL Target Premium]客户可用。 有关详细信息，请参阅[配置企业权限](/help/administrating-target/c-user-management/property-channel/properties-overview.md)。

   * [!DNL Adobe Target]产品级别上的管理权限（Sysadmin权限）
   >[!NOTE]
   >
   >您也可以通过 API 生成配置文件身份验证令牌。有关更多信息，请参阅 [Adobe Target 开发人员网站](https://developers.adobetarget.com/)上的[配置文件](https://developers.adobetarget.com/api/#profiles)。

1. 复制生成的令牌，并按以下格式将其包含在请求的标头中：&quot;授权&quot; : &quot;持有者&quot;。

单击[!UICONTROL 生成新用户档案身份验证令牌]以根据需要重新生成令牌。

>[!IMPORTANT]
>
>重置此令牌会导致使用当前令牌的 API 调用失败。这将需要更新使用此令牌的任何脚本或应用程序。
