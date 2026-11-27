---
keywords: 定位；可视化体验编辑器；白名单；允许列表；增强型可视化体验编辑器；VEC；可视化体验编辑器故障诊断；故障诊断；EEC；增强型体验编辑器；TLS；TLS 1.2
description: 了解如何解决在某些情况下[!DNL Target] [!UICONTROL 可视化体验编辑器] (VEC)和[!UICONTROL 增强型体验编辑器] (EEC)中有时出现的问题。
title: 如何解决与[!UICONTROL 可视化体验编辑器]和[!UICONTROL 增强型体验编辑器]相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: d829cd63-950f-4bb4-aa58-0247f85de383
TQID: 'https://experienceleague.adobe.com/4v7Qe-Yzjke-GceUSRDO2SMZGkxvrkdsSXQt8TR-bic'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 13%
---
# 与[!DNL Adobe Target] [!UICONTROL 可视化体验编辑器]和[!UICONTROL 增强型体验编辑器]相关的问题疑难解答 {#vec-eec-issues}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何解决同时影响&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)和&#x200B;**[!UICONTROL 增强型体验编辑器]** (EEC)的问题。

>[!ENDSHADEBOX]

在某些情况下，[!DNL Target] **[!UICONTROL 可视化体验编辑器]** (VEC)和&#x200B;**[!UICONTROL 增强型体验编辑器]** (EEC)有时会发生显示问题和其他问题。 以下项目描述了影响两种编辑器的问题以及如何解决这些问题。

## 浏览器和安全性

### Google Chrome SameSite Cookie 策略 {#samesite}

[!DNL Google Chrome]的SameSite Cookie强制策略会影响以下版本中的VEC和EEC。

>[!NOTE]
>
>以下更改适用于所有三个版本。 除非安装并启用[VEC Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)，否则无法在网站受密码保护的页面上使用VEC。 网站的登录Cookie被视为第三方Cookie，因此在&#x200B;**[!UICONTROL 浏览]**&#x200B;模式下，不会在VEC编辑器中随登录请求一起发送它们。 唯一的例外是登录Cookie已设置`SameSite=None`和`Secure`属性。

* **Chrome 94（2021年9月21日）：**&#x200B;对于具有Chrome 94及更高版本的所有用户，命令行标志`--disable-features=SameSiteByDefaultCookies,CookiesWithoutSameSiteMustBeSecure`已被删除。
* **Chrome 91 （2021年5月25日）：**&#x200B;对于具有Chrome 91及更高版本的所有用户，已从`chrome://flags`中删除标志`#same-site-by-default-cookies`和`#cookies-without-same-site-must-be-secure`。 默认情况下，此行为现在处于启用状态。
* **Chrome 80（2020年8月）：**&#x200B;对于使用Chrome 80及更高版本的所有用户：

  * 如果网站上没有[!DNL Target]库，则在编辑活动时无法下载这些库。 从客户域向安全[!DNL Adobe]域发起下载调用，并因未经身份验证而被拒绝。
  * EEC无法正常运行，因为它不能为`adobemc.com`域上的Cookie设置SameSite属性。 如果没有此属性，浏览器会拒绝这些Cookie，从而导致EEC失败。

+++ 确定阻止了哪些Cookie

要确定SameSite Cookie实施策略阻止了哪些Cookie，请在[!DNL Chrome]中使用[!DNL Developer Tools]。

1. 在[!DNL Chrome]中查看VEC时，单击Chrome > **[!UICONTROL 更多工具]** > **[!UICONTROL 开发人员工具]**&#x200B;右上角的&#x200B;**[!UICONTROL 省略号]**&#x200B;图标。
1. 单击&#x200B;**[!UICONTROL 网络]**&#x200B;选项卡，然后查找被阻止的Cookie。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL 已阻止的Cookie]**&#x200B;复选框可更轻松地查找已阻止的Cookie。

+++

+++ 内容安全策略(CSP)标头阻止网站上的[!DNL Target]库

如果网站的CSP标头阻止[!DNL Target]库，则网站会加载，但会阻止编辑。 确保未阻止[!DNL Target]库。

>[!NOTE]
>
>除了以下信息外，还可以使用适用于[!DNL Google Chrome]的[Adobe Target VEC Helper浏览器扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)。

![浏览器控制台显示已阻止的target.js请求，并显示违反内容安全策略指令的消息](assets/cps_headers.png)

作为解决方法，请配置[!DNL Requestly]规则以删除CSP标头，如下图所示。

