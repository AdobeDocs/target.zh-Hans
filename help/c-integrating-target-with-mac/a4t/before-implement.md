---
keywords: 推荐
description: 启用 Analytics 作为 Target 报表源 (A4T) 时，数据收集流程会发生一些更改。
title: 实施之前 将 Adobe Analytics 作为 Adobe Target 报表源 (A4T)
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 实施之前{#before-you-implement}

启用 Analytics 作为 Target 报表源 (A4T) 时，数据收集流程会发生一些更改。

在决定使用此集成之前，请先查阅以下部分并考虑此集成对报表流程的影响：

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用 A4T 之前，您需要请求对您的帐户进行配置，以便使用该集成。可使用[此表单](https://www.adobe.com/go/audiences)提交配置请求。

根据您是否要将重定向选件与 A4T 结合使用，此 A4T 集成要求您实施以下库版本（或更高版本）：

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* Experience Cloud 访客 ID 服务：visitorAPI.js 版本 1.8.0
* Adobe Target（取决于您的实施）：at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics：appMeasurement.js 版本 1.7.0

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* Experience Cloud 访客 ID 服务：visitorAPI.js 版本 2.3.0
* Adobe Target：at.js 版本 1.6.2

   **注意：** mbox.js 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 at.js。

* Adobe Analytics：appMeasurement.js 版本 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 如果您选择使用 Analytics 作为报表源，则会为新活动启用此集成。在进行本文中所述的实施更改后，现有活动不会受到影响。
* 将 Analytics 设置为 Target 报表源的过程包含若干实施步骤，之后还需执行一个配置步骤。在实施之前，最好通读下面所述的过程。完成这些步骤后，一经启用 Analytics for Target，您便可以使用 Analytics 作为报表源。配置过程可能最多需要 5 个工作日。
* 访客 ID 服务会创建一个在 Experience Cloud 中共享的访客 ID。虽然此 ID 不会取代 Target mboxPC ID 或 Audience Manager UUID，但它会替换 Analytics 标识新访客的方式。如果设置正确，Analytics 旧访客也应该由他们的旧 Analytics ID 来标识，以防止访客发生冲突。同样，由于 Target mboxPC ID 保持不变，因此在您升级到访客 ID 服务后，不会丢失任何 Target 访客配置文件数据。
* 必须先执行访客 ID 服务，然后再执行 Analytics 和 Target 页面代码。请确保 `VisitorAPI.js` 显示在所有其他 Experience Cloud 产品所对应的标记上方。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，您将在 Adobe Analytics 中经历 5 到 10 分钟的额外滞后。这额外增加的滞后允许您将 Analytics 和 Target 中的数据存储到同一个点击上，从而允许您按页面和网站部分来细分测试。

增加的滞后在所有的 Adobe Analytics 服务和工具（包括实时流和实时报表）中都有所体现，且适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于转化量度的当前数据、最终数据和数据馈送，所有的点击都会额外延迟 5 至 7 分钟的时间。

请注意，实施 Experience Cloud 访客 ID 服务后，即使您尚未完全实施此集成，也会开始增加滞后。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

为使 A4T 正常运行，A4T 活动用于交付内容或记录目标量度的所有 Target 调用必须具有一个对应的 Analytics 点击，且此点击共享同一个补充 ID。

包含 Analytics 和 Target 数据的点击具有一个补充数据 ID。You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务
* 已实施支持此集成的 [!DNL mbox.js] 版本。

进行故障诊断时，请务必确认 Analytics 点击中存在补充 ID。

## 客户端分析日志记录 {#client-side}

默认情况下，当 at.js、[!DNL Experience Cloud Visitor ID Service] 和 appMeasurement.js 均位于页面上时，只要页面中包含正确的补充 ID，[!DNL Adobe Analytics] 和 [!DNL Target] 就会在后端正确地将事件拼合到一起以用于报告和分析目的，如上所述。您无需管理和执行任何其他操作，A4T 即可正常运行。

但是，在某些情况下，您可能希望更好地控制何时以及如何将与 [!DNL Target] 相关的分析数据发送到 [!DNL Analytics] 进行报告。您可能已拥有可供内部使用的内部分析工具，而且您还希望通过内部分析产品将分析数据发送到 [!DNL Analytics]，以便贵组织的其他成员可以继续将 [!DNL Analytics] 用作可视化报表来源。有关更多信息，请参阅“Analytics for Target 实施”**&#x200B;中的[步骤 7：在所有网站页面上引用 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。
