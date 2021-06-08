---
keywords: 推荐
description: 了解Analytics for [!DNL Target] (A4T)的实施要求以及在实施此集成之前应考虑的事项。
title: 实施A4T之前，我应该了解什么？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 8c0cdfbe02e9159cf8348e68a782a4268a8df687
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 在使用at.js实施Analytics for Target(A4T)之前

启用[!DNL Adobe Analytics]作为[!DNL Adobe Target](A4T)的报表源时，数据收集流程会发生一些更改。

在您决定使用此集成之前，请查看以下部分并考虑对报表流程的影响。

>[!NOTE]
>
>本文仅适用于at.js实施。

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用A4T之前，您必须请求配置您的帐户以进行集成。 使用[Marketing Cloud集成配置表单](https://www.adobe.com/go/audiences_cn)请求进行配置。

根据您是否要将重定向选件与 A4T 结合使用，此 A4T 集成要求您实施以下库版本（或更高版本）：

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本1.8.0
* [!DNL Adobe Target]（取决于您的实施）：at.js 版本 0.9.1 或 mbox.js 版本 61
* Adobe Analytics：appMeasurement.js 版本 1.7.0

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本2.3.0

   **注意：**  at.js 1.8.0或更高版本不再适用于2.5.0以前的访客API版本，因此无法传递(AAM) [!DNL Adobe Audeince Manager] 参数。

* [!DNL Adobe Target]: at.js 1.6.2 版

   **注意**:mbox.js库不支持将重定向选件与A4T配合使用。您的实施必须使用 at.js。

* Adobe Analytics：appMeasurement.js 版本 2.1

[Analytics for Target实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)中列出了下载和部署说明。

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 当您选择使用[!DNL Analytics]作为报表源时，将在新活动上启用此集成。 在进行本文中所述的实施更改后，现有活动不会受到影响。
* 将[!DNL Analytics]设置为[!DNL Target]报表源的过程包括几个实施步骤，然后是一个设置步骤。 在实施之前，最好通读下面所述的过程。完成这些步骤后，您就可以在为您启用[!DNL Analytics]报表源时，将其用作报表源。 配置过程可能最多需要 5 个工作日。
* [!DNL Visitor ID service]会在[!DNL Adobe Experience Cloud]中创建共享的[!DNL Visitor ID]。 尽管它不会替换[!DNL Target] mboxPC ID或[!DNL Audience Manager] UUID，但会替换[!DNL Analytics]标识新访客的方式。 如果设置正确，则还应通过旧的[!DNL Analytics] ID来识别回访的[!DNL Analytics]访客。 同样，由于[!DNL Target] mboxPCid保持不变，因此升级到[!DNL Visitor ID service]时，没有[!DNL Target]访客配置文件数据丢失。
* [!DNL Visitor ID service]必须在[!DNL Analytics]和[!DNL Target]页面代码之前执行。 确保`VisitorAPI.js`显示在所有其他[!DNL Experience Cloud]解决方案的标记上方。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，您将在[!DNL Analytics]中经历额外5到10分钟的延迟。 这种延迟增加允许将[!DNL Analytics]和[!DNL Target]中的数据存储在同一点击中，从而允许您按页面和网站区域划分活动。

这一增长反映在所有[!DNL Analytics]服务和工具（包括实时流和实时报告）中，并适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于有关转化量度、完成数据和数据馈送的当前数据，所有点击都会额外延迟5到7分钟。

实施[!DNL Experience Cloud]访客ID服务后，即使您尚未完全实施此集成，滞后也会开始增加。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活动用于交付内容或记录目标量度的所有[!DNL Target]调用必须具有相应的[!DNL Analytics]点击，该点击与A4T的补充ID共享才能正常工作。

包含[!DNL Analytics]和[!DNL Target]数据的点击包含补充数据ID。 您可以在[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)中将此ID看作`sdid`参数。 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务
* 已实施支持此集成的 [!DNL mbox.js] 版本。

当[疑难解答](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)时，请务必确认[!DNL Analytics]点击中存在补充ID。

## 客户端分析日志记录 {#client-side}

如果at.js、[!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位于页面上，则只要页面中包含正确的补充ID，[!DNL Analytics]和[!DNL Target]就会在后端正确地将事件拼合到一起以用于报告和分析目的。 您无需管理和执行任何其他操作，A4T即可正常运行。

在某些情况下，您可能希望更好地控制何时以及如何将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]以进行报告。 您可能已拥有一个内部分析工具，可用于内部目的。 但是，您还希望通过内部分析产品将分析数据发送到[!DNL Analytics]，以便贵组织的其他成员可以继续将[!DNL Analytics]用作可视化报表源。 有关更多信息，请参阅“Analytics for Target 实施”**&#x200B;中的[步骤 7：在所有网站页面上引用 at.js 或 mbox.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)。

## 共享受众

在填写[Marketing Cloud集成配置表单](https://www.adobe.com/go/audiences)时，请注意以下与“[!UICONTROL 请求配置]？”下列出的[!UICONTROL 共享受众]选项有关的重要信息

![请求表单](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

在请求[!UICONTROL 共享受众]时，您可以启用[!UICONTROL Target]和[!UICONTROL Adobe Audience Manager](AAM)以共享信息，在此例中为受众。

>[!IMPORTANT]
>
>[!UICONTROL Target]与AAM之间的此集成会产生额外成本。 AAM中的每次[!UICONTROL Target]调用均需向您计费。
