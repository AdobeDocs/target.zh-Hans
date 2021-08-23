---
keywords: Analytics作为报表源；a4t;A4T；要求
description: 了解如何在Adobe [!DNL Target] using Analytics for [!DNL Target] (A4T)中配置创建基于Adobe Analytics的活动所需的用户帐户要求。
title: A4T需要哪些用户权限要求？
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: c9c335c241727c4eff1d27f52853e32b8d18b6a5
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 36%

---

# 用户权限要求

有关在 [!DNL Adobe Target] (A4T) 中创建基于 [!DNL Adobe Analytics] 的活动的用户帐户要求信息。

您需要具有一个 [!DNL Analytics] 用户帐户和一个 [!DNL Target] 用户帐户，才能在定义 [!DNL Analytics] 活动时选择报表包。

必须按照以下部分所述来配置您的用户帐户：

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

在 [!DNL Adobe Experience Cloud][Admin Console](https://adminconsole.adobe.com) 中完成以下任务：

### 将解决方案帐户关联到您的 Adobe ID。

您的 [!DNL Analytics] 和 [!DNL Target] 用户帐户必须已关联到您的 Adobe ID。

有关更多信息，请参阅[组织和帐户关联](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。

### 配置 Experience Cloud 组成员资格

您必须是一个或多个拥有 [!DNL Analytics] 和 [!DNL Target] 访问权限的 [!DNL Experience Cloud] 组的成员。

有关更多信息，请参阅[管理Experience Cloud用户和产品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

要在给定的报表包上使用A4T，您必须有权访问该报表包并授予对[!DNL Web Services Access]组的访问权限。

1. 在&#x200B;**[!UICONTROL Admin Console]**&#x200B;中，单击[!DNL Analytics]产品配置文件，然后单击&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。

   然后，您可以查看配置文件有权访问的报表包。

1. 确保要在[!DNL Target]中访问的报表包是您所属的产品配置文件中列出的报表包之一。

   下图是有权访问所有报表包的产品配置文件示例：

   ![Admin Console权限选项卡](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. 配置对[!UICONTROL Web服务访问]组的访问。

   需要访问[!DNL Analytics]中的[!UICONTROL Web服务访问]组，才能将[!DNL Analytics]用作[!DNL Target]的报表源。


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

无需其他权限。
