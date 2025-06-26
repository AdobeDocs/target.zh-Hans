---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 926a045e5bcebc8d094ea41a6c1b7c59568a35ab
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 27%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新时间：2025年6月26日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.6.4（2025年6月26日）

此版本包含以下修复和更新：

* 已将[!UICONTROL Rearrange]选项添加到更新的[!UICONTROL Visual Experience Composer] (VEC) UI，以便与旧版VEC中可用的功能保持一致。 （TGT-46957 和 TGT-52876）
* 修复了对[!UICONTROL A/B Test]活动中的变体体验（例如体验B）所做的修改未保留的问题。 在体验之间切换后，对变量的更改将消失。 此问题不会影响控制体验。 (TGT-52664)
* 修复了以下问题：某些客户无法创建或保存活动，而其他客户可以正常执行相同的操作。 不同帐户之间的问题不一致。(TGT-52842)
* 修复了在更新后的VEC中，用户无法移动对[!UICONTROL Page Load event]的修改的问题，该功能存在于旧版UI中。 (TGT-52617)
* 修复了一个问题，该问题导致某些活动修改无法在更新后的VEC中正常显示。 (TGT-52818)
* 修复了在获取[!UICONTROL Automated Personalization] (AP)活动的报表数据时发生的空指针异常。 (TGT-52362)
* 修复了导致选件级别详细信息无法在[!UICONTROL Automated Personalization] (AP)活动的.CSV文件中显示的问题。 (TGT-52675)
* 修复了在更新的VEC中应用修改时，更改最初正确显示的问题，包括预期的[!UICONTROL Experience Fragment]。 但是，在切换体验或进行其他编辑时，由于选择器问题，某些修改无法应用。 (TGT-52679)
* 修复了在通过克隆现有活动创建新活动时，克隆活动中的QA链接错误地保留原始活动中的页面URL的问题。 (TGT-52775)
* 修复了无意中导致[!UICONTROL On-device Decisioning]在更新的VEC中不可用的问题。 (TGT-52371)
* 修复了阻止编辑产品[!DNL Recommendations]活动的问题。 尝试通过Target UI访问VEC时，[!UICONTROL Overview]页面上出现错误，导致无法进行任何编辑。 (TGT-52823)
* 修复了在体验名称超过50个字符时阻止保存[!DNL Recommendations]活动的问题。 (TGT-52619)
* 修复了客户在新UI中修改标准后无法保存“推荐”活动的问题。 该问题似乎与权限相关，并不影响具有相似角色的所有用户。 (TGT-52816)
* 修复了具有[!UICONTROL Editor]角色的用户无法编辑[!DNL Recommendations]活动的问题。 尝试更改设计并保存活动会导致403禁止错误，声明“[编辑者]”权限是必需的，即使用户已在相关工作区中拥有该角色。 (TGT-52836)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
