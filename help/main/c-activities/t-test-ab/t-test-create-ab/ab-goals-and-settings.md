---
keywords: 活动设置;A/B 目标和设置;报表设置;目标量度;成功量度;依赖的成功量度;高级设置;主要目标;其他量度;目的;优先级;持续时间;报表解决方案;目标;报表的受众;递增此量度之前必须实现哪些成功量度;用户遇到此目标量度后会出现什么情况;注释
description: 了解如何使用 [!UICONTROL 目标和设置] 页面位置 [!DNL Adobe Target] 指定有关A/B活动目标的信息。
title: 如何在中指定目标和设置 [!DNL Target] A/B活动？
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 52%

---

# 目标和设置

此 [!UICONTROL 目标和设置] 页面位置 [!DNL Adobe Target] 在这里，您可以指定有关活动目标的信息。

可用的设置取决于您使用的是Target还是 [分析](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 作为报表源。

## [!UICONTROL 活动设置] {#section_DCBDC354261F420EBD4B43EA34947BAC}

此 [!UICONTROL 活动设置] 的部分 [!UICONTROL 目标和设置] 页面可配置以下选项：

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL 目标] | 键入一个可选目的。目标可以是任何有助于您和您的团队成员识别活动的信息。 |
| [!UICONTROL 优先级] | 根据您的设置， [!DNL Target] UI和选项 [!UICONTROL 优先级] 不同。 您可以使用旧版设置 [!UICONTROL 低]， [!UICONTROL 中]，或 [!UICONTROL 高]或者，您可以启用0到999的细粒度优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>如果未在中启用此选项 [!UICONTROL 管理] （默认），指定优先级： [!UICONTROL 低]， [!UICONTROL 中]，或 [!UICONTROL 高].<P>要启用 [细粒度优先级](/help/main/administrating-target/reporting.md)，单击 [!UICONTROL 管理] > [!UICONTROL 报表]，然后切换 [!UICONTROL 启用细粒度优先级] 选项到“开”位置。 <P>如果已启用此选项，请指定从0到999的值： 0 = [!UICONTROL 低] 和999 = [!UICONTROL 高]. <P>对于在以前版本中创建的活动 [!DNL Target]， [!UICONTROL 低] 优先级已转换为0， [!UICONTROL 中] 转换为5，并且 [!UICONTROL 高] 转换为10。 您可以根据需要调整这些值。<P>注意：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。 |
| 持续时间 | 活动可以在获得批准时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置特定的日期和时间。时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。 |

## [!UICONTROL 报表设置] {#section_13119392051044FBA6387D9B3B1C43CF}

