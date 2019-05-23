---
description: 使用单页应用程序 (SPA) 的可视化体验编辑器 (VEC)，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在大多数常用框架上创建活动，例如 React 和 Angular。
keywords: SPA VEC;React;Angular;react.js;SPA 可视化体验编辑器;SPA 体验编辑器选项;单页应用程序;single-page-app;SPA;移动设备体验选项;Target 视图
seo-description: 使用 Adobe Target 中单页应用程序 (SPA) 的可视化体验编辑器 (VEC)，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在大多数常用框架上创建活动，例如 React 和 Angular。
seo-title: 单页应用程序 (SPA) 可视化体验编辑器
solution: Target
title: 单页应用程序 (SPA) 可视化体验编辑器
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
translation-type: tm+mt
source-git-commit: 62552bfe5a6eb65dc1760b17543a0f5c84f0ecc5

---


# 单页应用程序 (SPA) 可视化体验编辑器{#single-page-app-spa-visual-experience-composer}

在 [!DNL Adobe Target] 中，[!UICONTROL 可视化体验编辑器] (VEC) 为营销人员提供了一种 DIY（自己动手）功能，可创建能够通过 Adobe Target 的全局 mbox 在传统的多页面应用程序上动态交付的活动和个性化体验。但是，这种方法依赖于页面加载或后续服务器调用中的检索选件，这会导致延迟，如下图所示。此方法不适用于单页应用程序 (SPA)，因为它会降低用户体验和应用程序性能。

![传统生命周期与 SPA 生命周期](/help/c-experiences/assets/trad-vs-spa.png)

现在，我们在最新版本中引入了 SPA VEC。使用 SPA VEC，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在常用框架（例如 React 和 Angular）上创建 [A/B 测试](/help/c-activities/t-test-ab/test-ab.md)和[体验定位](/help/c-activities/t-experience-target/experience-target.md) (XT) 活动。

## Adobe Target 视图和单页应用程序

Adobe Target 中 SPA VEC 利用了称作“视图”的新概念，即视觉元素的逻辑组合，这些元素共同构成了 SPA 体验。因此，SPA 可以被认为是通过基于用户交互的视图（而不是 URL）进行的转换。“视图”通常可显示整个站点或某个站点中分组的可视化元素。

为进一步说明“视图”的概念，让我们浏览一下这个在 React 中实施的假定的在线电子商务网站，并探索一些“视图”示例。单击下面的链接可在新浏览器选项卡中打开此站点。

