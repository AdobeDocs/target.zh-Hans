---
keywords: 包含规则；包含条件；推荐；促销；动态过滤；静态过滤
description: 在Adobe TargetRecommendations，手动输入一个或多个静态值以使用包含规则进行筛选。
title: Adobe TargetRecommendations包含规则中的静态值筛选
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 46%

---


# ![PEF Tatic](/help/assets/premium.png) 过滤器

手动输入一个或多个静态值以使用[!DNL Adobe Target] [!DNL Recommendations]中的包含规则进行筛选。

例如，仅推荐具有“G”或“PG”等级的电影关联(MPA)内容。

您可以根据需要创建不限数量的包含规则。包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版本（2017 年 6 月）之前的包含规则配置方式，那么您可能会注意到一些选项和运算符已经发生了变化。为了更加一致和直观，现在，只有那些适用于选定选项的运算符才会显示，而且部分运算符进行了重命名（“匹配”现在为“等于”）。此版本之前创建的所有已有排除规则均会迁移到新的结构中。您不需要重新调整结构。

## 推荐评级为G或PG的内容

要创建包含规则，其中包含静态值可推荐MPA等级为“G”或“PG”（仅排除“R”和“NC17”内容）的内容，可创建以下过滤规则“电影等级为g-araded”和“电影等级为pg-araded”，如下所示。

![电影评级示例](/help/c-recommendations/c-algorithms/assets/movies.png)

