---
keywords: 定位；可视化体验编辑器；VEC；可视化体验编辑器故障诊断；故障诊断；TLS；TLS 1.2
description: 了解如何解决[!UICONTROL 可视化体验编辑器] (VEC)中的问题。
title: 如何解决与[!UICONTROL 可视化体验编辑器]相关的问题？
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
TQID: 'https://experienceleague.adobe.com/VNkydzzU-WRRAL0pqQPOs-sKrY8a6DS5Go764UGh0Hs'
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
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 4%
---
# 排除与[!UICONTROL 可视化体验编辑器]相关的问题 {#vec-issues}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何解决仅影响&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)的问题。

>[!ENDSHADEBOX]

有时，在某些情况下，[!DNL Adobe Target] **[!UICONTROL 可视化体验编辑器]** (VEC)会发生显示问题。 以下项目介绍了仅影响VEC的问题以及如何解决这些问题。

+++ 在VEC中打开网站时未加载[!DNL Target]库

在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中打开网站时，[!DNL Target]将参数`mboxEdit=1`和`mboxDisable=1`添加到URL中。

在不重新加载页面的情况下从一个页面导航到另一个页面时，修剪或删除这些参数的网站（特别是单页面应用程序）会破坏[!DNL Target]功能，并且[!DNL Target]库不会加载。 要避免出现此问题，请在URL中保留这两个参数。

+++

+++ 页面无法在EEC中打开或加载缓慢，或者活动和体验在VEC中加载缓慢

多个问题可能会影响[!DNL Target]体验编辑器中的页面性能。 最常见的情况如下：

* 页面没有mbox。
* 网站使用代理阻止，阻止页面在任一体验编辑器中打开。
* 该站点不允许在iFrame中打开自身。

当&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;中发生问题时，请将其关闭并改用&#x200B;**[!UICONTROL 可视化体验编辑器]**。 为此，请转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 可视化体验编辑器]**，并关闭&#x200B;**[!UICONTROL 启用增强型体验编辑器]**&#x200B;选项。

控制台中会显示以下错误消息：

