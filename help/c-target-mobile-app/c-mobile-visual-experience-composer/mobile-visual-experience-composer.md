---
description: 使用本机移动设备应用程序的可视化体验编辑器 (VEC)，您能够以 DIY（自己动手）方式创建活动并对本机移动设备应用程序上的内容进行个性化，而无需持续依赖开发和应用程序发布循环。
seo-description: 使用本机移动设备应用程序的可视化体验编辑器 (VEC)，您能够以 DIY（自己动手）方式创建活动并对本机移动设备应用程序上的内容进行个性化，而无需持续依赖开发和应用程序发布循环。
seo-title: 移动设备应用程序可视化体验编辑器
solution: Target
title: 移动设备应用程序可视化体验编辑器
topic: Standard
uuid: 83702f9c-40ff-441b-b773-46b01155a6f2
translation-type: tm+mt
source-git-commit: 935e2d15854dd8f4b09b6df907764b2d86e474ad

---


# 移动设备应用程序可视化体验编辑器{#mobile-app-visual-experience-composer}

使用本机移动设备应用程序的可视化体验编辑器 (VEC)，您能够以 DIY（自己动手）方式创建活动并对本机移动设备应用程序上的内容进行个性化，而无需持续依赖开发和应用程序发布循环。

现有的[可视化体验编辑器](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)为您提供了以 DIY（自己动手）方式创建活动和个性化体验的功能，这些活动和体验可以通过 Target 的全局 Mbox 以动态方式交付到您的 Web 属性，而无需任何开发人员干预。您现在可以利用 VEC 对本机移动设备应用程序执行相同的操作。AEP [SDK v上提供的移动App CMS可](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec)用于为移动应用程序创建 [A/B测试](/help/c-activities/t-test-ab/test-ab.md) 和 [体验定位(XT)](/help/c-activities/t-experience-target/experience-target.md) 活动。对其他活动类型的支持将在以后提供。

移动应用程序CMS支持 [在支持的浏览器](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)中列出的浏览器。

## 使用本机移动设备应用程序的可视化体验编辑器 {#using-the-mobile-vec}

下图表示了使用移动应用程序CMS的过程：

![](assets/mobile-vec-diagram.png)

| 过程 | 详细信息 |
|--- |--- |
| 配对 | 安全授权您的移动设备应用程序和设备与 Target 配合使用。对于设备，此步骤只需一次。 |
| 创作 | 创作[Target 活动](/help/c-activities/activities.md)，实时预览在 Target UI 中执行的操作。 |
| 交付 | Target 在您的本机移动设备应用程序中自动交付活动。 |

**配对：**

移动App CMS实时连接营销人员的移动应用程序以创作Target活动。要做到这一点，第一步是将移动设备和应用程序与 Target 进行安全配对（授权）。

1. 例如，在创建 A/B 测试活动时，依次选择 **[!UICONTROL 移动设备应用程序]**、**[!UICONTROL 可视化（默认）]**，然后单击 **[!UICONTROL 下一步]**。

   ![](assets/mobile-vec-create-1.png)

1. 输入应用程序的 URL，然后单击 **[!UICONTROL 创建深层链接]**。

   ![](assets/mobile-vec-create-2.png)

配对过程包含以下步骤：

1. 输入可用于生成深层链接的应用程序 URL 方案。典型的深层链接如下所示：

   `mymobileapp://path?params`

1. 深层链接会以二维码或 URL 形式提供。用户可以从电话扫描QR码或通过电子邮件发送URL给自己。深层链接 URL 具有授权令牌，用于将移动设备应用程序和设备与 Target 进行安全配对。
1. 在您的移动设备上打开深层链接 URL。此操作将会启动移动设备应用程序。SDK 确定该应用程序已启动，可供进行配对和在 VEC 中进行创作。

   SDK 向 Target 服务器发出请求并自行注册。Target 服务器授权令牌并与相应设备建立实时连接（当前使用 Web 套接字）。

   建立连接后，Target 界面中会显示应用程序的实时视图。应用程序有一个红色叠加边界，指示应用程序已连接到 Target，如下图所示。

   ![](assets/mobile-vec-create-3.png)

   可以通过启动应用程序并打开创作界面来重新连接已配对的设备。

**创作：**

连接应用程序并在 VEC 中显示应用程序的实时视图后，您可以开始创作活动。目前支持以下操作：

| 操作 | 详细信息 |
|--- |--- |
| 交换图像 | 通过选择其他图像选件或直接设置图像的CDN URL，将图像替换为另一个图像。Target中的图像提供通过 [Adobe Scene提供](/help/administrating-target/scene7-settings.md)。 |
| 更改文本 | 在文本元素、按钮或标签中更改文本内容、颜色或字体大小。 |
| 更改背景 | 更改文本区域或按钮的内容或元素背景。 |

应用程序中可实时显示在 VEC 中执行的操作，从而允许在创作期间使用实时预览功能。这些操作与相关的“移动设备屏幕”或“视图”以恰当的方式相关联。

![](assets/mobile-vec-create-4.png)

## 疑难解答 {#troubleshooting}

