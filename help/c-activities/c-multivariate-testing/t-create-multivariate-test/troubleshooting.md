---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: 本主题包含解决在Adobe Target设计MVT测试时可能出现的一些问题的建议。
title: 多变量测试故障诊断
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 45%

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

