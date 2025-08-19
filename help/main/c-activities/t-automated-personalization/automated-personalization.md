---
keywords: 自动个性化；AP；受众；组合；随机林；多臂老虎机；汤普森采样；ML；机器学习
description: 了解如何在[!UICONTROL Automated Personalization]中使用 [!DNL Adobe Target]  (AP)活动，这些活动使用高级机器学习将不同的选件变体与每位访客匹配。
title: 什么是[!UICONTROL Automated Personalization] (AP)活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 29%

---

# [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization]中的[!DNL Adobe Target] (AP)活动将选件或消息组合在一起，并使用高级机器学习根据每位访客的个人客户配置文件将不同的选件变体与其匹配，以便个性化内容并促进提升。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]作为[!DNL Target Premium]解决方案的一部分提供。 如果没有 [!DNL Target Premium] 许可证，则此功能在 [!DNL Target Standard] 中不可用。有关此许可证提供的各项高级功能的更多信息，请参阅 [Target Premium](/help/main/c-intro/intro.md#premium)。

与[!UICONTROL Auto-Target]类似，[!UICONTROL Automated Personalization]使用[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)（一种领先的数据科学组合方法）作为其主要个性化算法，来确定向访客显示的最佳体验。 [!UICONTROL Automated Personalization]在测试的发现阶段可能很有价值。 当定位各种不同的访客时，它也有助于机器学习确定最有效的内容。随着时间的推移，该算法会学习预测最有效的内容并显示最有可能实现您的目标的内容。

要查找有关[!UICONTROL Automated Personalization]与[!UICONTROL Auto-Target]不同之处的详细信息，请参阅[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)。

营销人员在他们的网站上实施一个文件，使他们能够指向并单击任何内容，然后使用[!UICONTROL Visual Experience Composer] (VEC)为该区域直观地创建和选择其他内容选项。 之后，该算法会根据系统提供的有关每一位访客的所有行为数据自动确定向该访客提供的内容块，从而提供个性化体验。由于[!UICONTROL Automated Personalization]可以适应访客行为的变化，因此它可以在没有设定结束日期的情况下运行，以提供持续的提升和个性化。 此模式有时称为“始终运行”。 营销人员不需要先运行测试、分析结果、交付入选者，然后再实现从优化中发现的提升，这是实施标准 A/B 活动结果的标准操作顺序。

讨论[!UICONTROL Automated Personalization]时，以下术语很有用：

| 术语 | 定义 |
|---|---|
| 多臂老虎机 | 多臂老虎机优化方法可在探索式学习和对该学习的利用之间进行平衡。 |
| 随机森林 | 领先的机器学习方法。 在数据科学术语中，它是一种集成分类或回归方法，通过构建基于访客和访问属性的多个决策树来工作。 |
| 汤普森采样 | 汤普森采样的目标是确定哪个体验是最佳的整体（非个性化）体验，同时最大限度地降低找到该体验的“成本”。 即便两种体检之间没有统计意义上的差异，汤普森采样算法还是会选出一个入选者。有关更多信息，请参阅[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)。 |

使用[!UICONTROL Automated Personalization]时请考虑以下详细信息：

## [!UICONTROL Automated Personalization]使用随机林算法进行个性化

随机林是一种领先的机器学习方法。 在数据科学术语中，它是一种集成分类或回归方法，通过构建基于访客和访问属性的多个决策树来工作。 在[!DNL Target]内，随机林用于确定哪个体验对于每个特定访客具有最高的转化可能性（或每次访问的最高收入）。 例如，使用Chrome的访客是金会员忠诚会员，并且星期二访问您的网站可能会更倾向于使用体验A转化。来自纽约的访客可能更倾向于使用体验B转化。有关[!DNL Target]中随机林的详细信息，请参阅[随机林算法](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)。

## 个性化模型会针对每次访问进行优化

* 该算法预测访客的转化可能性（或估计的转化收入）以提供最佳体验。
* 访客有资格在现有会话结束时获得新体验，除非该访客位于控制组中。 如果访客在对照组内，则访客在首次访问时看到的体验与后续访问中看到的体验相同。
* 呈现的体验不会在会话中更改以保持视觉一致性。

## 个性化模型可适应访客行为的变化

* 多臂老虎机确保模型始终“花费”一小部分流量以在活动期间继续学习，并防止过度利用以前学习过的趋势。
* 使用最新的访客行为数据每24小时重建一次基础模型，以确保[!DNL Target]始终使用更改的访客偏好设置。
* 如果该算法无法为单个访客确定入选体验，则会自动切换为显示整体性能最佳的体验，同时仍继续寻找个性化的入选者。性能最佳的体验将使用[汤普森采样](https://en.wikipedia.org/wiki/Thompson_sampling)来查找。

## 模型会不断优化单个目标量度

* 此量度可以基于转化，也可以基于收入（具体而言，[!UICONTROL Revenue per Visitor]）。

## [!DNL Target]自动收集关于访客的信息以构建个性化模型

* 有关[!UICONTROL Auto-Target]和[!UICONTROL Automated Personalization]中使用的属性的更多信息，请参阅[Automated Personalization数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## [!DNL Target]自动使用所有[!DNL Adobe Experience Cloud]共享受众来构建个性化模型

* 您无需执行任何特定操作即可将受众添加到模型。 有关将 [!DNL Experience Cloud Audiences] 与 [!DNL Target] 配合使用的信息，请参阅 [Experience Cloud 受众](/help/main/c-integrating-target-with-mac/mmp.md)。

## 营销人员可以上传离线数据、倾向得分或其他自定义数据来构建个性化模型

在构建个性化模型时，离线数据（如CRM信息或客户流失倾向分数）可能非常有价值。 有几种方法可在[!UICONTROL Automated Personalization] (AP)和[!UICONTROL Auto-Target]个性化算法中输入数据。

* [mbox 参数](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hans){target=_blank}
* [轮廓参数](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hans){target=_blank}
* [用于轮廓更新的服务器端 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hans){target=_blank}

有关[!UICONTROL Automated Personalization]和[!UICONTROL Auto-Target]个性化算法自动收集和使用的数据的信息，请参阅[Automated Personalization数据收集](/help/main/c-activities/t-automated-personalization/ap-data.md)。

## 培训视频：活动类型

以下视频介绍了 [!DNL Target] 中可用的活动类型。从5[!UICONTROL Automated Personalization]开始讨论:55。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/30323?captions=chi_hans)
