---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;重定向;重定向选件;adobe-mc-sdid;adobe_mc_ref
description: 本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时使用重定向选件的常见问题解答。
title: 重定向选件 - A4T 常见问题解答
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 重定向选件 - A4T 常见问题解答{#redirect-offers-a-t-faq}

本主题包含有关在使用 Analytics 作为 Target 报表源 (A4T) 时使用重定向选件的常见问题解答。

## Analytics for Target (A4T) 是否支持重定向选件？{#section_46B8B03ED4D542C6AD875F5F61176298}

是，但前提是您的实施使用 [!DNL at.js]。但是，您的实施必须满足下列最低要求，才能在使用 Analytics 作为报表源的活动中使用[重定向选件](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

>[!NOTE]
>
>存在一个已知问题，该问题会导致将重定向与 A4T 结合使用的有限数量的客户看到较高的未经整合点击率百分比。请参阅[已知问题和已解决的问题](/help/r-release-notes/known-issues-resolved-issues.md#redirect)。

## 要将重定向选件与 A4T 配合使用，需要满足哪些最低要求？{#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

您的实施必须满足以下最低要求：

* Experience Cloud 访客 ID 服务：[!DNL visitorAPI.js] 版本 2.3.0 或更高版本。
* Adobe Analytics：[!DNL appMeasurement.js] 版本 2.1。
* Adobe Target：[!DNL at.js] 版本 1.6.2 或更高版本。

   [!DNL mbox.js] 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 [!DNL at.js]。

具有重定向选件的页面和访客被重定向到的页面都必须包含这三个库。

## 为什么 A4T 与 Analytics 之间有时会出现数据差异？

有些数据差异是预期行为。有关更多信息，请参阅[使用和不使用 A4T 时，Target 和 Analytics 之间的预期数据差异](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)。

## 为何有时会同时计入原始页面和重定向页面上的查看次数？{#section_B8F6CC2190B84CF08D945E797C5AF07B}

使用 at.js 版本 1.6.3 或更高版本时，不会出现此问题。这种争用情况仅影响使用早期版本的客户。Target 团队维护两个版本的 at.js：当前版本和当前版本的上一个版本。根据需要升级 at.js，以确保您运行的是[受支持的版本](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

如果您使用的是不受支持的早期 at.js 版本，则可能会发生某种争用情况，这种情况可能导致先触发 Analytics 调用，然后再在第一个页面上执行重定向。这可能会导致原始页面和重定向页面上的查看次数全都被计入。在这种情况下，第一个页面上的页面查看次数便是多余的，因为当时访客实际上从未“查看过”该页面。

为加快页面重定向的速度，建议使用基于表单的编辑器来构建重定向活动。这是因为页面中代码执行的位置需使用基于表单的编辑器。此外，还建议为每个体验各创建一个重定向选件，甚至对默认体验（在默认体验中重定向会返回原始页面）也是如此。这样做可确保计数错误如若发生，便会发生在所有体验中，因此报表和分析对于测试仍然有效。

您希望对活动中包括默认（控制）体验在内的所有体验都使用重定向选件，因这样可以为所有体验施加相同的条件。例如，如果默认体验没有重定向选件，但其他体验具有重定向选件，则没有重定向选件的体验速度将具有一种内在优势。建议仅对临时方案（例如测试）使用重定向选件。不建议对永久性方案（例如个性化）使用重定向选件。确定“入选者”后，应删除重定向以提高页面加载性能。

有关此问题的更多信息，请参阅[已知问题](/help/r-release-notes/known-issues-resolved-issues.md#redirect)中的“重定向选件”信息。

## 如果我使用的是 mbox.js JavaScript 库，能否将重定向选件与 A4T 配合使用？{#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

[!DNL mbox.js] 库不支持将重定向选件与 A4T 配合使用。您的实施必须使用 [!DNL at.js]。

## 可视化体验编辑器 (VEC) 和基于表单的体验编辑器是否均受支持？{#section_FDA26FE7909B48539DA770559E687677}

是，只要您使用内置的重定向选件，这两种编辑器便均受支持。

如果您使用自己的自定义重定向代码，则必须确保填充两个与重定向 URL 关联的新参数（即下面介绍的 `adobe_mc_sdid` 和 `adobe_mc_ref`）。

## 重定向 URL 中新增了哪些查询字符串参数？{#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

以下查询字符串参数与重定向选件相关联：

| 参数 | 描述 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid` 参数可将补充数据 ID (SDID) 和 Experience Cloud 组织 ID 从默认页面传递到新页面，以便 A4T 能够将默认页面上的 Target 请求与新页面上的 Analytics 请求“整合”到一起。 |
| `adobe_mc_ref` | `adobe_mc_ref` 参数可将默认页面的引荐 URL 传递到新页面。如果使用了 AppMeasurement.js 版本 2.1（或更高版本），则 Analytics 会将此参数值用作新页面上的引荐 URL。 |

在 VEC 和基于表单的体验编辑器中使用内置的重定向选件时，如果已在页面上实施访客 ID 服务，则这两个参数会自动添加到重定向 URL 中。如果您在 VEC 或基于表单的编辑器中使用自己的自定义重定向代码，则必须确保使用自定义代码传递这两个参数。

## 我的 Web 服务器将从我的 URL 中去除这些参数，我应该怎么做？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

您需要与 IT 团队协作，将这两个参数（`adobe_mc_sdid` 和 `adobe_mc_ref`）列入白名单。

## 如果我没有在重定向活动中使用 A4T，也不想在 URL 中添加这些额外的参数，我应该怎么做？{#section_9E608D75FF9349FE96C65FEDD7539F45}

如果您没有在重定向活动中使用 A4T，并且实施了访客 ID 服务，同时您不希望将这两个参数自动添加到 URL 中，则必须使用自定义编码的重定向。

但是，作为最佳实践，您可能想要在 URL 中保留 `adobe_mc_ref` 参数，以便能够向 [!DNL Analytics] 正确报告引荐信息。

## adobe_mc_ref 和 adobe_mc_sdid 参数为何会在我的实施中进行双重 URL 编码？{#section_5EFE5F012B944C40865731EA18E7E79E}

如果您同时使用 A4T 和重定向选件，则 Target 会将 `adobe_mc_ref` 和 `adobe_mc_sdid` 参数附加到 URL。这两个值已进行 URL 编码。在大多数情况下，一切都会按预期运行；但是，有些客户使用的负载平衡器或 Web 服务器可能会尝试对查询字符串参数再次进行编码。

由于此双重编码过程，访客 API 在尝试对 `adobe_mc_sdid` 值进行解码时，将无法提取 SDID 值，故而会生成一个新的 SDID。这会导致发送到 Target 和 Analytics 的 SDID 值不正确，您也会在 Analytics 报表中看到不均衡的重定向拆分。

为此，我们建议您联系 IT 团队，以确保将 `adobe_mc_ref` 和 `adobe_mc_sdid` 列入白名单，以便这两个参数的值不会发生任何形式的改变。

## 为何需要将引荐 URL 传递到新页面？{#section_91AB8B0891F6416CBF7E973DCAF54EB5}

假设一位访客单击了 [!DNL `www.google.com`] 上的链接并由此进入您的主页 ([!DNL `www.mysite.com/index.html]`)，而您的主页上有一个重定向活动处于活跃状态，该访客随后又被重定向到一个新页面 ([!DNL `www.mysite.com/index2.html`])。

以前，新页面上的 [!DNL Analytics] 请求报告的引荐 URL 是 [!DNL `www.mysite.com/index.html`]，而不是 [!DNL `www.google.com`]。这会导致 [!DNL Analytics] 中与引荐 URL 有关的报表（例如营销渠道报表）不准确。这些报表忽略了您是从 [!DNL `www.google.com`] 访问网站的事实。

现在，通过使用 [!DNL at.js] 版本 0.9.6（或更高版本）和 [!DNL AppMeasurement.js] 2.1（或更高版本），新页面上的 [!DNL Analytics] 请求报告的引荐 URL 将是 [!DNL `www.google.com`]。

## 我能否使用自定义/HTML 重定向选件？{#section_E49F9A83A286488C8F1098A040203D7E}

不能，您必须在使用 [!DNL Analytics] 作为报表源 (A4T) 的活动中使用内置的重定向选件。对 [!DNL Target] 而言，HTML 选件是不透明的：[!DNL Target] 无法知晓某段特定的 HTML 是否包含可对重定向进行实例化的 JavaScript。
