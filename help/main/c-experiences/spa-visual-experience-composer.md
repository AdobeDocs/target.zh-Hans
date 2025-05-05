---
keywords: SPA VEC;React;Angular;react.js;SPA 可视化体验编辑器;SPA 体验编辑器选项;单页应用程序;single-page-app;SPA;移动设备体验选项;Target 视图
description: 了解如何在Adobe [!DNL Target] 中使用SPA VEC以DIY（自己动手）方式创建测试并对SPA上的内容进行个性化，而无需持续依赖开发。
title: 如何使用单页应用程序可视化体验编辑器(SPA VEC)？
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '3569'
ht-degree: 64%

---

# 单页面应用程序 (SPA) 可视化体验编辑器

在[!DNL Adobe Target]中，[!UICONTROL Visual Experience Composer] (VEC)为营销人员提供了一种DIY（自己动手）功能，可创建能够通过Adobe Target的全局mbox在传统多页面应用程序上动态交付的活动和个性化体验。 但是，这种方法依赖于页面加载或后续服务器调用中的检索选件，这会导致延迟，如下图所示。此方法不适用于单页应用程序 (SPA)，因为它会降低用户体验和应用程序性能。

![传统生命周期与 SPA 生命周期](/help/main/c-experiences/assets/trad-vs-spa.png)

现在，我们在最新版本中引入了 SPA VEC。使用 SPA VEC，营销人员能够以 DIY（自己动手）方式创建测试并对 SPA 上的内容进行个性化，而无需持续依赖开发。VEC 可用于在常用框架（例如 React 和 Angular）上创建 [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md)和[体验定位](/help/main/c-activities/t-experience-target/experience-target.md) (XT) 活动。

## Adobe[!DNL Target]视图和单页应用程序

Adobe Target 中 SPA VEC 利用了称作“视图”的新概念，即视觉元素的逻辑组合，这些元素共同构成了 SPA 体验。因此，SPA 可以被认为是通过基于用户交互的视图（而不是 URL）进行的转换。“视图”通常可显示整个站点或某个站点中分组的可视化元素。

为进一步说明视图的概念，让我们浏览一下这个在React中实施的假定的在线电子商务网站，并探索一些视图示例。 单击下面的链接可在新浏览器选项卡中打开此站点。

**链接：[主站点](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)**

![home 站点](/help/main/c-experiences/assets/home.png)

导航到主页时，我们可以立即看到展示复活节促销活动的主页图像，以及网站上销售的最新产品。在这种情况下，可以将“视图”定义为整个 home 站点。这种方式很容易记忆，我们将在下面的“实施 Adobe Target 视图”章节中对此进行详细介绍。

**链接：[产品站点](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)**

![产品站点](/help/main/c-experiences/assets/product-site.png)

随着我们对产品的兴趣增加，我们决定单击“Products”（产品）链接。与主页网站类似，可将整个产品站点定义为一个“视图”。我们可以将此视图命名为“products”（产品），就像 `https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products` 中的路径名称一样。

![产品网站 2](/help/main/c-experiences/assets/product-site-2.png)

在本节的开始位置，我们将“视图”定义为整个站点，甚至是站点上的一组可视化元素。如上所示，可以将站点上显示的四个产品划归一组并将它们视为一个视图。如果想要命名此视图，则可以将其命名为“products”（产品）。

![产品网站 3](/help/main/c-experiences/assets/product-site-3.png)

我们决定单击“Load More”（了解更多）按钮，以浏览站点上的更多产品。在这种情况下，网站 URL 不会发生更改。但是，这里的视图只能呈现上面显示的第二行产品。此视图名称可称为“PRODUCTS-PAGE-2”。

**链接： [结帐](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/checkout)**

![结帐页面](/help/main/c-experiences/assets/checkout.png)

因为喜欢网站上显示的一些产品，因此我们决定购买几个产品。现在，在结帐站点上，我们可以选择正常递送或快递。由于视图可以是网站上的任意一组可视化元素，因此我们可以将其命名为“View Delivery Preferences”（查看递送首选项）。

