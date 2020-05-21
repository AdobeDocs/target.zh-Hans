---
keywords: Recommendations
description: 启用 Analytics 作为 Target 报表源 (A4T) 时，数据收集流程会发生一些更改。
title: 在将Adobe Analytics作为Adobe报告(A4T)的目标源实施之前
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 57%

---


# 实施之前{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

在决定使用此集成之前，请先查阅以下部分并考虑此集成对报表流程的影响：

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。可使用[此表单](https://www.adobe.com/go/audiences_cn)提交配置请求。

根据您是否要将重定向选件与 A4T 结合使用，此 A4T 集成要求您实施以下库版本（或更高版本）：

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js版本1.8.0
* [!DNL Adobe Target]（取决于您的实施）：at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics：appMeasurement.js 版本 1.7.0

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js版本2.3.0
* [!DNL Adobe Target]: at.js版本1.6.2

   **注意：** mbox.js 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 at.js。

* Adobe Analytics：appMeasurement.js 版本 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. 在进行本文中所述的实施更改后，现有活动不会受到影响。
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. 在实施之前，最好通读下面所述的过程。After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. 配置过程可能最多需要 5 个工作日。
* 创建 [!DNL Visitor ID service] 跨页面 [!DNL Visitor ID] 的共享 [!DNL Adobe Experience Cloud]。 Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* 必须 [!DNL Visitor ID service] 在您和页面代码 [!DNL Analytics] 之前 [!DNL Target] 执行该代码。 Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

After this integration is enabled, you will experience an additional 5-10 minutes of latency in [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务
* 已实施支持此集成的 [!DNL mbox.js] 版本。

When troubleshooting, be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## 客户端分析日志记录 {#client-side}

默认情况下，当 at.js、[!DNL Experience Cloud Visitor ID Service] 和 appMeasurement.js 均位于页面上时，只要页面中包含正确的补充 ID，[!DNL Analytics] 和 [!DNL Target] 就会在后端正确地将事件拼合到一起以用于报告和分析目的，如上所述。您无需管理和执行任何其他操作，A4T 即可正常运行。

但是，在某些情况下，您可能希望更好地控制何时以及如何将与 [!DNL Target] 相关的分析数据发送到 [!DNL Analytics] 进行报告。您可能已拥有可供内部使用的内部分析工具，而且您还希望通过内部分析产品将分析数据发送到 [!DNL Analytics]，以便贵组织的其他成员可以继续将 [!DNL Analytics] 用作可视化报表来源。有关更多信息，请参阅“Analytics for Target 实施”**&#x200B;中的[步骤 7：在所有网站页面上引用 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。
