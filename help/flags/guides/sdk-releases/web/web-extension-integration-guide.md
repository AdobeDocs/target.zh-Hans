---
title: Web集成指南的Flags扩展
description: 了解如何将Flags扩展与Web应用程序的Adobe Experience Platform Web SDK (Alloy)集成。
badge: label="Beta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---

# 标记Web扩展 {#web-extension-integration-guide}

本指南介绍如何将Flags扩展与Web应用程序的Adobe Experience Platform Web SDK (Alloy)集成。 Flags扩展可以为Web体验启用功能标记管理和受控转出。

## 先决条件 {#prerequisites}

在实施Flags扩展之前，请确保您已：

* 在[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中配置的Web属性
* 已安装Adobe Experience Platform Web SDK扩展
* Adobe Experience Cloud组织ID
* 访问组织中的标志

### 所需的权限 {#required-permissions}

确保您具有以下资产权限：

* 开发
* 管理扩展

## 扩展依赖关系 {#extension-dependencies}

Flags扩展需要以下Adobe Experience Platform扩展：

| 扩展 | 描述 | 必需 |
|---|---|---|
| Adobe Experience Platform Web SDK | 提供核心功能，包括Edge Network通信和身份管理 | 是 |

在安装Flags扩展之前，请确保将此扩展安装在数据收集Web资产中。

## 在数据收集中配置标志扩展 {#configure}

### 安装扩展 {#install-extension}

1. 使用您的Adobe ID凭据登录[experience.adobe.com](https://experience.adobe.com)。
1. 导航到&#x200B;**数据收集** > **标记**。
1. 选择所需的标记属性。
1. 导航到&#x200B;**扩展** > **目录**。
1. 搜索&#x200B;**标志**&#x200B;并选择扩展卡。
1. 选择&#x200B;**安装**。

### 配置扩展设置 {#configure-settings}

安装Flags扩展时，您将转到配置页面。 配置以下设置：

| 设置 | 描述 | 必需 |
|---|---|---|
| 客户端 ID | 标记中应用程序的唯一标识符。 | 是 |

### 保存并发布 {#save-publish}

1. 选择&#x200B;**保存**&#x200B;以保存扩展配置。
1. 按照发布流部署更改：
   1. 将扩展添加到库。
   1. 构建到您的开发环境。
   1. 使用Adobe Experience Platform Debugger进行验证。
   1. 提升至暂存和生产环境。

## 将Tags嵌入代码添加到您的网站 {#embed-code}

发布标记库后，必须将嵌入代码添加到您的网站。 嵌入代码是一个`<script>`标记，用于加载Tags库和所有配置的扩展（包括Flags扩展）。

### 复制嵌入代码 {#copy-embed-code}

1. 在数据收集中，导航到您的Web资产。
1. 在左侧导航中选择&#x200B;**环境**。
1. 在目标环境（开发、暂存或生产）的行中，选择&#x200B;**安装**&#x200B;列下的框图标。
1. 在&#x200B;**Web安装说明**&#x200B;对话框中，Tags默认为异步嵌入代码。
1. 选择&#x200B;**复制**&#x200B;图标以将嵌入代码复制到剪贴板。
1. 选择&#x200B;**关闭**&#x200B;以关闭该模式窗口。

>[!NOTE]
>
>每个环境都有一个唯一的嵌入代码URL。 有关更多信息，请参阅环境。

### 实施嵌入代码 {#implement-embed-code}

在HTML页面的`<head>`元素中添加嵌入代码。 嵌入代码应放置在依赖于Tags库的其他脚本之前：

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/yourcompany/your-property/launchENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

>[!NOTE]
>
>将`src` URL替换为环境页面中的实际嵌入代码。 URL包含您的公司标识符、属性标识符和环境标识符（例如，`launch-EN123456789abcdef.min.js`）。

### 使用“标记”组件评估标记 {#tags-components}

Flags扩展提供了标记本机评估界面。

| 组件 | 类型 | 描述 |
|---|---|---|
| 功能已启用 | 条件 | 返回是否为当前用户/上下文启用某个功能 |
| 功能标记 | 数据元素 | 返回布尔值或完整功能对象 |

## 初始化SDK {#initialize-sdk}

加载Tags库时，Flags扩展会自动初始化。 该扩展在以下位置公开客户端：

```javascript
window._flagClient
```

### 等待客户端准备就绪 {#client-readiness}

标记以异步方式加载。 在从自定义代码调用SDK方法之前，请等待客户端初始化：

```javascript
window.flagClientReady
  .then(function () {
    const enabled = window._flagClient.isFeatureEnabled('my-feature', context);
    // Use enabled to select the feature or fallback behavior.
  })
  .catch(function (error) {
    console.error('Flags initialization failed:', error);
  });
```

## 评估上下文 {#evaluation-context}

`FeatureEvaluationContext`包括标识（评估、A/B分段和分析所需）和可选定位属性（用于规则匹配）。

| 属性 | 必需 | 描述 |
|---|---|---|
| `identityNamespace` | 是 | 身份命名空间（请参阅[Adobe身份命名空间](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces)）。 公用值： `ECID`、`Email`、`CRMId`。 |
| `identityId` | 是 | 当前用户的身份值。 |
| `attributes` | 否 | `Record<string, string[]>`. 键是标记规则使用的上下文属性名称（例如`locale`、`platform`）。 值是该键的候选属性值的列表。 |

在Tags组件中，在条件或数据元素UI中设置标识默认值。 当第二个参数是平面属性映射时，功能标志数据元素也通过`getVar(name, attributes)`接受运行时属性。

### 使用情况 {#usage}

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: 'your-visitor-ecid',
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};
```

## API 引用 {#api-reference}

### isFeatureEnable {#is-feature-enabled}

`isFeatureEnabled`返回给定上下文的标志功能是打开还是关闭。 传递`featureKey`和`FeatureEvaluationContext`。 查看[评估上下文](#evaluation-context)。 使用&#x200B;**功能已启用**&#x200B;标记条件或在初始化后从自定义代码调用`window._flagClient.isFeatureEnabled(...)`。

**签名**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `context` | FeatureEvaluationContext | 身份（必需）和可选的定位属性。 查看[评估上下文](#evaluation-context)。 |

### 创建功能标志数据元素 {#create-data-element}

在规则或自定义代码中需要可用为`%Data Element Name%`的标志值时，请使用数据元素。

**步骤**

1. 在属性中，转到&#x200B;**数据元素**&#x200B;并选择&#x200B;**添加数据元素**。
1. 在&#x200B;**创建数据元素**&#x200B;屏幕上，配置标记字段：

   | 字段 | 数值 |
   |---|---|
   | 名称 | 描述性名称（例如`checkout flag`） |
   | 扩展 | 标志 |
   | 数据元素类型 | 功能标记 |

1. 配置&#x200B;**标记**&#x200B;扩展字段：

   | 字段 | 必需 | 描述 |
   |---|---|---|
   | 功能键 | 是 | 唯一标志键（例如`checkout_flag`） |
   | 返回类型 | 是 | **布尔值(true/false)** — 已启用/已禁用，或&#x200B;**功能对象（完整详细信息）** — 完整有效负载，包括`meta` |

1. 选择&#x200B;**保存**。

**返回类型**

| 返回类型 | 解析为 |
|---|---|
| 布尔 (true/false) | `true`（如果已启用），否则`false` |
| 功能对象（完整详细信息） | 已完整评估的功能有效负载，或者在不满足规则时执行`null` |

### 使用数据元素 {#use-data-element}

在规则中 — 按名称引用，例如`%Test Flag%`。

在自定义代码中 — 使用`_satellite.getVar`。 对于运行时属性，将平面属性映射作为第二个参数传递，以计算：

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});

if (isEnabled) {
  // your custom code
} else {
  // your default code
}
```

### getFeature {#get-feature}

当您需要启用/禁用以外的元数据时，`getFeature`会返回已评估的功能有效负载。

使用具有&#x200B;**返回类型的**&#x200B;功能标志&#x200B;**数据元素：功能对象（完整详细信息）** — 请参阅[创建功能标志数据元素](#create-data-element) — 或在`flagClientReady`解析后从自定义代码调用`window._flagClient.getFeature(...)`。

**签名**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**参数**

| 参数 | 类型 | 描述 |
|---|---|---|
| `featureKey` | 字符串 | 在Flags中评估的功能键 |
| `context` | FeatureEvaluationContext | 身份（必需）和定向属性。 查看[评估上下文](#evaluation-context)。 |

**响应**

*功能结果*

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | number | 数字功能标识符。 `-1`用于功能级的control sentinel。 |
| `key` | 字符串\| null | 功能键。 `null`用于功能级的control sentinel。 |
| `featureGroupKey` | 字符串\| null | 功能组密钥（可用时） |
| `meta` | 字符串\| null | 功能元数据（可用时） |
| `analyticsParam` | AnalyticsParam \|空 | 已评估功能的Analytics详细信息 |

*AnalyticsParam*

| 字段 | 类型 | 描述 |
|---|---|---|
| `featureGroupId` | number | 数字功能组标识符 |
| `featureId` | number | 数字功能标识符 |
| `variantId` | 数字\| null | 变量标识符（`0`用于控制） |

**控制组行为**

| 场景 | isFeatureEnable | getFeature | Analytics事件isFeatureEnabled | Analytics事件getFeature |
|---|---|---|---|---|
| 处理 | `true` | 正常结果 | 是 | 是 |
| 功能级控制 | `false` | 哨兵(`id: -1`， `key: null`) | 是(`variantId: 0`) | 是 |
| 条件不匹配/未找到 | `false` | `null` | 否 | 否 |

**示例**

```javascript
var feature = _flagClient.getFeature('new-testflag', {
  identityNamespace: 'ECID',
  identityId: visitorEcid,
  attributes: {
    locale: ['en-US']
  }
});

var meta = feature && feature.meta;
if (meta) {
  // your custom code
} else {
  // your default code
}
```

### extensionVersion {#extension-version}

返回Flags扩展的版本字符串。

**签名**

```javascript
_flagClient.extensionVersion(): string
```

**示例**

```javascript
const version = _flagClient.extensionVersion();
console.log(`Flags extension version: ${version}`);
```

## API摘要 {#api-summary}

| API | 返回值 |
|---|---|
| 功能标记（Tags数据元素，布尔值） | 布尔值 |
| 功能标记（Tags数据元素、对象） | 功能对象或`null` |
| `window.flagClientReady` | Promise — 等待扩展初始化 |
| `window._flagClient.isFeatureEnabled(featureKey, context)` | 布尔值 |
| `window._flagClient.getFeature(featureKey, context)` | 功能对象或`null` |
| `window._flagClient.extensionVersion()` | 扩展版本字符串 |

## 错误处理 {#error-handling}

该扩展可轻松处理错误：

| 场景 | 行为 |
|---|---|
| 网络在初始化时不可用 | SDK在回退的情况下重试初始获取3次，但初始化失败。 `window.flagClientReady`和`_satellite.getVar(...)`通过`Failed to initialize Flag`拒绝；`window._flagClient`仍为`undefined`。 |
| 上下文中缺少标识 | 评估引发错误；同时提供`identityNamespace`和`identityId` |
| 未找到功能 | `getFeature`返回`null`；`isFeatureEnabled`返回`false` |

```javascript
try {
  const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
} catch (error) {
  console.error('Evaluation failed:', error.message);
  // Use default value
}
```

## 最佳实践 {#best-practices}

### 提供一致的标识 {#consistent-identity}

在评估中使用相同的身份命名空间和ID，以百分比转出进行一致的分段。

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: identity,
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};

const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
```

### 谨慎处理缺少的特征 {#handle-missing}

当未找到某个功能或评估失败时，始终提供回退行为。

```javascript
const feature = _flagClient.getFeature('new-testflag', context);

if (feature && feature.meta) {
  // your custom code
} else {
  // Feature not enabled - use default code
}
```

### 在页面加载后评估 {#evaluate-after-load}

在调用API之前，请确保已初始化标记库和标记扩展。 在规则、**功能标志**&#x200B;数据元素中使用&#x200B;**Library Loaded**&#x200B;事件，或等待`flagClientReady`：

```javascript
window.flagClientReady.then(function () {
  var isEnabled = window._flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
});
```

## 另请参阅 {#see-also}

* [创建您的第一个功能标记](../../feature-flags/create-your-first-feature-flag.md)
* [功能标志和功能组中的受众](../../audience/audience-in-feature-flags-and-feature-groups.md)
* [报告](../../feature-flags/reporting.md)

<!-- -->
