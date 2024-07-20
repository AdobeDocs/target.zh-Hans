---
keywords: 多变量测试；故障诊断；故障诊断；MVT
description: 探索您在 [!DNL Adobe Target]中使用[!UICONTROL Multivariate Test] (MVT)活动时可能面临的潜在挑战以及建议的解决方案。
title: 如何为[!UICONTROL Multivariate Test]排除故障？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# [!UICONTROL Multivariate Test]活动疑难解答

本文包含了一些建议，用于解决在[!DNL Adobe Target]中设计[!UICONTROL Multivariate Test] (MVT)时可能出现的一些问题。

* 在编辑活动时，如果您使用基于[!DNL Analytics]的量度，但报表包未加载（显示旋转图），请将量度切换到[!DNL Target]个量度，然后再次切换到基于[!DNL Analytics]的量度。 此时，报表包应该可以成功加载。
* 如果对已在运行的测试进行更改，则可能会重置该测试及其数据。

  [!DNL Target]允许您编辑实时活动。 编辑正在进行的活动可能会重置测试，因此报表可能无法识别某些更改。

  稳妥的做法是进行一些小的更改，例如编辑现有的文本或 HTML 选件。

  重置体验名称和报表的特定操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件