此外，视图的概念可以进一步扩展。如果营销人员想要根据所选择的递送首选项来对网站上的内容进行个性化，则可以为每个递送首选项创建一个视图。在这种情况下，当我们选择“Normal Delivery”（普通递送）时，可以将视图命名为“Normal Delivery”（普通递送）。如果选择了“Express Delivery”（快递），则可以将视图命名为“Express Delivery”（快递）。

现在，营销人员可能想要运行 A/B 测试，以查看与将两个交付选项的按钮颜色保持为蓝色相比，在选择“Express Delivery”（快递）后将按钮颜色从蓝色更改为红色是否可以提高转化率。

## 正在实施Adobe[!DNL Target]视图

既然我们介绍了 Adobe Target 视图的内容，我们可以在 Target 中利用这一概念，使营销人员能够通过 VEC 在 SPA 上运行 A/B 和 XT 测试。这将需要一次性开发人员设置。下面我们将完成这些步骤以进行此设置。

1. 安装 at.js 2.x。

   首先，我们需要安装 at.js 2.x。开发此版本的 at.js 时考虑了 SPA。at.js的早期版本并且不支持Adobe Target视图和VEC for SPA。

   ![“实施详细信息”对话框](/help/main/c-experiences/assets/imp-200.png)

   通过位于[!UICONTROL Administration > Implementation]中的Adobe Target UI下载at.js 2.x。 at.js 2.x也可以通过[Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=zh-Hans){target=_blank}中的标记进行部署。 但是，Adobe Target扩展当前不是最新的，不受支持。

