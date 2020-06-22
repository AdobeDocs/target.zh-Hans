---
description: Target Standard 可与 Adobe Dynamic Media Classic（以前为 Scene7）集成以便在内容库中提供数字资产管理 (DAM)。
title: Dynamic Media Classic 集成 配置集成
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 0736f6f777f9f3d64706541bf5ef8265615e9082
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 22%

---


# Scene7配置 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>本主题中的信息已更新，可在Target Standard/高级版20.6.1版本（2020年7月）即将发布的UI更改中抢先登峰造极。 本主题中显示的大多数信息适用于当前UI; 但是，选项可能位于稍有不同的位置。

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. 当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. 配置此设置后，在可视体验书写器(VEC)和基于表单的体验书写器 [中都可以使用交换／更改图像优惠的选项](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)。 You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

在活动创建过程中，如果您想要在选件或自定义代码中直接引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器并在代码中使用您自己的 URL。There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. 按照合同规定，不允许使用此功能。

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. 您必须使用图像优惠功能，如我们的帮助文档中所述。

To integrate with [!DNL Dynamic Media Classic] ([!DNL Scene7]), you need to specify the following information.

1. 单击 **[!UICONTROL “管理]** ” **[!UICONTROL >“Scene7配置”]**。

   ![Scene7页面](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **地区：**[!DNL Dynamic Media]您的 帐户所在的地区：北美洲、欧洲或亚洲。

   **临时文件夹：** 驻留在目标文件夹外并手动上传到的内容的位置 [!DNL Dynamic Media]。

   **电子邮件地址：** 用于登录()的电子邮 [!DNL Dynamic Media Classic] 件地[!DNL Scene7]址。

   **密码：** 用于登录()的 [!DNL Dynamic Media Classic] 口[!DNL Scene7]令。

1. 单击&#x200B;**[!UICONTROL 提交]**。
