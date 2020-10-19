---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: 在Adobe TargetRecommendations，通过比较项目（实体）与用户用户档案中的值来动态过滤。
title: Adobe TargetRecommendations动态包含规则中用户档案属性匹配的过滤
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 5%

---


# ![PREMIUM用户档案](/help/assets/premium.png) 属性匹配

通过比较 [!DNL Adobe Target] 项目( [!DNL Recommendations] 实体)与用户用户档案中的值，动态筛选。

如  果要显示与访客用户档案中存储的值（如大小或喜爱的品牌）匹配的推荐，请使用用户档案属性匹配。

以下场景显示了如何使用 [!UICONTROL 用户档案属性匹配]:

* 一个卖眼镜的公司把访客最喜欢的框色储存成“胡桃”。 对于该特定访客，建议设置为仅返回与彩色“核桃木”匹配的眼镜框。
* 在用户档案浏览访客网站时，可以为的服装尺寸（例如，“小”、“中”或“大”）定义公司参数。 可以设置推荐以匹配该用户档案参数并返回仅针对用户首选服装尺寸的特定产品。

## 用户档案属性匹配示例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 用户档案属性匹配] 允许您仅推荐与访客用户档案中的属性匹配的项目，如以下示例所示。

### 推荐来自用户最喜爱品牌的项目

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. 在此规则下，如果访客正在查看特定品牌的运动裤，则只会显示与该用户最喜爱的品牌（存储在该访客配置文件的 `profile.favoritebrand` 中的值）相匹配的推荐。

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 将工作与求职者匹配

假设你试图把工作与求职者匹配。 你只想推荐那些和求职者在同一个城市的工作。

您可以使用包含规则将求职者的位置从其访客的用户档案与职务列表相匹配，如下例所示：

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 推荐与访客尺寸相符的衣服

让我们看一个例子，推荐与访客用户档案中设定的服装尺寸相符的服装。

产品页面在mbox `entity.size` 调用中发送（下图中的红色箭头）。

您可以创建 [用户档案脚本](/help/c-target/c-visitor-profile/profile-parameters.md) ，从访客访问的最后一页捕获访客的用户档案属性和值。

例如：

```
if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'small')) { return 'small';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'medium')) { return 'medium';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'large')) { return 'large';
}
```

用户档案脚本从名为 `entity.size` 的mbox中捕获该值 `target-global-mbox` ，并将其作为名为的用户档案属性( `user.size` 下图中的蓝色箭头)返回。

![大小mbox调用](/help/c-recommendations/c-algorithms/assets/size.png)

创建推荐条件时，单击添 [!UICONTROL 加筛选规则]，然后选择 [!UICONTROL 用户档案属性匹配]。

![用户档案属性匹配图](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

如果 `user.size` 用户档案已加载到 [!DNL Target]中，则当您设置规则以匹配在mbox调用()中传递到用户档案脚本名称()的值时，该会显示在下拉框中`size`进行匹配`user.size`。

然后，您可以选择“size”“equals”作为用户档案属性匹配的“user.size”中存储的值／文本。

在构建用户档案属性规则后，它们将过滤掉所有具有与访客存储的用户档案属性不匹配的属性的推荐。

### 根据大小推荐项目

有关用户档案属性匹配如何影响推荐的可视示例，请考虑一个销售粉丝的网站。

当访客单击此网站上的各种风扇图像时，每页都会根据图像中 `entity.size` 风扇的大小是小还是大来设置参数的值。

假定您创建了一个用户档案脚本，以跟踪和计算将值设 `entity.size` 置为“小”与“大”的次数。

如果访客返回主页，他／她将根据是否点击了更多小粉丝或大粉丝来看到筛选的推荐。

Recommendations的网站上有更多小粉丝：

![小粉丝推荐](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations的网站上有更多粉丝：

![大粉丝推荐](/help/c-recommendations/c-algorithms/assets/large-fans.png)