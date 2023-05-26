---
keywords: 推荐
description: 了解Analytics的实施要求 [!DNL Target] (A4T)以及在实施此集成之前需要考虑的事项。
title: 在实施A4T之前，我应该了解什么？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 24%

---

# 使用 at.js 实施 Analytics for Target (A4T) 之前

启用时，数据收集流程会发生一些更改 [!DNL Adobe Analytics] 作为的报表源 [!DNL Adobe Target] (A4T)。

在决定使用此集成之前，请查看以下部分并考虑对报表流程的影响。

>[!NOTE]
>
>本文仅适用于at.js实施。

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用A4T之前，您必须请求为集成配置您的帐户。 使用 [Marketing Cloud集成设置表单](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} 以请求进行配置。

根据您是否要将重定向选件与A4T结合使用，此A4T集成要求您实施以下库版本（或更高版本）。

>[!NOTE]
>
>以下要求列出了 *最小值* 实施A4T所需的at.js版本。 此 [!DNL Target] 团队仅维护两个版本的 [!DNL at.js] — 当前版本和当前版本的上一个版本。 请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

### *未*&#x200B;将重定向选件与 A4T 结合使用时需要满足的要求

如果您不打算将重定向选件与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本1.8.0
* [!DNL Adobe Target]: at.js 0.9.1 版
* Adobe Analytics：appMeasurement.js 版本 1.7.0

有关使用实施A4T的信息 [!DNL Platform Web SDK]，请参见 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

### 将重定向选件与 A4T 结合使用时需要满足的要求

要将重定向选件与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本2.3.0

   >[!NOTE]
   >
   >at.js 1.8.0+ 和 at.js 2.x+ 不再适用于 2.5.0 之前的访客 API 版本，无法传递 Adobe Audience Manager (AAM) 参数。

* [!DNL Adobe Target]: at.js 1.6.2 版

* Adobe Analytics：appMeasurement.js 版本 2.1

中列出了下载和部署说明 [Analytics for Target实施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

有关使用实施A4T的信息 [!DNL Platform Web SDK]，请参见 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 当您选择使用时，会在新活动上启用此集成 [!DNL Analytics] 作为报表源。 在进行本文中所述的实施更改后，现有活动不会受到影响。
* 设置过程 [!DNL Analytics] 作为的报表源 [!DNL Target] 包括几个实施步骤，以及预配步骤。 在实施之前，最好通读下面所述的过程。完成这些步骤后，即可使用 [!DNL Analytics] 作为您的报表源。 配置过程可能最多需要 5 个工作日。
* 此 [!DNL Visitor ID service] 创建共享 [!DNL Visitor ID] 跨越 [!DNL Adobe Experience Cloud]. 虽然它不能取代 [!DNL Target] mboxPC ID或 [!DNL Audience Manager] UUID，它确实取代了 [!DNL Analytics] 标识新访客。 如果设置正确，请返回 [!DNL Analytics] 还应该通过访客的旧访客来识别访客 [!DNL Analytics] ID。 同样，因为 [!DNL Target] mboxPCid保持不变，否 [!DNL Target] 当您升级到时，访客配置文件数据会丢失 [!DNL Visitor ID service].
* 此 [!DNL Visitor ID service] 必须在 [!DNL Analytics] 和 [!DNL Target] 页面代码。 确保 `VisitorAPI.js` 出现在所有其他标记的上方 [!DNL Experience Cloud] 解决方案。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，您会遇到5至10分钟的额外延迟。 [!DNL Analytics]. 延迟的增加使得来自以下位置的数据 [!DNL Analytics] 和 [!DNL Target] ，这样您就可以按页面和网站区域来细分活动。

这一增长反映在所有方面 [!DNL Analytics] 服务和工具（包括实时流和实时报表），并适用于以下场景：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于有关转化量度、最终数据和数据馈送的当前数据，所有点击都会额外延迟5至7分钟。

延迟增加会在您实施 [!DNL Experience Cloud] 访客ID服务，即使您尚未完全实施此集成也是如此。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

全部 [!DNL Target] A4T活动用于交付内容或记录目标量度的调用必须具有相应的 [!DNL Analytics] 共享A4T补充ID的点击才能正常工作。

包含来自以下各项的数据的点击 [!DNL Analytics] 和 [!DNL Target] 包含补充数据ID。 您可以在以下位置查看此ID： [Adobe Experience Cloud调试器](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 作为 `sdid` 参数。 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务

时间 [故障排除](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)，请务必确认上存在补充ID [!DNL Analytics] 点击量。

## 客户端分析日志记录 {#client-side}

如果at.js， [!DNL Experience Cloud Visitor ID Service]和appMeasurement.js在页面上， [!DNL Analytics]、和 [!DNL Target] 只要页面中包含正确的补充ID，便可以在后端正确拼合用于报告和分析的事件。 您无需管理和执行任何其他操作，A4T即可正常运行。

在某些情况下，您可能希望更好地控制何时以及如何向发送相关的分析数据 [!DNL Target] 到 [!DNL Analytics] 作报告用途。 您可能已拥有用于内部用途的内部分析工具。 但是，您还需要将分析数据发送到 [!DNL Analytics] 通过您的内部分析产品，以便贵组织的其他成员可以继续使用 [!DNL Analytics] 作为可视化报表源。 参见 [步骤7：在所有网站页面上引用at.js](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) 在 *Analytics for Target实施* 了解更多信息。

## 共享受众

填写 [Marketing Cloud集成设置表单](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}，请注意以下有关 [!UICONTROL 共享受众] “下方的选项[!UICONTROL 您请求配置的功能]？”

![申请表](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

当您请求时 [!UICONTROL 共享受众]，您启用 [!UICONTROL Target] 和 [!UICONTROL Adobe Audience Manager] (AAM)以共享信息，在本例中是受众。

>[!IMPORTANT]
>
>此集成介于 [!UICONTROL Target] 而AAM会额外付费。 您需为每个报表包付费 [!UICONTROL Target] 在AAM中调用。
