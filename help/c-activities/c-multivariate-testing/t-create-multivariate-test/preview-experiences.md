---
keywords: multivariate;mvt;预览；体验
description: 了解如何使用Visual Experience Composer(VEC)在Adobe [!DNL Target] 的“Multivariate Test(MVT)”活动中预览每个体验。
title: 如何预览多变量测试(MVT)的体验
feature: Multivariate Tests
exl-id: 33c3ef24-eb58-437b-bae5-fdca25317c25
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 67%

---

# 预览多变量测试体验

由于[!DNL Adobe Target]中的[!UICONTROL  Multivariate Test]比较了页面上的多个体验，因此将页面与每个体验预览非常有帮助。

1. 在Visual Experience Composer(VEC)中，单击&#x200B;**[!UICONTROL 预览]**。

   此时将显示一个包含所有体验的列表。

   ![](assets/preview.png)

1. 单击列表中的某个体验，以查看该体验。

1. 要从多变量测试中排除一个或多个体验，请选择所需体验，然后单击&#x200B;**[!UICONTROL 排除]**。

   ![排除体验](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

   您可能会排除显示冲突变体的体验，或在美学上未实现平衡的体验。

   >[!NOTE]
   >
   >在创建多变量测试时，您可以从测试中排除 10% 以上的体验，但前提是您确认了随后必须使用离线报表进行分析的警告。

   默认情况下，多变量测试中包含所有体验。要包含之前已被排除的体验，请选择该排除的体验，然后单击&#x200B;**[!UICONTROL 包含]**。

单击&#x200B;**[!UICONTROL 退出预览模式]**，以返回到体验编辑器，从而进行更改；或单击&#x200B;**[!UICONTROL 继续]**&#x200B;以转到测试摘要。
