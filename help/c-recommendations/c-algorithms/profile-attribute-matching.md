---
keywords: 包含规则；包含条件；推荐；促销；动态过滤；动态；用户档案属性匹配
description: 了解如何通过比较项目（实体）与用户用户档案中的值，在Adobe [!DNL Target] Recommendations中动态筛选。
title: 如何在Recommendations活动中按用户档案属性匹配进行筛选？
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 7%

---

# ![PREMIUMProfile属](/help/assets/premium.png) 性匹配

通过比较项目（实体）与用户用户档案中的值，在[!DNL Adobe Target] [!DNL Recommendations]中动态筛选。

如果要显示与访客用户档案中存储的值（如大小或喜爱的品牌）匹配的推荐，请使用[!UICONTROL 用户档案属性匹配]。

>[!NOTE]
>
>标准和促销的[创建和使用包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)的过程与使用案例和示例类似。

以下场景显示了如何使用[!UICONTROL 用户档案属性匹配]:

* 销售眼镜的公司将访客最喜欢的边框颜色存储为“核桃”。 对于该特定访客，建议设置为仅返回与彩色“核桃”匹配的眼镜框。
* 在用户档案浏览公司网站时，可以为访客的服装尺寸（例如，“小”、“中”或“大”）定义参数。 可以设置推荐以匹配该用户档案参数并返回仅针对用户首选服装尺寸的特定产品。

## 用户档案属性匹配示例{#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 用户档案属] 性匹配允许您仅推荐与访客用户档案中的属性匹配的项目，如以下示例中所示。

### 推荐用户最喜爱品牌中的项目

例如，您可以使用[!UICONTROL 用户档案属性匹配]选项创建规则，该规则仅建议品牌等于存储在`profile.favoritebrand`中的值或文本的项目。 在此规则下，如果访客正在查看特定品牌的运动裤，则只会显示与该用户最喜爱的品牌（存储在该访客配置文件的 `profile.favoritebrand` 中的值）相匹配的推荐。

![最喜爱的品牌](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将工作与求职者匹配

假设你试图将工作与求职者匹配。 你只想推荐那些和求职者在同一个城市的工作。

您可以使用包含规则将求职者的位置从其访客的用户档案匹配到职务列表，如下例所示：

![用户城市](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根据大小推荐项目

有关用户档案属性匹配如何影响推荐的可视示例，请考虑一个销售电扇的网站。

当访客单击此网站上的风扇的各种图像时，每个页面都会根据图像中风扇的大小是小还是大来设置`entity.size`参数的值。

假设您创建了一个用户档案脚本来跟踪和计算将`entity.size`值设置为小与大的次数。

如果访客随后返回主页，他或她将根据是否点击了更多小粉丝或大粉丝来查看筛选的推荐。

Recommendations基于在网站上查看更多小粉丝：

![小粉丝推荐](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations基于在网站上查看更多粉丝：

![大粉丝推荐](/help/c-recommendations/c-algorithms/assets/large-fans.png)
