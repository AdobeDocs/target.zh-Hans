---
keywords: 定位
description: 了解如何Adobe [!DNL Target] 显示并计算每个体验的转化率、提升度、置信度和置信区间。
title: 如何查看转化率、提升度和置信度级别？
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '2162'
ht-degree: 52%

---

# 转化率

每个体验均会报告转化率、提升度、置信度和置信区间。

下图显示了一个示例活动的图表表头，其中高亮显示了“[!UICONTROL 转化率]”、“[!UICONTROL 提升度]”和“[!UICONTROL 置信度]”表头。

![转化率图像](assets/conversion-rate.jpg)

>[!NOTE]
>
>在所有的数据中，如果传递 `orderID`，则会忽略重复订单。审计报表列出了被忽略的重复订单。

## 转化率 {#section_07A36846C4E84D0881906809B9CE5A74}

显示转化率中值、置信区间以及转化次数。

例如，请查看以下“转化率”报表列：

![转化率细节图像](assets/conversion-rate-detail.jpg)

第一行是控制体验。该行显示的转化率为 15%，转化次数为 3。第二行（体验 B）显示的转化率为 15%，置信区间为 ±15.65%，转化次数为 3。

>[!NOTE]
>
>当前仅计算二进制量度的置信区间。

## 提升度 {#section_0F409572C720433D9378092ABC999982}

将每个体验的转化率与控制体验的转化率进行比较。

提升度 =（体验转化率 - 控制转化率）/控制转化率。

如果控制体验为 0，则不存在提升百分比。


## 零售数据 {#section_30A674731BA6440E9BB93C421BE990EE}

如果您插入了下单，则会显示每个体验的AOV、RPV和销售数据(`orderConfirmPage`) mbox并将其选为转化mbox。

## 置信水平和置信区间 {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

对于每个体验，将显示置信度和置信区间。

您可以为 for Target (A4T) 执行离线计算，但需要在 [!DNL Analytics]Analytics 中完成数据导出步骤。有关更多信息，请参阅下面的“为 Analytics for Target (A4T) 执行离线计算”。

### 置信度 {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

显示的体验或选件的置信度是一种获得比实际观察到的结果更少极端的概率（以百分比表示），前提是空假设为真（本质上，如果该体验或选件与控制体验/选件之间的转化率没有差异）。 就p值而言，显示的置信度为1 - p值。 更简单地说，置信度越高，表示数据与控制选件/体验具有相等转化率的假设不太一致。

置信度如果大于或等于 99.995%，则向上舍入为 100.00%。

![conf_report图像](assets/conf_report.png)  ![conf_report_detail图像](assets/conf_report_detail.png)

在做出任何业务决策之前，请尝试等待一段时间，直到样本量足够大，并且一个或多个体验的四个置信度条块在一段连续的时间内保持一致，从而确保结果稳定。


### 置信区间 {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>当前仅计算二进制量度的置信区间。

此 *置信区间* 是一个估计范围，可以在该范围内在给定的置信水平下找到量度的真实值。 Target始终显示95%置信度间隔。 在“转化率”列中，置信区间显示为浅灰色 +/- 百分比值。在以下示例中，体验 B 的提升度所具有的置信区间为 +/- 15.65%。

![conversion_rate图像](assets/conversion_rate.png)

**示例：** 一个体验的观察到的真实现值为10美元，其中95%为真实现值 **置信区间** 5到15美元。 我们不知道，它的真正有效价值是12美元。 然后，如果我们多次运行此测试，则我们计算的置信区间的95%的时间将包含 _true_ RPV值12美元。

**置信区间的影响因素有哪些？**&#x200B;公式遵循计算置信区间的标准统计方法。

* **样本量：**&#x200B;随着样本的增加，区间将缩小。推荐采用较大样本，因为这意味着您的报表更加接近成功量度的真实值。
* **标准偏差减小：**&#x200B;结果越相似（如 AOV 越相似或者每天转化的次数或访客数越相似），标准偏差越小。

## 置信度计算及其离线执行方法 {#section_86F7C231943043A5B8B6BFE67B706E3B}

[下载的 CSV 报表](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)仅包含原始数据，而不包含计算量度，如 A/B 测试中使用的每位访客带来的收入、提升度或置信度。

