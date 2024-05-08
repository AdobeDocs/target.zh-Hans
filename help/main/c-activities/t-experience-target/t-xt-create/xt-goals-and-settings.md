---
keywords: 活动设置;体验定位目标和设置;XT 目标和设置;体验定位;报表设置;目标量度;成功量度;依赖的成功量度;高级设置;主要目标;其他量度;目的;优先级;持续时间;报表解决方案;目标;报表的受众;递增此量度之前必须实现哪些成功量度;用户遇到此目标量度后会出现什么情况;注释
description: 了解如何使用 [!UICONTROL Goals & Settings] 页面位置 [!DNL Adobe Target] 要指定有关目标的信息 [!UICONTROL Experience Targeting] (XT)活动。
title: 如何指定 [!UICONTROL Goals & Settings] 在 [!UICONTROL Experience Targeting] 活动？
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 39%

---

# 中的目标和设置 [!UICONTROL Experience Targeting] (XT)活动

此 [!UICONTROL Goals & Settings] 页面是输入有关测试目标信息的位置：

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

可用的设置取决于您是否使用 [!DNL Target] 或 [!DNL Analytics] 作为报表源。

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下设置可供使用：

### [!UICONTROL Objective]

键入一个可选目的。该目的可以是有助于您和您的团队成员识别营销活动的任何信息。

### [!UICONTROL Priority]

根据您的设置， [!DNL Target] UI和选项 [!UICONTROL Priority] 不同。 您可以使用旧版设置 [!UICONTROL Low]， [!UICONTROL Medium]，或 [!UICONTROL High]或者，您可以启用0到999的细粒度优先级。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配给位置，则会显示具有最高优先级的活动。

如果未在中启用此选项 [!UICONTROL Administration] （默认），指定优先级： [!UICONTROL Low]， [!UICONTROL Medium]，或 [!UICONTROL High].

要启用细粒度优先级，请单击 **[!UICONTROL Administration]** > **[!UICONTROL Reporting]**，然后切换 [!UICONTROL Enable Fine-Grained Priorities] 选项到“开”位置。

如果已启用此选项，请指定从0到999的值：

* 0 = 低
* 999 = 高

对于在以前版本中创建的活动 [!DNL Target]， [!UICONTROL Low] 优先级已转换为0， [!UICONTROL Medium] 转换为5，并且 [!UICONTROL High] 转换为10。 您可以根据需要调整这些值。

>[!NOTE]
>
>在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。

### [!UICONTROL Duration]

活动可以在获得批准时开始，或者您也可以设置特定的日期和时间。同样，活动可以在停用时结束，或者您也可以设置活动结束的日期和时间。 时间选择器使用的是 24 小时制时钟，其中 00:00 表示午夜。时区设置为在浏览器中配置的时区。要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

以下设置可供使用：

### [!UICONTROL Reporting Source]

指定从以下来源收集解决方案数据：

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

如果您在中指定了报表解决方案，则 [帐户设置](/help/main/administrating-target/reporting.md)，则使用指定的解决方案，并且此设置不可见。

在活动启动后，为保持报表一致，您不能更改报表源。

