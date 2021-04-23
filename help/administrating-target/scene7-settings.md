---
keywords: scene7；动态媒体经典；数字资产管理；资产；dam；内容库；交换图像
description: 了解如何将Adobe [!DNL Target] 与Adobe Dynamic Media Classic(以前称为Scene7)集成，以在内容库中提供数字资产管理(DAM)。
title: 如何配置Dynamic Media Classic(Scene7)集成？
feature: 管理和配置
role: Administrator
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---

# Dynamic Media Classic(以前称为Scene7)配置

[!DNL Adobe Target] 可与(以 [!DNL Adobe Dynamic Media Classic] 前)集 [!DNL Scene7]成，以在内容库中提供数字资 [!UICONTROL 产管理(DAM)]。

>[!NOTE]
>
>将[!DNL Target]与[!DNL Dynamic Media Classic]集成可投放上传到[!DNL Adobe Experience Cloud]资产文件夹的资产(作为活动的一部分)。 此集成不允许访问在[!DNL Dynamic Media Classic]中上传的所有资产，以便在[!DNL Target]活动中投放。

如果您已经有[!DNL Dynamic Media]帐户，则可以提供现有凭据。 如果您没有帐户，则可以从您的[!DNL Adobe]代表处申请受限使用[!DNL Dynamic Media Classic]帐户，但不收取任何额外费用。 此帐户只能用于限制在[!DNL Target]中使用的用途。 当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未配置此设置，则活动创建工作流中的[!UICONTROL 交换图像优惠]选项不可用。 配置此设置后，在[Visual Experience Composer(VEC)和基于表单的体验编辑器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中都提供了交换/更改图像优惠的选项。 然后，您可以将图像优惠用于从[!DNL Adobe Experience Cloud]上传的图像，以用于[!DNL Target]活动。

在活动创建过程中，如果您想要在选件或自定义代码中直接引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器并在代码中使用您自己的 URL。无法获取上传到[!DNL Experience Cloud]中的图像的已发布URL，以使用[!DNL Target]直接使用或在定位工作流之外使用。 按照合同规定，不允许使用此功能。

请注意，来自[!DNL Dynamic Media]的图像的存储URL和最终发布URL是不同的，必须&#x200B;*NOT*&#x200B;使用图像的存储链接创建优惠，因为在这种情况下投放将不起作用。 您必须使用图像优惠功能，如我们的帮助文档中所述。

要与[!DNL Dynamic Media Classic]([!DNL Scene7])集成，您需要指定以下信息。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Scene7配置]**。

   ![Scene7页面](/help/administrating-target/assets/scene7.png)

1. 指定以下[!DNL Dynamic Media Classic]帐户信息：

   **地区：**[!DNL Dynamic Media]您的 帐户所在的地区：北美洲、欧洲或亚洲。

   **临时文件** 夹：驻留在目标文件夹外并手动上载到的内容的位 [!DNL Dynamic Media]置。

   **电子邮件地址：** 用于登录()的电子 [!DNL Dynamic Media Classic] 邮件[!DNL Scene7]地址。

   **口令：** 用于登录()的 [!DNL Dynamic Media Classic] 口[!DNL Scene7]令。

1. 单击&#x200B;**[!UICONTROL 提交]**。
