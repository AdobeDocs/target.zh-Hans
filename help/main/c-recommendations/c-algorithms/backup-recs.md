---
keywords: 推荐;备用
description: 了解如何在Adobe [!DNL Target] Recommendations中使用备份推荐。 没有足够推荐项目的推荐会显示备份算法的结果。
title: 如何在Recommendations中使用备用推荐？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
source-git-commit: 6e15b9b10e6a40c8efec06c45442b0f9894e648e
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 77%

---

# 使用备用推荐

如果您在[!DNL Adobe Target]中使用备份推荐功能，则任何推荐中没有足够推荐项的推荐都不会显示默认内容。 “推荐”将改为显示备用算法的结果。

如果您不使用备用推荐并且推荐中的项目不足以填满整个显示区域，则系统会向用户显示默认内容。

>[!NOTE]
>
>创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)主题的[内容部分中包括其他信息，其中包括一个矩阵，该矩阵说明了将[!UICONTROL Partial Design Rendering]和[!UICONTROL Show Backup Recommendations]选项一起使用或单独使用时将观察到的结果。

备用推荐功能始终采用网站查看最多的项目来填充算法数据被使用后的剩余位置。例如，您的模板配置为显示 5 个推荐项目，并且您使用的是“*购买相关性*”算法。然而，您仅有足够的数据来填充 5 个位置中的两个，那么备用推荐功能就会使用查看最多的项目来填充其它 3 个位置。

备用推荐是从整个网站中前 500 个查看次数最多的产品中随机选择的。备用推荐的数据时间段为一周。

前 500 个查看次数最多的结果是按顺序排列的，且按 20 个为一个分段进行拆分。这些分段按顺序提供，但是每个分段内的结果会按随机顺序返回到页面。如果用户刷新页面，则会向其显示新的随机排列结果。如果结合使用收藏集和筛选规则后获得的结果集少于 20 个，则会从收藏集中随机选择。

此分段过程意味着备用推荐会按以下顺序显示：

1. 显示前 20 个查看次数最多的项目（随机排列），然后
1. 显示排在后面的 20 个查看次数最多的项目（随机排列），然后
1. 显示再排在后面的 20 个查看次数最多的项目（随机排列），
1. 依此类推

如果不对备用推荐进行分段，则可能会按以下顺序显示项目：先显示查看次数排在第 499 位的项目，再显示查看次数排在第 200 位的项目，再显示查看次数排在第 380 位的项目，等等。分段过程可以确保优先推荐查看次数最多的项目。

>[!NOTE]
>
>如果将项目分组到不同的目录中，则针对推荐中的各个算法生成的备用推荐也使用相应目录，因此，只有目录中的项目会包含在备用推荐中。

由全局排除规则排除在外的任何项目均不会用作备用推荐。

备用推荐默认情况下处于启用状态，并且使用在网站上随机选择的最热门项目填充模板中多余的推荐位。

推荐中的重复项会被删除。

在初始设置阶段与实施团队进行相关讨论时，通常会涉及使用备用推荐。在实施之后，假如你你要更改备用推荐设置，请联系帐户管理员。

如果未启用“启用局部设计渲染”（请参阅[内容设置](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)），并且未显示模板，则会显示备份推荐或默认内容。
