---
keywords: adobe.target.triggerView;triggerView;triggerview;触发器视图;at.js;函数;函数;viewName;viewname;视图名称
description: 对Adobe [!DNL Target] at.js JavaScript库使用adobe.目标.triggerView()函数，以在单页应用程序(SPA)中使用。 (at.js 2.x)
title: 如何使用adobe.目标.triggerView()函数？
feature: at.js
role: Developer
exl-id: 619d5166-d1d9-49a6-9807-338544782e66
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 84%

---

# adobe.target.triggerView (viewName, options) - at.js 2.x

每当加载新页面或重新渲染页面上的组件时，都可以调用此函数。应该为单页应用程序 (SPA) 实施 `adobe.target.triggerView()`，以便使用可视化体验编辑器 (VEC) 创建 A/B 测试和体验定位 (XT) 活动。如果未在网站上实施 `adobe.target.triggerView()`，则无法将 VEC 用于 SPA。有关更多信息，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函数已在 at.js 2.x 中引入。但此函数不适用于 at.js 版本 1.*x*。

| 参数 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| viewName | 字符串 | 是 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在 VEC 的[!UICONTROL 修改]面板中，供营销人员创建操作并运行其 A/B 和 XT 活动。 |
| options | 对象 | 否 |  |
| options > page | 布尔值 | 否 | **TRUE：** page 的默认值为 true。当 page=true 时，将向 [!DNL Target] 后端发送增加展示次数计数的通知。<br>默认情况下，通知始终在调用时 `triggerView` 发送，但选项>页面设置为false时除外。<br>**FALSE：**&#x200B;当 page=false 时，将不会发送增加展示次数计数的通知。当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

## 示例：True

`triggerView()` 调用向 Target 后端发送增加活动展示次数和其他量度的通知。

```javascript
adobe.target.triggerView("homeView")
```

## 示例：False

`triggerView()` 调用不会向 Target 后端发送增加展示次数计数的通知。

```javascript
adobe.target.triggerView("homeView", {page: false})
```
