---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: 探索您在Adobe Target中使用[!UICONTROL Automated Personalization] (AP)活动时可能面临的潜在挑战以及建议的解决方案。
title: 如何为[!UICONTROL Automated Personalization]活动排除故障？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 32%

---

# [!UICONTROL Automated Personalization]疑难解答

有时候，活动没有按预期进行。以下是您在使用[!UICONTROL Automated Personalization] (AP)时可能面临的一些潜在挑战，以及一些建议的解决方案。

## 我的[!UICONTROL Automated Personalization]活动在构建模型时用时过长。 {#section_20028B204DBB4D77A324BA193434AEE2}

+++查看详细信息

更改几项活动设置可以减少构建模型所需的预计时间，包括[!UICONTROL Automated Personalization]活动中的体验数量、您网站的流量以及您选择的成功量度。

**解决方案：**&#x200B;查看您的活动设置，看看是否愿意进行任何更改以提高模型构建的速度。

* 如果成功量度是设为 RPV，那么您是否可以改用转化作为成功量度？转化活动需要用来构建模型的流量通常较少。如果将成功量度从RPV更改为转化，则不会丢失活动数据。
* 您的成功量度在活动体验的销售漏斗中是否位于较远的位置？由于存在最低转化次数要求，较低的活动转化率会提高构建模型所需的流量要求。
* 是否有一些选件或体验可从活动中排除？减少活动中的体验数量可缩短构建模型的时间。
* 是否有更高流量的页面可让此活动更成功？ 活动位置的流量和转化越多，模型构建的速度就越快。

+++

## 我的[!UICONTROL Automated Personalization]活动未生成提升。 {#section_8900BC8968474438B8092F7A94C0C6CF}

+++查看详细信息

[!UICONTROL Automated Personalization]活动需要多个因素才能产生提升：

* 选件必须足够不同，才能影响访客。
* 选件必须位于对优化目标有所影响的位置。
* 测试中必须有足够的流量和统计“功效”，才能检测到提升度。
* 个性化算法必须运行良好。

**解决方案：**&#x200B;最好的做法是首先通过简单的非个性化 A/B 测试，确保构成活动体验的内容和位置对整体响应率真正发挥了作用。务必提前计算样本量。 提前计算样本大小有助于确保有足够的能力来看到合理的提升。 然后，您可以在不停止或进行任何更改的情况下，在固定的持续时间内运行A/B测试。 如果A/B测试结果显示一个或多个体验在统计上显着提升，则个性化活动可能会成功。 即使这些体验的总体响应率没有差异，Personalization也可以正常工作。 通常，问题源于选件或位置对优化目标的影响不足以被检测出具有统计显着性的情况。

+++

## 我的[!UICONTROL Automated Personalization]活动URL在不正确的页面上显示选件内容。 {#section_82A224406DBF4107B05204BEFBBE458C}

+++查看详细信息

在[!UICONTROL Automated Personalization]中，将URL和模板测试规则添加到[!DNL Target]请求条目约束（例如，target-global-mbox），其中只评估一次。 用户符合活动资格后，不会重新评估Target请求级别的定位规则。 但是，定位受众会添加到位置定位规则中。

**解决方案：**&#x200B;添加必要的模板规则作为活动的输入受众。 每次进行请求/调用时，都会进行受众评估。

+++

## 依赖于转化量度的所有量度从不转化。 {#section_076D1F44298C4E4A849AC52F5A33214D}

+++查看详细信息

这是符合预期的。

在[!UICONTROL Automated Personalization]活动中，转化量度（无论是优化目标还是后期目标）发生转化后，访客将会从体验中释放，并且活动会重新开始。

例如，一个活动拥有一个转化量度 (C1) 和一个其他量度 (A1)。A1依赖于C1。 当访客首次进入活动，并且转化 A1 和 C1 的标准并未实现转化，那么由于成功量度的依赖关系，量度 A1 不会进行转化。如果访客先转换C1，然后再转换A1，则仍不会转换A1，因为转换C1时，访客将会释放。

+++

## 我的体验 URL 未按预期工作。 {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++查看详细信息

* 如果您在新选项卡中看不到预览（由于浏览器缓存），请尝试刷新两到三次。 您还可以复制链接，并在新浏览器或新会话中打开该链接。
* 如果您已更改任何内容，请重新生成体验 URL 链接，并将新链接共享给同事。

+++
