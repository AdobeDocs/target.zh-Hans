---
keywords: FAQ；常见问题解答；Analytics for Target;A4T；分类；分类导入器；post-tnt-action；事件代码
description: 查找有关分类和使用 [!UICONTROL Analytics for Target] (A4T)。
title: 在哪里可以找到有关A4T分类的信息？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# 分类 - A4T 常见问题解答

本主题包含有关分类和使用的常见问题解答 [!DNL Analytics] 作为报表源 [!DNL Target] (A4T)。

## 使用 [!UICONTROL 分类导入器] 要下载分类，如何将post-tnt-action值与活动名称进行匹配？ {#section_6045DAC488B248418F430E663C38D001}

您可以从管理员工具的[分类导入程序](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)中下载 A4T/TNT 字符串的分类。该变量在导出列表中称为“TNT”。下载的数据包含活动和体验等内容的友好名称。

此查找文件对于接收 [!DNL Adobe]的点击流数据馈送。 该文件为 `post_tnt` 和 `post_tnt_action` 列提供了友好名称。

对于标准 [!UICONTROL A/B测试] 和 [!UICONTROL 体验定位] (XT)活动时，TNT字符串的格式为：

```
activityID:experienceID:targettype|event
```

对于 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动时，TNT字符串的格式为：

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` 和 `algorithmId` 是使用的内部标识符 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位] 活动。
* 若 event 为 0，则表示访客参加了体验。
* 若 event 为 1，则表示访客访问了体验。
* 若 event 为 2，则表示进行了活动展示。
* 事件= 3-32766表示分析成功量度ID。
* 若 event 为 32767，则表示进行了活动转化。
* 事件–1或65535表示用户已从活动或体验中删除。 当访客进行转化时，通常会发生这种情况。 该访客已从体验中发布，现在可用于任何其他体验。

您可以经常使用 [浏览器导入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) 或 [FTP导入](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). 您也可以联系工程服务部门，以便在获取点击流数据信息源的同时一起获取该文件作为查询表。