**链接：[主页](https://target.enablementadobe.com/react/demo/#/)**

![home 站点](/help/c-experiences/assets/home.png)

导航到主页时，我们可以立即看到展示复活节促销活动的主页横幅，以及网站上销售的最新产品。在这种情况下，可以将“视图”定义为整个 home 站点。这种方式很容易记忆，我们将在下面的“实施 Adobe Target 视图”章节中对此进行详细介绍。

**链接：[产品站点](https://target.enablementadobe.com/react/demo/#/products)**

![产品站点](/help/c-experiences/assets/product-site.png)

随着我们对产品的兴趣增加，我们决定单击“Products”（产品）链接。与主页网站类似，可将整个产品站点定义为一个“视图”。我们可以将此视图命名为“products”（产品），就像 `https://target.enablementadobe.com/react/demo/#/products` 中的路径名称一样。

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

1. 安装在. js2.x上。

   首先，我们需要安装. js2.x。此版本的. js是使用SPA开发的。at.js 和 mbox.js 的早期版本不支持 Adobe Target 视图和 SPA VEC。

   ![“实施详细信息”对话框](/help/c-experiences/assets/imp-200.png)

   通过位于设置&gt;实施中 [!UICONTROL ]的Adobe Target UI下载. js2.x。at. js2.x也可以通过 [Adobe Launch部署](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。但是，Adobe Target 扩展当前不是最新的，不受支持。

1. 在. js2.x的最新函数上实现： [网站上的TrigererView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) 。

   在定义要运行A/B或XT测试的SPA的视图后，在作为参数传入的视图中实现. js2.x `triggerView()` 的函数。这允许营销人员使用 VEC 来针对所定义的那些视图设计和运行 A/B 和 XT 测试。如果没有为这些视图定义 `triggerView()` 函数，则 VEC 将不会检测到视图，因此营销人员将无法使用 VEC 来设计和运行 A/B 和 XT 测试。

   **`adobe.target.triggerView(viewName, options)`**

   | 参数 | 类型 | 必需？ | 验证 | 描述 |
   | --- | --- | --- | --- | --- |
   | viewName | 字符串 | 是 | 1. 无尾随空格。<br>2. 不能为空。<br>3. 所有页面的视图名称应该都是唯一的。<br>4. **警告**：视图名称不应以 `/` 开头或结尾。这是因为客户通常会从 URL 路径中提取视图名称。对于我们来说，“home”和“`/home`”是不同的。<br>5. **警告**：不应使用 `{page: true}` 选项连续多次触发同一视图。 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在 VEC 的[!UICONTROL 修改]面板中，供营销人员创建操作并运行其 A/B 和 XT 活动。 |
   | options | 对象 | 否 |
   | options &gt; page | 布尔值 | 否 | **TRUE**：page 的默认值为 true。当 `page=true` 时，将向 Edge 服务器发送增加展示次数计数的通知。<br>**FALSE**：当 `page=false` 时，将不会发送增加展示次数计数的通知。当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

   现在，我们来查看一些关于如何在 React 中为假定的电子商务 SPA 调用 `triggerView()` 函数的示例用例：

   **链接：[主页](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   作为营销人员，如果我们想要在整个主页网站上运行 A/B 测试，那么可能需要将视图命名为可从 URL 中提取的“home”。

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

   现在，我们来看一个比较复杂的示例。假设我们是营销人员，想要在用户单击“Load More”（加载更多）按钮后将价格标签颜色更改为红色，以对第二行的产品进行个性化。

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

1. 通过 VEC 启动 A/B 或 XT 活动。

   当在 SPA 上实施 `adobe.target.triggerView()` 并作为参数传递视图名称后，VEC 将能够检测到这些视图，并允许用户为其 A/B 或 XT 活动创建操作和修改。

   >[!NOTE]
   >
   >SPA VEC 其实与在常规网页上使用的 VEC 相同，但当您打开实施了 `triggerView()` 的单页应用程序时，还可以使用一些其他功能。

VEC 的[修改](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)面板和“操作”有两项主要改进，使 VEC 可以更好地处理 SPA。

**“修改”面板**

如下所示，[!UICONTROL 修改]面板可捕获为特定视图创建的操作。请注意，视图的所有操作都将分组到该视图下。

**操作**

单击某个操作会突出显示将应用此操作的网站上的元素。在View下创建的每个CMS操作都有四个图标，如下所示：信息、编辑、移动和删除。

![修改](/help/c-experiences/assets/modifications-new.png)

下表对每个操作进行了描述：

| 页面 | 描述 |
| --- | --- |
| 信息 | 显示操作的详细信息。 |
| 编辑 | 允许您直接编辑操作的属性。 |
| 移动 | 将操作移至页面加载事件或修改面板中已经存在的任何其他视图。<br>[!UICONTROL 页面加载事件] -在Web应用程序的初始页面加载上应用与页面加载事件对应的任何操作。<br>**注意** ：完成移动操作后，您需要通过浏览导航到CMS中的视图，以查看移动是否为有效操作。如果操作无法应用到视图，您将看到一个错误 |
| 删除 | 删除操作。 |

>[!NOTE]
>
>您可以在页面加载到CMS中之前执行很多操作，或者即使页面无法完全加载也是如此。网站加载之前无法编辑的操作会在 UI 中禁用。

**示例 1**

让我们参考上面创建“Home”（主页）视图的示例。针对此视图，我们有两个目标：

1. 将“Add to Cart”（添加到购物车）和“Like”（赞）按钮颜色更改为浅蓝色。此过程应该位于“Page Load”（页面加载）中，因为我们正在更改页眉的组件。
1. 将“Latest Products for 2019”（2019 年最新产品）标签更改为“Hottest Products for 2019”（2019 年最畅销产品），并将文本颜色更改为紫色。

要实现这些目标，请在 VEC 中，单击[!UICONTROL 撰写]并在 Home 视图中应用这些更改。

![示例 1](/help/c-experiences/assets/example1.png)

**示例 2**

让我们参考上面创建 PRODUCTS-PAGE-2 视图的示例。我们的目标是将“Price”（价格）标签更改为“Sale Price”（销售价格），并将标签颜色更改为红色。

1. 单击[!UICONTROL 浏览]，然后单击页眉处的 [!UICONTROL Products]（产品）链接。
1. 单击一次 [!UICONTROL Load More]（加载更多）以转到第二行产品。
1. 单击[!UICONTROL 撰写]。
1. 应用操作，以将文本标签更改为“Sale Price”（销售价格），并将其颜色更改为红色。

![示例 2](/help/c-experiences/assets/example2.png)

**示例 3**

最后，如前面所述，可以在粒度级别定义视图。视图可以是一个状态，也可以是单选按钮的一个选项。之前，我们已经创建了 CHECKOUT-EXPRESS 和 CHECKOUT-NORMAL 视图。我们的目标是将 CHECKOUT-EXPRESS 视图的按钮颜色更改为红色。

1. 单击[!UICONTROL 浏览]。
1. 将几个产品添加到购物车。
1. 单击右上角的购物车图标。
1. 单击“Checkout your Order”（支付订单）。
1. 单击“Express Delivery”（快递）单选按钮。
1. 单击[!UICONTROL 撰写]。
1. 将“Pay”（付款）按钮更改为“Complete the Order”（完成订单）按钮，并将按钮颜色更改为红色。

![示例 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>在单击“Express Delivery”（快递）单选按钮之前，CHECKOUT-EXPRESS 视图将不会显示在修改面板中。这是因为 `triggerView()` 函数在选择了“Express Delivery”（快递）单选按钮时触发，但只有在 VEC 知道存在有要显示在修改面板中的视图时才会发生这种情况。

## 深入了解 at.js 和 SPA

**如何检索视图以获取 SPA 上的初始页面加载后通过操作补充的最新受众数据？**

在您的站点加载时，. js2.x的典型工作流是缓存的，这样，您的所有视图和操作都将缓存，以便在您的站点上后续用户操作不会触发服务器调用来检索选件。如果要根据可能依靠后续用户操作更新的最新配置文件数据来检索视图，则可以调用 `getOffers()` 和 `applyOffers()` 并传递最新受众用户或配置文件数据。

例如，假定您是电信公司，并且您有一个在. js2.x上使用的SPA。作为企业，您希望实现以下目标：

* 针对已注销的用户或匿名用户，显示公司最新的促销活动，例如在 `http://www.telecom.com/home` 上显示“First month free”（首月免费）主页选件。
* 对于已登录的用户，针对合同即将到期的用户显示升级促销选件，例如在 `http://www.telecom.com/loggedIn/home` 上面显示“You are eligible for a free phone!”（您有资格享受免费通话！）。

现在，您的开发人员将命名视图，并以下列方式调用 `triggerView()`：

* 对于 `http://www.telecom.com/home`，视图名称为“Logged Out Home”（注销主页）
   * 将调用 `triggerView(“Logged Out Home”)`。
* 对于 `http://www.telecom.com/loggedIn/home`，视图名称为“Logged In Home”（登录主页）
   * 将在路由更改时调用 `triggerView(“Logged In Home”)`。

然后，营销人员通过 VEC 运行以下 A/B 活动：

* 要显示在 `http://www.telecom.com/home` 中的受众具有参数“`loggedIn= false`”且包含“First Month Free”（首月免费）选件的 A/B 活动，此时视图名称为“Logged Out Home”（注销主页）。
* 要显示在 `http://www.telecom.com/loggedIn/home` 中的受众具有参数“`loggedIn=true`”且包含“You are eligible for a free phone!”（您有资格享受免费通话！）选件的 A/B 活动，此时视图名称为“Logged In Hero Offer”（登录主页选件）。

现在，我们来研究一下此用户流程：

1. 匿名注销用户登陆您的页面。
1. 由于您正在使用. js2.x，因此，您在页面加载上传递参数“`loggedIn = false`”，以检索活动活动中存在的所有视图，这些视图有资格在受众具有参数“`loggedIn = false`”时获得。
1. at. js2.x然后检索“注销的主页”视图和动作以显示“首月免费”选件并将其存储在缓存中。
1. 调用 `triggerView(“Logged Out Home”)` 时，将从缓存中检索“First Month Free”（首月免费）选件，因此无需服务器调用即可显示选件。
1. 现在，用户单击“Log in”（登录）并提供其凭据。
1. 由于您的网站是 SPA，因此您不会执行整页加载，而是将用户路由到 `http://www.telecom.com/loggedIn/home`。

现在，有一个问题。用户登录后，我们会遇到 `triggerView(“Logged In Home”)`，因为我们将此代码置于路由更改中。这会告知. js2.x从缓存中检索视图和操作，但缓存中存在的唯一视图是“注销”主页。

那么，我们如何才能检索“Logged In”（登录）视图，并且显示“您有资格享受免费通话！”（You are eligible for a free phone!）选件？由于网站上的所有后续操作都是从已登录用户角度进行的，那么怎样才能保证所有后续操作都能为已登录的用户提供个性化选件？

您可以使用. js2.x中支持的新 `getOffers()` 功能和 `applyOffers()` 功能：

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

将 `getOffers()` 的响应传递给 `applyOffers()`，现在，与“loggedIn = true”关联的所有视图和操作都将更新 at.js 缓存。

换句话说，在. js2.x上，. js2.x支持以点播方式获取最新受众数据的视图、操作和选件。

**对于单页应用程序，at. js2.x支持A4T吗？**

是的，在您已实施Adobe Analytics和Experience Cloud访问者ID服务的 `triggerView()` 情况下，. js2.x支持A4T以获得SPA。请参阅下图中的分步说明。

![Target 流程](/help/c-experiences/assets/atjs-spa-flow.png)

| 步骤 | 描述 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以呈现视图并应用操作来修改与视图关联的可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 Target 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

>[!NOTE]
>如果不想在每次触发视图时向 Adobe Analytics 发送展示次数计数通知，请将 `{page: false}` 传递到 `triggerView()` 函数，以便在对不断重新呈现的组件多次触发视图时，展示次数计数不会被夸大。例如：
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## 受支持的活动

| 活动类型 | 受支持? |
| --- | --- |
| [A/B 测试](/help/c-activities/t-test-ab/test-ab.md) | 是 |
| [Recommendations ](/help/c-recommendations/recommendations-as-an-offer.md)<br>可作为 A/B 测试和体验定位活动 (XT) 的选件 | 是 |
| [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 |
| [体验定位](/help/c-activities/t-experience-target/experience-target.md) | 是 |
| [多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | 否 |
| [Auto-Target（自动定位）](/help/c-activities/auto-target-to-optimize.md) | 否 |
| [自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [推荐](/help/c-recommendations/recommendations.md) | 否 |

**如果我们安装在. js2.x上并在`triggerView()`我们的站点上实施，则我们如何运行自动Target A/B活动，因为SPA CMS不支持自动Target？**

如果要使用自动定位 A/B 活动，可以在 VEC 中移动所有要在页面加载事件中执行的操作。将鼠标悬停在每个操作上方，然后单击[!UICONTROL 移动到页面加载事件]按钮。完成此操作后，在下一步中，您可以为流量分配方法选择“自动定位”。

## 受支持的集成

| 集成 | 受支持? |
| --- | --- |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | 是 |
| [Experience Cloud 受众](/help/c-integrating-target-with-mac/mmp.md) | 是 |
| [客户属性](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | 是 |
| [AEM 体验片段](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | 是 |

## 受支持的功能 {#supported-features}

| 功能 | 受支持? |
| --- | --- |
| [工作区和属性](/help/administrating-target/c-user-management/property-channel/property-channel.md) | 是 |
| [QA 链接](/help/c-activities/c-activity-qa/activity-qa.md) | 是 |
| [基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md) | 否 |
| [自定义代码](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 是 |
| [VEC 选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | 所有 |
| [点击跟踪](/help/c-activities/r-success-metrics/click-tracking.md) | 是 |
| [多活动交付](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | 是 |

## 培训视频：在 Adobe Target 中使用 SPA VEC

>[!VIDEO](https://video.tv.adobe.com/v/26249)

有关更多信息，请参阅 [Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) 中的使用Visual Experience Composer for Single Page Application(SPA CMS)。
