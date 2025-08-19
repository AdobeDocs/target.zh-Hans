---
keywords: 推荐
description: 了解Analytics for [!DNL Target] (A4T)的实施要求以及在实施此集成之前需要考虑的事项。
title: 在实施A4T之前，我应该了解什么？
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 656f728ba890f1f5afc0404e22f6acb1a2565fe6
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 24%

---

# 使用at.js实施Analytics for Target (A4T)之前

启用[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)的报表源时，数据收集过程中会发生一些更改。

在决定使用此集成之前，请查看以下部分并考虑对报表流程的影响。

>[!NOTE]
>
>本文仅适用于at.js实施。 有关使用[!UICONTROL Analytics for Target]实现[!DNL Adobe Experience Platform Web SDK] (A4T)的信息，请参阅Experience Platform Web SDK[中的](https://experienceleague.adobe.com/docs/target-dev/developer/a4t/overview-a4t.html?lang=zh-Hans){target=_blank}Adobe Analytics for Target (A4T)日志记录。

## 实施要求 {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>在开始使用A4T之前，您必须请求为集成配置您的帐户。 使用[Marketing Cloud集成设置表单](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}请求进行配置。

根据您是否要将重定向选件与A4T结合使用，此A4T集成要求您实施以下库版本（或更高版本）。

>[!NOTE]
>
>以下要求列出了实施A4T所需的&#x200B;*最低*&#x200B;版本的at.js。 [!DNL Target]团队仅维护两个版本的[!DNL at.js]：当前版本和当前版本的上一个版本。 请根据需要升级 [!DNL at.js]，以确保您运行的是受支持的版本。有关每个版本中功能的更多信息，请参阅 [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank}。

### *未*&#x200B;将重定向产品建议与 A4T 结合使用时需要满足的要求

如果您不打算将重定向产品建议与 A4T 结合使用，此集成要求您实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本1.8.0
* [!DNL Adobe Target]：at.js版本0.9.1
* Adobe Analytics：appMeasurement.js 版本 1.7.0

有关使用[!DNL Platform Web SDK]实现A4T的信息，请参阅[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}。

### 将重定向产品建议与 A4T 结合使用时需要满足的要求

要将重定向产品建议与 A4T 结合使用，您必须实施以下库版本（或更高版本）。所列的顺序即是操作顺序。

* [!DNL Experience Cloud Visitor ID Service]： visitorAPI.js版本2.3.0

  >[!NOTE]
  >
  >at.js 1.8.0+ 和 at.js 2.x+ 不再适用于 2.5.0 之前的访客 API 版本，无法传递 Adobe Audience Manager (AAM) 参数。

* [!DNL Adobe Target]：at.js版本1.6.2

* Adobe Analytics：appMeasurement.js 版本 2.1

[Analytics for Target实施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)中列出了下载和部署说明。

有关使用[!DNL Platform Web SDK]实现A4T的信息，请参阅[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}。

## 实施前注意事项 {#section_50D49CC52E11414089C89FB67F9B88F5}

* 当您选择使用[!DNL Analytics]作为报表源时，会在新活动上启用此集成。 在进行本文中所述的实施更改后，现有活动不会受到影响。
* 将[!DNL Analytics]设置为[!DNL Target]的报表源的过程包括几个实施步骤，然后是设置步骤。 在实施之前，最好通读下面所述的过程。完成这些步骤后，您便可以使用[!DNL Analytics]作为您的报表源，前提是您已经为您启用了。 配置过程可能最多需要 5 个工作日。
* [!DNL Visitor ID service]在整个[!DNL Visitor ID]中创建共享[!DNL Adobe Experience Cloud]。 尽管它没有替换[!DNL Target] mboxPC ID或[!DNL Audience Manager] UUID，但它确实替换了[!DNL Analytics]识别新访客的方式。 如果设置正确，则还应该通过旧[!DNL Analytics] ID识别[!DNL Analytics]回访访客。 同样，由于[!DNL Target] mboxPCid保持不变，因此当您升级到[!DNL Target]时，不会丢失[!DNL Visitor ID service]访客配置文件数据。
* [!DNL Visitor ID service]必须在您的[!DNL Analytics]和[!DNL Target]页面代码之前执行。 确保`VisitorAPI.js`出现在所有其他[!DNL Experience Cloud]解决方案的标记上方。

## 延迟 {#section_9489BE6FD21641A4844E591711E3F813}

启用此集成后，[!DNL Analytics]中会额外经历5至10分钟的延迟。 增加此延迟可将[!DNL Analytics]和[!DNL Target]的数据存储在同一点击中，从而允许您按页面和网站区域划分活动。

此增长反映在所有[!DNL Analytics]服务和工具中，包括实时流和实时报表，并适用于以下场景：

* 对于实时流、实时报表和 API 请求，以及流量变量的当前数据，仅包含额外数据 ID 的点击会发生延迟。
* 对于有关转化量度、最终数据和数据馈送的当前数据，所有点击都会额外延迟5 - 7分钟。

实施[!DNL Experience Cloud]访客ID服务后，即使您尚未完全实施此集成，滞后的时间也会开始增加。

## 补充 ID {#section_2C1F745A2B7D41FE9E30915539226E3A}

A4T活动用于交付内容或记录目标量度的所有[!DNL Target]调用必须具有共享补充ID的相应[!DNL Analytics]点击，A4T才能正常工作。

包含来自[!DNL Analytics]和[!DNL Target]的数据的点击包含补充数据ID。 您可以在[Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)中将此ID视为`sdid`参数。 例如：`sdid=2F3C18E511F618CC-45F83E994AEE93A0`。满足以下标准时，便会生成此 ID：

* 已实施访客 ID 服务

在[疑难解答](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)时，请务必确认[!DNL Analytics]点击中存在补充ID。

## 客户端Analytics日志 {#client-side}

如果at.js、[!DNL Experience Cloud Visitor ID Service]和appMeasurement.js位于页面上，则[!DNL Analytics]和[!DNL Target]可以在后端正确地将事件拼合到一起以用于报告和分析目的，前提是页面中包含正确的补充ID。 您无需管理和执行任何其他操作，A4T即可正常运行。

在某些情况下，您可能希望更好地控制何时以及如何将与[!DNL Target]相关的分析数据发送到[!DNL Analytics]进行报告。 您可能已拥有用于内部用途的内部分析工具。 但是，您还希望通过内部分析产品将分析数据发送到[!DNL Analytics]，以便贵组织的其他成员可以继续使用[!DNL Analytics]作为可视化报表源。 有关详细信息，请参阅[Analytics for Target实施](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7)中的&#x200B;*步骤7：在所有网站页面上引用at.js*。

## 共享受众

在填写[Marketing Cloud集成设置表单](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}时，请注意以下有关“[!UICONTROL Shared Audiences]”下列出的[!UICONTROL For which capabilities are you requesting provisioning]选项的重要信息？

![申请表单](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

当您请求[!UICONTROL Shared Audiences]时，您允许[!UICONTROL Target]和[!UICONTROL Adobe Audience Manager] (AAM)共享信息，在本例中是共享受众。

>[!IMPORTANT]
>
>[!UICONTROL Target]与AAM之间的集成需要额外付费。 在AAM中，您每调用[!UICONTROL Target]都要付费。
