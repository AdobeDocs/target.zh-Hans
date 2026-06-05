---
keywords: 活动设置;体验定位目标和设置;XT 目标和设置;体验定位;报表设置;目标量度;成功量度;依赖的成功量度;高级设置;主要目标;其他量度;目的;优先级;持续时间;报表解决方案;目标;报表的受众;递增此量度之前必须实现哪些成功量度;用户遇到此目标量度后会出现什么情况;注释
description: 了解如何使用 [!DNL Adobe Target] 中的[!UICONTROL 目标和设置]页面指定有关[!UICONTROL 体验定位] (XT)活动目标的信息。
title: 如何在[!UICONTROL 体验定位]活动中指定[!UICONTROL 目标和设置]？
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
TQID: https://experienceleague.adobe.com/vlpJSJ4Z6mxQI-D8UyUPEXHVWKfR54l89uoxULd2oD0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1285
ht-degree: 42%

---

# [!UICONTROL 体验定位] (XT)活动中的目标和设置

在[!UICONTROL 目标和设置]页面中输入有关测试目标的信息：

* [!UICONTROL 活动设置]
* [!UICONTROL 报表设置]
* [!UICONTROL 其他元数据]

可用的设置取决于您是使用[!DNL Target]还是[!DNL Analytics]作为报表源。

## [!UICONTROL 活动设置] {#section_DCBDC354261F420EBD4B43EA34947BAC}

以下设置可供使用：

### [!UICONTROL 目标]

键入一个可选目的。 该目的可以是有助于您和您的团队成员识别营销活动的任何信息。

### [!UICONTROL 优先级]

根据您的设置，[!UICONTROL 优先级]的[!DNL Target] UI和选项会有所不同。 您可以使用[!UICONTROL 低]、[!UICONTROL Medium]或[!UICONTROL 高]的旧设置，也可以启用0到999的细粒度优先级。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。 如果将两个或更多活动分配给位置，则会显示具有最高优先级的活动。

如果未在[!UICONTROL 管理]中启用此选项（默认值），请指定优先级： [!UICONTROL 低]、[!UICONTROL Medium]或[!UICONTROL 高]。

要启用细粒度优先级，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 报告]**，然后将[!UICONTROL 启用细粒度优先级]选项切换到“开”位置。

如果已启用此选项，请指定从0到999的值：

* 0 = 低
* 999 = 高

对于在以前版本的[!DNL Target]中创建的活动，[!UICONTROL 低]优先级已转换为0，[!UICONTROL Medium]已转换为5，[!UICONTROL 高]已转换为10。 您可以根据需要调整这些值。

>[!NOTE]
>
>在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。

### [!UICONTROL 持续时间]

活动可以在获得批准时开始，或者您也可以设置特定的日期和时间。 同样，活动可以在停用时结束，或者您也可以设置活动结束的日期和时间。 时间选择器使用24小时时钟，00:00为午夜。 时区设置为在浏览器中配置的时区。 要使用不同的时区，请将浏览器设置为其他时区并重新启动浏览器。

## [!UICONTROL 报表设置] {#section_13119392051044FBA6387D9B3B1C43CF}

以下设置可供使用：

### [!UICONTROL 报告Source]

指定从以下来源收集解决方案数据：

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

如果在[帐户设置](/help/main/administrating-target/reporting.md)中指定了报表解决方案，则会使用指定的解决方案，并且此设置不可见。

在活动启动后，为保持报表一致，您不能更改报表源。

