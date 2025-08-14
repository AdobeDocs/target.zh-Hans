---
keywords: 发行说明；版本；更新；未来版本；增强；新功能；修复；更新；预发行；抢先体验
description: 了解即将发布的 [!DNL Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 13%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2025年7月24日**

>[!NOTE]
>
>* 发布日期、功能及其他信息如有更改，恕不另行通知。
>
>* 要查看有关当前版本的信息，请参阅[Target发行说明](release-notes.md)。
>
>* 括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target Standard/Premium] 25.8.2（2025年8月13日）

此版本包含以下修复和更新：

**[!UICONTROL Activities]**

+++查看详细信息
* 修复了更新的[!DNL Target] UI中，某些活动在尝试编辑时加载失败的问题。 此问题导致客户将用户留在无限加载屏幕中。 此问题会影响多个活动，并且据报告在不同客户中发生的情况不一致。 通过此修复，受影响的活动现在可以正常加载，从而允许无缝编辑并减少活动工作流的中断。 (TGT-53209)
* 修复了活动创建过程中因后端验证错误导致客户无法保存更改的问题： `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:`在修改活动中的特定元素时，出现此问题，导致保存操作失败。 此修复程序确保`optionLocalId`引用现在已正确验证，允许客户保存活动而不遇到此错误。 (TGT-53293)
* 修复了活动创建过程中导致UI在编辑期间切换页面三次后崩溃的问题。 崩溃是由无效的选项引用触发的，这会导致控制台错误，例如“未找到localId为&#39;7&#39;的选项”。 通过此更新，客户现在可以在页面之间切换并应用修改，而不会遇到系统故障或中断。 (TGT-53295)
* 修复了活动创建过程中由于无效的用户输入错误而导致客户无法保存对活动所做更改的问题。 在更新的UI中修改体验时出现错误，导致无法提交更新。 现在可成功保存活动，从而允许客户在不中断的情况下进行编辑和发布。 (TGT-53267)
* 修复了活动创建过程中客户由于连续加载屏幕而无法编辑更新UI中的活动的问题。 客户现在可以打开和修改活动而不会遇到加载失败的情况。 (TGT-53415)

+++

**体验片段(XF)**

+++查看详细信息
* 修复了活动创建过程中允许客户编辑从[!DNL Experience Fragments]中的[!DNL Adobe Experience Manager] (AEM)导出的[!DNL Target] (XF)的HTML的问题。 这是意外行为，因为从AEM发布后，XF应该保持锁定状态以进行编辑。 此修复可确保“编辑HTML”选项不再可用于AEM导出的片段，并保留内容完整性和预期治理。 (TGT-53286)

+++

**QA模式**

+++查看详细信息
* 修复了活动创建过程中活动URL中的前导空格在保存时未正确修剪的问题。 这会导致后端中的QA链接无效和格式不正确。 更新后，现在可干净地保存URL，从而防止链接损坏，并提高了客户QA工作流的可靠性。 (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++查看详细信息
* 修复了新[!UICONTROL Catalog Search] UI中[!UICONTROL Advanced Search]功能无法提供建议的问题。 要求用户输入具有精确拼写的精确值，这使得搜索体验繁琐且容易出错。 通过此修复，[!UICONTROL Advanced Search]现在会根据用户类型提供相关建议，从而提高可用性并减少查找产品时的摩擦。 (TGT-52008)
* 解决了若干问题，包括对小屏幕设备上的标准详细信息响应不佳、在[!UICONTROL Environment]筛选器中选择“所有主机组”时缺少结果，以及无法与无名称的实体交互。 这些修复提高了所有屏幕大小的可用性，确保准确过滤，并允许与所有产品实体完全交互，从而增强用户的整体体验。 (TGT-52992)
* 修复了[!DNL Recommendations]活动创建过程中产品详细信息屏幕中缺少产品ID，从而导致客户在工作流期间难以复制或引用产品ID的问题。 产品ID现在清晰地显示在详细信息视图中，提高了可见性，并支持客户更高效的产品管理。 (TGT-51964)
* 修复了活动创建过程中[!UICONTROL Message]视图中的[!DNL Recommendations]列不显示产品数据（即使存在消息）的问题。 客户必须手动移除并重新添加列以临时显示内容，在滚动或搜索时，这些内容通常会再次消失。 此更新可恢复产品消息的一致可见性，并改进目录导航和审核工作流。 (TGT-52777)
* 修复了活动创建过程中在[!DNL Recommendations]视图中选择“所有主机组”环境未返回任何结果的问题。 客户现在可以按预期查看所有主机组中的产品数据，从而在活动设置期间提高可见性和过滤准确性。 (TGT-53006)
* 修复了活动创建过程中在活动设置中禁用前端促销活动切换开关在保存后无法持续存在的问题。 尝试删除前端促销的客户发现，在重新访问活动时重新启用了切换功能，从而妨碍了正常的自定义。 此更新允许可靠地保存更改，从而使客户能够完全控制促销设置。 (TGT-53215)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* 修复了活动创建过程中某些活动加载失败，导致客户无法访问修改内容的问题。 此外，[!UICONTROL Cancel]按钮无响应，阻止客户停止加载过程或退出编辑视图。 此修复程序确保活动现在可以可靠地加载，[!UICONTROL Cancel]按钮按预期运行，从而提高可视化体验编辑器(VEC)(TGT-53218)中的整体稳定性和用户体验
* 修复了更新后的VEC UI中的一个问题，即在体验定位(XT)活动中的体验之间切换时，无法加载修改。 客户无法编辑超出最初输入范围的体验，并且[!UICONTROL Cancel]按钮缺失或无响应。 此修复确保修改现在可以跨所有体验正确加载，并且[!UICONTROL Cancel]按钮可以可靠地运行，即使没有Helper扩展也是如此，从而改善编辑工作流并减少挫折感。 (TGT-53256)
* 修复了在多个体验之间切换导致白屏的问题。 还修复了活动创建过程中客户尝试修改活动中的多个体验时遇到白屏的问题。 在将更改应用于两个体验，然后选择第三个体验（阻止进一步编辑）后，出现此问题。 此更新可确保体验之间的顺利过渡，从而使客户能够在不中断的情况下进行修改。 (TGT-53266)
* 修复了在可视化体验编辑器(VEC)中所做的自定义代码修改无法可靠地在单次尝试中保存的问题。 客户报告，即使同时使用[!UICONTROL Edit Content]和最终[!UICONTROL Save]按钮，网站和QA URL中仍间歇性地缺少更改，例如样式更新或HTML编辑。 此回归已得到解决，确保所有自定义代码更改在整个编辑会话中按预期持续存在。 (TGT-53418)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明： Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