1. 在您的网站上实施at.js 2.x的最新函数： [triggerView()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-triggerview-atjs-2.html?lang=zh-Hans){target=_blank}。

   在定义要运行A/B或XT测试的SPA视图之后，实施at.js 2.x的`triggerView()`函数，并将视图作为参数传递。 这允许营销人员使用 VEC 来针对所定义的那些视图设计和运行 A/B 和 XT 测试。如果没有为这些视图定义 `triggerView()` 函数，则 VEC 将不会检测到视图，因此营销人员将无法使用 VEC 来设计和运行 A/B 和 XT 测试。

   **`adobe.target.triggerView(viewName, options)`**

   | 参数 | 类型 | 必需？ | 验证 | 描述 |
   | --- | --- | --- | --- | --- |
   | viewName | 字符串 | 是 | 1. 无尾随空格。<br>2. 不能为空。<br>3. 所有页面的视图名称应该都是唯一的。<br>4. **警告**：视图名称不应以 `/` 开头或结尾。这是因为客户通常会从 URL 路径中提取视图名称。对于我们来说，“home”和“`/home`”是不同的。<br>5. **警告**：不应使用 `{page: true}` 选项连续多次触发同一视图。 | 将任何名称作为要显示视图的字符串类型传递。此视图名称显示在VEC的[!UICONTROL Modifications]面板中，供营销人员创建操作并运行其A/B和XT活动。 |
   | options | 对象 | 否 |  |  |
   | options > page | 布尔值 | 否 |  | **TRUE**：page 的默认值为 true。当 `page=true` 时，将向 Edge 服务器发送增加展示次数计数的通知。<br>**FALSE**：当`page=false`时，将不会发送增加展示次数计数的通知。 当您只想在具有选件的页面上重新渲染组件时，才应该使用此选项。 |

   现在，我们来查看一些关于如何在React中为假定的电子商务SPA调用`triggerView()`函数的示例用例：

   **链接：[主站点](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)**

   ![home-react-1](/help/main/c-experiences/assets/react1.png)

   作为营销人员，如果我们想要在整个主页网站上运行 A/B 测试，那么可能需要将视图命名为可从 URL 中提取的“home”。

   ```javascript
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

   **链接：[产品站点](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)**

   现在，让我们来看一个比较复杂的示例。 假设我们是营销人员，想要在用户单击“Load More”（加载更多）按钮后将价格标签颜色更改为红色，以对第二行的产品进行个性化。

   ![react products](/help/main/c-experiences/assets/react4.png)

   ```javascript
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
       var page = this.state.page + 1; // assuming page number is derived from component's state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **链接： [结帐](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/checkout)**

   ![react checkout](/help/main/c-experiences/assets/react6.png)

   如果营销人员想要根据所选择的递送首选项来对网站上的内容进行个性化，则可以为每个递送首选项创建一个视图。在这种情况下，当我们选择“Normal Delivery”（普通递送）时，可以将视图命名为“Normal Delivery”（普通递送）。如果选择了“Express Delivery”（快递），则可以将视图命名为“Express Delivery”（快递）。

   现在，营销人员可能想要运行 A/B 测试，以查看与将两个交付选项的按钮颜色保持为蓝色相比，在选择“Express Delivery”（快递）后将按钮颜色从蓝色更改为红色是否可以提高转化率。

   ```javascript
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

VEC 的[修改](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)面板和“操作”有两项主要改进，使 VEC 可以更好地处理 SPA。

**“修改”面板**

如下所示，[!UICONTROL Modifications]面板可捕获为特定视图创建的操作。 请注意，视图的所有操作都将分组到该视图下。

**操作**

单击某个操作会突出显示将应用此操作的网站上的元素。在“视图”下创建的每个 VEC 操作都具有如下所示的几个图标：“信息”、“编辑”、“克隆”、“移动”和“删除”。

![修改](/help/main/c-experiences/assets/modifications.png)

下表对每个操作进行了描述：

| 页面 | 描述 |
| --- | --- |
| 信息 | 显示操作的详细信息。 |
| 编辑 | 允许您直接编辑操作的属性。 |
| 克隆 | 将操作克隆到[!UICONTROL Modifications]面板上存在的一个或多个视图，或者您在VEC中浏览并导航到的一个或多个视图。 此操作不一定存在于[!UICONTROL Modifications]面板中。<br>**注意**：完成克隆操作后，您需要通过[!UICONTROL Browse]导航到VEC中的视图，以查看克隆操作是否有效。 如果该操作未应用到视图，您将看到一个错误。 |
| 移动 | 将操作移动到“页面加载事件”或修改面板中已存在的任何其他视图。<br>[!UICONTROL Page Load Event] — 与页面加载事件对应的任何操作会应用于Web应用程序的初始页面加载。<br>**注意**&#x200B;完成移动操作后，您需要通过“浏览”导航到VEC中的视图，以查看移动操作是否有效。 如果该操作未应用到视图，您将看到一个错误 |
| 删除 | 删除操作。 |

>[!NOTE]
>
>您可以在页面加载到 VEC 之前执行很多操作，或者即使页面无法完全加载也是如此。网站加载之前无法编辑的操作会在 UI 中禁用。

**示例 1**

让我们参考上面创建“Home”（主页）视图的示例。 针对此视图，我们有两个目标：

1. 将“Add to Cart”（添加到购物车）和“Like”（赞）按钮颜色更改为浅蓝色。此过程应该位于“页面加载”中，因为我们正在更改页眉的组件。
1. 将“Latest Products for 2019”（2019 年最新产品）标签更改为“Hottest Products for 2019”（2019 年最畅销产品），并将文本颜色更改为紫色。

要执行这些目标，请在VEC中，单击[!UICONTROL Compose]并在“主页”视图中应用这些更改。

![示例 1](/help/main/c-experiences/assets/example1.png)

**示例 2**

让我们参考上面创建PRODUCTS-PAGE-2视图的示例。 我们的目标是将“Price”（价格）标签更改为“Sale Price”（销售价格），并将标签颜色更改为红色。

1. 单击[!UICONTROL Browse]，然后单击标题处的[!UICONTROL Products]链接。
1. 单击一次[!UICONTROL Load More]以转到第二行产品。
1. 单击 [!UICONTROL Compose]。
1. 应用操作，以将文本标签更改为“Sale Price”（销售价格），并将其颜色更改为红色。

![示例 2](/help/main/c-experiences/assets/example2.png)

**示例 3**

最后，如前面所述，可以在粒度级别定义视图。视图可以是一个状态，也可以是单选按钮的一个选项。之前，我们已经创建了 CHECKOUT-EXPRESS 和 CHECKOUT-NORMAL 视图。我们的目标是将 CHECKOUT-EXPRESS 视图的按钮颜色更改为红色。

1. 单击 [!UICONTROL Browse]。
1. 将几个产品添加到购物车。
1. 单击右上角的购物车图标。
1. 单击“Checkout your Order”（支付订单）。
1. 单击“Express Delivery”（快递）单选按钮。
1. 单击 [!UICONTROL Compose]。
1. 将“Pay”（付款）按钮更改为“Complete the Order”（完成订单）按钮，并将按钮颜色更改为红色。

![示例 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>在单击“Express Delivery”（快递）单选按钮之前，CHECKOUT-EXPRESS 视图将不会显示在修改面板中。这是因为 `triggerView()` 函数在选择了“Express Delivery”（快递）单选按钮时触发，但只有在 VEC 知道存在有要显示在修改面板中的视图时才会发生这种情况。

## 深入了解 at.js 和 SPA

**如何检索视图以获取 SPA 上的初始页面加载后通过操作补充的最新受众数据？**

at.js 2.x的典型工作流程是，在您的网站加载时，将缓存所有视图和操作都，这样网站上的后续用户操作不会触发检索选件的服务器调用。 如果要根据可能依靠后续用户操作更新的最新配置文件数据来检索视图，则可以调用 `getOffers()` 和 `applyOffers()` 并传递最新受众用户或配置文件数据。

例如，假定您是一家电信公司，并且拥有使用 at.js 2.x 的 SPA。作为一家企业，您想要实现以下目标：

* 对于已注销的用户或匿名用户，显示公司最新的促销活动，例如在`http://www.telecom.com/home`上显示“First month free”（首月免费）主页选件。
* 对于登录用户，为合同即将到期的用户显示升级促销优惠，例如“您有资格享受免费电话！” 在 `http://www.telecom.com/loggedIn/home` 上面显示“You are eligible for a free phone!”（您有资格享受免费通话！）。

