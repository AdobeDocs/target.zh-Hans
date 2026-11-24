---
keywords: 包含规则；包含标准；推荐；促销活动；促销活动；动态筛选；静态；静态筛选
description: 了解如何在Adobe [!DNL Target]推荐中手动输入一个或多个静态值以使用包含规则进行筛选。
title: 静态筛选
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
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
source-wordcount: '184'
ht-degree: 2%
---
# 静态筛选 {#static-filter}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何通过在[!DNL Adobe Target Recommendations]的包含规则中手动输入一个或多个静态值来筛选推荐。

>[!ENDSHADEBOX]

**[!UICONTROL 静态筛选器]**&#x200B;将推荐中的项目限制为与手动输入的静态值匹配的项目。 可以创建任意数量的包含规则。 由于包含规则使用AND运算符进行连接，因此必须满足所有规则才能将项目包含在推荐中。 有关包含规则的一般信息，请参阅[使用动态和静态包含规则](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)。

## 推荐分级为G或PG的内容

要仅推荐电影协会(MPA)评级为“G”或“PG”的内容（不包括“R”和“NC17”内容），请创建一个包含运算符“电影评级等于任何”的筛选规则，并输入“g评级”和“pg评级”的值。