**[!DNL Adobe Analytics]**：查看[[!DNL Adobe Analytics] 作为 [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的报告来源，了解报告解决方案之间的差异和各自的优势。

选择[!DNL Analytics]作为[!DNL Target] (A4T)的报表源时，请选择一个[!DNL Analytics]报表包以接收[!DNL Target]活动数据。 为此，请先从您的帐户绑定的[!DNL Analytics]家公司中选择任意，然后为活动选择合适的报表包。 只有配置为连接到[!DNL Target]的报表包才可供选择。 如果您没有看到预期的报表包，请先尝试注销并重新登录到[!DNL Adobe Experience Cloud]以重试。 如果列表中仍缺少报表包，请联系[客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

[!DNL Analytics for Target] (A4T)需要跟踪服务器才能正确报告结果。 默认跟踪服务器显示在[!UICONTROL 跟踪服务器]字段中。 如果使用多个跟踪服务器，请确保在此字段中包含正确的跟踪服务器。 有关详细信息，请参阅[使用Analytics跟踪服务器](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)。

**[!DNL Adobe Customer Journey Analytics]**：有关[!DNL Adobe Customer Journey Analytics]与[!DNL Target]之间集成的详细信息，请参阅[[!DNL Target] 在 [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)中报告。

### [!UICONTROL 目标量度]

选择访客为实现目标而执行的操作。 例如，选择一个[!UICONTROL 转化]量度，然后设置用于确定何时获得成功的参数。

有关设置量度的更多信息，请参阅[设置量度](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB)。

>[!NOTE]
>
>如果报表解决方案设置为[!DNL Analytics]，则唯一可用的目标量度是[!UICONTROL 转化]。 无法选择[!DNL Analytics]指标作为目标。

选择成功量度后，会显示一个选择器。 使用此选择器，可选择成功量度的具体信息。

如果启用，[!UICONTROL 转化的预计值]字段（不适用于[!UICONTROL 页面得分]量度）会为您的目标提供一个值，但此值不适用于其他量度。 通过此值，[!DNL Target] 可以计算出预计收入提升。 此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。 对于所有收入量度（[!UICONTROL 每位访客带来的收入]、[!UICONTROL 平均订单值]、[!UICONTROL 总销售额]和[!UICONTROL 订单数]），估计将使用[!UICONTROL 每位访客带来的收入]。 数据类型为货币。

实现活动目标后，访客可继续查看活动内容，除非该访客有资格参加更高优先级的活动。 如果访客再次实现目标，则会计为另一次转化。 此行为与[!DNL Target Classic]中的默认行为不同，后者在访客再次看到测试时将访客计为新访客。

### [!UICONTROL 其他量度]

创建其他成功量度。

如果报表解决方案设置为[!DNL Analytics]，则此设置不可用。 在这种情况下，将应用为[!DNL Analytics]报表包定义的量度。

### [!UICONTROL 报表受众]

默认情况下，报表会显示所有符合条件的访客的结果信息。 您可以添加报表受众，以仅显示与特定受众有关的信息。

如果选择[!DNL Analytics]作为报表解决方案，则此设置不可用。 将应用为[!DNL Analytics]报表包定义的受众。

## [!UICONTROL 其他Meta数据]

键入任何对您自己或其他团队成员有用的活动相关信息。 [!UICONTROL 注释]窗格可调整大小。

## [!UICONTROL 高级设置] {#section_E2FE441AFB324E498793ABB025ED9974}

高级设置适用于[!UICONTROL 体验定位]目标量度。

![高级设置](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>如果您将 [!DNL Analytics] 用作报表源，则设置会由 [!DNL Analytics] 服务器来管理。 [!UICONTROL 高级设置]选项不可用。

以下设置可供使用：

### [!UICONTROL 在递增此量度之前必须实现哪个成功量度？]

使用此选项可仅在访客之前达到不同的成功量度时将访客计为已达到成功量度。 例如，仅当访客在转化之前先点击了选件或访问了某个特定页面时，测试转化才可能有效。

您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。

在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。

通过“[!UICONTROL 添加依赖项]”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。

要添加依赖项，请执行以下操作：

1. 添加其他量度后，单击&#x200B;**[!UICONTROL 高级设置]**。
2. 单击&#x200B;**[!UICONTROL 添加依赖项]**：

   ![“添加依赖项”链接](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. 将所需量度从左侧窗格拖放到右侧窗格中，然后单击&#x200B;**[!UICONTROL 已实现]**，以在[!UICONTROL 已实现]和[!UICONTROL 未实现]之间进行切换。

   ![“添加量度依赖关系”对话框](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

添加依赖项后，您可以编辑或删除依赖项。

### [!UICONTROL 用户遇到此目标量度后会出现什么情况？]

对于访客实现此目标量度后会出现的情况，提供了以下三个选项：

* 选择[!UICONTROL 递增计数并保持用户处于活动中]，可指定递增计数的方式。
* 选择[!UICONTROL 递增计数、释放用户并允许再次进入]，可指定用户再次进入活动后看到的体验。
* 选择[!UICONTROL 递增计数、释放用户并阻止再次进入]，以指定用户看到的内容而非活动内容。

请参阅[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)，以了解有关高级设置的更多信息。

## 培训视频：活动设置(3:02)

以下视频包含有关活动设置的信息。

* 输入活动的目的
* 设置活动的优先级
* 计划活动的开始和结束时间
* 添加报表受众以创建报表筛选器
* 输入活动的注释

>[!VIDEO](https://video.tv.adobe.com/v/17381)
