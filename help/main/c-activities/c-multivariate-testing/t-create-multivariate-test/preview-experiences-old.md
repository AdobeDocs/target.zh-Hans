---
keywords: 多变量测试；MVT；预览；体验
description: 了解如何使用[!UICONTROL 可视化体验编辑器] (VEC)预览[!DNL Adobe Target]中[!UICONTROL 多变量测试] (MVT)活动中的每个体验。
title: 如何预览[!UICONTROL 多变量测试] (MVT)的体验？
feature: Multivariate Tests
exl-id: 33c3ef24-eb58-437b-bae5-fdca25317c25
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 29%
---
# 预览[!UICONTROL 多变量测试]的体验

由于[!DNL Adobe Target]中的[!UICONTROL 多变量测试]比较页面上的多个体验，预览每个体验中的页面将会很有帮助。

1. 在[!UICONTROL 可视化体验编辑器] (VEC)中，单击&#x200B;**[!UICONTROL 预览]**。

   此时将显示一个包含所有体验的列表。

   ![预览图像](assets/preview.png)

1. 单击列表中的某个体验，以查看该体验。

1. 要从多变量测试中排除一个或多个体验，请选择所需体验，然后单击“**[!UICONTROL 排除]**”。

   ![排除体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

   您可能会排除显示冲突变体的体验，或在美学上未实现平衡的体验。

   >[!NOTE]
   >
   >在创建多变量测试时，您可以从测试中排除10%以上的体验，但前提是您确认了随后必须使用离线报表进行分析的警告。

   默认情况下，多变量测试中包含所有体验。 要包含之前已被排除的体验，请选择该排除的体验，然后单击&#x200B;**[!UICONTROL 包含]**。

1. 单击&#x200B;**[!UICONTROL 退出预览模式]**&#x200B;以返回到[!UICONTROL 可视化体验编辑器]以进行更改，或单击&#x200B;**[!UICONTROL 继续]**&#x200B;以转到测试摘要。
