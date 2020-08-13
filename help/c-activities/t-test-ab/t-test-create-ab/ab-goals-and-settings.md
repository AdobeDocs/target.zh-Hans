---
keywords: activity settings;A/B goals and settings;reporting settings;goal metrics;success metrics;dependent success metrics;advanced settings;primary goal;additional metrics;objective;priority;duration;reporting solution;goal;audiences for reporting;Which success metric must be reached before incrementing this metric;What will happen after a user encounters this goal metric;notes
description: 您可以在“目标和设置”页面上输入有关测试目标的信息。
title: 目标和设置
feature: ab
uuid: 46d02e39-0c19-4da8-bdd8-48acb708831b
snippet: y
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 96%

---


# 目标和设置 {#goals-and-settings}

您可以在“目标和设置”页面上输入有关测试目标的信息。

可用的设置取决于您是使用 Target 还是 [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md) 作为数据源。

![“活动设置”对话框](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

## 活动设置 {#section_DCBDC354261F420EBD4B43EA34947BAC}

| 设置 | 描述 |
|--- |--- |
| 目的 | 键入一个可选目的。该目的可以是有助于您和您的团队成员识别营销活动的任何信息。 |
| 优先级 | 根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。<br>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<br>如果“管理”（默认）中未 [!UICONTROL 启用] 此选项，请指定优先级：低、中或高。 <br>要启用细粒度优先级，请单 [!UICONTROL 击“管理] ”> [!UICONTROL “报告]”，然后将“启用细粒度优先级”选项切换到“开启”位置。 <br>如果已启用此选项，请指定一个介于 0（= 低）到 999（= 高）之间值。<br>对于在以前的 Target Standard/Premium 版本中创建的活动，“低”优先级会转换为 0，“中”优先级会转换为 5，“高”优先级会转换为 10。您可以根据需要调整这些值。<br>注意：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。 |
| 持续时间 | 活动可以在获得批准时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。 |

## 报表设置 {#section_13119392051044FBA6387D9B3B1C43CF}

| 设置 | 描述 |
|--- |--- |
| 报表源 | 指定是从 Adobe Target 还是从 Adobe Analytics 收集数据。请参阅[将 Adobe Analytics 作为 Target 报表源](/help/c-integrating-target-with-mac/a4t/a4t.md)，以了解各种报表解决方案之间的差异以及每种解决方案的优点。当选择 Analytics 作为 Target 的报告源时，您可以选择一个 Analytics 报表包来接收 Target 活动数据。<br>要执行此操作，请先选择您的帐户绑定的任意 Analytics 公司，然后为活动选择合适的报表包。只有配置为连接至 Adobe Target 的报表包才可供选择。如果您看不到预期的报表包，请先注销 Adobe Experience Cloud，然后再重新登录以重试。如果报表包仍然没有出现在列表中，请联系客户关怀团队。<br>如果您在帐户设置中指定了报表源，则会使用指定的报表源，并且此设置不可见。<br>注意：在活动启动后，为保持报表一致，您不能更改报表源。 |
| 目标 | 选择访客为实现目标而执行的操作。例如，选择一个“转化”量度，然后设置相应参数以确定何时可取得成功。有关设置量度的更多信息，请参阅[设置量度](../../../c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)。<br>注意：如果将报表解决方案设置为 Analytics，则“转化”将是唯一可用的目标量度。不能选择 Analytics 量度作为目标。选择成功量度后，会显示一个选择器。使用此选择器，可选择成功量度的具体信息。<br>如果启用，“转化的预计值”字段（不适用于“页面得分”量度）会为您的目标提供一个值，但此值不适用于其他量度。通过此值，Target 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度（每位访客带来的收入、平均订单值、销售总额和订单总额），都会使用“每位访客带来的收入”进行估算。数据类型为货币。<br>实现活动目标后，访客可继续查看活动内容，除非该访客有资格参加更高优先级的活动。如果访客再次实现目标，则会计为另一次转化。请注意，这与 Target Classic 中的默认行为有所不同，如果访客再次查看测试，Target Classic 会在默认情况下将其计为新访客。 |
| 其他量度 | 创建其他成功量度。如果将报表解决方案设置为 Analytics，则此设置不可用。在这种情况下，会应用已为 Analytics 报表包定义的量度。 |
| 报表的受众 | 默认情况下，报表会显示所有符合条件的访客的结果信息。您可以添加报表受众，以仅显示与特定受众有关的信息。如果选择 Analytics 作为报表解决方案，则此设置不可用。将会应用为 Analytics 报表包定义的受众。 |

## 高级设置 {#section_E2FE441AFB324E498793ABB025ED9974}

高级设置适用于 A/B 测试的目标量度。

![“高级设置”菜单](/help/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>如果您将 Adobe Analytics 用作报表源，则设置会由 Analytics 服务器来管理。此时，高级设置选项将不可用。

![高级设置](/help/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 设置 | 描述 |
|--- |--- |
| 递增此量度之前必须实现哪些成功量度？ | 要仅在访客之前已实现了其他成功量度，然后又实现此量度时对其进行计数，请使用此选项。例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。通过“添加依赖项”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。要添加依赖项，请执行以下操作：<ul><li>添加其他量度后，单击高级设置。</li><li>单击“添加依赖项”选项：</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击“已实现”，以在“已实现”和“未实现”之间进行切换。</li><li>添加依赖项后，您可以编辑或删除依赖项。</li></ul> |
| 用户遇到此目标量度后会出现什么情况？ | 对于访客实现此目标量度后会出现的情况，提供了以下三个选项：<ul><li>选择递增计数并保持用户处于活动中，可指定递增计数的方式。</li><li>选择递增计数、释放用户并允许再次进入，可指定用户再次进入活动后看到的体验。</li><li>选择递增计数、释放用户并阻止再次进入，可指定用户将看到的活动内容的替代内容。</li></ul> |
| 如何递增计数？ | 递增计数的方式包括以下三种：<ul><li>每个参加者一次</li><li>每次展示时（页面刷新除外）)</li><li>每次展示时</li></ul> |

请参阅[成功量度](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)，以了解有关高级设置的更多信息。

## 其他元数据 {#section_2E8917BEFB954480A4206B9E9E917F80}

| 设置 | 描述 |
|---|---|
| 注释 | 键入有关您活动的任何信息，以便您自己或其他团队成员可随时使用这些信息。“注释”窗格的大小可以调整。 |

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 活动设置(3:02)教 ![程徽章](/help/assets/tutorial.png)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

(https://video.tv.adobe.com/v/17381?captions=chi_hans)

### 创建A/B测试(8:36)教 ![程徽章](/help/assets/tutorial.png)

以下视频演示了创建活动时三步引导式工作流中有哪些可用的活动设置。对目标和设置的讨论开始于 5:30。

* 在 Adobe Target 中创建 A/B 活动
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