**[!DNL Adobe Analytics]**：请参阅 [[!DNL Adobe Analytics] 作为的报表源 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 了解报表解决方案之间的差异和各自的优势。

选择时 [!DNL Analytics] 作为的报表源 [!DNL Target] (A4T)，则选择 [!DNL Analytics] 要接收的报表包 [!DNL Target] 活动数据。 要执行此操作，请先从任一 [!DNL Analytics] 您的帐户绑定的公司，然后为活动选择适当的报表包。 仅限配置为连接到的报表包 [!DNL Target] 可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到 [!DNL Adobe Experience Cloud] 再试一次。 如果列表中仍缺少报表包，请联系 [客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T)需要跟踪服务器才能正确报告结果。 默认跟踪服务器显示在 [!UICONTROL Tracking Server] 字段。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 请参阅 [使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 以了解更多信息。

**[!DNL Adobe Customer Journey Analytics]**：请参阅 [[!DNL Target] 报告 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) 有关集成的详细信息，请参阅 [!DNL Adobe Customer Journey Analytics] 和 [!DNL Target].

### [!UICONTROL Goal Metric]

选择访客为实现目标而执行的操作。例如，选择 [!UICONTROL Conversion] 量度，然后设置用于确定何时获得成功的参数。

有关设置量度的更多信息，请参阅[设置量度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB)。

>[!NOTE]
>
>如果报表解决方案设置为 [!DNL Analytics]，唯一可用的目标量度是 [!UICONTROL Conversion]. [!DNL Analytics] 不能选择量度作为目标。

选择成功量度后，会显示一个选择器。使用此选择器，可选择成功量度的具体信息。

如果启用， [!UICONTROL Estimated Value of the Conversion] 字段(不可用于 [!UICONTROL Page Score] 量度)为您的目标提供一个值，但此值不适用于其他量度。 通过此值，[!DNL Target] 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。对于所有收入量度([!UICONTROL Revenue per Visitor]， [!UICONTROL Average Order Value]， [!UICONTROL Total Sales]、和 [!UICONTROL Orders])，则估计使用 [!UICONTROL Revenue per Visitor]. 数据类型为货币。

实现活动目标后，访客可继续查看活动内容，除非该访客有资格参加更高优先级的活动。 如果访客再次实现目标，则会计为另一次转化。此行为不同于中的默认行为 [!DNL Target Classic]，如果访客再次看到测试，会将访客计为新访客。

### [!UICONTROL Additional Metrics]

创建其他成功量度。

如果将报表解决方案设置为，则此设置不可用 [!DNL Analytics]. 在本例中，为定义的量度 [!DNL Analytics] 报表包中所有规则都适用的URL区域。

### [!UICONTROL Audiences for Reporting]

默认情况下，报表会显示所有符合条件的访客的结果信息。您可以添加报表受众，以仅显示与特定受众有关的信息。

如果选择，则此设置不可用 [!DNL Analytics] 作为您的报表解决方案。 为定义的受众 [!DNL Analytics] 报表包中所有规则都适用的URL的区域。

## [!UICONTROL Other Meta Data]

键入任何对您自己或其他团队成员有用的活动相关信息。 此 [!UICONTROL Notes] 窗格可调整大小。

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

高级设置适用于 [!UICONTROL Experience Targeting] 目标量度。

![高级设置](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>如果您将 [!DNL Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。此 [!UICONTROL Advanced Settings] 选项不可用。

以下设置可供使用：

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

使用此选项可仅在访客之前达到不同的成功量度时将访客计为已达到成功量度。 例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。

您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。

在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。

此 [!UICONTROL Add Dependency] 选项允许在已达到另一个成功量度或尚未达到时递增成功量度。

要添加依赖项，请执行以下操作：

1. 添加其他量度后，单击 **[!UICONTROL Advanced Settings]**.
2. 单击 **[!UICONTROL Add Dependency]**：

   ![“添加依赖项”链接](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. 将所需量度从左窗格拖放到右窗格中，然后单击 **[!UICONTROL Reached]** 以切换设置 [!UICONTROL Reached] 和 [!UICONTROL Not Reached].

   ![“添加量度依赖关系”对话框](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

添加依赖项后，您可以编辑或删除依赖项。

### [!UICONTROL What will happen after a user encounters this goal metric?]

对于访客实现此目标量度后会出现的情况，提供了以下三个选项：

* 选择 [!UICONTROL Increment Count & Keep User in Activity] 以指定计数的递增方式。
* 选择 [!UICONTROL Increment Count, Release User & Allow Reentry] 以指定用户再次进入活动时看到的体验。
* 选择 [!UICONTROL Increment Count, Release User & Bar from Reentry] 以指定用户看到的内容而非活动内容。

请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)，以了解有关高级设置的更多信息。

## 培训视频：活动设置 (3:02)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381)
