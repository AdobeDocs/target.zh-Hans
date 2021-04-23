---
keywords: 包含规则；包含条件；推荐；促销；动态过滤；静态过滤
description: 了解如何在Adobe [!DNL Target] Recommendations中手动输入一个或多个静态值以使用包含规则进行筛选。
title: 如何按Recommendations活动中的静态值进行筛选？
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 46%

---

# ![溢](/help/assets/premium.png) 价滤波器

手动输入一个或多个静态值以使用[!DNL Adobe Target] [!DNL Recommendations]中的包含规则进行筛选。

例如，仅推荐具有“G”或“PG”等级的动画图片关联(MPA)内容。

您可以根据需要创建不限数量的包含规则。包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版本（2017 年 6 月）之前的包含规则配置方式，那么您可能会注意到一些选项和运算符已经发生了变化。为了更加一致和直观，现在，只有那些适用于选定选项的运算符才会显示，而且部分运算符进行了重命名（“匹配”现在为“等于”）。此版本之前创建的所有已有排除规则均会迁移到新的结构中。您不需要重新调整结构。

## 推荐评级为G或PG的内容

要创建包含规则(其静态值为推荐仅MPA等级为“G”或“PG”（不包括“R”和“NC17”内容）的内容)，可创建以下过滤规则“电影等级为g等级”和“电影等级为pg等级”，如下所示。

![movie-rating示例](/help/c-recommendations/c-algorithms/assets/movies.png)
