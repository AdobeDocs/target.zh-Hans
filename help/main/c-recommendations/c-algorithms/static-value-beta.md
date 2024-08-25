---
keywords: 包含规则；包含标准；推荐；促销活动；促销活动；动态筛选；静态；静态筛选
description: 了解如何使用Adobe [!DNL Target] Recommendations中的包含规则手动输入一个或多个要过滤的静态值。
title: 如何在Recommendations活动中按静态值筛选？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 52755b3a-ae6d-4fe4-8f1c-a660b038f2fb
source-git-commit: 22b0ba18efb736b291f9b7951acd9f706beedbe1
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 45%

---

# [!UICONTROL Static Filter]

使用[!DNL Adobe Target Recommendations]中的包含规则手动输入一个或多个要过滤的静态值。

例如，只推荐美国电影协会(MPA)评级为“G”或“PG”的内容。

您可以根据需要创建不限数量的包含规则。包含规则使用“与”运算符进行结合。所有规则都必须得到满足，才能在推荐中包含某个项目。

>[!NOTE]
>
>如果您熟悉 Target 17.6.1 版本（2017 年 6 月）之前的包含规则配置方式，那么您可能会注意到一些选项和运算符已经发生了变化。为了更加一致和直观，现在，只有那些适用于选定选项的运算符才会显示，而且部分运算符进行了重命名（“匹配”现在为“等于”）。此版本之前创建的所有已有排除规则均会迁移到新的结构中。您不需要重新调整结构。

## 推荐分级为G或PG的内容

要使用静态值创建包含规则，以仅推荐MPA评级为“G”或“PG”的内容（不包括“R”和“NC17”内容），您可以创建以下过滤规则：“电影评级等于任何g评级”和“电影评级等于任何pg评级”。