要计算这些计算量度，请下载Target的 [完全置信度计算器](/help/main/assets/complete_confidence_calculator.xlsx) 用于输入活动值或审阅的Excel文件 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>此计算器适用于基于 Target 的报表，而不适用于 A4T 报表。

## 为Analytics for Adobe Target (A4T)执行离线计算 {#section_B34BD016C8274C97AC9564F426B9607E}

您可以为 A4T 执行离线计算，但需要在 [!DNL Analytics] 中完成数据导出步骤。

对于A4T，我们使用 [韦尔奇t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} 连续变量的计算（而不是二进制量度）。 在 Analytics 中，会始终跟踪访客，并计入所执行的每项操作。因此，如果访客进行了多次购买或多次访问了某个成功量度，则会计入这些额外的点击。这会使量度变为连续变量。要执行Welch的t检验计算，需要“平方和”来计算方差，方差用作t统计量的分母。 [A/Bn测试中的统计计算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) 说明使用的数学公式的详细信息。 平方和可以从 [!DNL Analytics]. 要获取平方和数据，您需要导出样本时间段内要优化的量度在访客级别对应的数值。

例如，如果您针对每位访客的页面查看次数进行优化，则可以导出一个样本，即在指定的时间段内（可能几天）每位访客的页面查看总次数（只需几千个数据点）。 之后，您可以对每个值求平方，然后将总数相加（此处的运算顺序至关重要）。此“平方和”值随后可用在完整置信度计算器中。应在该电子表格的“收入”部分中使用这些值。

**使用 [!DNL Analytics] 数据导出功能执行此操作：**

1. 登录到 [!DNL Adobe Analytics]。
1. 单击&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]**。
1. 在 **[!UICONTROL Data Warehouse 请求]**&#x200B;选项卡中，填写相应的字段。

   有关各个字段的更多信息，请参阅 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html) 中的“Data Warehouse 请求描述”。

   | 字段 | 说明 |
   |--- |--- |
   | 请求名称 | 指定请求的名称。 |
   | 报告日期 | 指定时间段和时间粒度。<br>对于首次请求，最好选择不超过 1 小时或 1 天的数据。请求的时间段越长，Data Warehouse 文件处理的时间也就会越长，因此第一次最好请求较短时间段内的数据，以确保文件返回预期的结果。之后，转到“请求管理器”，复制您的请求，然后在第二次请求中请求更多的数据。此外，如果将粒度切换为“无”以外的任何粒度，文件大小都将急剧增加。<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | 可用区段 | 根据需要应用区段。 |
   | 划分 | 选择所需的维度：“标准”维度为开箱即用 (OOTB) 维度，而“自定义”维度包含 eVar 和 prop。如果需要访客ID级别信息，建议您使用“访客ID”，而不是“Experience Cloud访客ID”。<ul><li>访客 ID 是 Analytics 使用的最终 ID。访客 ID 将为 AID（如果客户是旧客户）或 MID（如果客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie）。</li><li>仅当客户是新客户，或者清除了自 MC 访客 ID 服务启动以来的 Cookie 时，才会为客户设置 Experience Cloud 访客 ID。</li></ul> |
   | 量度 | 选择所需的量度。“标准”量度为开箱即用量度，而“自定义”量度包含自定义事件。 |
   | 报表预览 | 在计划报表之前查看您的设置。<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | 计划提交 | 输入要将文件提交到的电子邮件地址，为文件命名，然后选择[!UICONTROL 立即发送]。<br>注意：可通过[!UICONTROL 高级提交选项]<br>![计划提交](/help/main/c-reports/assets/datawarehouse3.png)下方的 FTP 来提交文件。 |

1. 单击&#x200B;**[!UICONTROL 请求此报表]**。

   根据请求的数据数量，文件提交最多可能需要 72 小时。您可以随时查看请求的进度，方法是单击“[!UICONTROL 工具]”>“[!UICONTROL Data Warehouse]”>“[!UICONTROL 请求管理器]”。

   如果您希望重新请求您过去请求的数据，则可以从 [!UICONTROL 请求管理器] 根据需要。

有关 [!DNL Data Warehouse] 的更多信息，请访问 [!DNL Analytics] 帮助文档中的以下链接：

