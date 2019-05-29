---
description: 在实施 Adobe Analytics 作为 Target 报表源 (A4T) 时，需要执行几个步骤。
keywords: A4T;Adobe Analytics;基于 Analytics 的活动;Analytics 报表包;报表包;Analytics 与 Target 集成;配置报表包
seo-description: 在实施 Adobe Analytics 作为 Target 报表源 (A4T) 时，需要执行几个步骤。
seo-title: Analytics for Target 实施
solution: Target
title: Analytics for Target 实施
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 1be00210754e8fa3237fdbccf48af625c2aafe65

---


# Analytics for Target 实施{#analytics-for-target-implementation}

在实施 Adobe Analytics 作为 Target 报表源 (A4T) 时，需要执行几个步骤。

## 实施步骤 {#section_73961BAD5BB4430A95E073DE5C026277}

下表介绍了将此集成部署到您的网站时需要执行的步骤。

## 步骤 1：请求配置 Analytics 和 Target。

将 Analytics 作为 Target 报表源进行实施后，您必须配置 Analytics 和 Target。[使用此表单可请求配置](http://www.adobe.com/go/audiences)。

## 步骤 2：设置用户权限

您必须满足用户帐户要求，然后才能在 Adobe Target 中创建基于 Adobe Analytics 的活动。请参阅[用户权限要求](/help/c-integrating-target-with-mac/a4t/account-reqs.md)。

## 步骤 3：实施 Experience Cloud 访客 ID 服务。

通过访客 ID 服务，您可以在各个 Experience Cloud 解决方案中识别用户。您必须实施或迁移到所需版本的 Experience Cloud 访客 ID 服务。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

请参阅 Experience Cloud 访客 ID 服务文档中的[为 Target 实施 Experience Cloud ID 服务](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html)。

## 步骤 4：更新 AppMeasurement for JavaScript 或 s_code

您必须实施或迁移到所需版本的 appMeasurement.js。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

对于新实施，请参阅 [Analytics JavaScript 实施](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html)。

对于迁移，请参阅[迁移到 AppMeasurement for JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs_migrate)。

## 步骤 5：下载并更新 at.js 或 mbox.js

您必须使用生产帐户实施或迁移到所需版本的 at.js 或 mbox.js。无需对代码进行修改。

有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

## 步骤 6：托管 at.js 或 mbox.js

如果您之前已部署 at.js 或 mbox.js，则可以将现有文件替换为更新版本。有关更多信息，请参阅[实施之前](/help/c-integrating-target-with-mac/a4t/before-implement.md)中的“实施要求”。

如果不替换，则可以将此文件与访客 ID 服务文件和 AppMeasurement for JavaScript 文件一起托管。这些文件必须托管在可从您网站上的所有页面进行访问的 Web 服务器上。下一步需要使用这些文件的路径。

## 步骤 7：在所有网站页面上引用 at.js 或 mbox.js

通过在每个页面上的 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 标记中添加以下代码行来将 at.js 或 mbox.js 插入到 VisitorAPI.js 下面：

对于 at.js：

```
<script language="JavaScript" type="text/javascript" 
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

对于 mbox.js：

```
<script language="JavaScript" type="text/javascript" 
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

必须先加载 VisitorAPI.js，然后再加载 at.js 或 mbox.js，因此如果您要更新现有的 at.js 或 mbox.js 文件，请务必确认加载顺序。

## 步骤 8：验证实施

更新 JavaScript 库后，加载您的页面，以确认 Target 调用中的 mboxMCSDID 参数值与 Analytics 页面查看调用中的 sdid 参数值相匹配。

在单页应用程序 (SPA) 中，由于调用顺序并不总是可以预测，因此尤其务必要进行此验证。

**注意：**为使 A4T 能够正常运行，这些值必须匹配。

## 步骤 9：（可选）删除之前的集成代码

我们建议您删除之前的集成，以便简化您的实施，并免除解决系统间差异的麻烦。您可以删除可能已为之前的 SC 与 T&amp;T 集成部署的任何代码，包括 `mboxLoadSCPlugin`。

## 步骤 10：启用可将 Analytics 用作 Target 报表源的选项

在 Target 中，单击[!UICONTROL 设置 &gt; 首选项]，然后选择[!UICONTROL 为每个活动选择]或 [!UICONTROL Adobe Analytics]，以启用相应的选项。

* 如果选择为每个活动选择，您在创建每个活动时可以在 Target 和 Analytics 之间进行选择。
* 如果选择 Adobe Analytics，则会将 Analytics 设置为您创建的所有活动的报表源。

