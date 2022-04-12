---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发行的版本中包含哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 01c36c0288a15d68f99a6c2f136da9066ccf2e62
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 34%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2022 年 4 月 13 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## Target平台版本（2022年4月13日）

此版本包含以下更新：

* 修复了在使用配置文件脚本捕获IP地址的最后八位字节时，确保正确进行模糊处理的问题。 (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1（错开发行，日期待定）

此版本包含以下更改和增强功能：

* 修复了在编辑、激活和停用配置文件脚本后，对配置文件脚本所做的编辑还原到原始未编辑脚本的问题。 配置文件脚本现在保持其编辑状态。 (TGT-43249)
* 修复了导致 [!DNL Target] 在移动活动中使用的具有“草稿”状态的受众时使用UI:“我们无法完成您的请求。 如果问题仍然存在，请联系Adobe客户关怀。” (TGT-43212)
* 修复了导致 [!UICONTROL 包括] 和 [!UICONTROL 排除] 用于编辑活动时禁用组合受众的选项。 (TGT-43422)
* 修复了某些客户在编辑活动时无法看到可用受众列表的问题。 (TGT-43404)
* 修复了导致某些客户无法从“[!UICONTROL 要从中排除的IP [!DNL Target] 报告数据]&quot;列表 [!UICONTROL 管理] > [!UICONTROL 报表]. (TGT-43384)
* 修复了在受众标准中无法使用负数的问题，该负数会检查任何变量是否“大于”、“大于或等于”、“小于”或“小于或等于”。 (TGT-43367)
* 修复了阻止客户查看 [!UICONTROL 受众详细信息] 卡片。 (TGT-43303)
* 修复了导致 [!DNL Target] UI或新 [!UICONTROL 受众] UI为某些客户过早超时。 （TGT-42590 和 TGT-43273）

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
