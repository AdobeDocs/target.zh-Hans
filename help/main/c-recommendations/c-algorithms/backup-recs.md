---
keywords: 推荐;备用
description: 了解如何在Adobe [!DNL Target Recommendations]中使用备份推荐。
title: 使用备用推荐
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 18%
---
# 使用备用推荐 {#backup-recommendations}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解备份推荐如何在[!DNL Adobe Target Recommendations]中填充设计的剩余版块。

>[!ENDSHADEBOX]

当推荐没有足够的推荐项来填充设计时，[!DNL Adobe Target]中的备份推荐功能会显示备份算法的结果而不是默认内容。 如果没有备份推荐，系统会向用户显示默认内容。

>[!NOTE]
>
>有关详细信息（包括说明使用&#x200B;**[!UICONTROL 部分设计渲染]**&#x200B;和&#x200B;**[!UICONTROL 同时或单独显示备份内容]**&#x200B;选项结果的矩阵），请参阅创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)的[备份内容部分。

备用推荐功能始终使用网站上查看次数最多的项目，来填充使用算法数据后剩余的任何空位。 例如，一个设计被配置为显示五个推荐项目，但算法拥有的数据仅够填充五个版块中的两个。 然后，备用推荐功能会将其他三个版块中的查看次数最多的项目填满。

备用推荐是从整个网站中前 500 个查看次数最多的产品中随机选择的。 备用推荐的数据时间段为一周。

前 500 个查看次数最多的结果是按顺序排列的，且按 20 个为一个分段进行拆分。 存储桶按顺序提供，但每个存储桶中的结果均是随机的，并会返回到页面，因此刷新页面的用户会看到新的随机结果。 如果来自集合和筛选规则的并集的结果集小于20，则从集合中随机选择项目。

此分段过程意味着备用推荐会按以下顺序显示：

1. 查看次数最多的20个项目，随机。
1. 接下来的20个最常查看的项目，是随机的。
1. 接下来的20个查看次数最多的项目，随机分配等。

如果不进行分段，则将显示查看次数最多的第499个项目，然后是查看次数最多的第200个项目，最后是查看次数最多的第380个项目，依此类推。 分段可确保首先推荐查看次数最多的项目。

如果项目被分组到收藏集中，则为每个标准生成的备用推荐也使用收藏集，因此备用推荐中仅包含收藏集中的项目。 由全局排除规则排除在外的任何项目均不会用作备用推荐。 推荐中的重复项会被删除。

默认启用备用推荐，并通过随机选择网站上最受欢迎的项目来填充设计中的额外版块。

使用备用建议通常是初始设置期间与实施团队讨论的一部分。 要在实施后更改备用推荐设置，请联系客户经理。

未启用&#x200B;**[!UICONTROL 部分设计渲染]**（请参阅[备份内容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)）并且无法填充设计时，将改为显示备份推荐（启用时）或默认内容。
