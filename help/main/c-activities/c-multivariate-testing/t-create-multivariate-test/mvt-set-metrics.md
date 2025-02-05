---
keywords: 多变量测试;MVT;量度;设置量度;目标量度;活动设置;成功量度;转化;收入;参与度
description: 了解如何在 [!DNL Adobe Target] [!UICONTROL Multivariate Test]活动中指定量度以确定访问何时成功，例如[!UICONTROL Conversion]、[!UICONTROL Revenue]和[!UICONTROL Engagement]。
title: 如何在[!UICONTROL Multivariate Test] (MVT)活动中设置目标指标？
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 60%

---

# 为[!UICONTROL Multivariate Test]活动设置量度

在[!DNL Adobe Target] [!UICONTROL Multivariate Test]中使用量度来确定访问何时被视为成功。

有关成功指标的详细信息，请参阅[成功指标](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. 指定活动目标。
1. 选择[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![设置量度列表](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   [!UICONTROL Select Metrics]页列出了可为活动选择的成功量度。 这些成功量度分为以下类别：

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   您可以选择任何预先构建的成功量度，或者也可创建自定义成功量度。您还可以将某个成功量度标记为主量度。如果设置了主量度，报表和 Experience Cloud 卡片默认将显示该主量度。

1. 指定量度设置。

   可用的设置取决于您所使用的成功量度。

   如果启用，[!UICONTROL Estimated Value of the Conversion]字段（不适用于[!UICONTROL Page Score]量度）会为您的目标提供一个值。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。数据类型为货币。当用户的操作满足您设置的目标后，该字段会逐渐显示积累的值。请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。

   正确配置成功量度对于确保获得您预期的数据至关重要。

   有关更多信息，请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. （可选）添加其他量度。
1. 完成设置量度时，请单击&#x200B;**[!UICONTROL Save and Close]**。

在命名或重命名指标时，不允许使用以下字符：

| 字符 | 描述 |
|--- |--- |
| `/` | 正斜线 |
| `?` | 问号 |
| `#` | 数字符号 |
| `:` | 冒号 |
| `=` | 等号 |
| `+` | 加号 |
| `-` | 减号 |
| `@` | @ 符号 |

## 培训视频：活动量度(7:43) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关使用成功量度的信息。

* 了解“目标”量度
* 了解并生成[!UICONTROL Conversion]、[!UICONTROL Revenue]和[!UICONTROL Engagement]量度
* 构建点击跟踪量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
