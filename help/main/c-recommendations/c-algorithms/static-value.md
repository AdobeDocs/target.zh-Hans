---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；静态筛选
description: 了解如何在Adobe中使用包含规则手动输入一个或多个静态值以进行筛选 [!DNL Target] Recommendations。
title: 如何按Recommendations活动中的静态值进行过滤？
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 46%

---

# ![PREMIUM](/help/main/assets/premium.png) 静态筛选器

手动输入一个或多个静态值，以使用 [!DNL Adobe Target] [!DNL Recommendations].

例如，只推荐评级为“G”或“PG”的电影关联(MPA)内容。

您可以根据需要创建不限数量的包含规则。包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版本（2017 年 6 月）之前的包含规则配置方式，那么您可能会注意到一些选项和运算符已经发生了变化。为了更加一致和直观，现在，只有那些适用于选定选项的运算符才会显示，而且部分运算符进行了重命名（“匹配”现在为“等于”）。此版本之前创建的所有已有排除规则均会迁移到新的结构中。您不需要重新调整结构。

## 推荐评级为G或PG的内容

要创建包含规则（包含静态值）以推荐MPA评级为“G”或“PG”（仅排除“R”和“NC17”内容）的内容，可以创建以下过滤规则“电影评级等于g评级”和“电影评级等于pg评级”，如下所示。

![影片评级示例](/help/main/c-recommendations/c-algorithms/assets/movies.png)