现在，您的开发人员将命名视图，并以下列方式调用 `triggerView()`：

* 对于 `http://www.telecom.com/home`，视图名称为“Logged Out Home”（注销主页）
   * 将调用 `triggerView("Logged Out Home")`。
* 对于 `http://www.telecom.com/loggedIn/home`，视图名称为“Logged In Home”（登录主页）
   * 将在路由更改时调用 `triggerView("Logged In Home")`。

然后，营销人员通过 VEC 运行以下 A/B 活动：

* 要显示在`http://www.telecom.com/home`中的受众具有参数“`loggedIn= false`”且包含“First Month Free”（首月免费）选件的A/B活动，此时视图名称为“Logged Out Home”（注销主页）。
* A/B活动中的“您有资格免费使用电话！” 参数为“`loggedIn=true`”的受众的选件显示在`http://www.telecom.com/loggedIn/home`中，其中视图名称为“登录主页选件”。

现在，我们来研究一下此用户流程：

1. 匿名注销用户登陆您的页面。
1. 由于您使用的是at.js 2.x，因此在页面加载中传递参数“`loggedIn = false`”，以在受众具有参数“`loggedIn = false`”时，检索活跃活动中存在的符合条件的所有视图。
1. 然后，at.js 2.x检索“Logged Out Home”（注销主页）视图和操作以显示“First Month Free”（首月免费）选件并将其存储在缓存中。
1. 调用`triggerView("Logged Out Home")`时，将从缓存中检索“First Month Free”（首月免费）选件，无需服务器调用即可显示选件。
1. 用户现在单击“登录”并提供其凭据。
1. 由于您的网站是 SPA，因此您不会执行整页加载，而是将用户路由到 `http://www.telecom.com/loggedIn/home`。

现在，有一个问题。用户登录后，我们会遇到 `triggerView("Logged In Home")`，因为我们将此代码置于路由更改中。这会告知 at.js 2.x 从缓存中检索视图和操作，但缓存中唯一存在的视图是“Logged Out Home”（注销主页）。

那么，我们如何才能检索“Logged In”（登录）视图，并显示“您有资格享受免费电话！”(You are eligible for a free phone！) 选件？由于网站上的所有后续操作都是从已登录用户角度进行的，那么怎样才能保证所有后续操作都能为已登录的用户提供个性化选件？

