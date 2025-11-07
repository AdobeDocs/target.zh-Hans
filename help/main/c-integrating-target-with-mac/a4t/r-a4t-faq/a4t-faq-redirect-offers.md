---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;重定向;重定向产品建议;adobe-mc-sdid;adobe_mc_ref
description: 查找有关在使用Analytics for [!DNL Target] (A4T)时使用重定向选件的问题解答。 A4T允许您对 [!DNL Target] 活动使用Analytics报表。
title: 可在何处找到有关使用A4T重定向选件的常见问题解答？
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 50%

---

# 重定向产品建议 - A4T 常见问题解答

本主题包含有关在使用[!DNL Adobe Analytics]作为[!DNL Adobe Target] (A4T)的报表源时使用重定向选件的常见问题解答。

## Analytics for Adobe Target (A4T)是否支持重定向选件？ {#section_46B8B03ED4D542C6AD875F5F61176298}

+++回答
是，如果您的实施使用[!DNL at.js]。 但是，您的实施必须满足下列最低要求，才能在使用 Analytics 作为报表源的活动中使用[重定向产品建议](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)。

+++

## ![Adobe Experience Platform Web SDK徽章](/help/main/assets/platform.png) [!DNL Adobe Experience Platform Web SDK]是否支持A4T的重定向选件？ {#platform}

+++回答
以下常见问题解答提供了有关将A4T和重定向选件与[!DNL Platform Web SDK]结合使用的更多信息。

+++

### Analytics for Target (A4T) 是否支持重定向选件？

