---
description: Target Standard 可与 Adobe Dynamic Media Classic（以前为 Scene7）集成以便在内容库中提供数字资产管理 (DAM)。
seo-description: Target Standard 可与 Adobe Dynamic Media Classic（以前为 Scene7）集成以便在内容库中提供数字资产管理 (DAM)。
seo-title: Dynamic Media Classic 集成
solution: Target
subtopic: 入门指南
title: Dynamic Media Classic 集成
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic 集成{#scene-settings}

Target Standard 可与 Adobe Dynamic Media Classic（以前为 Scene7）集成以便在内容库中提供数字资产管理 (DAM)。

>[!NOTE]
>
>将 Target 与 Dynamic Media Classic 集成后，可以交付已上传到 Adobe Experience Cloud 资产文件夹的资产（作为活动的一部分交付）。但是，配置此集成后，并不能访问 Dynamic Media Classic 中已上传的所有资产以在 Target 活动中进行交付。

如果您已经拥有 Dynamic Media 帐户，则可以提供现有凭据。如果您还没有帐户，则可以向 Adobe 代表请求获取使用受限的 Dynamic Media Classic 帐户，而不需要支付额外费用。可以使用此帐户在 Target 中执行一些限定的操作。当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

如果未配置此设置，活动创建工作流中的“交换图像”选件选项将不可用。配置此设置后，交换/更改图像选件的选项在[可视化体验编辑器 (VEC) 和基于表单的体验编辑器](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中均可用。随后，您可以使用图像选件，其中包含从 Adobe Experience Cloud 上传的以供在 Target 活动中使用的图像。

在活动创建过程中，如果您想要在选件或自定义代码中直接引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器并在代码中使用您自己的 URL。无法获取已上传到 Experience Cloud 的图像的已发布 URL，以将其直接用在使用 Adobe Target 的定位工作流中或这些工作流之外。按照合同规定，不允许使用此功能。

请注意，Dynamic Media 中图像的存储 URL 和最终发布 URL 是不同的，任何人“不得”使用图像的存储链接创建选件，否则将无法正常交付。所有人都必须按照帮助文档中的相关说明来使用图像选件功能。

要与 Dynamic Media Classic (Scene7) 集成，您需要指定下面一些信息。

1. 单击&#x200B;**[!UICONTROL 设置]** &gt; **[!UICONTROL Scene7 设置]**。
1. 指定以下 Dynamic Media Classic 帐户信息：

   **地区：**&#x200B;您的 Dynamic Media 帐户所在的地区：北美洲、欧洲或亚洲。

   **临时文件夹：**&#x200B;位于 Target 文件夹以外且手动上传到 Dynamic Media 的内容所在的位置。

   **电子邮件地址：**&#x200B;用于登录到 Dynamic Media Classic (Scene7) 的电子邮件地址。

   **密码：**&#x200B;用于登录到 Dynamic Media Classic (Scene7) 的密码。
1. 单击&#x200B;**[!UICONTROL 提交]**。
