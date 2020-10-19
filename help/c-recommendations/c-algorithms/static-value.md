---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: 在Adobe TargetRecommendations，手动输入一个或多个静态值以使用包含规则进行筛选。
title: Adobe TargetRecommendations包含规则中的静态值筛选
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 75%

---


# ![PREMIUM静态](/help/assets/premium.png) 滤镜

在Adobe TargetRecommendations，手动输入一个或多个静态值以使用包含规则进行筛选。

例如，只推荐美国电影协会 (MPAA) 评级为“G”或“PG”的内容。

可用的运算符：

* 等于
* 不等于
* 包含
* 不包含
* 始于
* 止于
* 值存在
* 值不存在
* 大于或等于
* 小于或等于

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版本（2017 年 6 月）之前的包含规则配置方式，那么您可能会注意到一些选项和运算符已经发生了变化。为了更加一致和直观，现在，只有那些适用于选定选项的运算符才会显示，而且部分运算符进行了重命名（“匹配”现在为“等于”）。此版本之前创建的所有已有排除规则均会迁移到新的结构中。您不需要重新调整结构。

您可以根据需要创建不限数量的包含规则。包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。