![浏览器控制台错误消息，指出由于X-Frame-Options设置为SAMEORIGIN，页面被拒绝显示在框架中](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

当这两种编辑器都不工作时，覆盖站点的X-Frame-Options标头的浏览器扩展(如[!DNL Requestly] （[!DNL Chrome]或[!DNL Firefox]）或Modify Response Headers ([!DNL Firefox]))允许站点在iFrame中加载，从而启用VEC。 当无法使用浏览器扩展时，请使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)。 除了下面的过程外，还可以使用[!DNL Google Chrome]的[[!DNL Adobe Target] **[!UICONTROL 可视化编辑帮助程序&#x200B;]**&#x200B;扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)。

>[!NOTE]
>
>这些扩展仅用于VEC编辑。
>
>使用[!DNL Requestly]，无论何时需要删除标头，均请执行下列操作之一：
>
>* 为要在VEC中打开的URL添加URL规则，以便仅删除这些URL的标头。
>* 在VEC中编辑时启用规则，并在VEC未使用时禁用规则。
>
>对于&#x200B;**[!UICONTROL Modify Response Headers]** ([!DNL Firefox])，URL规则不可用，因此必须在VEC中编辑时启用该规则，并在VEC未使用时禁用该规则。

设置扩展后，即使&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;被禁用，页面也会在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中加载。

+++

+++ 使用Requestly（Chrome或Firefox）删除X-Frame-Options标头

1. 关闭&#x200B;**[!UICONTROL 增强型体验编辑器]**。
1. 在[!DNL Chrome]或[!DNL Firefox]上安装[!DNL Requestly]浏览器扩展。
1. 打开扩展并选择&#x200B;**[!UICONTROL 修改标头]**。
1. 输入规则名称。
1. 在修改规则中，创建一个删除标题的规则：

   * 将&#x200B;**[!UICONTROL 添加]**&#x200B;切换为&#x200B;**[!UICONTROL 删除]**。
   * 将&#x200B;**[!UICONTROL 请求]**&#x200B;切换为&#x200B;**[!UICONTROL 响应]**。
   * 输入“X-Frame-Options”作为标头名称。

1. 重复上一步并输入“x-frame-options”作为标题名称。

   >[!NOTE]
   >
   >使用[!DNL Requestly]处理的标头区分大小写。

1. 将&#x200B;**[!UICONTROL Equals]**&#x200B;更改为&#x200B;**[!UICONTROL Contains]**&#x200B;作为源URL的条件，并输入要加载到VEC中的活动的URL。

   ![名为Bypass iframe嵌套代码的Requestly规则，用于为包含adobe.com的URL删除X-Frame-Options响应标头](assets/chrome_extension.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

   ![删除所有URL的X-FRAME-OPTIONS和x-frame-options响应标头的Requestly规则](assets/requestly.png)

该页面现在应在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中快速加载。

+++

+++ 删除带有修改响应标头的X-Frame-Options标头(Firefox)

1. 在[!DNL Firefox]上安装[!DNL Modify Response Headers]扩展并重新启动浏览器。
1. 从[!DNL Firefox]扩展中，选择[!DNL Modify Response Headers]扩展。
1. 单击&#x200B;**[!UICONTROL 首选项]**。
1. 从&#x200B;**[!UICONTROL 操作]**&#x200B;下拉列表中选择Select **[!UICONTROL 筛选器]**。
1. 在&#x200B;**[!UICONTROL 标头名称]**&#x200B;字段中，输入&#x200B;**[!UICONTROL X-Frame-Options]**。
1. 重复前两个步骤以添加具有&#x200B;**[!UICONTROL x-frame-options]**&#x200B;的筛选器。
1. 单击&#x200B;**[!UICONTROL 添加]**。
1. 单击&#x200B;**[!UICONTROL 启动]**。

![在Firefox中修改响应标头窗口，X-Frame-Options标头上的筛选器显示为已启用](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

+++

+++ VEC中不显示页面

检查以下原因：

* **扩展版本：** [[!DNL Adobe Experience Cloud] **[!UICONTROL 可视化编辑帮助程序&#x200B;]**&#x200B;扩展的最新版本](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)提供了与VEC的最佳兼容性。 若要验证已安装的版本，请转到&#x200B;**[!UICONTROL &#x200B;扩展&#x200B;]**>**[!UICONTROL &#x200B;管理扩展&#x200B;]**，然后单击&#x200B;**[!UICONTROL &#x200B;详细信息&#x200B;]**。
* **创作库：** VEC需要创作库才能修改网页。 它们嵌入在at.js库中，每次使用VEC时，扩展都会从[!DNL Adobe]服务器下载该库，无论at.js或[!DNL Adobe Experience Platform Web SDK]是否已在页面上。 检查&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实现]**&#x200B;中配置的at.js标头是否不包含任何无效更改。
* **阻止的请求：**&#x200B;当页面嵌入到iFrame中时，该页面不能阻止必须加载的请求。 此类阻止包括`frame-ancestors` CSP指令、网站中的自定义JavaScript代码、元HTML标记和`x-frame-options`标头。
* **保留的文件名：**&#x200B;页面的JavaScript不得干扰创作库。 请勿使用或包含具有以下保留名称的文件：

  * `target-vec-helper.js`
  * `target-vec.js`
  * `target.js`
  * `admin.css`
  * `sizzle.js`
  * `mixContentCheck.html`

  意外覆盖在这些文件中定义的变量或事件也会导致VEC出现问题。

* **安全站点上的非安全页面：**&#x200B;浏览器阻止该页面。 单击地址栏中URL左侧的图标，然后单击&#x200B;**[!UICONTROL 在此页面上禁用保护]**。
* **无效的URL：**&#x200B;输入的URL无效。
* **Cookie：**&#x200B;如果网站无法在VEC中加载或行为异常，则在[!DNL Target]中加载网站之前在浏览器中接受其Cookie可以解决此问题。

+++

+++ 在浏览模式下，VEC显示为已损坏

在&#x200B;**[!UICONTROL 浏览]**&#x200B;模式下，如果打开的URL缺少[!DNL Target]库（[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=zh-Hans){target=_blank}或[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=zh-Hans){target=_blank}）或包含frame-buster标头，则VEC显示为已损坏。 出于浏览器安全原因，[!DNL Target]无法正确访问导航到的URL，或者在页面加载时VEC URL未一致更新。

VEC在`<iframe>`中加载网页，当前浏览器的安全机制阻止[!DNL Target] UI访问相同源策略下的框架元素。 浏览器会阻止尝试访问具有不同来源的帧的脚本，包括`location.href`等信息。

使用新的[Visual Editing Helper扩展](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)将[!DNL Target]库插入到页面中，以便以最佳方式浏览页面。

+++

+++ 问题由VEC中的CSS冲突导致

检查当页面在编辑器中加载时，是否有任何CSS文件影响可见性。 例如，页面主体上的`overflow: hidden`属性可能会导致滚动问题或触发干扰创作菜单的点击事件。

+++
