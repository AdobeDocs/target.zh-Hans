---
description: 有关使用 at.js 2.x 实施单页应用程序 (SPA) 的信息。
keywords: 单页应用程序实施;实施单页应用程序;SPA;at.js 2.x；at. js；单页应用程序；单页应用程序
seo-description: 有关使用 Adobe Target at.js 2.x 实施单页应用程序 (SPA) 的信息。
seo-title: Adobe Target中的单页应用程序实施
solution: Target
title: 单页应用程序实施
topic: 标准
uuid: 5887ec53-e5b1-40f9-b469-33685f5c6cd6
translation-type: tm+mt
source-git-commit: 8aa1d0fcff8d46bbfa2d296206d36ea79fe6181c

---


# 单页应用程序实施{#single-page-application-implementation}

传统网站使用的是“页面到页面”导航模型，也称为多页应用程序，其中网站设计与 URL 紧密耦合，并且从一个网页转换到另一个网页时，需要页面加载。而现代 Web 应用程序（例如单页应用程序 (SPA)）采用的模型可以提高使用浏览器 UI 渲染的速度，这种渲染通常与页面重新加载无关。这些体验通常通过客户交互触发，例如滚动、点击和光标移动。随着现代 Web 范例的不断发展，传统的通用事件（例如页面加载）与部署个性化和实验不再具有相关性。

![传统页面生命周期与 SPA 生命周期](/help/c-experiences/assets/trad-vs-spa.png)

at.js 2.x 提供了丰富的功能，使您的企业能够在下一代客户端技术上实现个性化。此版本着重改进了 at.js，以便与 SPA 进行和谐的交互。

以下是使用 at.js 2.x 的一些好处，这些好处在以前的版本中未提供：

* 能够在页面加载时缓存所有选件，将多次服务器调用减少至一次服务器调用。
* 由于选件是通过缓存立即显示的，不存在传统服务器调用引入的时间延迟，因此极大地提升了最终用户在您网站上的体验。
* 通过简单的单行代码和一次性开发人员设置，您的营销人员能够通过 VEC 在 SPA 上创建和运行 A/B 和体验定位 (XT) 活动。

## Adobe Target 视图和单页应用程序

Adobe Target 中 SPA VEC 利用了称作“视图”的新概念，即视觉元素的逻辑组合，这些元素共同构成了 SPA 体验。因此，SPA 可以被认为是通过基于用户交互的视图（而不是 URL）进行的转换。“视图”通常可显示整个站点或某个站点中分组的可视化元素。

为进一步说明“视图”的概念，让我们浏览一下这个在 React 中实施的假定的在线电子商务网站，并探索一些“视图”示例。单击下面的链接可在新浏览器选项卡中打开此站点。

