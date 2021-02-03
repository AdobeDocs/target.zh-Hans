---
keywords: 推荐
description: 启用 Analytics 作为 Target 报表源 (A4T) 时，数据收集流程会发生一些更改。
title: 在将Analytics作为报告源(A4T)实施之前
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 52%

---


# 实施之前{#before-you-implement}

当启用[!DNL Analytics]作为[!DNL Target](A4T)的报告源时，数据收集过程中会发生一些更改。

在决定使用此集成之前，请先查阅以下部分并考虑此集成对报表流程的影响：

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。使用[Marketing Cloud集成设置表单](https://www.adobe.com/go/audiences_cn)请求设置。

根据您是否要将重定向选件与 A4T 结合使用，此 A4T 集成要求您实施以下库版本（或更高版本）：

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本1.8.0
* [!DNL Adobe Target]（取决于您的实施）：at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics：appMeasurement.js 版本 1.7.0

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本2.3.0
* [!DNL Adobe Target]:at.js版本1.6.2

   **注意：** mbox.js 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 at.js。

* Adobe Analytics：appMeasurement.js 版本 2.1

下载和部署说明列在[目标实施分析](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中。

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 当您选择使用[!DNL Analytics]作为活动源时，此集成在新报告上处于启用状态。 在进行本文中所述的实施更改后，现有活动不会受到影响。
* 将[!DNL Analytics]设置为[!DNL Target]的报告源的过程包括几个实施步骤，然后是设置步骤。 在实施之前，最好通读下面所述的过程。完成这些步骤后，您将准备好在为您启用[!DNL Analytics]后立即将其用作报告源。 配置过程可能最多需要 5 个工作日。
* [!DNL Visitor ID service]将跨[!DNL Adobe Experience Cloud]创建共享的[!DNL Visitor ID]。 尽管它不替换[!DNL Target] mboxPC id或[!DNL Audience Manager] UUID，但它确实替换了[!DNL Analytics]标识新访客的方式。 如果设置正确，还应通过其旧的[!DNL Analytics] ID识别返回的[!DNL Analytics]访客，以防止访客剪切。 同样，由于[!DNL Target] mboxPCid保持不变，因此升级到[!DNL Visitor ID service]时不会丢失[!DNL Target]访客用户档案数据。
* [!DNL Visitor ID service]必须在[!DNL Analytics]和[!DNL Target]页码之前执行。 确保`VisitorAPI.js`出现在所有其他[!DNL Experience Cloud]解决方案的标记上方。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，您将在[!DNL Analytics]中再经历5-10分钟的延迟。 这种延迟增加使得[!DNL Analytics]和[!DNL Target]的数据能够存储在同一次点击中，从而使您能够按页面和站点部分划分活动。

这一增长反映在所有[!DNL Analytics]服务和工具(包括实时流和实时报告)中，并适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

请注意，实施[!DNL Experience Cloud]访客ID服务后，延迟会增加开始，即使您尚未完全实现此集成也是如此。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活动用于传送内容或记录目标度量的所有[!DNL Target]调用必须具有相应的[!DNL Analytics]点击，该点击与A4T的相同补充ID共享才能正常工作。

包含[!DNL Analytics]和[!DNL Target]数据的点击包含补充数据ID。 您可以在[Adobe Experience Cloud调试器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)中将此ID看作`sdid`参数。 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务
* 已实施支持此集成的 [!DNL mbox.js] 版本。

当[疑难排解](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)时，请确保确认在[!DNL Analytics]点击中存在补充ID。

## 客户端分析日志记录 {#client-side}

默认情况下，当 at.js、[!DNL Experience Cloud Visitor ID Service] 和 appMeasurement.js 均位于页面上时，只要页面中包含正确的补充 ID，[!DNL Analytics] 和 [!DNL Target] 就会在后端正确地将事件拼合到一起以用于报告和分析目的，如上所述。您无需管理和执行任何其他操作，A4T 即可正常运行。

但是，在某些情况下，您可能希望更好地控制何时以及如何将与 [!DNL Target] 相关的分析数据发送到 [!DNL Analytics] 进行报告。您可能已拥有可供内部使用的内部分析工具，而且您还希望通过内部分析产品将分析数据发送到 [!DNL Analytics]，以便贵组织的其他成员可以继续将 [!DNL Analytics] 用作可视化报表来源。有关更多信息，请参阅“Analytics for Target 实施”**&#x200B;中的[步骤 7：在所有网站页面上引用 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

## 共享受众

在填写[Marketing Cloud集成设置表单](https://www.adobe.com/go/audiences)时，请注意下列与“[!UICONTROL 请求设置]的[!UICONTROL 共享受众]选项相关的重要信息？”

![请求表单](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

当您请求[!UICONTROL 共享受众]时，您启用[!UICONTROL 目标]和[!UICONTROL Adobe Audience Manager](AAM)以共享信息，在本例中为受众。

>[!IMPORTANT]
>
>[!UICONTROL 目标]与AAM之间的这种集成会带来额外成本。 AAM中的每次[!UICONTROL 目标]调用将向您收费。
