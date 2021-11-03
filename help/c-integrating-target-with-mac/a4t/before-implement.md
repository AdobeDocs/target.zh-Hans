---
keywords: 推荐
description: 了解Analytics的实施要求，适用于 [!DNL Target] (A4T)以及在实施此集成之前应考虑的事项。
title: 实施A4T之前，我应该了解什么？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 9a1603cbbe773638693f5836b6cf7c62dc0b56b8
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 26%

---

# 使用 at.js 实施 Analytics for Target (A4T) 之前

在启用 [!DNL Adobe Analytics] 作为报表源 [!DNL Adobe Target] (A4T)。

在您决定使用此集成之前，请查看以下部分并考虑对报表流程的影响。

>[!NOTE]
>
>本文仅适用于at.js实施。

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用A4T之前，您必须请求配置您的帐户以进行集成。 使用 [Marketing Cloud集成配置表单](https://www.adobe.com/go/audiences_cn) 请求进行配置。

根据您是否要将重定向选件与A4T结合使用，此A4T集成要求您实施以下库版本（或更高版本）。

>[!NOTE]
>
>以下要求列出了 *最小* 实施A4T所需的at.js版本。 的 [!DNL Target] 团队仅维护两个版本 [!DNL at.js] — 当前版本和第二个最新版本。 请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)。

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本1.8.0
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics：appMeasurement.js 版本 1.7.0

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]:visitorAPI.js版本2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ 和 at.js 2.x+ 不再适用于 2.5.0 之前的访客 API 版本，无法传递 Adobe Audience Manager (AAM) 参数。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics：appMeasurement.js 版本 2.1

下载和部署说明列在 [Analytics for Target实施](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 当您选择使用 [!DNL Analytics] 作为报表源。 在进行本文中所述的实施更改后，现有活动不会受到影响。
* 设置过程 [!DNL Analytics] 作为报表源 [!DNL Target] 包括几个实施步骤，然后是一个配置步骤。 在实施之前，最好通读下面所述的过程。完成这些步骤后，即可使用 [!DNL Analytics] 作为报表源。 配置过程可能最多需要 5 个工作日。
* 的 [!DNL Visitor ID service] 创建共享 [!DNL Visitor ID] 跨 [!DNL Adobe Experience Cloud]. 尽管它不会替换 [!DNL Target] mboxPC id或 [!DNL Audience Manager] UUID，它会取代 [!DNL Analytics] 识别新访客。 如果设置正确，则返回 [!DNL Analytics] 访客还应通过其旧 [!DNL Analytics] ID。 同样，因为 [!DNL Target] mboxPCid保持不变，无 [!DNL Target] 升级到时，访客配置文件数据会丢失 [!DNL Visitor ID service].
* 的 [!DNL Visitor ID service] 必须在 [!DNL Analytics] 和 [!DNL Target] 页面代码。 确保 `VisitorAPI.js` 显示在所有其他标记的上方 [!DNL Experience Cloud] 解决方案。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，您将在 [!DNL Analytics]. 这种延迟增加允许从 [!DNL Analytics] 和 [!DNL Target] 存储在同一点击上，以便按页面和网站区域划分活动。

这一增长反映在 [!DNL Analytics] 服务和工具（包括实时流和实时报表），并适用于以下情况：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于有关转化量度、完成数据和数据馈送的当前数据，所有点击都会额外延迟5到7分钟。

实施 [!DNL Experience Cloud] 访客ID服务，即使您尚未完全实施此集成。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

全部 [!DNL Target] A4T活动用于交付内容或记录目标量度的调用必须具有相应的 [!DNL Analytics] 点击，以便共享A4T的补充ID。

包含来自 [!DNL Analytics] 和 [!DNL Target] 包含补充数据ID。 您可以在 [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 作为 `sdid` 参数。 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务

When [疑难解答](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)，请确保确认 [!DNL Analytics] 点击量。

## 客户端分析日志记录 {#client-side}

如果at.js [!DNL Experience Cloud Visitor ID Service]，以及appMeasurement.js [!DNL Analytics]和 [!DNL Target] 只要页面中包含正确的补充ID，就会在后端正确地拼合事件以用于报告和分析目的。 您无需管理和执行任何其他操作，A4T即可正常运行。

在某些情况下，您可能希望更好地控制何时以及如何发送与 [!DNL Target] to [!DNL Analytics] 报表。 您可能已拥有一个内部分析工具，可用于内部目的。 但是，您还希望将分析数据发送到 [!DNL Analytics] ，以便贵组织的其他成员可以继续使用 [!DNL Analytics] 作为可视化报表源。 请参阅 [步骤7:在所有网站页面上引用at.js](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analytics for Target实施* 以了解更多信息。

## 共享受众

在 [Marketing Cloud集成配置表单](https://www.adobe.com/go/audiences)，请注意以下与 [!UICONTROL 共享受众] “[!UICONTROL 您请求为其配置哪些功能]?&quot;

![请求表单](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

请求时 [!UICONTROL 共享受众]，则启用 [!UICONTROL Target] 和 [!UICONTROL Adobe Audience Manager] (AAM)共享信息，在此例中为受众。

>[!IMPORTANT]
>
>此集成 [!UICONTROL Target] 而AAM则会带来额外成本。 您将按 [!UICONTROL Target] 在AAM中调用。
