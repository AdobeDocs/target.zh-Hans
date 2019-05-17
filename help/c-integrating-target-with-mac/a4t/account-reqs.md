---
description: 在 Adobe Target (A4T) 中创建基于 Adobe Analytics 的活动时的用户帐户要求。
keywords: Analytics 作为报表源;a4t;A4T
seo-description: 在 Adobe Target (A4T) 中创建基于 Adobe Analytics 的活动时的用户帐户要求。
seo-title: 用户权限要求
solution: Target,Analytics
title: 用户权限要求
topic: Reports & Analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 用户权限要求 {#user-permission-requirements}

有关用户帐户要求的信息，用于创建 [!DNL Adobe Analytics]( [!DNL Adobe Target] A4T)的活动。

在定义 [!DNL Analytics] 活动时，可以选择报表包，您需要 [!DNL Analytics] 用户帐户和 [!DNL Target] 用户帐户。

必须按照以下部分所述来配置您的用户帐户：

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud][Admin Console中完成以下任务](https://adminconsole.adobe.com)：

### 将解决方案帐户关联到您的Adobe ID

您 [!DNL Analytics] 和 [!DNL Target] 用户帐户必须链接到您的Adobe ID。

有关更多信息，请参阅 [组织和帐户链接](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html)。

### 配置Experience Cloud组成员资格

您必须是有权访问和访问的一 [!DNL Experience Cloud] 个或多个组的成员 [!DNL Analytics][!DNL Target]。

有关更多信息，请参阅 [管理Experience Cloud用户和产品](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)。


## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

完成以下任务 [!DNL Adobe Analytics]：

### 配置对Analytics报告套件的访问权限

在创建或查看以Analytics为后盾的活动的报告之前，您必须是 **[!UICONTROL “所有报告访问”]** 组的成员，或有权访问要使用的报表包中至少一个报告的组成员。如果您无法查看报表，请确保您是上述任一组的成员。

有关更多信息，请参阅 [产品配置和组](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)。

### 配置对Web服务访问组的访问权限

您必须属于中 [!DNL Adobe Analytics] 的Web服务访问组，才能 [!DNL Analytics] 用作报告源 [!DNL Target]。

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

无需其他权限。
