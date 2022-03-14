---
keywords: adobe.target.triggerView;triggerView;triggerview;触发器视图;at.js;函数;函数;viewName;viewname;视图名称
description: 使用adobe.target.triggerView()函数进行Adobe [!DNL Target] at.js JavaScript库，用于单页应用程序(SPA)。 (at.js 2.x)
title: 如何使用adobe.target.triggerView()函数？
feature: at.js
role: Developer
exl-id: 619d5166-d1d9-49a6-9807-338544782e66
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 84%

---

# adobe.target.triggerView (viewName, options) - at.js 2.x

每当加载新页面或重新渲染页面上的组件时，都可以调用此函数。应该为单页应用程序 (SPA) 实施 `adobe.target.triggerView()`，以便使用可视化体验编辑器 (VEC) 创建 A/B 测试和体验定位 (XT) 活动。如果未在网站上实施 `adobe.target.triggerView()`，则无法将 VEC 用于 SPA。有关更多信息，请参阅[单页应用程序实施](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

>[!NOTE]
>
>此函数已在 at.js 2.x 中引入。但此函数不适用于 at.js 版本 1.*x*。

| 参数 | 类型 | 必需？ | 描述 |
| --- | --- | --- | --- |
| viewName | 字符串 | 是 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在 VEC 的[!UICONTROL 修改]面板中，供营销人员创建操作并运行其 A/B 和 XT 活动。 |
| options | 对象 | 否 |  |
| options > page | 布尔值 | 否 | **TRUE：** page 的默认值为 true。当 page=true 时，将向 [!DNL Target] 后端发送增加展示次数计数的通知。<br>默认情况下，当 `triggerView` 调用，但选项>页面设置为false时除外。<br>**FALSE：**&#x200B;当 page=false 时，将不会发送增加展示次数计数的通知。当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

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
