---
keywords: scene7;dynamic media classic;数字资产管理;资源;dam;内容库;交换图像
description: 将Adobe Target连接到Adobe Dynamic Media Classic (Scene7)，以便创作者可以在活动中使用来自Experience Cloud资源的图像选件和交换图像。
landing-page-description: 在“管理”中配置Scene7配置以在VEC和基于表单的体验编辑器中启用图像选件、内容库DAM工作流和交换图像操作。
short-description: 在“管理”中配置Scene7配置以在VEC和基于表单的体验编辑器中启用图像选件、内容库DAM工作流和交换图像操作。
title: 如何配置 Dynamic Media Classic (Scene7) 集成？
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: 'https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 553aa8fb523a62f72f0e2be7d7fd1b4eb663da6b
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 5%
---
# 配置Dynamic Media Classic (Scene7)

使用&#x200B;**[!UICONTROL 管理]**&#x200B;下的&#x200B;**[!UICONTROL Scene7配置]**&#x200B;选项卡将[!DNL Adobe Target]连接到[!DNL Adobe Dynamic Media Classic]（以前为[!DNL Scene7]）。 该集成将数字资产管理(DAM)引入[!UICONTROL 内容库]并在活动中启用图像交换工作流。

有关此选项卡如何与其他管理任务配合使用，请参阅[如何管理Target？](/help/main/administrating-target/administrating-target.md)。 要在界面中找到&#x200B;**[!UICONTROL 管理]**，请参阅[了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)。

**概述**

1. [集成支持的功能](#what-it-enables)：图像选件、交换图像和符合条件的资产。
1. [帐户和凭据](#account-and-credentials)：现有[!DNL Dynamic Media]帐户和支持的帐户类型。
1. [使用指南](#usage-guidelines)： URL、投放以及不支持的。
1. [在Target中配置Scene7](#configure-scene7)：登录和区域设置。

{{permissions-update}}

## 集成支持的功能 {#what-it-enables}

设置&#x200B;**[!UICONTROL Scene7配置]**&#x200B;后，作者可以使用上载到[!DNL Target]活动中[!DNL Adobe Experience Cloud]资源文件夹的图像。 **[!UICONTROL 交换图像选件]**&#x200B;选项出现在活动工作流中，包括在[可视化体验编辑器和基于表单的体验编辑器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中。 有关VEC中的交换行为，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

如果未配置此设置，则在活动创建期间将无法使用&#x200B;**[!UICONTROL 交换图像选件]**。

集成提供的资产属于Experience Cloud资产文件夹中的活动。 它&#x200B;**不**&#x200B;公开[!DNL Dynamic Media Classic]中的每个资产以用于[!DNL Target]活动。

配置后，在[!UICONTROL 选件]库中管理图像选件。 请参阅[管理内容](/help/main/c-experiences/c-manage-content/manage-content.md)。

## 帐户和凭据 {#account-and-credentials}

如果您已经拥有[!DNL Dynamic Media]帐户，请在&#x200B;**[!UICONTROL Scene7配置]**&#x200B;页面上输入这些凭据。

Adobe不再为新[!DNL Target]客户或新用户设置使用受限、免费的[!DNL Dynamic Media Classic]帐户。 如果您的组织已经拥有此集成的登录凭据，则这些凭据将继续工作。 有关帐户问题，请联系您的[!DNL Adobe]代表。

## 使用指南 {#usage-guidelines}

将图像与此集成一起使用时，请牢记以下限制：

* **图像选件，而不是存储URL。** [!DNL Dynamic Media]存储URL和发布的投放URL不同。 不要从存储链接构建选件；投放失败。 请改用[图像选件](/help/main/c-experiences/c-manage-content/manage-content.md)和交换图像工作流。
* 自定义代码中的&#x200B;**公共URL。** 要直接在选件或自定义代码中引用公共图像URL，请将图像托管在您自己的Web服务器上，并使用该URL。 您无法为已上传的Experience Cloud图像获取已发布的URL，以在[!DNL Target]定位工作流之外使用；合同不允许使用该功能。
* **符合条件的资源。** 只有上传到Experience Cloud资源文件夹的资源（以及此集成支持的工作流）在范围内，而不是完整的[!DNL Dynamic Media Classic]目录。

## 在Target中配置Scene7 {#configure-scene7}

使用以下步骤连接[!DNL Dynamic Media Classic] ([!DNL Scene7])：

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Scene7配置]**。
1. 输入您的[!DNL Dynamic Media Classic]帐户信息：

   | 字段 | 描述 |
   | --- | --- |
   | **地区** | [!DNL Dynamic Media]帐户的地区：北美洲、欧洲或亚洲。 |
   | **临时文件夹** | 用于手动上传到[!DNL Dynamic Media]的Target文件夹之外的内容的位置。 |
   | **电子邮件地址** | 用于登录到[!DNL Dynamic Media Classic] ([!DNL Scene7])的电子邮件地址。 |
   | **密码** | 用于登录到[!DNL Dynamic Media Classic] ([!DNL Scene7])的密码。 |

   ![Scene7配置字段](/help/main/administrating-target/assets/scene7-1.png)

1. 单击“提交”****。