* [创建 Data Warehouse 请求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [data warehouse最佳实践](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

## 计数方法 {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

您可以选择按不同的计数方法查看报表，以便了解在活动的生命周期或在单个会话期间，活动对您的用户产生了何种影响。

以下活动类型支持计数方法：

* A/B 测试

   自动定位 A/B 活动是一个特例，它仅支持默认的“访问”计数方法。

* 体验定位 (XT)
* 多变量测试 (MVT)

   在 MVT 元素贡献报表中，Target 对于收入量度类型不支持活动展示次数。

* 推荐

自动个性化 (AP) 活动当前仅支持默认的计数方法（即“访问次数”）。

您可以按以下计数方法查看报表：

* **访客：**&#x200B;活动生命周期内活动中的独特参加者。

   在以下情况下，可以将一个人计为新参加者：此人从新的计算机或新的浏览器访问网站；此人删除了 Cookie；或此人在转化后使用相同的 Cookie 再次返回到活动。由访客的 mbox Cookie 中的 PCID 对参加者进行标识。如果 PCID 发生更改，则此人会被计为新访客。

* **访问：**&#x200B;独特参加者在持续 30 分钟的单次浏览器会话期间对体验进行的访问。

   如果实现了转化，或者访客在离开至少 30 分钟后再次回到网站，则该访客的回访会被计为新访问。由访客的 mbox Cookie 中的 `sessionID` 对访问进行标识。`sessionID` 发生更改时，该访问将被视为新访问。

* **展示/页面查看：**&#x200B;每次访客加载活动的任何页面时均进行一次计数。

   单次访问可能包含多次展示，例如您的主页在一次访问期间可能会展示多次。

>[!NOTE]
>
>通常情况下，计数取决于 Cookie 和会话活动。但是，如果您达到了活动的最终转化点，然后又重新进入活动，则您会被视为新参加者，而您对活动的访问也会被视为新访问。即使用户的 PCID 和 `sessionID` 值不变，也是如此。

## 为什么 [!DNL Target] 建议使用Welch的t检验？ {#t-test}

A/B测试是比较控制变量中某个商业量度（也称为体验）的平均值与一个或多个替代体验中该同一量度的平均值的实验。

[!DNL Target] 建议使用 [韦尔奇t检验](https://en.wikipedia.org/wiki/Welch%27s_t-test)，因为这些测试所需的假设比z检验等替代测试更少，并且是用于与控制体验和替代体验之间进行（定量）业务量度配对比较的合适统计测试。

### 详细信息

运行联机A/B测试时，每个用户/访客均会随机分配到单个变体。 随后，我们对感兴趣的业务量度（例如转化率、订单、收入等）进行测量 用于每个变体中的访客。 我们使用的统计测试然后测试平均业务量度（例如，转化率、每用户订单数、每用户收入等）的假设 对于对照和给定替代变体是相同的。

尽管业务量度本身可能会根据某种任意分布进行分布，但此量度的平均值分布（在每个变量内）应通过 [中心极限定理](https://en.wikipedia.org/wiki/Central_limit_theorem). 请注意，虽然无法保证均值采样分布收敛到正常值的速度，但通常根据在线测试中的访客规模达到此条件。

给定该均值的这种正态性，可表明所使用的测试统计量遵循t分布，因为它是正态分布值（业务量度的均值差）与基于来自数据的估计（均值差的标准误差）的缩放项的比率。 此 **t检验** 是次适当的假设检验，假设检验的统计量服从t分布。

### 为什么不使用其他测试

A **z检验** 在技术上是不合适的，因为在典型的A/B测试场景中，测试统计量的分母不是从已知方差中派生的，而是必须从数据中估计。 然而，当样本量足够大时，z检验和t检验是相同的。

**卡方检验** 不使用，因为它们适用于确定两个变体之间是否存在定性关系（即，变量之间无差异的null假设）。 T测试更适用于场景 _定量_ 比较指标。

此 **Mann-Whitney U检验** 是一种非参数测试，当平均业务量度（针对每个变体）的采样分布不是正态分布时，此测试较为合适。 但如前所述，考虑到在线测试中涉及的流量大小，通常应用中心极限定理，因此t测试可以安全应用。

更复杂的方法，例如 **ANOVA** （将t测试推广到两个以上的变体）可以在测试具有两个以上的体验（“A/Bn测试”）时应用。 然而，ANOVA回答了“是否所有变体具有相同的均值”的问题，而在典型的A/Bn测试中，我们更感兴趣 _哪个特定变体_ 最好。 In [!DNL Target]因此，我们应用常规t检验来比较每个变体与对照，并进行Bonferroni校正以考虑多次比较。