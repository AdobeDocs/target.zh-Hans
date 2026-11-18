---
keywords: Automated Personalization；AP；故障诊断；故障诊断；模型；提升
description: 探索您在Adobe Target中使用[!UICONTROL Automated Personalization] (AP)活动时可能面临的潜在挑战以及建议的解决方案。
title: 如何为[!UICONTROL Automated Personalization]活动排除故障？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: 'https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 7%
---
# [!UICONTROL Automated Personalization]疑难解答 {#ap-troubleshooting}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动常见问题的解决方案。

>[!ENDSHADEBOX]

活动并非总是按预期进行。 使用以下列表确定[!UICONTROL Automated Personalization] (AP)活动中常见问题的原因并应用建议的解决方案。

## 模型和提升 {#models-and-lift}

+++ 我的[!UICONTROL Automated Personalization]活动在构建模型时用时过长

多个活动设置选项会影响模型需要构建的时间，包括&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中的体验数量、您网站的流量以及您选择的成功量度。

**解决方案：**&#x200B;检查您的活动设置，并检查是否可以进行更改以提高模型构建的速度。

* 如果成功量度是设为 RPV，那么您是否可以改用转化作为成功量度？ 转化活动需要用来构建模型的流量通常较少。 如果将成功量度从RPV更改为转化，则不会丢失活动数据。
* 您的成功量度在活动体验的销售漏斗中是否位于较远的位置？ 较低的活动转化率会增加要构建模型的流量要求，因为需要达到最低转化次数。
* 是否有一些选件或体验可以从您的活动中排除？ 减少活动中的体验数量会加快构建模型的时间。
* 是否有更高流量的页面可让此活动更成功？ 活动位置的流量和转化越多，模型构建的速度就越快。

+++

+++ 我的[!UICONTROL Automated Personalization]活动未生成提升

**[!UICONTROL Automated Personalization]**&#x200B;活动需要多个因素才能生成提升：

* 选件必须足够不同，才能影响访客。
* 选件必须位于对优化目标有所影响的位置。
* 测试中必须有足够的流量和统计“功效”，才能检测到提升度。
* 个性化算法必须运行良好。

**解决方案：**&#x200B;最好的做法是首先使用简单的非个性化A/B测试，确保构成活动体验的内容和位置对整体响应率真正发挥了作用。 提前计算样本大小以确保有足够的能力来查看合理的提升，然后固定持续时间运行A/B测试而不会停止它或进行任何更改。 如果A/B测试结果显示一个或多个体验在统计上显着提升，则个性化活动可能会成功。 即使这些体验的总体响应率没有差异，Personalization也可以正常工作。 通常，问题源于选件或位置对优化目标的影响不足以被检测出具有统计显着性的情况。

+++

## 活动设置和报告 {#setup-and-reporting}

+++ 我的[!UICONTROL Automated Personalization]活动URL在不正确的页面上显示选件内容

**原因：**&#x200B;在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;中，将URL和模板测试规则添加到[!DNL Target]请求条目约束（例如，target-global-mbox），其中只评估一次。 访客符合活动条件后，不会重新评估[!DNL Target]请求级别的定位规则，而会将定位受众添加到位置定位规则。

**解决方案：**&#x200B;添加必要的模板规则作为活动的输入受众。 在每个请求（调用）时进行受众评估。

+++

+++ 依赖于转化量度的所有量度从不转化

此行为是正常的。

在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中，转化量度（无论是优化目标还是后期目标）发生转化后，访客将会从体验中释放，并且活动会重新开始。

例如，某个活动具有一个转化量度(C1)和一个依赖于C1的其他量度(A1)。 当访客首次进入活动，并且既未转化C1也未转化A1时，由于成功量度依赖关系，A1未转化。 如果访客先转换C1，然后再转换A1，则仍不会转换A1，因为转换C1时会释放访客。

+++

+++ 我的体验URL未按预期工作

**解决方案：**&#x200B;使用以下操作：

* 如果您在新选项卡中看不到预览（由于浏览器缓存），请尝试刷新两到三次。 您还可以复制链接，并在新浏览器或新会话中打开该链接。
* 如果您更改了任何内容，请重新生成Experience URL链接，并与您的队友共享新链接。

+++
