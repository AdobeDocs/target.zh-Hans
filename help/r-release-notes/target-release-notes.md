---
keywords: 发行说明；发行；更新；未来发行；增强；新增功能；修复；更新；预发行
description: 了解即将发布的Adobe Target版本（包括SDK、API和JavaScript库）中包含的新功能、增强和修复。
title: 即将发布的版本中包含哪些新增功能？
feature: 发行说明
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: a45cfbd52df935fa3138eda6cc7f1028c13ff81d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 24%

---

# Target 发行说明（预发行版本）

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2021 年 4 月 9 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js终止使用**:自2021年3月31日起， [!DNL Adobe Target] 不再支持mbox.js库。2021年3月31日之后，从mbox.js发出的所有调用都会正常失败，并会通过提供默认内容影响运行[!DNL Target]活动的页面。
>
>要避免站点出现任何潜在问题，请迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

## Target Standard/Premium 21.4.1（2021 年 4 月 19 日） 

此版本包含以下新增功能。 括号中的问题编号供 [!DNL Adobe] 内部使用。

| 功能 | 详细信息 |
| --- | --- |
| 对at.js的设备上决策支持 | 设备上决策允许营销人员和开发人员在用户浏览器上以接近零的延迟进行试验和个性化。 |

此版本包含以下增强、修复和更改。

* 修复了将活动更改为[!UICONTROL 所有受众]后，访客无法同步的问题。 (TGT-40259)
* 修复了在[!UICONTROL Automated Personalization]活动中的不同位置使用优惠时，即使启用了[!UICONTROL 禁止重复]选项，也阻止复制的问题。 (TGT-39567)
* 修复了阻止正确加载[!UICONTROL Administration] > [!UICONTROL Scene7配置]页面的问题。 (TGT-39918)
* 修复了导致属性映射到错误工作区的问题。 (TGT-39869)
* [!DNL Target Recommendations] 支持新的基于列表的运算符，用于实体筛选规则。(TGT-39234)

   新添加的运算符包括：

   * 包含在列表中
   * 未包含在列表中
   * 列表包含
   * 列表不包含
   * 列表包含
   * 列表不包含

* 修复了在创建推荐排除时更改环境后请求失败时导致无限加载的问题。 (TGT-39948)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