**移动App CMS表示我的应用程序已断开连接。**

您的 Internet 连接可能已断开。在 Internet 可用后，重新启动应用程序，此时将会建立新连接。我们建议在WiFi连接上创作移动应用程序CMS活动。

**移动App CMS不与我的移动应用程序同步。**

单击 VEC 中的“[!UICONTROL 刷新]”按钮可同步显示。

## Target 视图和移动设备应用程序 {#target-views}

移动App CMS利用了新的视图概念：构成移动应用体验的可视可视元素组。

**介绍 Target 视图**

我们以花卉销售应用程序为例。该应用程序允许用户执行以下任务：

* 列出在售的鲜花和花束
* 查看详细信息
* 订购鲜花
* 控制设置，例如付款选项和地址

在此应用程序中，您可以在移动设备应用程序的不同屏幕上完成上述每项任务。当用户浏览该应用程序时，会呈现一个屏幕，允许他们执行后续某一任务。如果您是 Android 开发人员，您很可能会创建四个不同的 Android 活动类，每个类均与其中一项任务相关联。

在这种情况下，可以将每项任务视为由移动设备应用程序转换的视图。我们将其称为目标视图，每个视图都有特色。Target 视图（简称“视图”）是在移动设备屏幕上显示的可视化元素的逻辑容器。例如，Android 中的一个屏幕或活动类就是一个视图。

移动设备应用程序很少能够做到如此简单。让我们使它更实用一点。在第一项列出在售鲜花和花束的任务中，我们可以添加创建多个布局的功能，从而创建不同的屏幕。例如，让我们添加一个“排序依据”功能，该功能有三个选项：

* 按受欢迎程度
* 价格 - 由低到高
* 价格 - 由高到低

在此示例中，每当用户选择不同的“排序依据”选项时，即使活动类相同，也会显示新屏幕。因此，可以将其中的每个屏幕视为不同的 Target 视图。

作为营销人员，您会希望创建不同的体验并对其中每个视图运行不同的选件，而无需要求开发人员设置本地 mbox 或完成应用程序发布循环。

## 设置Target移动应用程序CMS {#setting-up}

开发人员必须执行以下操作才能为移动应用程序启用移动应用程序CMS：

* 在Launch中配置Adobe Target CMS扩展
   * CMS扩展取决于Adobe [Target扩展](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)。确保Adobe Target扩展已配置和启用。
* 将Target CMS扩展添加到应用程序。
   * [Android - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)
   * [iOS - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)

## Target CMS的实施方法

Target CMS扩展可通过网络请求检索应用程序的相关Target体验。通过此网络调用检索选件并自动应用于目标屏幕。当用户浏览应用程序多个屏幕时，不会发出后续网络请求来检索CMS体验。

扩展的默认行为是在应用程序启动时发出同步网络请求(阻止调用)。您可以使用Launch控制此网络请求的行为以满足您的应用程序行为。

### 自动Fetch Target活动

这是通过Target CMS扩展自动启动网络请求的默认行为。您可以使用以下选项之一来请求阻止调用或异步请求。

* 在同步呼叫中提取(背景已关闭)

   选择此选项后，Target CMS扩展将作为应用程序启动时的阻止调用进行网络请求。立即应用选件，应用程序中不会闪烁闪烁。这是扩展的默认行为。

* 在异步调用中提取(背景已开启)

   选择此选项后，Target CMS扩展在应用程序启动时在后台发出网络请求，但不阻止应用程序加载。如果您的体验创作在应用程序的主屏幕上，则在调用完成之前，选件可能不适用于主屏幕。应用程序屏幕渲染通常通过生命周期事件 `didFinishLaunchingWithOptions` 和iOS `onActivityResumed` 和Android分别标识。选件会自动应用于所有后续屏幕。

### 以编程方式获取Target活动

您可以禁用Target CMS扩展以自动发出网络请求，并决定有计划地调用Extension API。这使开发人员能够控制如何在应用程序中集成Target CMS选件。Target CMS扩展有两种静态方法 `prefetchOffers` ，可用于编程检索Target `prefetchOffersBackground` CMS提供的内容。

* `prefetchOffers` 此方法会隐藏当前屏幕，直到获取Target CMS选件。选件会自动应用于当前屏幕(如果适用)，屏幕会再次可见。
* `prefetchOffersBackground` 该方法不隐藏当前屏幕，并发出调用以检索相关的Target选件。目标选件 ** 不会应用于当前屏幕，而且不会闪烁。当用户导航到后续屏幕时，会自动应用选件(如果适用)。

### 处理目标工作区限制

您可以使用Launch界面设置工作区 `at_property` 的值。这将确保只有该工作区中的活动才会发送到您的移动应用程序。

## Target API调用的一般指南 {#section_C7276795F02540DCA230AEEDF882A833}

要为 Android 正确添加 Target 视图，请查看此处的简单表格，其中列出了正确放置 `targetView` 调用的位置：

