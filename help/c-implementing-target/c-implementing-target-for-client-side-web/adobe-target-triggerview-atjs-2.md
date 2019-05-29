---
description: '有关at. js的adobe. target. TriggerView(ViewName、options)函数的信息。 '
keywords: adobe.target.notification;元素;选择器;通知;扩展
seo-description: 有关Adobe Target at. js JavaScript库的adobe. target. TriggerView(ViewName、options)函数的信息。
seo-title: 有关Adobe Target at. js JavaScript库的adobe. target. TriggerView(ViewName、options)函数的信息。
solution: Target
subtopic: 入门指南
title: adobe.target.triggerView (viewName, options)
topic: Standard
translation-type: tm+mt
source-git-commit: 19834da75f163d6357bc9b986a23f0bc1fea6d8e

---


# adobe. target. righterView(ViewName，options)- at. js2.x

每当加载新页面或重新渲染页面上的组件时，都可以调用此函数。应该为单页应用程序 (SPA) 实施 `adobe.target.triggerView()`，以便使用可视化体验编辑器 (VEC) 创建 A/B 测试和体验定位 (XT) 活动。如果未在网站上实施 `adobe.target.triggerView()`，则无法将 VEC 用于 SPA。有关更多信息，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函数在. js2.x中引入。此函数不适用于. js版本1。*x*。

| 参数 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| viewName | 字符串 | 是 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在 VEC 的[!UICONTROL 修改]面板中，供营销人员创建操作并运行其 A/B 和 XT 活动。 |
| options | 对象 | 否 |
| options &gt; page | 布尔值 | 否 | **TRUE：** page 的默认值为 true。当 page=true 时，将向 [!DNL Target] 后端发送增加展示次数计数的通知。<br>**FALSE：** 当page= false时，不会发送通知以增加印象计数。当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

## 将向 Target 后端发送增加展示次数计数通知的 `triggerView()` 调用示例

```
adobe.target.triggerView("homeView")
```

## 不会向 Target 后端发送增加展示次数计数通知的 `triggerView()` 调用示例

```
adobe.target.triggerView("homeView", {page: false})
```
