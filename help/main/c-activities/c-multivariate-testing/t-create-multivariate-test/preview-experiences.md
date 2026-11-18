---
keywords: 多变量测试；MVT；预览；体验
description: 了解如何使用[!UICONTROL 可视化体验编辑器] (VEC)预览[!DNL Adobe Target]中[!UICONTROL 多变量测试] (MVT)活动中的每个体验。
title: 如何预览[!UICONTROL 多变量测试] (MVT)的体验？
feature: Multivariate Tests
exl-id: 33c3ef24-eb58-437b-bae5-fdca25317c25
TQID: 'https://experienceleague.adobe.com/IswPThtgoGod4lcCbHWbsSp6-cTzhI6hi0CvTZ1al9A'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%
---
# 预览[!UICONTROL 多变量测试]的体验 {#preview-mvt-experiences}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中预览&#x200B;**[!UICONTROL 多变量测试]**&#x200B;的每个体验，以及如何排除或包含体验。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 多变量测试]** (MVT)比较页面上的多个体验，因此预览每个体验中的页面很有帮助。 预览会显示选件在每个体验中的合并方式，以便您决定在测试开始之前是否排除体验。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中，单击&#x200B;**[!UICONTROL 预览]**，然后单击&#x200B;**[!UICONTROL 显示体验]**&#x200B;图标（![显示体验图标](/help/main/assets/icons/WebPages.svg)）以显示左框架中所有体验的列表。

   ![更改图像选件菜单](../assets/multivariate-5.png)

1. 单击列表中的特定体验，以查看该体验。

1. （可选）要排除或包含体验，请单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）以显示&#x200B;**[!UICONTROL 管理内容]**&#x200B;对话框。

1. 您可能会选择排除显示冲突变体的体验，或在美学上未实现平衡的体验。 然后执行以下操作之一：

   * 要排除一个体验，请单击该体验旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL 排除]**。
   * 要排除多个体验，请选中体验对应的复选框，然后单击&#x200B;**[!UICONTROL 排除]**。
   * 要包含已排除的多个体验，请选中体验对应的复选框，然后单击“**[!UICONTROL 包含]**”。

>[!NOTE]
>
>在创建多变量测试时，您可以从测试中排除10%以上的体验，但前提是您确认了随后必须使用离线报表进行分析的警告。
