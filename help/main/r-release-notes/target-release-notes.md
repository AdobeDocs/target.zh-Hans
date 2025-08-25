---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 65bc050a189b65af57b1258afeff497a0dafcfb5
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 44%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年8月21日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。本文中的信息会经常更新，尤其是在发布版本之前。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.4（2025年8月28日）

此版本包含以下更新和修复：

**[!DNL Recommendations]**

+++查看详细信息
**更新了UI，以便[!UICONTROL Product Catalog Search]中的高级搜索筛选不区分大小写**： [!UICONTROL Advanced Search]页中的[!UICONTROL Product Catalog Search] UI以前对返回的值执行完全大小写匹配，即使后端查询和GraphQL查询都不区分大小写。 这种不一致会导致混淆，并降低搜索准确性。 [!UICONTROL Advanced Search]筛选现在不区分大小写，与后端行为保持一致，并提高了可用性。

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++查看详细信息
* **修复了在导航到[!UICONTROL Automated Personalization]步骤并返回后，重命名[!UICONTROL Multivariate Test] (AP)或[!UICONTROL Targeting] (MVT)活动中的位置未持续存在的问题。**&#x200B;客户现在可以成功编辑和保存位置名称，并且更改在整个活动创建过程中保持可见。 (TGT-52367)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
