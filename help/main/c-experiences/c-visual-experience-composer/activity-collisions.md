---
keywords: 定位；冲突；冲突
description: 通过在Adobe Target中正确配置活动来防止同一页面上的内容投放冲突。
title: 如何避免活动冲突？
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 5c963e97dae11326396a5c1c5e32d19f4d463c74
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 46%

---

# 活动冲突

[!UICONTROL Collisions]中[!UICONTROL Activity Overview]页面上的[!DNL Adobe Target]选项卡列出了您网站上的活动冲突。

当多个活动被设置为将内容发布到同一页面时，就会发生活动冲突。如果发生活动冲突，您可能无法在页面上看到预期的内容。

“[!UICONTROL Collisions]”选项卡在活动概述页面上可用，并且可以通知您活动是否包含潜在冲突。

要访问[!UICONTROL Collisions]选项卡，请单击&#x200B;**[!UICONTROL Activities]** >从列表中单击所需的活动>然后单击左边栏中的&#x200B;**[!UICONTROL Collisions]**。

同一 URL 上的所有活动均会列出，而不考虑每个活动中的任何受众定位。打开该选项卡后，会显示可能发生冲突的活动列表。如果冲突改变了预期体验，则需编辑相应的活动。

[!UICONTROL Collisions]列表可帮助您：

* 在设置新活动之前确认页面上是否已有测试在运行
* 在未显示预期内容时，对活动进行故障诊断

[!UICONTROL Collisions]列表显示每个[!DNL Target]方案，其中使用mbox并使用相同的URL。 对于每个潜在冲突，此列表都会显示活动URL、发生冲突的mbox名称以及任何符合这两个条件的活动。 如果存在多个 mbox，则会列出每个 mbox。

此列表还会显示每个潜在冲突的状态和优先级，以及其他相关信息。您可以使用状态和优先级来帮助确定冲突发生的可能性。以两个可能相互冲突的活动为例。 如果一个活动当前未处于活动状态，则不会发生冲突。 仅当非活动处于活动状态时，才可能出现冲突。 如果具有相同优先级和相同受众的两个实时活动之间存在潜在冲突，则会发生冲突。 您可以更改优先级或状态来阻止冲突发生。

如果活动的受众不相同，活动之间仍可能存在冲突，因为某个特定访客可能属于多个受众。
