---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；配置文件属性匹配
description: 了解如何通过比较项目（实体）与用户配置文件中的值在[!DNL Target Recommendations]中动态筛选。
title: 轮廓属性匹配
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: 'https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 5%
---
# 轮廓属性匹配 {#profile-attribute-matching}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何通过比较项目（实体）与访客配置文件中的值在[!DNL Adobe Target Recommendations]中动态筛选推荐。

>[!ENDSHADEBOX]

使用&#x200B;**[!UICONTROL 配置文件属性匹配]**&#x200B;显示与访客配置文件中存储的值匹配的推荐，如大小或最喜爱的品牌。 如用例和示例所述，针对标准和促销活动创建和使用包含规则的过程类似。 有关详细信息，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

以下情形显示如何使用&#x200B;**[!UICONTROL 配置文件属性匹配]**：

* 一家销售眼镜的公司将访客最喜欢的框架颜色存储为“核桃”。 对于该访客，推荐设置为仅返回颜色与“核桃”匹配的眼镜框。
* 当访客浏览公司网站时，可以为该访客的服装尺寸（例如，小、Medium或大）定义配置文件参数。 可以设置推荐以匹配该配置文件参数，并仅返回访客首选服装尺寸中的产品。

## 配置文件属性匹配示例

**[!UICONTROL 配置文件属性匹配]**&#x200B;只建议与访客配置文件中的属性匹配的项目，如以下示例所示。

### 推荐用户最喜爱的品牌中的项目

**[!UICONTROL 配置文件属性匹配]**&#x200B;选项可以创建规则，仅在品牌等于`profile.favoritebrand`中存储的值或文本时推荐项目。 在此规则下，如果访客正在查看特定品牌的运动裤，则仅显示与该访客最喜爱的品牌相匹配的推荐（该访客的配置文件中存储在`profile.favoritebrand`中的值）。

![最喜爱的品牌](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将职位与求职者匹配

为了将就业岗位与求职者相匹配，只推荐与求职者位于同一城市的工作。 包含规则可以将求职者从访客个人资料的位置与工作列表相匹配，如以下示例所示：

![用户的城市](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 根据大小推荐项目

以下示例显示了配置文件属性匹配如何影响销售电风扇的网站上的推荐。

当访客单击此网站上风扇的各种图像时，每个页面会根据图像中风扇的大小是小还是大来设置`entity.size`参数的值。 配置文件脚本跟踪和计算`entity.size`的值设置为小或大的次数。

如果访客随后返回主页，则会根据点击的小粉丝还是大粉丝来显示过滤的推荐。

基于在网站上查看更多小粉丝的建议：

![小粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

基于在网站上查看更多大粉丝的建议：

![大粉丝推荐](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
