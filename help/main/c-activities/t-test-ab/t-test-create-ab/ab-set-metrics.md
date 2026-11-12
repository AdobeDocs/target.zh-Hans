---
keywords: A/B;活动量度;量度;设置量度;目标量度;活动设置;成功量度;转化;收入;参与度
description: 了解如何在A/B、体验定位或多变量测试活动中设置量度以确定访问成功，包括[!UICONTROL 转化]、[!UICONTROL 收入]和[!UICONTROL 参与]。
title: 如何在A/B活动中设置目标指标？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 25%
---
# 设置量度 {#ab-set-metrics}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何设置A/B、体验定位(XT)或多变量测试(MVT)活动的目标量度和其他量度，以及量度名称中不允许使用哪些字符。

>[!ENDSHADEBOX]

在[!DNL Adobe Target] A/B、[!UICONTROL 体验定位] (XT)或[!UICONTROL 多变量测试] (MVT)活动中使用量度来确定访问何时被视为成功。 有关成功指标的详细信息，请参阅[成功指标](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)。

>[!NOTE]
>
>此页面在[!DNL Adobe Target]为报表源时适用。 对于其他报表源，请参阅[[!DNL Adobe Analytics] 作为 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [[!DNL Target] 报表的报表源。

## 设置量度 {#set-a-metric}

1. 在&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面的&#x200B;**[!UICONTROL 报表设置]**&#x200B;部分中，选择[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)。

   **[!UICONTROL 选择量度]**&#x200B;选项列出了可为活动选择的成功量度。 这些成功量度分为以下类别：

   * **[!UICONTROL 转化]**
   * **[!UICONTROL 收入]**
   * **[!UICONTROL 参与]**

   您可以选择任何预先构建的成功量度，或者也可创建自定义成功量度。 您还可以将某个成功量度标记为主量度。 如果设置了主量度，报表和 Experience Cloud 卡片默认将显示该主量度。

   ![](../../assets/metric-1.png)

1. 指定量度设置。 可用的设置取决于您所使用的成功量度。

1. 如果启用，**[!UICONTROL 转换的预计值]**&#x200B;字段将为您的目标提供一个值：

   * 该值允许[!DNL Target]计算预计收入提升。
   * 字段是可选的；但是，如果没有该字段，则无法计算任何非收入量度的增量收入。
   * 该字段不适用于&#x200B;**[!UICONTROL 页面得分]**&#x200B;量度。
   * 数据类型为货币。
   * 在用户指示为满足目标而采取的操作后，该字段将逐步显示。

   请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。 正确配置成功量度对于确保获得您预期的数据至关重要。

   ![](../../assets/metric-2.png)

1. （可选）要跟踪的目标量度之外的其他量度，请单击&#x200B;**[!UICONTROL 添加新量度]**，然后按照前面步骤所述选择并配置每个其他量度。

1. 完成设置量度后，在XT活动中单击&#x200B;**[!UICONTROL 继续]**，或者在MVT活动中单击&#x200B;**[!UICONTROL 保存并关闭]**。

## 指标名称中不允许使用字符 {#metric-name-rules}

![](../../assets/metric-3.png)

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
