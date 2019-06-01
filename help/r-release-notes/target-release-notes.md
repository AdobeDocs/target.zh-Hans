---
description: 下列发行说明将介绍最新版本或即将发布的 Target 版本的功能、增强功能、修复信息和已知问题。
keywords: 发行说明
seo-description: 这些发行说明提供有关最新或即将推出的Adobe Target版本的功能、增强、修复和已知问题的信息
seo-title: Target 发行说明（预发行版本）
solution: Target
title: Target 发行说明（预发行版本）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: fe022b641580e33afdac446f71cec85fd232b275

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

下列发行说明将介绍最新版本或即将发布的 [!DNL Adobe Target] 版本的功能、增强功能、修复信息和已知问题。

**上次更新时间：2019年月28日**

>[!NOTE]
>
>下列发行说明包含预发布的信息。发布日期、功能和其他信息可能会有变动。要查看有关当前版本的信息，请参阅 [目标发行说明](release-notes.md)。这些页面上的信息可能相同，也可能不同，具体取决于发行版的时间。

## at. js version2.1.0(2019年月日)

我们很高兴在. js2.1.0上宣布下列激动人心的功能：

| 功能/增强 | 描述 |
| --- | --- |
| Adobe选择加入支持 | 通过 Adobe 选择加入，可轻松将 Adobe 解决方案与同意管理平台集成。<br>有关Adobe选择加入的详细信息，请参阅 [隐私和一般数据保护规定(GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)。 |
| 符合行业标准的CSP | at. js不再使用eval()执行JavaScript。 |
| 客户端分析日志记录 | 无论客户端还是服务器端，都可以完全控制如何将分析数据发送到Adobe Analytics。 |
| 发送通知 | 允许开发人员在体验呈现的而不是使用 `applyOffer()` 或 `applyOffers()`使用的代码呈现通知时发送通知。 |
| 文件大小更小 | . js的大小减小了~24%。文件大小较小，可提高页面加载性能并缩短页面上下载. js的时间。 |

## [!DNL Target] Standard/Premium19.5.1(2019年月21日) {#release-19-5-1-prerelease}

这个版本包括以下功能、变化和增强功能：

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

### 功能更新

| 功能/增强 | 描述 |
| --- | --- |
| 单页应用程序可视化体验编辑器(SPA CMS) | SPA VEC 包含以下增强功能，可让您更快捷、更高效地完成工作：<ul><li>单击SPA中的某个操作会突出显示要应用此操作的站点上的元素。在View下创建的每个CMS操作都有四个对应图标：信息、编辑、移动和删除。此版本中新增的“移动”功能允许您将操作移至页面加载事件或修改面板中已经存在的任何其他视图。(TGT-33746)</li><li>在 VEC 中加载页面之前，或者即使页面无法完全加载（例如，自定义代码不再可操作），您可以执行许多操。网站加载之前无法编辑的操作会在 Target UI 中禁用。（TGT-33851 和 TGT-34149）</li></ul>有关更多信息，请参阅[单页应用程序 (SPA) 可视化体验编辑器](/help/c-experiences/spa-visual-experience-composer.md)。 |

### 增强功能、修复和更改

* 当您在 VEC 中取消载入页面后，系统会正确地显示出工具栏图标。如果某些特定的操作只有在完全载入页面后才能执行，那么相关的工具栏图标将会禁用。(TGT-33811)

## Mobile App Visual Experience Composer(2019年月14日){mobile-vec-月14日

| 功能/增强 | 描述 |
| --- | --- |
| 移动应用视觉体验书写器(CMS) | 利用移动App CMS，您无需连续的开发依赖关系和应用程序发布周期，即可在本机移动应用程序上创建活动和个性化内容。<br>有关详细信息，请参阅：<ul><li>[移动设备应用程序可视化体验编辑器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - 设置移动设备应用程序](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[在移动设备 VEC 中设置点击跟踪](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[视频：移动应用视觉体验书写器](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要获得有关Target和其他Adobe Experience Cloud解决方案的即将产品增强的预先通知，请注册Adobe优先产品更新：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
