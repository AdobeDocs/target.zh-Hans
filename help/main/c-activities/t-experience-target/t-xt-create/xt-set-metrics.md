---
keywords: 体验定位;XT;量度;设置量度;目标量度;活动设置;成功量度;转化;收入;参与度
description: 了解如何在 [!DNL Adobe Target] [!UICONTROL 体验定位] 用于确定访问何时成功的活动，例如 [!UICONTROL 转化]， [!UICONTROL 收入]，或 [!UICONTROL 参与].
title: 如何在中设置目标指标 [!UICONTROL 体验定位] 活动？
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 55%

---

# 在中设置量度 [!UICONTROL 体验定位] (XT)活动

在中使用量度 [!DNL Adobe Target] [!UICONTROL 体验定位] (XT)活动，用于确定访问何时被视为成功。

有关成功量度的详细信息，请参阅 [成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. 指定活动目标。
1. 选择[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![选择成功量度](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   此 [!UICONTROL 选择量度] 页面列出了可为活动选择的成功量度。 这些成功量度分为以下类别：

   * [!UICONTROL 转化]
   * [!UICONTROL 收入]
   * [!UICONTROL 参与]

   您可以查看任何预建的成功量度，也可以创建自定义成功量度。 您还可以将某个成功量度标记为主量度。如果设置了主量度，报表和 Experience Cloud 卡片默认将显示该主量度。
1. 指定量度设置。

   可用的设置取决于您所使用的成功量度。

   如果启用， [!UICONTROL 转化的预计值] 字段(不可用于 [!UICONTROL 页面得分] 量度)为您的目标提供一个值。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。数据类型为货币。当用户的操作满足您设置的目标后，该字段会逐渐显示积累的值。请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。

   正确配置成功量度对于确保获得您预期的数据至关重要。

   有关更多信息，请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)。

1. （可选）添加其他量度。
1. 完成设置量度时，单击&#x200B;**[!UICONTROL 继续]**。


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
* 了解和构建 [!UICONTROL 转化]， [!UICONTROL 收入]、和 [!UICONTROL 参与] 量度
* 构建点击跟踪量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
