---
keywords: FAQ；常见问题解答；Analytics for Target；A4T；分类；分类导入程序；post-tnt-action；事件代码
description: 查找有关分类和使用[!UICONTROL Analytics for Target] (A4T)的问题的答案。
title: 可在何处找到有关使用A4T进行分类的信息？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 24%

---

# 分类 - A4T 常见问题解答

本主题包含有关分类和使用[!DNL Analytics]作为[!DNL Target] (A4T)的报表源的常见问题解答。

## 使用[!UICONTROL Classifications Importer]下载分类后，如何将post-tnt-action值与活动名称相匹配？ {#section_6045DAC488B248418F430E663C38D001}

+++回答
您可以从管理工具[分类导入器](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=zh-Hans)中下载A4T/TNT字符串的分类。 该变量在导出列表中称为“TNT”。 下载的数据包含活动和体验等内容的友好名称。

此查找文件对于接收[!DNL Adobe]的点击流数据馈送的客户非常有用。 该文件为 `post_tnt` 和 `post_tnt_action` 列提供了友好名称。

对于标准[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting] (XT)活动，TNT字符串的格式为：

```
activityID:experienceID:targettype|event
```

对于[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动，TNT字符串的格式为：

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype`和`algorithmId`是[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动使用的内部标识符。
* 若 event 为 0，则表示访客参加了体验。
* 若 event 为 1，则表示访客访问了体验。
* 若 event 为 2，则表示进行了活动展示。
* 事件= 3-32766表示Analytics成功量度ID。
* 若 event 为 32767，则表示进行了活动转化。
* 事件–1或65535表示从活动或体验中删除用户。 这种情况经常在访客转化时发生。 访客已从体验中释放，现在可以有资格体验任何其他体验。

您可以使用[浏览器导入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=zh-Hans)或[FTP导入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=zh-Hans)，经常从UI导入分类文件。 您也可以联系工程服务部门，以便在获取点击流数据信息源的同时一起获取该文件作为查询表。

+++
