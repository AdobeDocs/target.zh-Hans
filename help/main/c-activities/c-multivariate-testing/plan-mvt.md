---
keywords: 多变量测试;MVT;MVT 规划;多变量测试规则
description: 了解如何在Adobe中规划多变量测试 [!DNL Target] 以便创建成功的测试。
title: 如何规划多变量测试？
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 92%

---

# 规划多变量测试

[!DNL Adobe Target] 中的[!UICONTROL 多变量测试] (MVT) 需要先进行一些规划，然后才能创建成功的测试。

MVT 需要足够的流量才能生成有用的结果。在设置测试之前，您应该知晓通常会获取的流量数量，包括展示次数和转化次数。了解此信息可降低设计的测试所需的流量超出网站流量的可能性。

建议元素之间维持相互独立的关系。（例如，不要在同一个测试中测试布局和内容。）

应检查要测试的页面的 HTML 代码。请确保您网站上的 HTML 元素不存在重复的 DOM ID。重复的 ID 可能会导致将相同的内容交付到多个位置。

应规划以测试页面上可能会产生显著结果的元素。例如，与在页脚中做出更改相比，横幅或主页图像可能会促进更多转化。在测试中包含影响力较弱的元素只会增加测试页面上影响力较为显著的元素所需的流量和时间。

最后，在创建测试之前，您应该创建要测试的内容。您需要了解各个选件的内容差异，并创建希望在测试中使用的图像、文本和 HTML 选件。

## 培训视频：创建多变量测试 (9:25) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 Target 三步引导式工作流规划并创建多变量测试。

* 定义和设计多变量测试
* 创建多变量测试

>[!VIDEO](https://video.tv.adobe.com/v/17395)
