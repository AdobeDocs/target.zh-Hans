---
keywords: 列入允许列表定位；可视化体验编辑器；白名单；允许列表；增强型可视化体验编辑器；VEC；可视化体验编辑器故障诊断；故障诊断；EEC；增强型体验编辑器；TLS；TLS 1.2
description: 了解如何对在某些情况下Adobe [!DNL Target] 可视化体验编辑器(VEC)和增强型体验编辑器(EEC)中有时出现的问题进行故障排除。
title: 如何排除与可视化体验编辑器和增强型体验编辑器相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1401'
ht-degree: 45%

---

# 与[!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]相关的问题疑难解答

在某些情况下，[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Enhanced Experience Composer] (EEC)中有时会出现显示问题和其他问题。

## Google Chrome SameSite Cookie 强制执行政策对 VEC 和 EEC 有什么影响？ {#samesite}

在使用以下Chrome版本时，请注意会影响VEC和EEC的更改：

>[!NOTE]
>
>以下更改将影响下面列出的所有三次更新：
>
> * 如果&#x200B;*没有安装VEC Helper扩展并为受密码保护的网站页面启用VEC，则*&#x200B;将无法使用VEC。 您的网站登录Cookie被视为第三方Cookie，在浏览模式下，不会与VEC编辑器中的登录请求一起发送。 唯一的例外是您的网站登录Cookie已设置`SameSite=None`和`Secure`属性。

**Chrome 94（2021年9月21日）**：由于计划对Chrome 94版本（2021年9月21日）进行即将进行的更改，以下更改将影响具有Chrome 94+浏览器版本的所有用户：

* 将删除命令行标志`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`。

**Chrome 91（2021年5月25日）**：随着对Chrome 91版本（2021年5月25日）实施更改，以下更改将会影响具有Chrome 91+浏览器版本的所有用户：

* 已从`chrome://flags`中删除标志`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`。 默认情况下，此行为现在处于启用状态。

**Chrome 80（2020年8月）**：随着更改在2020年8月实施，具有Chrome 80+浏览器版本的所有用户：

* 编辑活动时，*无法*&#x200B;下载[!DNL Target]库吗（当这些库不在网站上时）。 这是因为下载调用是从客户域向安全的[!DNL Adobe]域发起的，并且被拒绝为未经身份验证。
* 对于所有用户，EEC将&#x200B;*不是*&#x200B;函数，因为它不能为`adobemc.com domain`上的Cookie设置SameSite属性。 如果没有此属性，浏览器会拒绝这些Cookie，从而导致EEC失败。

### 确定阻止了哪些Cookie

要确定哪些Cookie因SameSite Cookie实施策略而被阻止，请使用Chrome中的开发人员工具。

1. 在Chrome中查看VEC时，要访问开发人员工具，请单击Chrome > **[!UICONTROL More Tools]** > **[!UICONTROL Developer Tools]**&#x200B;右上角的&#x200B;**[!UICONTROL ellipsis]**&#x200B;图标。
1. 单击&#x200B;**[!UICONTROL Network]**&#x200B;选项卡> ，然后查找阻止的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL Has blocked cookies]**&#x200B;复选框可更轻松地查找阻止的Cookie。

   下图显示了一个被阻止的Cookie：

   ![开发人员工具>网络选项卡，显示被阻止的Cookie](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/chrome-developer-tools.png)

### [!DNL Adobe Target] VEC Helper扩展

从版本0.7.1开始，当在扩展UI中打开“Cookie”切换时，[!DNL Adobe Target] VEC助手浏览器扩展会将`SameSite=None`和`Secure`属性添加到源自VEC内编辑的网页的响应的所有Cookie：

![Adobe Target VEC助手扩展UIAdobe Target VEC助手扩展UI](assets/cookies-vec-helper.png)

### 替代方案和解决方法

使用以下选项之一，确保VEC和EEC继续按预期工作：

* 下载并使用更新的[VEC助手扩展](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak?hl=en)。
* 使用Mozilla Firefox浏览器。 Firefox尚未强制执行此策略。
* 使用以下标记从命令行运行Google Chrome，直到2021年9月21日。 9月21日之后，需要Cookie的功能在VEC中将不再有效，例如登录或Cookie同意弹出窗口。 如果您更新到Chrome 94，则必须在您的网站上手动使用`SameSite=none`和`Secure`生成Cookie。

  ```
  --disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure
  ```

## [!DNL Target]是否支持多级iframe？

[!DNL Target]不支持多级iframe。 如果您的网站加载的iframe具有子iframe，则at.js仅与父iframe交互。 [!DNL Target]库不与子iframe交互。

作为解决方法，您可以在体验中添加一个页面，其中包含子 iframe 的 URL。

## 我在尝试编辑页面时，看到的只是一个旋转图标而不是我的页面。（VEC 和 EEC） {#section_313001039F79446DB28C70D932AF5F58}

如果URL包含#字符，则可能会发生这种情况。 要解决此问题，请在可视化体验编辑器中切换到“浏览”模式，然后再切换回“撰写”模式。此时，旋转图标应当消失，页面应会加载。

