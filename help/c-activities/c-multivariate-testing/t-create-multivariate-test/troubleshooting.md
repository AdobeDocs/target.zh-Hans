---
keywords: Mobile Web Experience Editor
description: 本主题包含了一些建议，可帮助解决在设计 MVT 测试时可能出现的一些问题。
title: 多变量测试故障诊断
feature: null
subtopic: Mobile Viewports
topic: Standard
uuid: 4de03e03-cbbd-4e8f-a1b9-19ba8b2e6951
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 100%

---


# 多变量测试故障诊断{#troubleshoot-multivariate-tests}

本主题包含了一些建议，可帮助解决在设计 MVT 测试时可能出现的一些问题。

* 编辑活动时，如果您使用的是基于 Analytics 的量度，而报表包并未加载（显示旋转器），请先将量度切换为 Target 量度，然后再重新切换为基于 Analytics 的量度。此时，报表包应该可以成功加载。
* 如果要对已在运行的测试进行更改，您可能需要重置该测试及其数据。

   Target 允许您编辑实时活动。请注意，对正在运行的活动进行编辑可能会重置测试，因此报表可能无法识别某些更改。

   稳妥的做法是进行一些小的更改，例如编辑现有的文本或 HTML 选件。

   可重置体验名称和报表的具体操作包括：

   * 添加新位置
   * 删除位置
   * 添加新选件或从现有位置删除选件