您可以使用 at.js 2.x 中支持的新 `getOffers()` 和 `applyOffers()` 函数：

```javascript
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

将`getOffers()`的响应传递给`applyOffers()`，现在，与“loggedIn = true”关联的所有视图和操作都将更新at.js缓存。

换句话说，at.js 2.x 支持一种以按需方式检索具有最新受众数据的视图、操作和选件的方法。

**at.js 2.x 是否支持用于单页应用程序的 A4T？**

支持，at.js 2.x 通过 `triggerView()` 函数支持用于 SPA 的 A4T，只要您实施了 Adobe Analytics 和 Experience Cloud 访客 ID 服务。请参阅下图中的分步说明。

![Target 流程](/help/main/c-experiences/assets/atjs-spa-flow.png)

| 步骤 | 描述 |
| --- | --- |
| 1 | 在 SPA 中调用 `triggerView()` 以呈现视图并应用操作来修改与视图关联的可视化元素。 |
| 2 | 从缓存中读取视图的目标内容。 |
| 3 | 目标内容会在默认内容不发生闪烁的情况下尽快显示。 |
| 4 | 通知请求将发送到 Target 配置文件存储区，以计算活动中的访客和递增量度。 |
| 5 | Analytics 数据会发送到数据收集服务器。 |
| 6 | Target 数据会通过 SDID 匹配到 Analytics 数据，并且会进行相应处理以保存到 Analytics 报表存储中。之后，便可以在 Analytics 和 Target 中通过 A4T 报表查看 Analytics 数据。 |

>[!NOTE]
>如果不想在每次触发视图时向Adobe Analytics发送展示次数计数通知，请将`{page: false}`传入`triggerView()`函数，以便在对不断重新呈现的组件多次触发视图时，展示次数计数不会被夸大。 例如：
>
>`adobe.target.triggerView("PRODUCTS-PAGE-2", {page:false})`

## 受支持的活动

| 活动类型 | 受支持? |
| --- | --- |
| [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md) | 是 |
| 在A/B测试和体验定位(XT)活动中[Recommendations作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)<br> | 是 |
| [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 是 |
| [体验定位](/help/main/c-activities/t-experience-target/experience-target.md) | 是 |
| [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | 否 |
| [Auto-Target（自动定位）](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 否 |
| [自动个性化](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | 否 |
| [推荐](/help/main/c-recommendations/recommendations.md) | 否 |

**如果安装了 at.js 2.x 并在网站上实施了 `triggerView()`，则在 SPA VEC 不支持自动定位时，我们该如何运行自动定位 A/B 活动？**

如果要使用自动定位 A/B 活动，可以在 VEC 中移动所有要在页面加载事件中执行的操作。将鼠标悬停在每个操作上，然后单击[!UICONTROL Move to Page Load Event]按钮。 完成此操作后，在下一步中，您可以为流量分配方法选择“自动定位”。

## 受支持的集成

| 集成 | 受支持? |
| --- | --- |
| [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | 是 |
| [Experience Cloud 受众](/help/main/c-integrating-target-with-mac/mmp.md) | 是 |
| [客户属性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=zh-Hans){target=_blank} | 是 |
| [AEM 体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | 是 |

## 受支持的功能 {#supported-features}

| 功能 | 受支持? |
| --- | --- |
| [工作区和属性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) | 是 |
| [QA 链接](/help/main/c-activities/c-activity-qa/activity-qa.md) | 是 |
| [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) | 否 |
| [自定义代码](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 是 |
| [VEC 选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | 所有 |
| [点击跟踪](/help/main/c-activities/r-success-metrics/click-tracking.md) | 是 |
| [多活动交付](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) | 是 |

## SPA VEC的“页面交付”设置 {#page-delivery-settings}

通过[!UICONTROL Page Delivery]设置，可配置规则以确定Target活动应何时符合条件并为受众执行。

要从VEC的三步引导式活动创建工作流中访问[!UICONTROL Page Delivery]选项，请从&#x200B;**[!UICONTROL Experiences]**&#x200B;步骤中单击&#x200B;**[!UICONTROL Configure]**（齿轮图标）> **[!UICONTROL Page Delivery]**。

![“页面交付”选项对话框](/help/main/c-experiences/assets/page-delivery.png)

例如，如上面显示的[!UICONTROL Page Delivery]设置所定义，当访客直接登陆`https://www.adobe.com` *或*&#x200B;且访客登陆任何包含`https://www.adobe.com/products`的URL时，Target活动就会符合条件并执行。 这非常适用于任何多页面应用程序，在该应用程序中，与页面的每次交互都会调用页面重新加载，at.js 会为此检索符合用户导航到的 URL 条件的活动。

