---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: 在Adobe TargetRecommendations，通过比较项目（实体）与用户用户档案中的值来动态过滤。
title: Adobe TargetRecommendations动态包含规则中用户档案属性匹配的过滤
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 7%

---


# ![PREMIUMProfile属](/help/assets/premium.png) 性匹配

通过比较项目（实体）与用户用户档案中的值，在[!DNL Adobe Target] [!DNL Recommendations]中动态筛选。

如果要显示与用户档案用户档案中存储的值（如大小或喜爱的品牌）匹配的推荐，请使用[!UICONTROL 访客属性匹配]。

>[!NOTE]
>
>用于创建和使用包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)作为标准和促销的[过程与用例和示例类似。

以下场景显示如何使用[!UICONTROL 用户档案属性匹配]:

* 一个卖眼镜的公司把访客最喜欢的框色储存成“胡桃”。 对于该特定访客，建议设置为仅返回与彩色“核桃木”匹配的眼镜框。
* 在用户档案浏览访客网站时，可以为的服装尺寸（例如，“小”、“中”或“大”）定义公司参数。 可以设置推荐以匹配该用户档案参数并返回仅针对用户首选服装尺寸的特定产品。

## 用户档案属性匹配示例{#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 用户档案属] 性匹配允许您仅推荐与访客用户档案中的属性匹配的项目，如以下示例所示。

### 推荐来自用户最喜爱品牌的项目

例如，可以使用[!UICONTROL 用户档案属性匹配]选项创建规则，该规则建议仅在品牌等于存储在`profile.favoritebrand`中的值或文本的情况下使用项目。 在此规则下，如果访客正在查看特定品牌的运动裤，则只会显示与该用户最喜爱的品牌（存储在该访客配置文件的 `profile.favoritebrand` 中的值）相匹配的推荐。

![最喜爱的品牌](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将工作与求职者匹配

假设你试图把工作与求职者匹配。 你只想推荐那些和求职者在同一个城市的工作。

您可以使用包含规则将求职者的位置从其访客的用户档案与职务列表相匹配，如下例所示：

![用户城市](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根据大小推荐项目

有关用户档案属性匹配如何影响推荐的可视示例，请考虑销售电扇的网站。

当访客单击此网站上的风扇的各种图像时，每页都根据图像中风扇的大小是小还是大来设置`entity.size`参数的值。

假定您创建了一个用户档案脚本来跟踪和计算`entity.size`值设置为小与大的次数。

如果访客返回主页，他／她将根据是否点击了更多小粉丝或大粉丝来看到筛选的推荐。

Recommendations的网站上有更多小粉丝：

![小粉丝推荐](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations的网站上有更多粉丝：

![大粉丝推荐](/help/c-recommendations/c-algorithms/assets/large-fans.png)