| 可接受的 TargetView 位置 | 正确添加的条件 |
|--- |--- |
| `Activity::onStart`、`Activity::onResume` 的末尾 | 取决于开发人员是将 `OnStart` 和 `OnResume` 视为相同还是不同的 `targetViews`。如果视为相同，则使用相同的 `viewName`。如果视为不同，则使用不同的 `viewNames`。这些事件由 SDK 自动添加。 |
| 紧跟 `Activity::SetContent` 调用之后 | 如果 UI 不发生更改，我们可以插入一个 `targetView` 调用。 |
| `View::willAppear` 内部 | 如果所选视图在某个特定视图层次结构中唯一显示。 |
| 紧跟 `Activity::SetContentView` 调用之后 | 如果活动不更改/修改其在后续代码中的任何内容。 |

对于 Android，可查看此处的表格，了解错误放置 `targetView` 调用的位置：

| 不可接受的 TargetView 位置 | 原因 |
|--- |--- |
| `Activity::onCreate` 内部 | 活动已创建，但与活动关联的视图不保证完成和/或附加到窗口。放置在此处可能会导致不对创作屏幕进行取样或取样不完整，并且/或者以非确定性方式应用选件。 |
| `View::didAppear` 内部 | 视图已经显示，应用选件将会造成闪烁，从而提供较差的 UI 体验。 |
| `View::didLoad` 内部 | 视图未附加到主视图层次结构，且可能已实例化，但不保证会显示在应用程序 UI 上。 |

## 交付 {#delivery}

使用移动App CMS创作的Target活动会自动在移动应用程序中提供。这些活动在应用程序启动时(基于启动配置)进行预访，并随着用户浏览不同的目标视图而应用，通常映射到屏幕。

调用 `TargetVEC.prefetchOffersBackground()` API方法时，将从目标Edge获取Target选件，并在本地缓存Target。这样可以提供更流畅的用户体验，因为当使用 `targetView()` 调用触发 Target 视图时，会立即从缓存中应用 Target 选件，而不是通过网络获取。

为获得更多灵活性，您还可以调用 `TargetVEC.prefetchOffers()` API，它将隐藏当前布局，直到Target选件被预访存并应用于可见视图(可能导致闪烁)。

当用户浏览客户应用程序以使用最合适的内容刷新本地 Target 选件缓存时（在对当前用户的 Target 配置文件进行最新更新后），也可以重复调用 `TargetVEC.prefetchOffersBackground()`。

请注意，每次预取 Target 选件时，如果可能，也会应用通过 `AdobeTargetMobile.targetView()` 触发的最后一个 Target 视图的选件。

## 疑难解答 {#ts}

**我收到一个错误，表明我的“context. application. name”值包含禁止的字符。移动应用程序名称中允许哪些字符？**

移动应用程序名称中允许的字符包括：

| 允许的字符 | 描述 |
| --- | --- |
| 字母 |  |
| 数量 |  |
| `-` | 连字符 |
| `.` | 句点 |
| `,` | 逗号 |
| `:` | 冒号 |
| `#` | 数字符号 |
| `(` | 左括号 |
| `)` | 闭合括号 |
| `&` | Ampersand |
| `+` | 加号 |

例如，使用不允许的字符( `'` )，您会收到以下错误消息：

```
Target Response was received : {"status":400,"message":"Errors: field - [context.application.name] - Value contains prohibited chars;"}
```

## 已知限制 {#limitations}

* 移动App CMS当前可用于为移动应用程序创建 [A/B测试](/help/c-activities/t-test-ab/test-ab.md) 和 [体验定位(XT)](/help/c-activities/t-experience-target/experience-target.md) 活动。对其他活动类型的支持将在以后提供。
* 尚不支持预览功能。它将在即将发布的版本中提供。
* 在尝试将应用程序重新连接到移动App CMS时，您必须完全退出应用程序并重新启动它。

   在下面列出的任何情景中，如果移动设备应用程序已经打开，则必须关闭该应用程序，然后重新打开它。但是，您“必须”**从最近使用的应用程序部分中关闭应用程序，而“不是”**通过按“返回”按钮来关闭。如果通过按“返回”按钮来关闭应用程序，可能会出现间歇性连接问题。

   如果应用程序已经打开，您必须重新启动应用程序，才能连接到移动App CMS：

   * 创建新活动时，在选择移动设备应用程序后，会显示设备列表对话框。如果应用程序已经打开，您必须将其关闭，然后重新启动，这样才能将其设备显示为可供选择。
   * 开始编辑活动时，会显示设备对话框。如果应用程序已经打开，您必须将其关闭，然后重新启动，这样才能将其设备显示为可供选择。
   * 从“目标和设置”步骤导航回“创作”步骤（步骤 1）时，会显示设备对话框。如果应用程序已经打开，您必须关闭应用程序，然后重新启动应用程序以连接到移动应用程序CMS。
   请确保您是从最近使用的应用程序部分中关闭应用程序，而不是通过按“[!UICONTROL 返回]”按钮来关闭。

## 培训视频：Adobe Target Mobile App Visual Experience Composer(3：33) {#video}

>[!VIDEO](https://video.tv.adobe.com/v/27528?captions=chi_hans)