## 内容安全策略(CSP)标头阻止我的网站上的[!DNL Target]库。 （VEC 和 EEC） {#section_89A30C7A213D43BFA0822E66B482B803}

如果您网站的 CSP 标头会阻止 Target 库，从而导致加载了网站却无法进行编辑，则请确保 Target 库不受阻止。

>[!NOTE]
>
>除了以下信息外，您还可以使用适用于 Google Chrome 的 [Adobe Target VEC 助手浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![cps_headers图像](assets/cps_headers.png)

作为解决方法，您可以配置 Requestly 规则以删除 CSP 标头，如下所示：

![cps_headers_2图像](assets/cps_headers_2.png)

您可以为导致资源无法在 VEC 中加载的任何标头配置类似的 Requestly 规则。

对于 Requestly，每当需要删除标头时，您都应该执行以下任一操作：

* 为要在 VEC 中打开的 URL 添加 URL 规则，以便仅删除这些 URL 的标头。
* 在 VEC 中进行编辑时启用该规则，而在不使用 VEC 时禁用该规则。

## 重新编辑保存的活动时，VEC 或 EEC 显示为已损坏或未初始化。（VEC 和 EEC） {#section_5AC3BA8F8FBB451EA814F298D0645E54}

如果在定义体验后网站在可视化体验编辑器外部进行了更改，则在打开活动以进行重新编辑时，将无法找到之前执行操作时所用的选择器。页面会显示为已损坏，且不会出现任何警告。

## VEC 或 EEC 不显示我的旋转横幅以及其他包含 JavaScript 的内容。（VEC 和 EEC） {#section_8B5BE6EB050B42D6A14A054724C41330}

默认情况下，可视化体验编辑器会阻止 JavaScript 元素。如果在可视化体验编辑器设置中禁用 JavaScript，则可以使用这些元素。根据网站的设置方式，某些项目可能会继续以不正确方式显示或仍然不可用。

## 我在页面上更改一个元素时，多个元素会发生更改。（VEC 和 EEC） {#section_309188ACF34942989BE473F63C5710AF}

如果页面上的多个元素使用相同的 DOM 元素 ID，则更改其中一个元素会导致具有该 ID 的所有元素都发生更改。为防止这种情况发生，一个 ID 只应在每个页面上使用一次。该实践是标准的HTML最佳实践。 有关详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 我无法编辑防 iFrame 嵌套网站的体验。（VEC 和 EEC） {#section_9FE266B964314F2EB75604B4D7047200}

启用增强型体验编辑器即可解决此问题。单击&#x200B;**[!UICONTROL Administation]** > **[!UICONTROL Visual Experience Composer]**，然后选中启用增强型体验编辑器的复选框。 增强型体验编辑器使用 Adobe 管理的代理来加载页面以进行编辑。此代理允许在iFrame-busting网站上进行编辑，并允许在尚未添加Adobe Target代码的网站和页面上进行编辑。 在添加代码之前，活动不会向网站交付内容。有些网站可能无法通过增强型体验编辑器来加载，在这种情况下，您可以取消选中此选项以通过iFrame加载可视化体验编辑器。

>[!NOTE]
>
>Adobe 代理服务器无法访问本地托管页面或在您的网络外部不可访问的页面，这些页面无法在 EEC 中打开。这些页面可能包括测试 URL、用户验收测试 (UAT) URL 或本地托管页面。

## 我想在尚未完成 mbox/Target 实施的页面上设置测试。（VEC 和 EEC） {#section_DE63BCCB5B124E10A71FA579B582A80A}

请参阅上面的“我无法编辑防 iFrame 嵌套网站的体验”。

## 我的页面上不会显示使用“编辑文本/HTML”或“更改文本/HTML”设置的粗体和斜体文本样式。有时，在应用这些样式更改后，文本会消失。（VEC 和 EEC） {#section_7A71D6DF41084C58B34C18701E8774E5}

如果您在可视化体验编辑器中对A/B活动或体验定位活动使用&#x200B;**[!UICONTROL Edit Text/HTML]**，或者对Automated Personalization活动或多变量测试活动使用&#x200B;**[!UICONTROL Change Text/HTML]**&#x200B;以使文本粗体或斜体，则这些样式可能不会在页面上应用，或者文本会从可视化体验编辑器中的页面中消失。 出现这种情况是因为富文本编辑器应用这些样式的方式可能会干扰网站标记。

如果您遇到此问题：

1. 单击富文本编辑器中的&#x200B;**[!UICONTROL HTML]**&#x200B;按钮以进入源编辑模式。
1. 找到样式文本元素。

   * 对于粗体文本，请将 `<strong>` 元素更改为 `<b>`。

   * 对于斜体文本，请将 `<em>` 元素更改为 `<i>`。

## 对于自动个性化活动，VEC 或 EEC 中的图像交换显示为已中断。（VEC 和 EEC） {#section_88AABFDFE6A3420299B0D508B12A3994}

向某个位置添加图像选件会占据 VEC 或 EEC 中原始图像空间的整个大小范围。在交付时，图像不会展开，而是会按原样显示，这样便不会影响交付。
