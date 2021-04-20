---
keywords: 发行说明；新增功能；发行；更新；更新；发行；增强；修复；错误修复；更新
description: 了解 Adobe Target 当前版本包含的新增功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 当前版本中包含哪些新增功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 35%

---

# Target 发行说明（当前版本）

这些发行说明提供了有关每个[!DNL Adobe Target Standard]和[!DNL Target Premium]版本的功能、增强和修复的信息。 此外，还包含目标 API、SDK、JavaScript库(at.js)的发行说明和其他平台更改（如果适用）。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用将轻松失败，并会通过提供默认内容来影响运行[!DNL Target]活动的页面。
>
>在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## Target Standard/Premium 21.4.1（2021 年 4 月 19 日） 

此版本包含以下新增功能和增强功能。 括号中的问题编号供 [!DNL Adobe] 内部使用。

| 功能 | 详细信息 |
| --- | --- |
| 对at.js<br>的设备上决策支持（宣布日期） | 设备上决策允许营销人员和开发人员在用户浏览器上以接近零的延迟进行试验和个性化。<br>有关详细信息， [请参阅at.js的设备上决策。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![基](/help/assets/premium.png) 于PremiumList的实体筛选规则运算符 | [!DNL Target Recommendations] 支持新的基于列表的运算符，用于实体筛选规则。(TGT-39234)<br>新添加的运算符包括：<br><ul><li>包含在列表中</li><li>未包含在列表中</li><li>列表包含</li><li>列表不包含</li><li>列表包含</li><li>列表不包含</li></ul>有关详细信息，请参阅[使用动态和静态包含规则](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)中的“可用运算符”。 |

此版本包含以下修复。

* 修复了将活动更改为[!UICONTROL 所有受众]后，访客无法同步的问题。 (TGT-40259)
* 修复了在[!UICONTROL Automated Personalization]活动中的不同位置使用优惠时，即使启用了[!UICONTROL 禁止重复]选项，也阻止复制的问题。 (TGT-39567)
* 修复了阻止正确加载[!UICONTROL Administration] > [!UICONTROL Scene7配置]页面的问题。 (TGT-39918)
* 修复了导致属性映射到错误工作区的问题。 (TGT-39869)
* 修复了在创建推荐排除时更改环境后请求失败时导致无限加载的问题。 (TGT-39948)

## at.js版本2.5.0（宣布日期）

此版本的at.js包含以下增强和更改：

* [对at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 的设备上决策支持
* [预览](/help/c-activities/c-activity-qa/activity-qa.md) 链接支持Automated Personalization活动。

此版本还删除了对Microsoft Internet Explorer 10及更高版本的支持。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 视图本指南中未包含的更新的详细信息。<br>有关更多信息，请参阅[文档更改](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](/help/r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参阅 [Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe优先级产品更新 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
