---
keywords: 多变量测试；疑难解答；mvt
description: 探索在Adobe Target使用Multivariate Test(MVT)活动时可能面临的潜在挑战以及建议的解决方案。
title: 如何对多变量测试进行疑难解答？
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---


# 多变量测试故障诊断

本主题包含有关解决在[!DNL Adobe Target]中设计[!UICONTROL Multivariate](MVT)测试时可能出现的一些问题的建议。

* 在编辑活动时，如果您使用基于[!DNL Analytics]的度量并且报表包未加载（微调框显示），请将度量切换为[!DNL Target]度量，然后再次切换为基于[!DNL Analytics]的度量。 此时，报表包应该可以成功加载。
* 如果对已运行的测试进行了更改，则可能会重置测试及其数据。

   [!DNL Target] 允许您编辑实时活动。请注意，对正在运行的活动进行编辑可能会重置测试，因此报表可能无法识别某些更改。

   稳妥的做法是进行一些小的更改，例如编辑现有的文本或 HTML 选件。

   可重置体验名称和报表的具体操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件

