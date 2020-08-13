---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: 本主题包含有关分类和使用 Analytics 作为 Target 报表源 (A4T) 的常见问题解答。
title: 分类 - A4T 常见问题解答
feature: a4t troubleshooting
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 66%

---


# 分类 - A4T 常见问题解答{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## 使用分类导入程序下载分类后，如何将 post-tnt-action 值与活动名称相匹配？{#section_6045DAC488B248418F430E663C38D001}

您可以从管理员工具的[分类导入程序](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html)中下载 A4T/TNT 字符串的分类。该变量在导出列表中称为“TNT”。下载的数据包含活动和体验等内容的友好名称。

对于接收 Adobe 点击流数据信息源的客户而言，这是一个很有用的查询文件。该文件为 `post_tnt` 和 `post_tnt_action` 列提供了友好名称。

TNT 变量的字符串格式为 `activityID:experienceID:targettype|event`。

* targettype = 0(control/random)或1（目标） [!UICONTROL 用于自动分配][!UICONTROL 和自动目标] 活动。
* 若 event 为 0，则表示访客参加了体验。
* 若 event 为 1，则表示访客访问了体验。
* 若 event 为 2，则表示进行了活动展示。
* 若 event 为 32767，则表示进行了活动转化。

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). 您也可以联系工程服务部门，以便在获取点击流数据信息源的同时一起获取该文件作为查询表。
