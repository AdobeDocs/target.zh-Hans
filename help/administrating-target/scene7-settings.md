---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Adobe Target可以与AdobeDynamic Media经典(以前称为Scene7)集成，在内容库中提供数字资产管理(DAM)。
title: Dynamic Media经典集成配置集成
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 2e80c972e432ce97596c856dd396b8f1be05a61a
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 18%

---


# Dynamic Media经典(前Scene7)配置

[!DNL Adobe Target] 可与(以 [!DNL Adobe Dynamic Media Classic] 前) [!DNL Scene7]集成，在内容库中提供数字资 [!UICONTROL 产管理(DAM)]。

>[!NOTE]
>
>将[!DNL Target]与[!DNL Dynamic Media Classic]集成可对上传到[!DNL Adobe Experience Cloud] assets文件夹的资产(作为活动的一部分)进行投放。 此集成不允许访问在[!DNL Dynamic Media Classic]中上传的所有资产，以便在[!DNL Target]活动中投放。

如果您已经有[!DNL Dynamic Media]帐户，则可以提供现有凭据。 如果您没有帐户，您可以请求一个受限使用[!DNL Dynamic Media Classic]帐户，而不收取您的[!DNL Adobe]代表的额外费用。 此帐户只能用于限制在[!DNL Target]中使用的用途。 当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未配置此设置，则活动创建工作流中的[!UICONTROL 交换图像优惠]选项不可用。 配置此设置后，在[Visual Experience Composer(VEC)和基于表单的体验书写器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中都可以使用交换／更改图像优惠的选项。 然后，您可以将图像优惠用于从[!DNL Adobe Experience Cloud]上传的用于[!DNL Target]活动的图像。

在活动创建过程中，如果您想要在选件或自定义代码中直接引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器并在代码中使用您自己的 URL。无法获取上传到[!DNL Experience Cloud]的图像的已发布URL，以直接使用或不使用使用[!DNL Target]的定位工作流。 按照合同规定，不允许使用此功能。

请注意，来自[!DNL Dynamic Media]的图像的存储URL和最终发布URL是不同的，必须&#x200B;*NOT*&#x200B;使用图像的存储链接创建优惠，因为在这种情况下投放将无效。 您必须使用图像优惠功能，如我们的帮助文档中所述。

要与[!DNL Dynamic Media Classic]([!DNL Scene7])集成，您需要指定以下信息。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Scene7配置]**。

   ![Scene7页面](/help/administrating-target/assets/scene7.png)

1. 指定以下[!DNL Dynamic Media Classic]帐户信息：

   **地区：**[!DNL Dynamic Media]您的 帐户所在的地区：北美洲、欧洲或亚洲。

   **临时文件** 夹：驻留在目标文件夹外并手动上传到的内容的位 [!DNL Dynamic Media]置。

   **电子邮件地址：** 用于登录()的电子邮 [!DNL Dynamic Media Classic] 件地[!DNL Scene7]址。

   **口令：** 用于登录()的 [!DNL Dynamic Media Classic] 口令[!DNL Scene7]。

1. 单击&#x200B;**[!UICONTROL 提交]**。
