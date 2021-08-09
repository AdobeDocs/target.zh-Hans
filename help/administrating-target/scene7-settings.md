---
keywords: scene7;dynamic media classic;数字资产管理;资源;dam;内容库;交换图像
description: 了解如何将 Adobe [!DNL Target] 与 Adobe Dynamic Media Classic（以前为 Scene7）集成以便在内容库中提供数字资产管理 (DAM)。
title: 如何配置 Dynamic Media Classic (Scene7) 集成？
feature: 管理和配置
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: ht
source-wordcount: '404'
ht-degree: 100%

---

# Dynamic Media Classic（以前为 Scene7）配置

[!DNL Adobe Target] 可与 [!DNL Adobe Dynamic Media Classic]（以前为 [!DNL Scene7]）集成以便在[!UICONTROL 内容库]中提供数字资产管理 (DAM)。

>[!NOTE]
>
>将 [!DNL Target] 与 [!DNL Dynamic Media Classic] 集成后，可以交付已上传到 [!DNL Adobe Experience Cloud] 资源文件夹的资源（作为活动的一部分交付）。此集成不允许访问在 [!DNL Dynamic Media Classic] 中上传以便在 [!DNL Target] 活动中交付的所有资源。

如果您已经拥有 [!DNL Dynamic Media] 帐户，则可以提供现有凭据。如果您没有帐户，则可以向 [!DNL Adobe] 代表请求获取使用受限的 [!DNL Dynamic Media Classic] 帐户，而不需要支付额外费用。可以使用此帐户在 [!DNL Target] 中只执行一些限定的操作。当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

如果未配置此设置，则活动创建工作流中的[!UICONTROL 交换图像选件]选项将不可用。配置此设置后，[可视体验编辑器 (VEC) 和基于表单的体验编辑器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中都会提供用于交换/更改图像选件的选项。随后，您可以使用图像选件，其中包含从 [!DNL Adobe Experience Cloud] 上传以供在 [!DNL Target] 活动中使用的图像。

在活动创建过程中，如果您想要直接在选件或自定义代码中引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器，并在代码中使用您自己的 URL。无法获取已上传到 [!DNL Experience Cloud] 的图像的已发布 URL，以将其直接用在使用 [!DNL Target] 的定位工作流中或这些工作流之外。按照合同规定，不允许使用此功能。

请注意，[!DNL Dynamic Media] 中图像的存储 URL 和最终发布 URL 是不同的，任何人&#x200B;*不得*&#x200B;使用图像的存储链接创建选件，否则将无法正常交付。您必须按照帮助文档中的相关说明来使用图像选件功能。

要与 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 集成，您需要指定以下信息。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL Scene7 配置]**。

   ![Scene7 页面](/help/administrating-target/assets/scene7.png)

1. 指定以下 [!DNL Dynamic Media Classic] 帐户信息：

   **区域：**&#x200B;您的 [!DNL Dynamic Media] 帐户所在的区域：北美洲、欧洲或亚洲。

   **临时文件夹：**&#x200B;位于 Target 文件夹以外且手动上传到 [!DNL Dynamic Media] 的内容所在的位置。

   **电子邮件地址：**&#x200B;用于登录到 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 的电子邮件地址。

   **密码：**&#x200B;用于登录到 [!DNL Dynamic Media Classic] ([!DNL Scene7]) 的密码。

1. 单击&#x200B;**[!UICONTROL 提交]**。
