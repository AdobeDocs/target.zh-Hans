---
description: Target Standard可与Adobe Dynamic Media Classic(以前称为Scene7)集成，在内容库中提供数字资产管理(DAM)。
seo-description: Target Standard可与Adobe Dynamic Media Classic(以前称为Scene7)集成，在内容库中提供数字资产管理(DAM)。
seo-title: Dynamic Media经典集成
solution: Target
subtopic: 入门指南
title: Dynamic Media经典集成
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic integration{#scene-settings}

Target Standard可与Adobe Dynamic Media Classic(以前称为Scene7)集成，在内容库中提供数字资产管理(DAM)。

>[!NOTE]
>
>将Target与Dynamic Media Classic集成可提供上传到Adobe Experience Cloud资产文件夹的资产(作为活动的一部分)。此集成不支持访问在Dynamic Media经典中上传的所有资产，以便在Target活动中交付。

如果您已经有了Dynamic Media帐户，则可以提供现有凭据。如果您没有帐户，则可以请求受限使用Dynamic Media经典帐户，而不需要Adobe代表支付额外费用。可以使用此帐户在 Target 中执行一些限定的操作。当客户的工作流需要使用图像交换功能时，他们可以使用此服务。

如果未配置此设置，活动创建工作流中的“交换图像”选件选项将不可用。配置此设置后，交换/更改图像选件的选项在[可视化体验编辑器 (VEC) 和基于表单的体验编辑器](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中均可用。随后，您可以使用图像选件，其中包含从 Adobe Experience Cloud 上传的以供在 Target 活动中使用的图像。

在活动创建过程中，如果您想要在选件或自定义代码中直接引用公共图像 URL，则应当将图像部署到您自己的 Web 服务器并在代码中使用您自己的 URL。无法获取已上传到 Experience Cloud 的图像的已发布 URL，以将其直接用在使用 Adobe Target 的定位工作流中或这些工作流之外。按照合同规定，不允许使用此功能。

请注意，Dynamic Media中图象的存储URL和最终发布URL是不同的，且用户不得使用图像存储链接创建选件，因为在这种情况下，交付将不起作用。所有人都必须按照帮助文档中的相关说明来使用图像选件功能。

要与Dynamic Media Classic(Scene7)集成，您需要指定一些以下信息。

1. 单击 **[!UICONTROL 设置]** &gt; **[!UICONTROL Scene7 设置]**。
1. 指定以下Dynamic Media经典帐户信息：

   **地区：** Dynamic Media帐户的区域：北美、欧洲或亚洲。

   **Adhoc文件夹：** 位于目标文件夹之外并手动上传到Dynamic Media的内容的位置。

   **电子邮件地址：** 用于登录Dynamic Media Classic(Scene7)的电子邮件地址。

   **密码：** 用于登录到Dynamic Media Classic(Scene7)的口令。
1. 单击 **[!UICONTROL 提交]**。
