---
keywords: Analytics as reporting source;a4t;A4T
description: 在 Adobe Target (A4T) 中创建基于 Adobe Analytics 的活动时的用户帐户要求。
title: 用户权限要求
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 3215aa7c5ce986ff335dd2669c250ef5900d8789
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 51%

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

要在给定报表包上使用A4T，您必须有权访问该报表包。 要在Admin Console中 [!UICONTROL 访问]，请单击 [!DNL Analytics] 产品用户档案，然后单 [!UICONTROL 击权限] 选项卡。 然后，您可以查看用户档案有权访问的报表包。 确保您要访问的报表包是您所 [!DNL Target] 属产品用户档案中列出的报表包之一。

下图是具有所有报表包访问权限的产品用户档案的示例：

![Admin Console权限选项卡](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

无需其他权限。