此 [!UICONTROL 报表设置] 的部分 [!UICONTROL 目标和设置] 页面可配置以下选项：

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL 报表源] | 指定是否从收集数据 [!DNL Adobe Target] 或从 [!DNL Adobe Analytics]. 请参阅[将 Adobe Analytics 作为 Target 报表源](/help/main/c-integrating-target-with-mac/a4t/a4t.md)，以了解各种报表解决方案之间的差异以及每种解决方案的优点。选择时 [!DNL Analytics] 作为的报表源 [!DNL Target]，您选择 [!DNL Analytics] 要接收的报表包 [!DNL Target] 活动数据。<P>要指定报表源，请先从以下任意选项中选择 [!DNL Analytics] 您的帐户绑定的公司，然后为活动选择适当的报表包。 仅限配置为连接到的报表包 [!DNL Adobe Target] 可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到 [!DNL Adobe Experience Cloud] 再试一次。 如果列表中仍缺少报表包，请联系客户关怀团队。<P>如果您在帐户设置中指定了报表源，则会使用指定的报表源，并且此设置不可见。<P>注意：在活动启动后，为保持报表一致，您不能更改报表源。 |
| [!UICONTROL 目标量度] | 选择访客为实现目标而执行的操作。例如，选择 [!UICONTROL 转化] 量度，然后设置用于确定何时获得成功的参数。 有关设置量度的更多信息，请参阅[设置量度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md)。<P>注意：如果将报表解决方案设置为 [!DNL Analytics]，唯一可用的目标量度是 [!UICONTROL 转化]. [!DNL Analytics]不能选择 量度作为目标。选择成功量度后，会显示一个选择器。使用此选择器，可选择成功量度的具体信息。<P>如果启用， [!UICONTROL 转化的预计值] 字段(不适用于 [!UICONTROL 页面得分] 量度)为您的目标提供一个值，但此值不适用于其他量度。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度([!UICONTROL 每位访客带来的收入]， [!UICONTROL 平均订单价值]， [!UICONTROL 销售总额]、和 [!UICONTROL 订购])，则估计使用 [!UICONTROL 每位访客带来的收入]. 数据类型为货币。<P>实现活动目标后，访客可继续查看活动内容，除非该访客有资格参加更高优先级的活动。 如果访客再次实现目标，则会计为另一次转化。这与中的默认行为不同 [!DNL Target Classic]，如果访客再次看到活动，则将其计为新访客。 |
| [!UICONTROL 其他量度] | 创建其他成功量度。如果将报表解决方案设置为，则此设置不可用 [!DNL Analytics]. 在本例中，为定义的量度 [!DNL Analytics] 报表包中所有规则都适用的URL区域。 |
| [!UICONTROL 报表的受众] | 默认情况下，报表会显示所有符合条件的访客的结果信息。您可以添加报表受众，以仅显示与特定受众相关的信息。 如果选择，则此设置不可用 [!DNL Analytics] 作为您的报表解决方案。 为定义的受众 [!DNL Analytics] 报表包中所有规则都适用的URL的区域。 |

## 高级设置 {#section_E2FE441AFB324E498793ABB025ED9974}

此 [!UICONTROL 高级设置] 的部分 [!UICONTROL 目标和设置] 页面可配置以下选项：

要指定高级设置，请单击 **[!UICONTROL 更多]** 图标（垂直省略号），然后单击 **[!UICONTROL 高级设置]**，如下图所示。

![“高级设置”菜单](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>如果您将 [!DNL Adobe Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。高级设置选项不可用。

![高级设置](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| 设置 | 描述 |
|--- |--- |
| [!UICONTROL 递增此量度之前必须实现哪些成功量度？] | 使用此选项可仅将之前达到不同成功量度的用户计为已达到成功量度。 例如，活动转化可能只有在转化之前访客点击了选件或访问了某个特定页面时才有效。 您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。在使一个量度依赖于另一个量度之前，定义两个（或多个）成功量度。 通过“[!UICONTROL 添加依赖项]”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。要添加依赖项，请执行以下操作：<ul><li>添加其他量度后，单击[!UICONTROL 高级设置]。</li><li>单击[!UICONTROL 添加依赖项]选项：</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL 已实现]，以在[!UICONTROL 已实现]和[!UICONTROL 未实现]之间进行切换。</li><li>添加依赖项后，您可以编辑或删除依赖项。</li></ul> |
| [!UICONTROL 用户遇到此目标量度后会出现什么情况？] | 对于访客实现此目标量度后会出现的情况，提供了以下三个选项：<ul><li>选择[!UICONTROL 递增计数并保持用户处于活动中]，可指定递增计数的方式。</li><li>选择[!UICONTROL 递增计数、释放用户并允许再次进入]，可指定用户再次进入活动后看到的体验。</li><li>选择[!UICONTROL 递增计数、释放用户并阻止再次进入]，可指定用户将看到的活动内容的替代内容。</li></ul> |
| [!UICONTROL 如何递增计数？] | 递增计数的方式包括以下三种：<ul><li>[!UICONTROL 每个参加者一次]</li><li>[!UICONTROL 每次展示时（页面刷新除外）)]</li><li>[!UICONTROL 每次展示时]</li></ul> |

请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)，以了解有关高级设置的更多信息。

## 其他元数据 {#section_2E8917BEFB954480A4206B9E9E917F80}

此 [!UICONTROL 其他元数据] 的部分 [!UICONTROL 目标和设置] 页面可让您指定有关您的活动的任何信息，这些信息有助于您自己或其他团队成员随时掌握。 注释窗格可调整大小。|

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
