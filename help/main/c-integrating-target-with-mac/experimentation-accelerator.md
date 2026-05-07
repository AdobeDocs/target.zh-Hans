---
keywords: experimentation accelerator；target workspace；沙盒分配；adobe journey optimizer；集成
description: 了解如何将Adobe Target工作区映射到Experimentation Accelerator沙盒，以便团队可以在一处查看Adobe Target和Adobe Journey Optimizer中的实验。
title: 如何将 [!DNL Target] 与Experimentation Accelerator集成？
feature: Integrations
source-git-commit: e6c1d1799a27130524b1965acaffc07e1d08377f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# 将[!DNL Target]与Experimentation Accelerator集成

Experimentation Accelerator帮助管理员管理如何在应用程序中组织和显示[!DNL Adobe Target]工作区活动。 通过将每个[!DNL Target]工作区映射到适当的Experimentation Accelerator沙盒，团队可以在一处查看[!DNL Adobe Target]和[!DNL Adobe Journey Optimizer]中的试验。

➡️ [了解有关Adobe Experimentation Accelerator的更多信息](https://experienceleague.adobe.com/zh-hans/docs/experimentation-accelerator/using/overview)

## 开始之前

在设置沙盒分配之前，请确认您具有所需的权限。 要在Experimentation Accelerator中访问&#x200B;**[!UICONTROL Administration]**，您必须具有&#x200B;**[!UICONTROL Manage configuration]**&#x200B;权限。

只有在同时满足以下两个条件时，用户才能将[!DNL Target]工作区分配给沙盒：

* 用户在Experimentation Accelerator中具有&#x200B;**[!UICONTROL Manage configuration]**&#x200B;权限。
* 用户是[!DNL Target]产品管理员。

## 为[!DNL Target]工作区设置沙盒分配

在分配工作区之前，请注意，[!DNL Target]工作区只能分配给一个沙盒，以防止同一测试出现重复条目。

要选择每个[!DNL Target]工作区出现在哪个沙盒中：

1. 在Experimentation Accelerator中，打开&#x200B;**[!UICONTROL Administration]**。

   ![](assets/experimentation-1.png)

1. 查看当前[!DNL Target]工作区到沙盒分配的表。

   ![](assets/experimentation-2.png)

1. 单击 **[!UICONTROL Edit]**。

   ![](assets/experimentation-3.png)

1. 对于每个沙盒，分配相应的[!DNL Target]工作区。

   ![](assets/experimentation-4.png)

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;以应用更改。

为[!DNL Target]工作区创建初始连接后，留出最多30分钟时间，以便更新在整个系统中传播。
