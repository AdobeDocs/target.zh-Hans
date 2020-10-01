---
keywords: traffic estimator;automated personalization;ap
description: 流量估计器提供反馈，让您了解您是否有足够的流量使您的Adobe Target活动成功。
title: 估算成功所需流量
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: 20ecf93ec1ee9adbe2fce50d4d18c1471b69c8aa
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 25%

---


# ![PREMIUM](/help/assets/premium.png) 估算成功所需流量{#estimate-the-traffic-required-for-success}

The [!UICONTROL Traffic Estimator] provides feedback that lets you know whether you have sufficient traffic for your [!DNL Adobe Target] activity to succeed.

Because an [!UICONTROL Automated Personalization] activity uses multiple offer combinations, it is important to know how much traffic is required to provide meaningful results. The [!UICONTROL Traffic Estimator] uses statistics about your page and the number of experiences being tested to estimate the amount of traffic and the test duration needed to make the activity successful.

The [!UICONTROL Traffic Estimator] determines if there is enough traffic to generate personalized models, by comparing the estimated page impressions and typical conversion rate for the pages. 对于成功的活动，在理想的情况下，正确的样本量可确保个性化内容在活动持续时间的一半时间或 14 天内（以较短者为准）准备就绪。这样便可以有充足的时间来获取个性化内容，并学习要交付哪些内容。

Remember that [!DNL Target] randomly serves experiences until the personalization algorithms are built. The checkmark icon beside each offer shows when the model for that offer is ready and [!DNL Target] is able to begin delivering personalized content. 由于只有在个性化模型准备就绪后才会出现提升，因此显示的指示标记可帮助您设置正确的预期。Use the [!UICONTROL Traffic Estimator] in the [!UICONTROL Visual Experience Composer] (VEC) to get a guideline of when the models will be ready.

## 使用流量估计器

1. From the [!UICONTROL Visual Experience Composer], click **[!UICONTROL Traffic]**.

   ![“流量”图标](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   The [!UICONTROL Traffic Estimator] opens. You can click **[!UICONTROL Traffic]** again to hide the [!UICONTROL Traffic Estimator].

   ![](assets/ap_est.png)

1. 提供典型转化率（或此活动的预期转化率）、预计每日活动展示次数，及测试持续时间。

   * **优惠数**:根据在任何排除后作为活动的一部分创建的体验数自动计算。
   * **典型转化率**：转化率以百分比表示，根据估算或 Analytics 系统中的以往数据得出.
   * **估计每日访问量**:这是根据定位标准，能够视图活动的访客每天的访问次数。 可以基于您的分析数据。请注意，此数值应为访问次数，而不是独特访客数。
   * **测试持续时间**：您希望该活动运行的天数。

   The [!UICONTROL Traffic Estimato]r uses these statistics to determine what adjustments are needed to run a successful test.

   Near the top of the [!UICONTROL Traffic Estimator], the values you entered are calculated and the results are shown.

   ![](assets/ap_est_no.png)

   当您更改这些数字时，估算的结果也会相应改变。For example, if you are testing a large number of combinations and your conversion rate and impressions are too low, the [!UICONTROL Traffic Estimator] shows how long the test will need to run to be successful. Or, if your traffic is low, the [!UICONTROL Traffic Estimator] might suggest a lower number of offer combinations so you can run the test the desired number of days.

   如果流量不足，您可以执行以下任一或所有操作：

   * Consider using an [Auto-Target](/help/c-activities/auto-target-to-optimize.md) activity instead of [!UICONTROL Automated Personalization] to create experiences with several offer changes in one experience variation.
   * Reduce the number of offer combinations within your [!UICONTROL Automated Personalization] activity.
   * 延长活动持续时间。

   Adjust the numbers until the [!UICONTROL Traffic Estimator] says you have sufficient traffic, then design your test accordingly.

   ![](assets/ap_est_yes.png)

   If the traffic is sufficient, the [!UICONTROL Traffic] icon shows a green check. 如果流量不足，该图标会显示一个红色警告标签。

## 有关流量估计器的常见问题

使用流量估计器时，请考虑以下常 [!UICONTROL 见问题]:

### 为什么 [!DNL Target] 在AP活动拥有足够流量时不构建个性化模型？

在某些情况下，您的流量可能足够大，足以构建个性化模型，但流量可能表明，个 [!DNL Target] 性化模型与随机模型之间没有有意义的差异。 虽然模型是经过内 [!DNL Target] 建和测试的，但是它不会部署，因为模型并不比随机模型好得多。

这种模式未能比现有模式更好的一个原因可能是，优惠之间没有显着差异。 如果是这种情况，您可以尝试通过使优惠的视觉效果更加不同或更改内容本身来增加这些差异。
