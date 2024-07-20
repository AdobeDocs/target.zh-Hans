---
keywords: 活动设置;A/B 目标和设置;报表设置;目标量度;成功量度;依赖的成功量度;高级设置;主要目标;其他量度;目的;优先级;持续时间;报表解决方案;目标;报表的受众;递增此量度之前必须实现哪些成功量度;用户遇到此目标量度后会出现什么情况;注释
description: 了解如何使用[!UICONTROL Goals and Settings]页面指定有关A/B活动目标的信息。
title: 如何在 [!DNL Target] A/B活动中指定目标和设置？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: b5f508d283390c859085d4ee52c582312085addc
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 35%

---

# 目标和设置

在[!DNL Adobe Target]中的[!UICONTROL Goals & Settings]页面中，您可以指定有关活动目标的信息。

可用的设置取决于您是使用Target还是[Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md)作为报表源。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

通过[!UICONTROL Goals & Settings]页的[!UICONTROL Activity Settings]部分，可配置以下选项：

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL Objective] | 键入一个可选目的。目标可以是任何有助于您和您的团队成员识别活动的信息。 |
| [!UICONTROL Priority] | 根据您的设置，[!UICONTROL Priority]的[!DNL Target] UI和选项会有所不同。 您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的旧版设置，也可以启用0到999的细粒度优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>如果未在[!UICONTROL Administration]中启用此选项（默认），请指定优先级： [!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]。<P>要启用[细粒度优先级](/help/main/administrating-target/reporting.md)，请单击[!UICONTROL Administration] > [!UICONTROL Reporting]，然后将[!UICONTROL Enable Fine-Grained Priorities]选项切换到“开”位置。 <P>如果已启用此选项，请指定一个从0到999的值： 0 = [!UICONTROL Low]和999 = [!UICONTROL High]。 <P>对于在以前的[!DNL Target]版本中创建的活动，[!UICONTROL Low]优先级将转换为0，[!UICONTROL Medium]优先级将转换为5，[!UICONTROL High]优先级将转换为10。 您可以根据需要调整这些值。<P>注意：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为0、5、10。 |
| 持续时间 | 活动可以在获得批准时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。 |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

