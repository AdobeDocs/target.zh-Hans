---
keywords: 定位；可视化体验编辑器；白名单；白名单；;允许列表允许列表；增强型可视化体验编辑器；VEC；可视化体验编辑器故障诊断；故障诊断；EEC；增强型体验编辑器；TLS;TLS 1.2
description: 了解如何在某些情况下，对Adobe [!DNL Target] 可视化体验编辑器(VEC)和增强型体验编辑器(EEC)有时会出现的问题进行故障诊断。
title: 如何对与可视化体验编辑器和增强型体验编辑器有关的问题进行故障诊断？
feature: 可视化体验编辑器 (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 13b980bbcd63bf6fd6b3ac880a80bd7bd4b67653
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 49%

---

# 对与可视化体验编辑器和增强型体验编辑器有关的问题进行故障诊断

在某些情况下， [!DNL Adobe Target] [!UICONTROL 可视化体验编辑器](VEC)和[!UICONTROL 增强型体验编辑器](EEC)有时会出现显示问题和其他问题。

## Google Chrome SameSite Cookie实施策略对VEC和EEC有何影响？ {#samesite}

请注意使用以下Chrome版本时对VEC和EEC所做的更改：

>[!NOTE]
>
>以下更改会影响下面列出的所有三个更新：
>
> * *不*&#x200B;能够在其网站的受密码保护页面中使用VEC（无论是否安装并启用了VEC助手扩展）。 您的网站登录Cookie被视为第三方Cookie，随登录请求发送。 唯一的例外是您的网站登录Cookie已将SameSite参数设置为“none”。


**Chrome 94（2021年9月21日）**:由于Chrome 94版本（2021年9月21日）即将进行的更改，以下更改将对使用Chrome 94及更高版本浏览器的所有用户造成影响：

* 将删除命令行标记`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`。

**Chrome 91（2021年5月25日）**:通过为Chrome 91版本（2021年5月25日）实施更改，以下更改将对使用Chrome 91及更高版本浏览器的所有用户产生影响：

* 标记`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`已从`chrome://flags`中删除。 此行为现在默认启用。

**Chrome 80（2020年8月）**:通过在2020年8月实施更改，所有使用Chrome 80及更高浏览器版本的用户：

* 在编辑活动时（如果这些库不在网站上）， *不能*&#x200B;下载[!DNL Target]库。 这是因为下载调用是从客户域向安全Adobe域发起的，并因未经身份验证而被拒绝。
* EEC将对所有用户&#x200B;*不*&#x200B;起作用，因为它无法在`adobemc.com domain`上为Cookie设置SameSite属性。 如果没有此属性，浏览器将拒绝这些Cookie，从而导致EEC失败。

### 确定阻止的Cookie

要确定哪些Cookie因SameSite Cookie实施策略而被阻止，请使用Chrome中的开发人员工具。

1. 要访问开发人员工具，请在Chrome中查看VEC时，单击Chrome右上角的&#x200B;**[!UICONTROL 省略号]**&#x200B;图标> **[!UICONTROL 更多工具]** > **[!UICONTROL 开发人员工具]**。
1. 单击&#x200B;**[!UICONTROL Network]**&#x200B;选项卡> ，然后查找阻止的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL 已阻止Cookie]**&#x200B;复选框，更便于查找已阻止的Cookie。

   下图显示了阻止的Cookie:

   ![显示已阻止的Cookie的开发人员工具>网络选项卡](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### Google VEC助手扩展

Adobe已将更新的VEC助手扩展提交到Google Chrome应用商店。 此扩展会覆盖Cookie属性，以根据需要设置`SameSite="none"`属性。 可在此处](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)找到[更新的扩展。 有关安装和使用VEC助手扩展的更多信息，请参阅[可视化体验编辑器助手扩展](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

对于您自己的网站Cookie，必须按名称指定Cookie。

>[!NOTE]
>
>仅当在单个域中设置了所有Cookie时，此方法才适用。 VEC助手不允许[!DNL Target]为多个域指定Cookie。

将[!UICONTROL Cookie]滑块切换到开位置，然后按名称和Cookie域指定Cookie。 Cookie名称为“mbox”，Cookie域是您提供mbox的域的二级和顶级域。 由于这是来自您的公司域，所以此 Cookie 是第一方 Cookie。示例: `mycompany.com`. 有关更多信息，请参阅《Experience Cloud界面用户指南》**&#x200B;中的[Adobe Target Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html??lang=zh-Hans)。

![Cookie在VEC助手扩展中切换](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

### 备选方案和解决方法

使用以下选项之一确保您的VEC和EEC继续按预期工作：

* 下载并使用更新的[VEC助手扩展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。
* 使用Mozilla Firefox浏览器。 Firefox尚未强制实施此策略。
* 使用以下标记从命令行运行Google Chrome，直到2021年9月21日。 9月21日后，您的网站在VEC中将无法再正常使用。 如果更新到Chrome 94，则必须在您的网站上手动生成包含`SameSite=none`和`Secure`的Cookie。

   ```
   --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
   ```

## [!DNL Target]是否支持多级iframe?

[!DNL Target] 不支持多级 iframe。如果您的网站加载的iframe具有子iframe，则at.js仅与父iframe交互。 [!DNL Target] 库不会与子 iframe 进行交互。

作为解决方法，您可以在体验中添加一个页面，其中包含子 iframe 的 URL。

## 我在尝试编辑页面时，看到的只是一个旋转图标而不是我的页面。（VEC 和 EEC） {#section_313001039F79446DB28C70D932AF5F58}

如果URL包含#字符，则可能会发生这种情况。 要解决此问题，请在可视化体验编辑器中切换到“浏览”模式，然后再切换回“撰写”模式。此时，旋转图标应当消失，页面应会加载。

## 内容安全策略(CSP)标头会阻止我网站上的[!DNL Target]库。 （VEC 和 EEC） {#section_89A30C7A213D43BFA0822E66B482B803}

如果您网站的 CSP 标头会阻止 Target 库，从而导致加载了网站却无法进行编辑，则请确保 Target 库不受阻止。

>[!NOTE]
>
>除了以下信息外，您还可以使用适用于 Google Chrome 的 [Adobe Target VEC 助手浏览器扩展](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![](assets/cps_headers.png)

作为解决方法，您可以配置 Requestly 规则以删除 CSP 标头，如下所示：

![](assets/cps_headers_2.png)

您可以为导致资源无法在 VEC 中加载的任何标头配置类似的 Requestly 规则。

对于 Requestly，每当需要删除标头时，您都应该执行以下任一操作：

* 为要在 VEC 中打开的 URL 添加 URL 规则，以便仅删除这些 URL 的标头。
* 在 VEC 中进行编辑时启用该规则，而在不使用 VEC 时禁用该规则。

## 重新编辑保存的活动时，VEC 或 EEC 显示为已损坏或未初始化。（VEC 和 EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

如果在定义体验后网站在可视化体验编辑器外部进行了更改，则在打开活动以进行重新编辑时，将无法找到之前执行操作时所用的选择器。页面会显示为已损坏，且不会出现任何警告。

## VEC 或 EEC 不显示我的旋转横幅以及其他包含 JavaScript 的内容。（VEC 和 EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

默认情况下，可视化体验编辑器会阻止 JavaScript 元素。如果在可视化体验编辑器设置中禁用 JavaScript，则可以使用这些元素。根据网站的设置方式，某些项目可能会继续以不正确方式显示或仍然不可用。

## 我在页面上更改一个元素时，多个元素会发生更改。（VEC 和 EEC） {#section_309188ACF34942989BE473F63C5710AF}

如果页面上的多个元素使用相同的 DOM 元素 ID，则更改其中一个元素会导致具有该 ID 的所有元素都发生更改。为防止这种情况发生，一个 ID 只应在每个页面上使用一次。此做法是标准的HTML最佳实践。 有关更多信息，请参阅[页面修改方案](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 我无法编辑防 iFrame 嵌套网站的体验。（VEC 和 EEC） {#section_9FE266B964314F2EB75604B4D7047200}

启用增强型体验编辑器即可解决此问题。单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选中启用增强型体验编辑器的复选框。 增强型体验编辑器使用 Adobe 管理的代理来加载页面以进行编辑。此代理允许在防iFrame嵌套的网站上进行编辑，并允许在尚未添加Adobe Target代码的网站和页面上进行编辑。 在添加代码之前，活动不会向网站交付内容。有些网站可能无法通过增强型体验编辑器来加载，在这种情况下，您可以取消选中此选项以通过 iFrame 加载可视化体验编辑器。

>[!NOTE]
>
>Adobe 代理服务器无法访问本地托管页面或在您的网络外部不可访问的页面，这些页面无法在 EEC 中打开。这些页面可能包括测试 URL、用户验收测试 (UAT) URL 或本地托管页面。

## 我想在尚未完成 mbox/Target 实施的页面上设置测试。（VEC 和 EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

请参阅上面的“我无法编辑防 iFrame 嵌套网站的体验”。

## 我的页面上不会显示使用“编辑文本/HTML”或“更改文本/HTML”设置的粗体和斜体文本样式。有时，在应用这些样式更改后，文本会消失。（VEC 和 EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

如果您在可视化体验编辑器中对 A/B 活动或体验定位活动使用&#x200B;**[!UICONTROL 编辑文本/HTML]**，或者对自动个性化活动或多变量测试活动使用&#x200B;**[!UICONTROL 更改文本/HTML]**，以使文本变为粗体或斜体，则这些样式可能不会在页面上应用，或者文本会从可视化体验编辑器内的页面中消失。之所以出现这种情况，是因为富文本编辑器应用这些样式的方式可能会干扰网站标记。

如果您遇到此问题：

1. 单击富文本编辑器中的 **[!UICONTROL HTML]** 按钮以进入源编辑模式。
1. 找到样式文本元素。

   * 对于粗体文本，请将 `<strong>` 元素更改为 `<b>`。

   * 对于斜体文本，请将 `<em>` 元素更改为 `<i>`。

## 对于自动个性化活动，VEC 或 EEC 中的图像交换显示为已中断。（VEC 和 EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

向某个位置添加图像选件会占据 VEC 或 EEC 中原始图像空间的整个大小范围。在交付时，图像不会展开，而是会按原样显示，这样便不会影响交付。
