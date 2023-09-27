---
keywords: 多变量测试；故障诊断；故障诊断；MVT
description: 探索您在使用过程中可能面临的潜在挑战 [!UICONTROL 多变量测试] (MVT)中的活动 [!DNL Adobe Target]，以及建议的解决方案。
title: 如何对进行故障排除 [!UICONTROL 多变量测试]？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 21%

---

# 疑难解答 [!UICONTROL 多变量测试] 活动

本文包含一些建议，可用于解决设计应用程序时可能出现的一些问题 [!UICONTROL 多变量测试] (MVT)输入 [!DNL Adobe Target].

* 编辑活动时，如果您使用 [!DNL Analytics]基于的量度且报表包未加载（旋转显示），请将量度切换到 [!DNL Target] 量度，然后再次切换到 [!DNL Analytics]基于的量度。 此时，报表包应该可以成功加载。
* 如果对已在运行的测试进行更改，则可能会重置该测试及其数据。

  [!DNL Target] 允许您编辑实时活动。 编辑正在进行的活动可能会重置测试，因此报表可能无法识别某些更改。

  稳妥的做法是进行一些小的更改，例如编辑现有的文本或 HTML 选件。

  重置体验名称和报表的特定操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件