**链接：[主页](https://target.enablementadobe.com/react/demo/#/)**

![home 站点](/help/c-experiences/assets/home.png)

导航到主页时，我们可以立即看到展示复活节促销活动的主页横幅，以及网站上销售的最新产品。在这种情况下，可以将“视图”定义为整个 home 站点。这种方式很容易记忆，我们将在下面的“实施 Adobe Target 视图”章节中对此进行详细介绍。

**链接：[产品站点](https://target.enablementadobe.com/react/demo/#/products)**

![产品网站](/help/c-experiences/assets/product-site.png)

当我们对企业销售的产品产生浓厚的兴趣时，我们将决定单击“Products”（产品）链接。与主页网站类似，可将整个产品站点定义为一个“视图”。我们可以将此视图命名为“products”（产品），就像 `https://target.enablementadobe.com/react/demo/#/products)` 中的路径名称一样。

![产品网站 2](/help/c-experiences/assets/product-site-2.png)

在本节的开始位置，我们将“视图”定义为整个站点，甚至是站点上的一组可视化元素。如上所示，可以将站点上显示的四个产品划归一组并将它们视为一个视图。如果想要命名此视图，则可以将其命名为“products”（产品）。

![产品网站 3](/help/c-experiences/assets/product-site-3.png)

我们决定单击“Load More”（了解更多）按钮，以浏览站点上的更多产品。在这种情况下，网站 URL 不会发生更改。但是，这里的视图只能呈现上面显示的第二行产品。此视图名称可称为“PRODUCTS-PAGE-2”。

**链接：[结帐](https://target.enablementadobe.com/react/demo/#/checkout)**

![结帐页面](/help/c-experiences/assets/checkout.png)

因为喜欢网站上显示的一些产品，因此我们决定购买几个产品。现在，在结帐站点上，我们可以选择正常递送或快递。由于视图可以是网站上的任意一组可视化元素，因此我们可以将其命名为“View Delivery Preferences”（查看递送首选项）。

此外，视图的概念可以进一步扩展。如果营销人员想要根据所选择的递送首选项来对网站上的内容进行个性化，则可以为每个递送首选项创建一个视图。在这种情况下，当我们选择“Normal Delivery”（普通递送）时，可以将视图命名为“Normal Delivery”（普通递送）。如果选择了“Express Delivery”（快递），则可以将视图命名为“Express Delivery”（快递）。

现在，营销人员可能想要运行 A/B 测试，以查看与将两个交付选项的按钮颜色保持为蓝色相比，在选择“Express Delivery”（快递）后将按钮颜色从蓝色更改为红色是否可以提高转化率。

## 实施 Adobe Target 视图

既然我们介绍了 Adobe Target 视图的内容，我们可以在 Target 中利用这一概念，使营销人员能够通过 VEC 在 SPA 上运行 A/B 和 XT 测试。这将需要一次性开发人员设置。下面我们将完成这些步骤以进行此设置。

1. 安装 at.js 2.x。

   首先，我们需要安装 at.js 2.x。开发此版本的 at.js 时考虑了 SPA。at.js 和 mbox.js 的早期版本不支持 Adobe Target 视图和 SPA VEC。

   通过位于[!UICONTROL 设置 &gt; 实施]中的 Adobe Target UI 下载 at.js 2.x。at.js 2.x 也可以通过 Adobe Launch 进行部署。但是，Adobe Target 扩展当前不是最新的，不受支持。

1. 在您的网站上实施 at.js 2.x 的最新函数：`triggerView()`。

   在定义要运行 A/B 或 XT 测试的 SPA 视图之后，实施 at.js 2.x 的 `triggerView()` 函数，并将视图作为参数传递。这允许营销人员使用 VEC 来针对所定义的那些视图设计和运行 A/B 和 XT 测试。如果没有为这些视图定义 `triggerView()` 函数，则 VEC 将不会检测到视图，因此营销人员将无法使用 VEC 来设计和运行 A/B 和 XT 测试。

   **`adobe.target.triggerView(viewName, options)`**

   | 参数 | 类型 | 必需？ | 验证 | 描述 |
   | --- | --- | --- | --- | --- |
   | viewName | 字符串 | 是 | 1. 无尾随空格。<br>2. 不能为空。<br>3. 所有页面的视图名称应该都是唯一的。<br>4. **警告**：视图名称不应以 `/` 开头或结尾。这是因为客户通常会从 URL 路径中提取视图名称。对于我们来说，“home”和“`/home`”是不同的。<br>5. **警告**：不应使用 `{page: true}` 选项连续多次触发同一视图。 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在 VEC 的[!UICONTROL 修改]面板中，供营销人员创建操作并运行其 A/B 和 XT 活动。 |
   | options | 对象 | 否 |  |  |
   | options &gt; page | 布尔值 | 否 |  | **TRUE**：page 的默认值为 true。当 `page=true` 时，将向 Edge 服务器发送增加展示次数计数的通知。<br>**FALSE**：当 `page=false` 时，将不会发送增加展示次数计数的通知。当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

   现在，我们来查看一些关于如何在 React 中为假定的电子商务 SPA 调用 `triggerView()` 函数的示例用例：

   **链接：[主页](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   作为营销人员，如果我们想要在整个主页网站上运行 A/B 测试，那么可能需要将视图命名为“home”。

```
 function targetView() {
   var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash

   viewName = viewName || 'home'; // view name cannot be empty

   // Sanitize viewName to get rid of any trailing symbols derived from URL
   if (viewName.startsWith('#') || viewName.startsWith('/')) {
     viewName = viewName.substr(1);
   }

   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 // react router v4
 const history = syncHistoryWithStore(createBrowserHistory(), store);
 history.listen(targetView);

 // react router v3
 <Router history={hashHistory} onUpdate={targetView} >
```

**链接：[产品站点](https://target.enablementadobe.com/react/demo/#/products)**

现在，我们来看一个比较复杂的示例。假设我们是营销人员，想要在用户单击“Load More”（加载更多）按钮后将“Price”（价格）标签颜色更改为红色，以对第二行的产品进行个性化。

![react products](/help/c-experiences/assets/react4.png)

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Products extends Component {
   render() {
     return (
       <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
     );
   }

   handleLoadMoreClicked() {
     var page = this.state.page + 1; // assuming page number is derived from component’s state
     this.setState({page: page});
     targetView('PRODUCTS-PAGE-' + page);
   }
 }
```

**链接：[结帐](https://target.enablementadobe.com/react/demo/#/checkout)**

![react checkout](/help/c-experiences/assets/react6.png)

如果营销人员想要根据所选择的递送首选项来对网站上的内容进行个性化，则可以为每个递送首选项创建一个视图。在这种情况下，当我们选择“Normal Delivery”（普通递送）时，可以将视图命名为“Normal Delivery”（普通递送）。如果选择了“Express Delivery”（快递），则可以将视图命名为“Express Delivery”（快递）。

现在，营销人员可能想要运行 A/B 测试，以查看与将两个交付选项的按钮颜色保持为蓝色相比，在选择“Express Delivery”（快递）后将按钮颜色从蓝色更改为红色是否可以提高转化率。

```
 function targetView(viewName) {
   // Validate if the Target Libraries are available on your website
   if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
     adobe.target.triggerView(viewName);
   }
 }

 class Checkout extends Component {
   render() {
     return (
       <div onChange={this.onDeliveryPreferenceChanged}>
         <label>
           <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
           <span> Normal Delivery (7-10 business days)</span>
         </label>

         <label>
           <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
           <span> Express Delivery* (2-3 business days)</span>
         </label>
       </div>
     );
   }
   onDeliveryPreferenceChanged(evt) {
     var selectedPreferenceValue = evt.target.value;
     targetView(selectedPreferenceValue);
   }
 }
```

## at.js 2.x 系统图

下图可帮助您了解含有视图的 at.js 2.x 工作流程以及其如何增强 SPA 集成。要更好地了解 at.js 2.x 中使用的概念，请参阅[单页应用程序实施](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)。

![使用 at.js 2.x 的 Target 流程](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 步骤 | 详细信息 |
| --- | --- |
| 1 | 如果用户通过了身份验证，则调用会返回 [!DNL Experience Cloud ID]；另一调用会同步客户 ID。 |
| 2 | at.js 库会同步加载，并隐藏文档正文。<br>也可以选择预先隐藏页面上实施的代码段，以异步方式加载 at.js。 |
| 3 | 将会发出页面加载请求，其中包括已配置的所有参数（例如，MCID、SDID 和客户 ID）。 |
| 4 | 配置文件脚本在执行后进入配置文件存储区。存储区向受众库请求符合条件的受众（例如从 Adobe Analytics、Audience Management 等共享的受众）。<br>客户属性会以批量过程发送到配置文件存储区。 |
| 5 | 根据 URL 请求参数和配置文件数据，[!DNL Target] 可决定将哪些活动和体验返回给查看当前页面和未来视图的访客。 |
| 6 | 目标内容会发送回页面，其中可能包含其他个性化的配置文件值。<br>当前页面上的目标内容会在默认内容不发生闪烁的情况下尽快显示。<br>视图中作为 SPA 用户操作结果显示的目标内容会缓存在浏览器中，因此当通过 `triggerView()` 触发视图时，可以立即应用它而无需额外的服务器调用。 |
| 7 | Analytics 数据会发送到数据收集服务器。 |
| 8 | 目标数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 Analytics for Target (A4T) 报表查看 <br>Analytics 数据。 |

现在，无论在 SPA 上的什么位置实施 `triggerView()`，都会从缓存中检索查看次数和操作，并在没有服务器调用的情况下显示给用户。`triggerView()` 还会向 [!DNL Target] 后端发出通知请求，以增加和记录展示次数计数。

![Target 流程 at.js 2.x triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 步骤 | 详细信息 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以渲染视图并应用操作来修改可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 [!DNL Target] 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

## 单页应用程序可视化体验编辑器

完成安装 at.js 2.x 并将 `triggerView()` 添加到站点后，便可使用 VEC 来运行 A/B 和 XT 活动。有关更多信息，请参阅[单页应用程序 (SPA) 可视化体验编辑器](/help/c-experiences/spa-visual-experience-composer.md)。

>[!NOTE]
>
>SPA VEC 其实与在常规网页上使用的 VEC 相同，但当您打开实施了 `triggerView()` 的单页应用程序时，还可以使用一些其他功能。

## 使用 TriggerView 确保 A4T 与 at.js 2.x 和 SPA 一起正常工作 {#triggerview}

要确保 [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) 与 at.js 2.x 一起正常工作，请务必在 Target 请求和 Analytics 请求中发送相同的 SDID。

与 SPA 相关的最佳实践：

* 使用自定义事件来通知应用程序中发生了一些有趣事件
* 在视图开始渲染之前触发自定义事件
* 在视图完成渲染时触发自定义事件

at.js 2.x 添加了一个新的 API [triggerView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) 函数。您应该使用 `triggerView()` 来通知 at.js 视图将开始渲染。

要了解如何组合自定义事件、at.js 2.x 和 Analytics，请参阅一个示例。此示例假设 HTML 页面包含访客 API，其后依次是 at.js 2.x 和 AppMeasurement。

假设存在以下自定义事件：

* `at-view-start` - 当视图开始渲染时
* `at-view-end` - 当视图完成渲染时

要确保结合使用 A4T 与 at.js 2.x，

视图开始处理程序应当如下：

```
document.addEventListener("at-view-start", function(e) {
  var visitor = Visitor.getInstance("<your Adobe Org ID>");
  
  visitor.resetState();
  adobe.target.triggerView("<view name>");
});
```

视图结束处理程序应当如下：

```
document.addEventListener("at-view-end", function(e) {
  // s - is the AppMeasurement tracker object
  s.t();
});
```

>[!NOTE]
>
>您必须触发 `at-view-start` 和 `at-view-end` 事件。这些事件并不是 at.js 自定义事件的一部分。

尽管这些示例使用的是 JavaScript 代码，但如果您正在使用标签管理器（例如 [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)），则可以简化所有这些代码。

如果遵循上述步骤，则应该针对 SPA 提供一个强大的 A4T 解决方案。

## 培训视频

以下视频包含更多信息：

### 了解 at.js 2.x 的工作原理

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=chi_hans)

请参阅 [了解. js2.x的工作](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) 原理以了解更多信息。

### 在 SPA 中实施 at.js 2.x

>[!VIDEO](https://video.tv.adobe.com/v/26248?captions=chi_hans)

有关 [更多信息，请参阅在单页应用程序(SPA)](https://helpx.adobe.com/target/kt/using/atjs2-single-page-application-technical-video-implement.html) 中实施Adobe Target. js2.x。

### 在 Adobe Target 中使用 SPA 的 VEC

>[!VIDEO](https://video.tv.adobe.com/v/26249?captions=chi_hans)

See [Using the Visual Experience Composer for Single Page Application (SPA VEC) in Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) for more information.