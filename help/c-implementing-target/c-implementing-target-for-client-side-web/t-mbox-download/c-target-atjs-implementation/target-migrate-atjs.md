---
keywords: Target;at.js;migrate to at.js;readiness;audit at.js;integrate at.js
description: 从 mbox.js 迁移到 at.js 是一个简单的过程。
title: 如何从 mbox.js 迁移到 at.js
feature: null
topic: Standard
uuid: 45f81fe8-7b04-4a36-931d-bbf03ed6cbb3
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 98%

---


# 如何从 mbox.js 迁移到 at.js{#how-to-migrate-to-at-js-from-mbox-js}

在 [!DNL Adobe Target] 中从 mbox.js 迁移到 at.js 是一个简单的过程。

可执行以下步骤以便从 [!DNL mbox.js] 迁移到 [!DNL at.js]，并检查您的迁移：

1. 确定贵组织的[浏览器支持](../../../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)要求。
1. 检查网站当前的 [!DNL mbox.js] 实施，以查看是否存在不受 [!DNL at.js] 支持的功能。

   审核实施时，请考虑以下事项：

   **您当前使用了哪些类型的 mbox？**

   | 类型 | 详细信息 |
   |--- |--- |
   | 自动创建的全局 mbox | 如果您网站上的唯一一行 Target 代码是 mbox.js 文件，则会创建自动创建的全局 mbox。该文件会自动生成 mbox 调用。 |
   | 空的全局 mboxCreate | 建议您转为使用自动创建的全局 mbox。 |
   | 封装式 mboxCreate | 只要 `mboxCreate()`的前面是 `<div class="mboxDefault"></div>`，那么迁移过程应该会很简单。 |
   | mboxUpdate | 当`mboxUpdate()` 与 `mboxDefine()` 或 `mboxCreate()` 结合使用时，迁移过程应该会很简单。`mboxUpdate()` 不会更新自动创建的全局 mbox，或最初由 `getOffer()` 创建的 mbox。在这些情况下，迁移到 at.js 时，应使用 `getOffer()` 和 `applyOffer()` 的组合代替 `mboxUpdate()`。 |
   | 自定义点击跟踪 mbox，包括 mboxTrack | 建议您更新代码以使用 `trackEvent()`。 |

   >[!NOTE]
   >
   >有关上表中所提及的各种函数的更多信息，请参阅 [at.js 函数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)。

   **您是否对[!DNL mbox.js]文件进行了任何自定义？**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * 额外 Javascript
   * 其他位置

   大多数 [mbox.js 对象和方法](../../../../c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537)（例如 `mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories`，等等）都不受支持。一些替代方法或许可能实现您要尝试执行的操作。

   **您的任何网页上是否有[!DNL mbox.js]？**

   不能在同一网页上同时使用 [!DNL at.js] 和 [!DNL mbox.js]。但是，可以在同一网站的两个不同页面上分别使用这两个 JavaScript 库。

   Adobe 主要使用 mbox Cookie 来跟踪访客在页面之间的行动轨迹。在 QA 过程中，当访客在具有 [!DNL at.js] 的页面和具有 [!DNL mbox.js] 的页面之间来回切换时，您应该确认该 Cookie 得以保留并可正确读取。不论访客先登陆网站的哪个区域（`mboxPC` 或 `mboxSession`），也不论最初是在哪个区域设置了 Cookie，都应确保 mbox 调用中传递了 [!DNL at.js] 和 [!DNL mbox.js] 值。如果您在实施中使用了第三方 Cookie，请确保浏览网站时这两个值保持不变。

   **您是否将[!DNL Target]与任何其他 Adobe 解决方案集成？**

   * Analytics (A4T)
   * Analytics（旧版集成）
   * AAM（后端）
   * AAM（旧版前端）
   * AEM
   * Data Workbench

   [!DNL at.js] 不支持某些旧版集成。有关更多信息，请参阅[集成](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)页面。

   **您是否将[!DNL Target]与任何第三方工具集成？**

   * 其他 Analytics 工具
   * 其他 DMP
   * Demandbase
   * Click-tale
   * 其他

   可能需要对这些集成进行调整，以使其可与 [!DNL at.js] 配合使用。有关更多信息，请参阅[集成](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)页面。

   **您是否使用了标签管理器？**

   * 动态标签管理
   * Ensighten
   * Tealium
   * Signal/BrightTag

   有关更多信息，请参阅 [at.js 集成](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)。

   >[!NOTE]
   >
   >如果您当前未使用标签管理器来部署 [!DNL Target]，现在可以考虑使用此方法。Adobe 的[动态标签管理](https://dtm.adobe.com)免费向 [!DNL Target] 客户提供，建议使用此方法来部署 [!DNL Target]。有关更多信息，请参阅[使用动态标签管理实施 Adobe Target 的最佳实践](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html)。

1. 确认当前所有活动和集成均可按预期运行。

   在测试过程中，您可以执行下面一些操作，以确认 [!DNL at.js] 可按预期运行：

   * 确保当前所有活动均可与新的 JavaScript 库配合使用。
   * 确认所有[集成](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)和[插件](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)均可按预期运行。
   * 确保您可以顺利使用 [!DNL at.js] 提供的方法进行[调试](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F)。

**迁移到 at.js 时可能出现的问题**&#x200B;迁移到 at.js 后，有些客户报告了以下问题：

* 之前在具有 [!DNL mbox.js] 的页面上构建的某些 VEC 活动可能需要进行更新，才能与 [!DNL at.js] 配合使用。

   如果网站的 HTML 元素中未使用足够多的 ID 或类属性，则这些网站最常出现此问题。您可以通过以下方法来确认自己是否遇到了此问题：通过 `?mboxDebug=true` 加载页面，并检查控制台语句，以确定体验是否按预期交付。

   ![](assets/mboxdebug.png)
在这些情况下，元素选择器可能以如下内容开头

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   而且构建元素选择器时所设定的预期是 [!DNL mbox.js] 将一个额外的 `<div>` 元素添加到页面顶部。由于 [!DNL at.js] 不会将 `<div>` 元素添加到页面顶部，因此该选择器将不再适用于 [!DNL at.js]。

   可以通过以下方法解决此问题：在 VEC 中在使用 [!DNL at.js] 的 URL 上重新创建活动，或在 VEC 中使用 **[!UICONTROL &lt;/> 代码]** > **[!UICONTROL 修改]**&#x200B;选项手动更新选择器。

   要修复此问题，您应该将 BODY 后面的第一个 DIV 元素中的 nth-of-type 数字减去 1。在上面的示例中，编辑后的代码将为：

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   有关如何使用代码编辑器执行此操作的更多信息，请参阅[代码编辑器](../../../../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)。

* 由于所有 mbox 现在均为异步，因此它们不会阻止页面按照其触发的顺序进行呈现或返回。有关更多信息，请参阅“异步注意事项”，此内容位于 [at.js 限制](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE)。