但是，由于SPA的工作方式不同，因此必须配置[!UICONTROL Page Delivery]设置，以便允许将所有操作应用于SPA VEC活动中定义的视图。

### 示例用例

请考虑以下示例用例：

![SPA VEC“修改”面板](/help/main/c-experiences/assets/page-delivery-example.png)

进行了以下更改：

* 更改了“主页”视图中的背景颜色，该视图位于以下URL下： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)。
* 更改了“产品”视图中的按钮颜色，该视图位于以下URL下： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)。

SPA根据上面的示例，当我们将[!UICONTROL Page Delivery]设置配置为仅包含[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)时，将会发生什么情况：在使用at.js 2.*x* 的 SPA 中），会出现什么情况？

![“页面交付”对话框](/help/main/c-experiences/assets/spa-page-delivery.png)

下图显示了 at.js 2.*x* 中的 Target 流程 - 页面加载请求：

![Target 流程 - at.js 2.0 页面加载请求](/help/main/c-experiences/assets/page-load-request.png)

**用户历程 1**

* 用户直接导航到[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)。
* at.js 2.*x*&#x200B;向Edge发出查询，以了解是否需要为以下URL执行任何活动： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/)。
* 在步骤 6 中，Target Edge 会返回“主页”和“产品”视图的操作，以便在浏览器中缓存它们。

**结果**：用户看到“主页”视图中的背景颜色显示为绿色。当用户随后导航到[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)时，会看到按钮的蓝色背景颜色，因为该操作已缓存在浏览器中的“产品”视图下。

注意：用户导航到[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)不会触发页面加载。

**用户历程 2**

* 用户直接导航到[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)。
* at.js 2.*x*&#x200B;向Edge发出查询，以了解是否需要为以下URL执行任何活动： [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)。
* 没有符合[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)条件的活动。
* 由于没有符合条件的活动，因此不存在要缓存以供 at.js 2.*x* 从中触发的操作和视图。

**结果**：即使您已经为“产品”视图定义了`triggerView()`并通过SPA VEC对“产品”视图执行了操作，您也不会看到预期的操作，因为您未在“页面交付”设置中创建包含[https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=zh-Hans#/products)的规则。

### 最佳实践

您可以看到，管理用户历程可能非常困难，因为用户可以登陆 SPA 的任何 URL 并导航到任何其他页面。因此，最好指定包含基本 URL 的“页面交付”规则，以使其包含整个 SPA。这样一来，您就无需考虑所有不同的历程和路径，用户可能会使用这些历程和路径访问要显示A/B测试或体验定位(XT)活动的页面。

例如，为了解决以上面临的问题，我们可以在“页面交付”设置中指定基本 URL，如下所示：

![“页面交付”对话框](/help/main/c-experiences/assets/conclusion.png)

这可确保只要访客登陆 SPA 并导航到“主页”或“页面”视图，就会看到所应用的操作。

现在，每当您向SPA VEC中的视图添加操作时，我们都会显示以下弹出消息，提醒您考虑[!UICONTROL Page Delivery]规则。

![“页面交付设置”消息](/help/main/c-experiences/assets/pop-up-message.png)

当您为创建的每个新活动的视图添加第一个操作时，将会显示此消息。此消息有助于确保贵组织中的每个人都能够了解如何正确应用这些[!UICONTROL Page Delivery]规则。

## 培训视频：在 Adobe Target 中使用 SPA VEC

>[!VIDEO](https://video.tv.adobe.com/v/34758?captions=chi_hans)

有关详细信息，请参阅[在Adobe Target中使用单页应用程序的可视化体验编辑器(SPA VEC)](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html)。
