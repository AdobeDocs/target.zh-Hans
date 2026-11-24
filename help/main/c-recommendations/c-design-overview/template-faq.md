---
keywords: 推荐;常见问题解答;FAQ
description: 关于[!DNL Target Recommendations]设计的常见问题解答(FAQ)及其答案。
title: 设计常见问题解答
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
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
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 10%
---
# 设计常见问题解答 {#design-faq}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找有关[!DNL Adobe Target] [!DNL Recommendations]设计的常见问题解答。

>[!ENDSHADEBOX]

+++ 推荐项目的价格如何在小数点的右侧同时显示两位数？

默认情况下，设计中返回的数值（如`entity.value`）不会在小数点之后显示任何尾随零。 例如，如果某个项目的成本为$35.00，则`entity.value`等于35，并且页面上只显示35，而不是$35.00。

有两种方法可用于解决此问题：

* Velocity脚本或JavaScript可以对返回的值应用格式。

* 项目的价格可以传递到两个单独的实体属性中。 第一个属性 `entity.value` 可用于进行数值比较（例如价格比较规则）。 第二个应该是自定义属性，例如`entity.displayValue`，它将实体的值存储为字符串以便进行正确渲染。

  例如：

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ 为何在使用$entity1.categoryId时，设计中不显示该类别？

类别ID无法在设计中显示。 由于可以存储多个类别，所以系统不知道要显示哪个类别。

+++

+++ 如何更改设计才能即时更新？

对当前正在使用的设计进行更改后，需要等待一段时间才会更新。 要立即更改设计，请创建新设计，在活动中选择它，然后保存推荐。

+++

+++ 如何在设计中显示关键信息，例如关键产品的类别？

`$key`参数捕获关键产品的大部分信息以便在设计中显示。 例如，要显示关键产品的缩略图，请使用`$key.thumbnailURL`。

+++

+++ 使用哪个版本的 Velocity？

版本1.7，未添加其他工具或库。 仅提供基本的 Velocity 功能。

+++

+++ 如何将现有实体值替换为空白，例如，当促销活动结束时必须清除项目的entity.message时？

发送JavaScript不间断空格似乎可以做到这一点。 开发人员发送`\u00A0`作为值，例如`entity.message=\u00A0`。 当不存在任何值时使用该值作为默认值，而不是空值，也可以考虑。

+++

+++ 能否在[!DNL Recommendations]设计中使用配置文件脚本？

是. 要在[!DNL Recommendations]设计中使用配置文件脚本，请将该名称包装在`\${...}`中。 例如，如果配置文件脚本名为`user.basket`，请在设计中将其引用为`\${user.basket}`。 反斜杠表示配置文件脚本不由Velocity渲染，因此不能对Velocity模板中的配置文件脚本执行任何操作。 该值直接打印在页面上。

+++
