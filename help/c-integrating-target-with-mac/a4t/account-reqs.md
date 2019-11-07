---
keywords: Analytics 作为报表源;a4t;A4T
description: 在 Adobe Target (A4T) 中创建基于 Adobe Analytics 的活动时的用户帐户要求。
title: 用户权限要求
solution: Target,Analytics
topic: Reports & Analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 用户权限要求 {#user-permission-requirements}

有关在 [!DNL Adobe Target] (A4T) 中创建基于 [!DNL Adobe Analytics] 的活动的用户帐户要求信息。

您需要具有一个 [!DNL Analytics] 用户帐户和一个 [!DNL Target] 用户帐户，才能在定义 [!DNL Analytics] 活动时选择报表包。

必须按照以下部分所述来配置您的用户帐户：

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud][Admin Console](https://adminconsole.adobe.com) 中完成以下任务：

### 将解决方案帐户关联到您的 Adobe ID。

您的 [!DNL Analytics] 和 [!DNL Target] 用户帐户必须已关联到您的 Adobe ID。

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### 配置 Experience Cloud 组成员资格

您必须是一个或多个拥有 [!DNL Analytics] 和 [!DNL Target] 访问权限的 [!DNL Experience Cloud] 组的成员。

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).


## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

在 [!DNL Adobe Analytics] 中完成以下任务：

### 配置对 Analytics 报表包的访问权限

要创建或查看启用了 Analytics 的活动的报表，您必须是&#x200B;**[!UICONTROL 所有报表访问权限]**&#x200B;组的成员，或您所属的组有权访问要使用的报表包中的至少一个报表。如果您无法查看报表，请确保您是上述任一组的成员。

有关详细信息，请参阅 [产品配置和组](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)。

### 配置对“Web 服务访问”组的访问权限

您必须属于 [!DNL Adobe Analytics] 中的“Web 服务访问”组，才能将 [!DNL Analytics] 用作 [!DNL Target] 报表源。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

无需其他权限。
