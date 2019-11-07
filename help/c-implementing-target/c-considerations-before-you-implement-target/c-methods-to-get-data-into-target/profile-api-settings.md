---
keywords: 实施;API;配置文件;配置文件 API 设置
description: 可为通过 API 进行的批量更新启用或禁用身份验证，并生成配置文件身份验证令牌。
title: 配置文件 API 设置
subtopic: 入门指南
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 配置文件 API 设置{#profile-api-settings}

可为通过 API 进行的批量更新启用或禁用身份验证，并生成配置文件身份验证令牌。

Adobe Target 会为每一个用户创建并维护一个配置文件。此配置文件存储在 Target 边缘集群中，且会在每次访问后实时更新，不过，您也可以通过 API 逐个或以批量方式更新配置文件。

为了提高安全性，您可以要求批量更新 API 调用必须在请求的标头中传递有效的访问令牌。具有审批者权限的用户可以生成并启用配置文件 API 身份验证令牌。

**使用 Target UI 设置身份验证要求并生成访问令牌：**

1. 单击&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL 实施]**。
1. 在&#x200B;**[!UICONTROL 配置文件 API 设置]**&#x200B;下方，使用&#x200B;**需要身份验证]下拉列表启用或禁用身份验证要求。[!UICONTROL **

   ![](assets/profile_api_settings.png)

1. （视情况而定）如果启用了身份验证要求，请单击&#x200B;**[!UICONTROL 生成配置文件身份验证令牌]**。

   ![](assets/profile_api_settings_2.png)

   令牌将根据“[!UICONTROL 到期时间]”框中所列的时间到期。

   >[!NOTE]
   >
   >您也可以通过 API 生成配置文件身份验证令牌。有关更多信息，请参阅 [Adobe Target 开发人员网站](https://developers.adobetarget.com/)上的[配置文件](https://developers.adobetarget.com/api/#profiles)。

1. 复制生成的令牌，并按以下格式将其包含在请求的标头中："授权" : "持有者"。

如果需要，单击[!UICONTROL 重新生成配置文件身份验证令牌]以重新生成令牌。

>[!IMPORTANT]
>
>重置此令牌会导致使用当前令牌的 API 调用失败。这将需要更新使用此令牌的任何脚本或应用程序。