+++回答
是，通过Platform Web SDK的A4T支持[重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

+++

### 是否支持[!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Form-Based Experience Composer]？

+++回答
是，如果您使用内置的重定向选件，则支持[[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)和[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)。

+++

## 要将重定向选件与A4T配合使用，最低要求是什么？ {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++回答
您的实施必须满足以下最低要求：

* Experience Cloud 访客 ID 服务：[!DNL visitorAPI.js] 版本 2.3.0 或更高版本。
* Adobe Analytics：[!DNL appMeasurement.js] 版本 2.1。
* Adobe Target：[!DNL at.js] 版本 1.6.2 或更高版本。

具有重定向产品建议的页面和访客被重定向到的页面都必须包含这三个库。

+++

## 为什么 A4T 与 Analytics 之间有时会出现数据差异？

+++回答
有些数据差异是预期行为。有关更多信息，请参阅[使用和不使用 A4T 时，Target 和 Analytics 之间的预期数据差异](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md)。

+++

## 在 A4T 活动中使用重定向产品建议时，如何最大限度地减少流量分布的差异？ {#discrepancies}

+++回答
在配置了[!UICONTROL Analytics for Target] (A4T)的活动中使用重定向选件时，有限数量的客户报告流量分布的差异程度较高。

请考虑以下事项：

* [!DNL Target]和[!DNL Analytics]调用顺序不正确可能导致差异程度较高。

  [!DNL Target]调用必须位于源页面（其中发生重定向）和目标页面（其中重定向结束）上的[!DNL Analytics]调用之前。

* 确保在A4T重定向活动中使用重定向选件。
* 如果源页面上有多个[!DNL Target]位置请求（发生重定向），[!DNL Adobe]建议您在第一个[!DNL Target]位置请求上运行重定向活动。

  对前[!DNL Target]个位置请求运行重定向活动可减少其他[!DNL Target]个位置请求中发生任何活动资格并被计入报表中的可能性。 被重定向的访客无需计入其他活动的报表中，因为他们看不到这些体验。

+++

## 为何有时会同时计入原始页面和重定向页面上的查看次数？ {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++回答
使用at.js版本1.6.3或更高版本时，不计算两个页面上的页面查看次数。 这种争用情况仅影响使用早期版本的客户。Target 团队维护两个版本的 at.js：当前版本和当前版本的上一个版本。根据需要升级 at.js，以确保您运行的是[受支持的版本](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}。

如果您使用的是不受支持的早期 at.js 版本，则可能会发生某种争用情况，这种情况可能导致先触发 Analytics 调用，然后再在第一个页面上执行重定向。这种情况可能会导致同时计入原始页面和重定向页面上的页面查看次数。 在这种情况下，第一个页面上的页面查看次数便是多余的，因为当时访客实际上从未“查看过”该页面。

鉴于代码在页面上的执行位置，建议使用基于表单的编辑器构建重定向活动，以提高页面重定向的速度。 此外，还建议为每个体验各创建一个重定向选件，甚至对默认体验（在默认体验中重定向会返回原始页面）也是如此。为每个体验创建重定向选件可确保在发生计数错误时，所有体验都会发生该错误。 报告和分析对于测试仍然有效。

您希望对活动中包括默认（控制）体验在内的所有体验都使用重定向产品建议，因这样可以为所有体验施加相同的条件。例如，如果默认体验没有重定向产品建议，但其他体验具有重定向产品建议，则没有重定向产品建议的体验速度将具有一种内在优势。建议仅对临时方案（例如测试）使用重定向产品建议。不建议对永久性方案（例如个性化）使用重定向产品建议。确定“入选者”后，应删除重定向以提高页面加载性能。

+++

## 可视化体验编辑器 (VEC) 和基于表单的体验编辑器是否均受支持？ {#section_FDA26FE7909B48539DA770559E687677}

+++回答
是，只要您使用内置的重定向产品建议，这两种编辑器便均受支持。

如果您使用自己的自定义重定向代码，则必须确保填充两个与重定向 URL 关联的新参数（即下面介绍的 `adobe_mc_sdid` 和 `adobe_mc_ref`）。

+++

## 重定向 URL 中新增了哪些查询字符串参数？ {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++回答
以下查询字符串参数与重定向选件相关联：

| 参数 | 描述 |
|--- |--- |
| `adobe_mc_sdid` | `adobe_mc_sdid`参数可将补充数据ID (SDID)和Experience Cloud组织ID从默认页面传递到新页面。 这些ID允许A4T将默认页面上的Target请求与新页面上的Analytic请求“拼合”在一起。<br>在URL中传递sdid的预期格式（对于混合应用，或者从一个应用传递到网站，或者从一个网站传递到另一个网站）是`ex. adobe_mc_sdid=SDID=123\|MCORGID=123456789@AdobeOrg\|TS=1498569322` |
| `adobe_mc_ref` | `adobe_mc_ref` 参数可将默认页面的引荐 URL 传递到新页面。如果与AppMeasurement.js版本2.1（或更高版本）一起使用，则Analytics会将此参数值用作新页面上的引荐URL。 |

在 VEC 和基于表单的体验编辑器中使用内置的重定向选件时，如果已在页面上实施访客 ID 服务，则这两个参数会自动添加到重定向 URL 中。如果您在 VEC 或基于表单的编辑器中使用自己的自定义重定向代码，则必须确保使用自定义代码传递这两个参数。

+++

## 我的 Web 服务器将从我的 URL 中去除这些参数，我应该怎么做？ {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++回答
与您的IT团队合作，列入允许列表这些参数（`adobe_mc_sdid`和`adobe_mc_ref`）。

+++

## 如果我没有在重定向活动中使用 A4T，也不想在 URL 中添加这些额外的参数，我应该怎么做？ {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++回答
在下列情况下使用自定义编码重定向：

* 您的重定向活动未使用A4T
* 您已实施访客ID服务
* 您不希望将这些参数自动添加到URL

但是，作为最佳实践，您可能想要在 URL 中保留 `adobe_mc_ref` 参数，以便能够向 [!DNL Analytics] 正确报告引荐信息。

+++

## adobe_mc_ref和adobe_mc_sdid参数为何会在我的实施中进行双重URL编码？ {#section_5EFE5F012B944C40865731EA18E7E79E}

+++回答
如果您同时使用 A4T 和重定向产品建议，则 Target 会将 `adobe_mc_ref` 和 `adobe_mc_sdid` 参数附加到 URL。这两个值已进行 URL 编码。在大多数情况下，一切都会按预期运行；但是，有些客户使用的负载平衡器或 Web 服务器可能会尝试对查询字符串参数再次进行编码。

由于此双重编码过程，访客 API 在尝试对 `adobe_mc_sdid` 值进行解码时，将无法提取 SDID 值，故而会生成一个新的 SDID。此过程会导致发送到Target和Analytics的SDID值不正确，并且您会在Analytics报表中看到重定向拆分不均匀。

Adobe列入允许列表建议您与IT团队联系，以确保`adobe_mc_ref`和`adobe_mc_sdid`，以便这两个值不会发生任何形式的转换。

+++

## 为何必须将引荐URL传递到新页面？ {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++回答
假设一位访客单击了[!DNL `www.google.com`]上的链接并由此进入您的主页(`www.mysite.com/index.html`)，而您的主页上有一个重定向活动处于活跃状态，该访客随后又被重定向到一个新页面(`www.mysite.com/index2.html`)。

以前，新页面上的[!DNL Analytics]请求报告的引荐URL是[!DNL `www.mysite.com/index.html`]，而不是[!DNL `www.google.com`]。 这会导致 [!DNL Analytics] 中与引荐 URL 有关的报表（例如营销渠道报表）不准确。这些报表忽略了您是从[!DNL `www.google.com`]访问网站的事实。

使用[!DNL at.js]版本0.9.6（或更高版本）和[!DNL AppMeasurement.js] 2.1（或更高版本）时，新页面上的[!DNL Analytics]请求报告的引荐URL为[!DNL `www.google.com`]。

+++

## 我能否使用自定义/HTML 重定向选件？ {#section_E49F9A83A286488C8F1098A040203D7E}

+++回答
不能，您必须在使用 [!DNL Analytics] 作为报表源 (A4T) 的活动中使用内置的重定向产品建议。对 [!DNL Target] 而言，HTML 产品建议是不透明的：[!DNL Target] 无法知晓某段特定的 HTML 是否包含可对重定向进行实例化的 JavaScript。

+++

### 我能否将自定义/HTML重定向选件与[!DNL Platform Web SDK]结合使用？

+++回答
不能，您必须在使用A4T的活动中使用内置的重定向选件。 从[!DNL Target]的角度来看，HTML选件是不透明的。 [!DNL Target]无法知晓某段HTML是否包含可实例化重定向的JavaScript。

+++
