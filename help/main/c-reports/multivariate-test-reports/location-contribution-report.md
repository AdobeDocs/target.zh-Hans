---
keywords: MVT;多变量测试;位置贡献报表
description: 了解如何使用位置贡献报表进行Adobe [!DNL Target] [!UICONTROL 体验定位] 显示每个元素和每个选件性能的活动。
title: 如何使用 [!UICONTROL 位置贡献] 报告 [!UICONTROL 多变量测试] 活动？
feature: Reports
exl-id: 2fb7d2b3-d981-44fd-9bb2-021903605a09
source-git-commit: 6f70ff18cfbee5c02e6bb2bd345acbd2e1b2006f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 37%

---

# [!UICONTROL 位置贡献] 报表 (MVT)

此 [!UICONTROL 位置贡献] 报表显示每个元素和每个选件的性能。

报表顶部显示了报表中使用的量度、开始和结束日期以及受众。您可以对所有这些元素进行更改。

>[!NOTE]
>
>在使用时，请记住以下信息 [!UICONTROL 位置贡献] 报告：
>
>* 受众和量度选取器仅在 [!DNL Analytics] 用作报表源(A4T)。
>
>* 的数据 [!UICONTROL 位置贡献] 报告是从以下位置获取的： [!DNL Target] 后端，即使活动配置为使用 [!UICONTROL 将Analytics作为报表源] (A4T)。
>
>* 的数据 [!UICONTROL 位置贡献] 即使在“ ”中定义了其他默认环境，也会为“生产”环境获取报告 [!DNL Target] 帐户级别。


此 [!UICONTROL 位置贡献] 报告包含两个表。

第一个表显示了每个元素的相对影响力。此表显示了在添加选件的元素中，哪些元素的转化率最高。

![Adobe Target中的位置贡献报表](/help/main/c-reports/assets/locationcontributiontop.png)

第二个表提供了选件级别的报表。该表显示了每个元素中每个选件的转化率、提升度和置信度。此表可帮助您确定最成功的选件。 第二列显示了选件的选定量度（转化率、RPV、AOV、订单或参与度量度）所对应的值以及一个标准化。

![Adobe Target中的位置贡献报表](/help/main/c-reports/assets/locationcontributionbottom.png)

## 培训视频：创建MVT测试 ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了如何使用 Target 三步引导式工作流创建多变量测试。对位置贡献报表的介绍开始于 8:45。

>[!VIDEO](https://video.tv.adobe.com/v/17395)
