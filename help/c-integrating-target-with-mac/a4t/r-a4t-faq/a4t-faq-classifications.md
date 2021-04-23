---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;分类;分类导入程序;post-tnt-action
description: 查找有关分类和使用 [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] 活动的Analytics的问题的答案。
title: 在哪里可以找到有关A4T分类的信息？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 59%

---

# 分类 - A4T 常见问题解答

本主题包含有关分类和将[!DNL Analytics]用作[!DNL Target](A4T)报告源的常见问题的解答。

## 使用分类导入程序下载分类后，如何将 post-tnt-action 值与活动名称相匹配？{#section_6045DAC488B248418F430E663C38D001}

您可以从管理员工具的[分类导入程序](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)中下载 A4T/TNT 字符串的分类。该变量在导出列表中称为“TNT”。下载的数据包含活动和体验等内容的友好名称。

对于接收 Adobe 点击流数据信息源的客户而言，这是一个很有用的查询文件。该文件为 `post_tnt` 和 `post_tnt_action` 列提供了友好名称。

TNT 变量的字符串格式为 `activityID:experienceID:targettype|event`。

* targettype = 0(control/random)或1（目标），用于[!UICONTROL 自动分配]和[!UICONTROL 自动目标]活动。
* 若 event 为 0，则表示访客参加了体验。
* 若 event 为 1，则表示访客访问了体验。
* 若 event 为 2，则表示进行了活动展示。
* 事件= 3-32766表示分析成功量度ID。
* 若 event 为 32767，则表示进行了活动转化。

您可以使用[浏览器导入](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html)或[FTP导入](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html)频繁从UI导入分类文件。 您也可以联系工程服务部门，以便在获取点击流数据信息源的同时一起获取该文件作为查询表。
