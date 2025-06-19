---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 28%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新时间：2025年6月19日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.6.3（2025年6月20日）

此版本包含以下修复和更新：

* 已将[!UICONTROL Rearrange]选项添加到更新的[!UICONTROL Visual Experience Composer] (VEC) UI，以便与旧版VEC中可用的功能保持一致。 (TGT-46957)
* 修复了将活动从一个工作区复制到另一个工作区时触发错误（如“不能为空”或“出现错误”）的问题。 (TGT-52474)
* 修复了无法为某些活动生成[!UICONTROL Automated Segments]和[!UICONTROL Important Attributes]报告的问题。 (TNT-52904)
* 修复了更新后的VEC中，[!UICONTROL Automated Personalization] (AP)活动中的默认内容处理与旧版UI不匹配的问题。 在没有显式添加组时，系统现在将自动添加名为“默认内容”的默认`optionGroup`和`optionGroupLocalId = 0`。 此组包含默认选项（例如，`optionLocalId: 0`）。 如果移除默认内容，则也会移除相应的选项组。 (TGT-52651)
* 修复了[!UICONTROL Multivariate Test] (MVT)活动中的一个问题，该问题导致不正确地不允许重用之前已删除体验中的`experienceLocalId`。 (TNT-52672)
* 修复了活动位置中的URL由于斜杠(/)等无效字符而无法显示查询参数的问题。 (TNT52845)
* 改进了通过后端API进行的[!DNL A/B Test]活动更新的验证错误消息。 当存在重复的位置名称时，该消息现在会明确声明：`locations.selectors`的“不允许存在重复的名称”。 (TGT-52589)
* 修复了更新实时[!UICONTROL Recommendations]活动时由于请求有效负载中的属性无法识别而发生的错误。 系统现在可以正确处理“无效JSON”。 无法识别的属性名称”错误。 (TNT52723)
* 修复了在保存[!UICONTROL Recommendations]活动时导致出现“400错误请求”错误的后端验证错误。 (TNT-52716)
* 修复了[!UICONTROL Form-Based Experience Composer]中的一个问题，该问题导致将鼠标悬停在[!UICONTROL Location]下拉列表中具有特殊字符的mbox上导致编辑器变为空白并触发“无法对‘元素’执行‘querySelector’”。 错误。(TGT-52717)
* 通过新的“PARTIALLY_IMPORTED”指示符提高了馈送状态准确性。 以前，即使未导入文件中的所有行，信息源也会标记为“success”，这很有误导性。
* 修复了迁移到AP V2后，对`/admin/rest/ui/v1/campaigns`的特定API调用返回客户端错误(HTTP 4xx)的错误。 (TGT-52721)

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
