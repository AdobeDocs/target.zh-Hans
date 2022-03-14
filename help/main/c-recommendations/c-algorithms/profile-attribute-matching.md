---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；配置文件属性匹配
description: 了解如何在Adobe中动态筛选 [!DNL Target] Recommendations(通过比较项目（实体）与用户配置文件中的值)。
title: 如何在Recommendations活动中按配置文件属性匹配进行过滤？
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 6%

---

# ![PREMIUM](/help/main/assets/premium.png) 配置文件属性匹配

动态筛选 [!DNL Adobe Target] [!DNL Recommendations] 通过比较项目（实体）与用户配置文件中的值。

使用 [!UICONTROL 配置文件属性匹配] 当您想要显示与访客配置文件中存储的值（如大小或最喜爱的品牌）匹配的推荐时。

>[!NOTE]
>
>的 [创建和使用包含规则的过程](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) 与用例和示例一样，标准和促销活动的用例和示例也类似。

以下方案显示了如何使用 [!UICONTROL 配置文件属性匹配]:

* 一家销售眼镜的公司将访客最喜爱的框架颜色存储为“核桃”。 对于该特定访客，推荐设置为仅返回与颜色“核桃”匹配的眼镜框。
* 可以为访客在公司网站中浏览时的服装尺寸（例如，小、中或大）定义配置文件参数。 推荐可设置为与配置文件参数匹配，并返回仅特定于用户首选服装尺寸的产品。

## 配置文件属性匹配示例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 配置文件属性匹配] 允许您仅推荐与访客配置文件中的属性匹配的项目，如以下示例所示。

### 推荐用户最喜爱品牌中的项目

例如，您可以使用 [!UICONTROL 配置文件属性匹配] 用于创建仅在品牌等于中存储的值或文本时推荐项目的规则 `profile.favoritebrand`. 在此规则下，如果访客正在查看特定品牌的运动裤，则只会显示与该用户最喜爱的品牌（存储在该访客配置文件的 `profile.favoritebrand` 中的值）相匹配的推荐。

![最喜爱的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将工作与求职者匹配

假设你试图将工作与求职者匹配。 您只想推荐与求职者位于同一城市的工作。

您可以使用包含规则将求职者的位置从其访客的配置文件匹配到职务列表，如以下示例所示：

![用户的城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根据大小推荐项目

有关配置文件属性匹配如何影响推荐的直观示例，请考虑一个销售电风扇的网站。

当访客单击此网站上的各种粉丝图像时，每个页面都会设置 `entity.size` 参数，此参数取决于图像中风扇的大小是小还是大。

假设您创建了一个配置文件脚本来跟踪和计算 `entity.size` 设置为“小”与“大”。

如果访客随后返回主页，则他或她将根据点击的粉丝数量是小粉丝还是大粉丝数量，看到过滤的推荐。

Recommendations基于在网站上查看更多小粉丝的信息：

![小粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations基于在网站上查看更多大粉丝的信息：

![大粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