![Requestly对话框，修改HTTP请求和响应中的标头，该标头具有名为Content-Security-Policy的规则，可从响应中删除Content-Security-Policy标头](assets/cps_headers_2.png)

可以为任何导致资源无法在VEC中加载的标头配置类似的[!DNL Requestly]规则。 当需要使用[!DNL Requestly]删除标头时，请执行下列操作之一：

* 为要在VEC中打开的URL添加URL规则，以便仅删除这些URL的标头。
* 在VEC中编辑时启用规则，并在VEC未使用时禁用规则。

+++

+++ 不支持多级iframe

[!DNL Target]不支持多级iframe。 如果网站加载的iframe具有子iframe，则at.js仅与父iframe交互。 [!DNL Target]库不与子iframe交互。

作为解决方法，请在体验中添加一个页面，其中包含子iframe的URL。

+++

+++ 无法在iFrame-busting网站或没有[!DNL Target]实施的页面上编辑体验

启用&#x200B;**[!UICONTROL 增强型体验编辑器]** (EEC)以解决此问题。 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，然后选中启用&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;的复选框。

EEC使用[!DNL Adobe]管理的代理加载页面以进行编辑。 此代理允许在iFrame-busting网站以及尚未添加[!DNL Adobe Target]代码的网站和页面上编辑。 在添加代码之前，活动不会向网站交付内容。 某些网站可能无法通过EEC加载，在这种情况下，清除此选项将通过iFrame加载页面。

>[!NOTE]
>
>[!DNL Adobe]代理服务器无法访问本地托管的页面和无法从网络外部访问的页面，无法在EEC中打开。 这些页面可能包括测试 URL、用户验收测试 (UAT) URL 或本地托管页面。

+++

## 页面加载和显示

+++ 编辑页面时，将显示旋转图标而不是页面

如果URL包含#字符，则可能会发生这种情况。 要解决此问题，请在VEC或EEC中切换到&#x200B;**[!UICONTROL 浏览]**&#x200B;模式，然后切换回&#x200B;**[!UICONTROL 撰写]**&#x200B;模式。 此时，旋转图标应当消失，页面应会加载。

+++

+++ 再次编辑保存的活动时，VEC或EEC显示为已损坏或未初始化

如果定义体验后，网站在VEC外部发生更改，则在打开活动以进行重新编辑时，无法找到之前对其执行操作的选择器。 页面会显示为已损坏，且不会出现任何警告。

+++

+++ 旋转横幅和包含JavaScript的其他内容不会显示在VEC或EEC中

默认情况下，VEC会阻止JavaScript元素。 禁用JavaScript后，可以处理这些元素。 根据网站的设置方式，某些项目可能会继续以不正确方式显示或仍然不可用。

+++

+++ 对于Automated Personalization活动，VEC或EEC中的图像交换显示为已中断

向某个位置添加图像选件会占据 VEC 或 EEC 中原始图像空间的整个大小范围。 在交付时，图像不会展开，而是会按原样显示，这样便不会影响交付。

+++

## 编辑结果

+++ 更改页面上的一个元素会更改多个元素

如果页面上的多个元素使用相同的 DOM 元素 ID，则更改其中一个元素会导致具有该 ID 的所有元素都发生更改。 要防止出现这种情况，请在每个页面上仅使用一次ID。 这是标准的 HTML 最佳实践。 有关详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#vec-scenarios)。

+++

+++ 在应用“编辑文本”/“编辑HTML”或“更改文本”/“更改HTML”后，不显示粗体和斜体文本样式，或文本消失

当&#x200B;**[!UICONTROL 编辑文本]**/**[!UICONTROL 编辑HTML]**&#x200B;在VEC中用于&#x200B;**[!UICONTROL A/B测试]**、**[!UICONTROL 体验定位]**&#x200B;活动，或者&#x200B;**[!UICONTROL 更改文本]**/**[!UICONTROL 更改HTML]**&#x200B;用于&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;或&#x200B;**[!UICONTROL 多变量测试]**&#x200B;活动时，要使文本变为粗体或斜体，样式可能不会在页面上应用，或者文本可能会从VEC中的页面中消失。 之所以发生这种情况，是因为富文本编辑器应用这些样式的方式可能会干扰网站标记。

如果出现此问题：

1. 单击富文本编辑器中的 **[!UICONTROL HTML]** 按钮以进入源编辑模式。
1. 查找样式化的文本元素。

   * 对于粗体文本，请将 `<strong>` 元素更改为 `<b>`。
   * 对于斜体文本，请将 `<em>` 元素更改为 `<i>`。

+++