通过[!UICONTROL Goals & Settings]页的[!UICONTROL Reporting Settings]部分，可配置以下选项：

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL Reporting Source] | 指定从以下来源收集解决方案数据：<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>如果在[帐户设置](/help/main/administrating-target/reporting.md)中指定了报表源，则会使用指定的报表源，并且此设置不可见。<P>在活动启动后，为保持报表一致，您不能更改报表源。<P>**Adobe Analytics**：请参阅[Adobe Analytics作为Target的报表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md)，了解报表解决方案之间的差异和各自的优势。 选择[!DNL Analytics]作为[!DNL Target]的报告源时，请选择一个[!DNL Analytics]报告包来接收[!DNL Target]活动数据。<P>要指定报表源，请先从您的帐户绑定的[!DNL Analytics]家公司中选择任意，然后为活动选择合适的报表包。 只有配置为连接到[!DNL Adobe Target]的报表包才可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到[!DNL Adobe Experience Cloud]以重试。 如果列表中仍缺少报表包，请联系客户关怀团队。<P><P>**Adobe Customer Journey Analytics**：有关[!DNL Adobe Customer Journey Analytics]与[!DNL Target]之间集成的详细信息，请参阅[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中报告。<P>使用手动流量拆分的A/B活动支持[!DNL Customer Journey Analytics]中的[!DNL Target]报表。 [!UICONTROL Auto-Target]和[!UICONTROL Auto-Allocate] A/B活动不能在[!DNL Customer Journey Analytics]中使用[!DNL Target]报表。 |
| [!UICONTROL Goal Metric] | 选择访客为实现目标而执行的操作。例如，选择一个[!UICONTROL Conversion]量度，然后设置用于确定何时获得成功的参数。 有关设置量度的更多信息，请参阅[设置量度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)。<P>注意：如果将报表解决方案设置为[!DNL Analytics]，则唯一可用的目标量度是[!UICONTROL Conversion]。 无法选择[!DNL Analytics]指标作为目标。 选择成功量度后，会显示一个选择器。使用此选择器，可选择成功量度的具体信息。<P>如果启用，[!UICONTROL Estimated Value of the Conversion]字段（不适用于[!UICONTROL Page Score]指标）会为您的目标提供一个值，但此值不适用于其他指标。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度（[!UICONTROL Revenue per Visitor]、[!UICONTROL Average Order Value]、[!UICONTROL Total Sales]和[!UICONTROL Orders]），估计使用[!UICONTROL Revenue per Visitor]。 数据类型为货币。<P>实现活动目标后，访客可继续查看活动内容，除非该访客有资格参加更高优先级的活动。 如果访客再次实现目标，则会计为另一次转化。这不同于[!DNL Target Classic]中的默认行为，如果访客再次看到该活动，则将其计为新访客。 |
| [!UICONTROL Additional Metrics] | 创建其他成功量度。 如果报表解决方案设置为[!DNL Analytics]，则此设置不可用。 在这种情况下，将应用为[!DNL Analytics]报表包定义的量度。 |
| [!UICONTROL Audiences for Reporting] | 默认情况下，报表会显示所有符合条件的访客的结果信息。您可以添加报表受众，以仅显示与特定受众相关的信息。 如果选择[!DNL Analytics]作为报表解决方案，则此设置不可用。 将应用为[!DNL Analytics]报表包定义的受众。 |

## 高级设置 {#section_E2FE441AFB324E498793ABB025ED9974}

通过[!UICONTROL Goals & Settings]页的[!UICONTROL Advanced Settings]部分，可配置以下选项：

要指定高级设置，请单击&#x200B;**[!UICONTROL More]**&#x200B;图标（垂直省略号），然后单击&#x200B;**[!UICONTROL Advanced Settings]**，如下图所示。

![“高级设置”菜单](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>如果您将 [!DNL Adobe Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。高级设置选项不可用。

![高级设置](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | 使用此选项可仅将之前达到不同成功量度的用户计为已达到成功量度。 例如，活动转化可能只有在转化之前访客点击了选件或访问了某个特定页面时才有效。 您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。 在使一个量度依赖于另一个量度之前，定义两个（或多个）成功量度。 [!UICONTROL Add Dependency]选项允许在已达到另一个成功量度或尚未达到时递增成功量度。 要添加依赖项，请执行以下操作：<ul><li>添加其他量度后，单击[!UICONTROL Advanced Settings]。</li><li>单击[!UICONTROL Add Dependency]选项：</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL Reached]以在[!UICONTROL Reached]和[!UICONTROL  Not Reached]之间切换设置。</li><li>添加依赖项后，您可以编辑或删除依赖项。</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | 对于访客实现此目标量度后会出现的情况，提供了以下三个选项：<ul><li>选择[!UICONTROL Increment Count & Keep User in Activity]以指定递增计数的方式。</li><li>选择[!UICONTROL Increment Count, Release User & Allow Reentry]以指定用户再次进入活动时看到的体验。</li><li>选择[!UICONTROL Increment Count, Release User & Bar from Reentry]以指定用户看到的内容而非活动内容。</li></ul> |
| [!UICONTROL How will the count be incremented?] | 递增计数的方式包括以下三种：<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)，以了解有关高级设置的更多信息。

## 其他元数据 {#section_2E8917BEFB954480A4206B9E9E917F80}

通过[!UICONTROL Goals & Settings]页的[!UICONTROL Other Metadata]部分，您可以指定任何有助于自己或其他团队成员随时掌握的活动相关信息。 注释窗格可调整大小。|

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 活动设置(3:02) ![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

(https://video.tv.adobe.com/v/17381?captions=chi_hans)

### 创建A/B测试(8:36) ![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了创建活动时三步引导式工作流中有哪些可用的活动设置。对目标和设置的讨论开始于 5:30。

* 在 Adobe Target 中创建 A/B 活动
* 使用手动拆分或自动流量分配来分配流量

>[!VIDEO](https://video.tv.adobe.com/v/17391)
