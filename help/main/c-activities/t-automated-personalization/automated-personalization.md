---
keywords: 自动个性化；AP；受众；组合；随机林；多臂老虎机；汤普森采样；ML；机器学习
description: 了解如何在Adobe中使用Automated Personalization (AP)活动 [!DNL Target] 高级机器学习将不同的选件变体与每位访客相配。
title: 什么是Automated Personalization (AP)活动？
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 81%

---

# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization （美联社）

[!UICONTROL Automated Personalization] (AP)中的活动 [!DNL Adobe Target] 可组合选件或消息，并使用先进的机器学习技术，根据每位访客的个人客户配置文件将不同的选件变体与其匹配，以便个性化内容并促进提升。

>[!NOTE]
>
>[!UICONTROL 自动个性化]作为 [!DNL Target Premium] 解决方案的一部分提供。在没有 [!DNL Target Premium] 许可证的情况下，不会包含在 [!DNL Target Standard] 中。如果您有 [!DNL Target Premium] 许可证，在 [!DNL Adobe Experience Cloud] 中，[!DNL Target Premium] 信息卡会替换 [!DNL Target Standard] 信息卡。

与[!UICONTROL 自动定位]类似，[!UICONTROL 自动个性化]也使用随机林算法（一种领先的数据科学组合方法）作为其主要个性化算法，来确定向访客显示的最佳体验。[!UICONTROL 自动个性化在测试的探索阶段可能很有意义。]当定位各种不同的访客时，它也有助于机器学习确定最有效的内容。随着时间的推移，该算法会学习预测最有效的内容并显示最有可能实现您的目标的内容。

查找有关以下内容的更多信息： [!UICONTROL Automated Personalization] 不同于 [!UICONTROL 自动定位]，请参见 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

营销人员可在他们的网站上实施一个文件，使他们能够指向并单击任何内容，然后使用 VEC（[!UICONTROL 可视化体验编辑器]）为该区域直观地创建和选择其他内容选项。之后，该算法会根据系统提供的有关每一位访客的所有行为数据自动确定向该访客提供的内容块，从而提供个性化体验。由于[!UICONTROL 自动个性化]可以根据访客行为的变化进行相应调整，因此它可以在没有设定结束日期的情况下运行，以提供持续的提升和个性化。这有时被称为“始终运行”模式。营销人员不需要先运行测试、分析结果、交付入选者，然后再实现从优化中发现的提升，这是实施标准 A/B 活动结果的标准操作顺序。

讨论[!UICONTROL 自动个性化]时，以下术语将会很有用：

| 术语 | 定义 |
|---|---|
| 多臂老虎机 | 多臂老虎机优化方法可在探索式学习和对该学习的利用之间进行平衡。 |
| 随机森林 | 随机林是一种领先的机器学习方法。从数据科学领域来讲，它是一种基于访客和访问属性构建大量决策树的组合分类或回归方法。在 Target 中，随机林用来确定对于每个特定访客而言，哪个体验的转化可能性最高（或每次访问带来的收入最高）。有关 Target 中随机林的更多信息，请参阅[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。 |
| 汤普森采样 | 汤普森采样的目标是确定哪个体验是最佳的整体（非个性化）体验，同时最大限度地降低找到该体验的“成本”。 即便两种体检之间没有统计意义上的差异，汤普森采样算法还是会选出一个入选者。有关更多信息，请参阅[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

使用[!UICONTROL 自动个性化]时请考虑以下详细信息：

**自动个性化使用随机林算法进行个性化。**

随机林是一种领先的机器学习方法。从数据科学领域来讲，它是一种基于访客和访问属性构建大量决策树的组合分类或回归方法。在 Target 中，随机林用来确定对于每个特定访客而言，哪个体验的转化可能性最高（或每次访问带来的收入最高）。例如，使用 Chrome 的访客是金牌忠实成员，且周二访问您的网站更有可能使用体验 A 进行转化，而来自纽约的访客则更有可能使用体验 B 进行转化。有关 Target 中随机林的更多信息，请参阅[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

**个性化模型会针对每次访问进行优化。**

* 该算法可预测访客转化的可能性（或转化带来的预计收入），以便提供最佳体验。
* 在现有会话结束后，访客将有资格获得新体验（除非该访客在控制组中，在这种情况下，访客在首次访问时看到的体验将与其在后续访问中看到的体验相同）。
* 在会话中，所呈现的体验不会为保持视觉一致性而发生更改。

**个性化模型会根据访客行为的变化进行相应调整。**

* 多臂老虎机确保模型始终“花费”一小部分流量以在活动期间继续学习，并防止过度利用以前学习到的趋势。
* 系统会每 24 小时使用最新的访客行为数据重新构建基础模型，以确保 Target 始终利用不断发生更改的访客偏好。
* 如果该算法无法为单个访客确定入选体验，则会自动切换为显示整体性能最佳的体验，同时仍继续寻找个性化的入选者。性能最佳的体验将使用[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)来查找。

**模型会不断优化单个目标量度。**

* 此量度可以基于转化，也可以基于收入（更具体地说，[!UICONTROL 每位访客带来的收入]）。

**Target 会自动收集关于访客的信息来构建个性化模型。**

* 有关[!UICONTROL 自动定位]和[!UICONTROL 自动个性化]中所使用的属性的更多信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

**[!DNL Adobe Experience Cloud]Target 会自动使用所有 共享受众来构建个性化模型。**

* 您无需执行任何特定操作来将受众添加到模型中。有关将 [!DNL Experience Cloud Audiences] 与 [!DNL Target] 配合使用的信息，请参阅 [Experience Cloud 受众](/help/main/c-integrating-target-with-mac/mmp.md)。

**营销人员可以上传离线数据、倾向得分或其他自定义数据来构建个性化模型。**

在构建个性化模型时，离线数据（例如 CRM 信息或客户流失倾向评分）可能会有极大的价值。可通过多种方式在[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 自动定位]个性化算法中输入数据。

* [mbox 参数](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [配置文件参数](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [用于配置文件更新的服务器端 API](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

有关[!UICONTROL 自动个性化]和[!UICONTROL 自动定位]个性化算法自动收集和使用的数据的信息，请参阅[自动个性化数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## ![“概述”标记](/help/main/assets/overview.png) 培训视频：活动类型

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。[!UICONTROL 对自动个性化的讨论开始于 5:55。]

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)
