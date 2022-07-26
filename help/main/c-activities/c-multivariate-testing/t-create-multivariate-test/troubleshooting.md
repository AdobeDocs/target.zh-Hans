---
keywords: 多变量测试；故障诊断；MVT
description: 探索在Adobe Target中使用多变量测试(MVT)活动时可能遇到的潜在挑战，以及建议的解决方案。
title: 如何对多变量测试进行故障诊断？
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# 多变量测试故障诊断

本主题包含一些建议，用于解决在设计 [!UICONTROL 多变量] (MVT)测试 [!DNL Adobe Target].

* 在编辑活动时(如果使用 [!DNL Analytics]基于量度且报表包未加载（显示旋转图标），请将量度切换为 [!DNL Target] 量度，然后再次切换到 [!DNL Analytics]基于的量度。 此时，报表包应该可以成功加载。
* 如果对已运行的测试进行了更改，则可能会重置测试及其数据。

   [!DNL Target] 允许您编辑实时活动。 请注意，对正在运行的活动进行编辑可能会重置测试，因此报表可能无法识别某些更改。

   稳妥的做法是进行一些小的更改，例如编辑现有的文本或 HTML 选件。

   可重置体验名称和报表的具体操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件
