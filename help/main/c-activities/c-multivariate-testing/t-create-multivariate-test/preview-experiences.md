---
keywords: 多变量；MVT；预览；体验
description: 了解如何在Adobe中预览多变量测试(MVT)活动中的每个体验 [!DNL Target] 使用可视化体验编辑器(VEC)。
title: 如何预览多变量测试(MVT)体验
feature: Multivariate Tests
exl-id: 33c3ef24-eb58-437b-bae5-fdca25317c25
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 67%

---

# 预览多变量测试体验

因为 [!UICONTROL 多变量测试] 在 [!DNL Adobe Target] 比较页面上的多个体验，使用每个体验预览页面很有帮助。

1. 在可视化体验编辑器(VEC)中，单击 **[!UICONTROL 预览]**.

   此时将显示一个包含所有体验的列表。

   ![预览图像](assets/preview.png)

1. 单击列表中的某个体验，以查看该体验。

1. 要从多变量测试中排除一个或多个体验，请选择所需体验，然后单击&#x200B;**[!UICONTROL 排除]**。

   ![排除体验](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

   您可能会排除显示冲突变体的体验，或在美学上未实现平衡的体验。

   >[!NOTE]
   >
   >在创建多变量测试时，您可以从测试中排除 10% 以上的体验，但前提是您确认了随后必须使用离线报表进行分析的警告。

   默认情况下，多变量测试中包含所有体验。要包含之前已被排除的体验，请选择该排除的体验，然后单击&#x200B;**[!UICONTROL 包含]**。

单击&#x200B;**[!UICONTROL 退出预览模式]**，以返回到体验编辑器，从而进行更改；或单击&#x200B;**[!UICONTROL 继续]**&#x200B;以转到测试摘要。
