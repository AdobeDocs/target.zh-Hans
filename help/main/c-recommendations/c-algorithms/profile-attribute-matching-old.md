---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；配置文件属性匹配
description: 了解如何在Adobe [!DNL Target] Recommendations中通过比较项目（实体）与用户配置文件中的值来进行动态筛选。
title: 如何在Recommendations活动中按配置文件属性匹配进行筛选？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 7%

---

# 配置文件属性匹配

通过比较项目（实体）与用户配置文件中的值在[!DNL Adobe Target] [!DNL Recommendations]中动态筛选。

当您想要显示与访客配置文件中存储的某个值（如大小或最喜爱的品牌）匹配的推荐时，请使用[!UICONTROL Profile Attribute Matching]。

>[!NOTE]
>
>为标准和促销活动创建和使用包含规则[&#128279;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的过程与用例和示例类似。

以下情形显示如何使用[!UICONTROL Profile Attribute Matching]：

* 一家销售眼镜的公司将访客最喜欢的框架颜色存储为“核桃”。 对于该特定访客，推荐设置为仅返回颜色与“核桃”匹配的眼镜框。
* 可以为访客在浏览您公司的网站时的服装尺寸(例如，小号、Medium或大号)定义配置文件参数。 可以设置推荐以匹配该配置文件参数，并仅返回特定于用户首选服装尺寸的产品。

## 配置文件属性匹配示例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching]允许您仅推荐与访客配置文件中某个属性匹配的项目，如以下示例所示。

### 推荐用户最喜爱的品牌中的项目

例如，您可以使用[!UICONTROL Profile Attribute Matching]选项创建一个规则，仅在品牌等于`profile.favoritebrand`中存储的值或文本时推荐项目。 在此规则下，如果访客正在查看特定品牌的运动裤，则只会显示与该用户最喜爱的品牌（存储在该访客轮廓的 `profile.favoritebrand` 中的值）相匹配的推荐。

![最喜爱的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将职位与求职者匹配

假设你试图将工作岗位与求职者相匹配。 您只想推荐与求职者在同一城市的工作。

您可以使用包含规则将求职者的位置从其访客的配置文件匹配到工作列表，如以下示例所示：

![用户的城市](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根据大小推荐项目

有关配置文件属性匹配如何影响推荐的可视示例，请考虑销售电风扇的网站。

当访客单击此网站上风扇的各种图像时，每个页面会根据图像中风扇的大小是小还是大来设置`entity.size`参数的值。

假设您创建了一个配置文件脚本来跟踪和计数`entity.size`的值设为小与大的次数。

如果访客随后返回主页，则将根据点击的粉丝数量是较小还是较大而查看过滤推荐。

Recommendations基于在网站上查看更多小粉丝的信息：

![小粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations基于在网站上查看更多大粉丝的数据：

![大粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
