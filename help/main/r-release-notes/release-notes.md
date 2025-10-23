---
keywords: 发行说明；新功能；版本；更新；更新；版本；增强；增强；修复；错误修复；更新；当前更新
description: 了解  [!DNL Adobe Target] 当前版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
landing-page-description: 了解  [!DNL Adobe Target] 当前版本中包括的新增功能、增强功能和修复。
short-description: 了解  [!DNL Target] 当前版本中包括的新增功能、增强功能和修复。
title: 当前版本中包括什么功能？
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 17%

---

# [!DNL Target]发行说明（当前版本）

浏览[!DNL Adobe Target]中的最新功能、增强功能和修复。 这些发行说明还涵盖了[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、at.js和其他平台组件（如果适用）的更新。

（括号中的问题编号供 [!DNL Adobe] 内部使用。）

## 您需要了解的时间性更新 {#time-sensitive}

[!BADGE 重要]{type=Informative}

对于与[!DNL Adobe Target]和您的实施相关的时效性更新，[!DNL Adobe]通过[!UICONTROL Experience League]提供详细的发行说明和文档。 以下是一些与您的实施相关的关键功能亮点：

### [!DNL Target] UI版本切换弃用

有关详细信息，请参阅[[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)。

## [!DNL Target Standard/Premium] 25.10.1（2025年10月22日）

此版本包含以下更新和修复：

**活动**

+++ 查看详细信息
* **解决了更新后的UI中的可用性问题**。 [!UICONTROL Observers]现在可以使用[!UICONTROL View Activity]选项预览活动，就像在旧版UI中一样。 (TGT-51741)
* **[!UICONTROL Observer]用户现在可以在更新后的UI中查看活动内容。**&#x200B;已恢复观察者角色用户在更新后的活动UI中的可见性。 以前，观察者无法查看旧版UI中可用的修改、选件和内容更改。 (TGT-53785)
* **[!UICONTROL Approver]用户现在可以编辑活动目标，而不会出现编辑器权限错误。**&#x200B;解决了活动创建UI中的权限问题，该问题阻止审批者级别的用户保存对高级目标设置的更改。 受影响的用户收到`403 Forbidden.Resource`错误，需要编辑器权限，尽管具有足够的访问权限。 (TGT-53819)

+++

**受众**

+++查看详细信息
* **已在“仅此活动”报表中恢复多受众选择。**&#x200B;解决了活动创建UI中阻止用户在[!UICONTROL This activity only]的[!UICONTROL Goals & Settings]部分下选择多个受众的问题。 (TGT-53283)
* **基于受众的报表图形现在可正确显示转化数据。**&#x200B;解决了[!UICONTROL Reports]选项卡中导致图形在选择非默认受众时失败的问题。 虽然提供了数据和置信度量度，但可视化图表只显示一条实线，导致分析困难。 (TGT-53769)
* **[!UICONTROL Targeting] UI现在明确指示排除的受众规则。**&#x200B;解决了在活动创建UI的[!UICONTROL Targeting]部分中，未明确显示设置为[!UICONTROL Exclude]的受众规则的问题。 这会导致查看定位逻辑时出现混淆，尤其是对于排除特定URL的受众。 (TGT-53809)
* **受众定义值现在可以在[!UICONTROL Targeting]选项卡中选择和复制。**&#x200B;解决了活动创建界面中阻止用户在[!UICONTROL Targeting]选项卡中选择和复制受众规则值的问题。 旧版UI中提供了此功能，但更新后的UI中缺少此功能。 (TGT-53856)

+++

**本地化**

+++查看详细信息
* **更正了zh_CN页面编辑器上下文中“引用”的错误。**&#x200B;更正了zh_CN区域设置中的上下文翻译错误，该错误导致术语“quote”被不准确地翻译为“报价”，从而暗含商业价格报价。 在“排版规则”>“标题样式”>“块引用”部分中，预期含义是指格式元素（引用块）而不是定价。 (TGT-53841)
* **更正了zh_CN页面编辑器上下文中“删除了引号”的错误。**&#x200B;更正了zh_CN区域设置中的一个翻译错误，该错误中“quote removed”未准确地呈现为“移除了报价”，这意味着提供了商业报价。 在“排版规则”>“标题样式”>“块引用”部分中，术语是指格式元素（引用块）而不是定价。 (TGT-53843)
* **更正了zh_CN页面编辑器上下文中“重新排列报价”的错误。**&#x200B;更正了zh_CN区域设置中的上下文翻译错误，其中“quote reorized”被不准确地翻译为“重新排列了报价”，这意味着商业报价。 在“排版规则”>“标题样式”>“块引用”部分中，术语是指格式元素（引用块）而不是定价。 (TGT-53844)
* **更正了zh_CN页面编辑器上下文中“quote changed”的错误。**&#x200B;更正了zh_CN区域设置中的一个翻译错误，该错误中“quote changed”未准确地呈现为“更改了报价”，这表示使用了商业报价。 在“排版规则”>“标题样式”>“块引用”部分中，术语是指格式元素（引用块）而不是定价。 (TGT-53845)

+++

**推荐**

+++查看详细信息
* 现在可正确保存推荐的&#x200B;**CSS选择器更改。**&#x200B;解决了活动创建UI中阻止用户更新推荐投放的CSS选择器的问题。 更改在保存后已恢复，阻止对定向容器的更新。 (TGT-53835)
* **页面加载事件选择现在在推荐修改中持续存在。**&#x200B;解决了在将推荐的事件类型从[!UICONTROL View]切换到[!UICONTROL Page Load]时，活动创建UI中阻止用户保存更改的问题。 尽管选择似乎成功，但在导航离开并阻止活动发布后已恢复。 (TGT-53957)

+++

**报表**

+++查看详细信息
* **“[!UICONTROL Export order details to CSV]”现在下载完整数据。**&#x200B;解决了在更新的[!UICONTROL Overview] UI中导致“[!UICONTROL Export Order details to CSV]”选项下载空文件的问题，即使存在有效的报表数据也是如此。 (TGT-53787)

+++

**安全性**

+++查看详细信息
* 已添加&#x200B;**IMS预筛选器以保护GQL端点免受跨组织数据泄露的影响。**&#x200B;解决了“管理员”选项卡中影响licenseGroups和targetProperties GraphQL端点的安全漏洞。 问题源于将JIL API与管理员客户端令牌一起使用，可能会利用此令牌访问跨组织产品数据。 (TGT-53837)

+++

**可视化体验编辑器 (VEC)**

+++查看详细信息
* **在活动创建UI中恢复了创作稳定性。**&#x200B;解决了VEC UI中的一个间歇性问题，该问题会导致创作失败，并且链接会变得意外可点击，从而将用户重定向到离开页面的位置。 (TGT-53153)
* 在活动创建UI中&#x200B;**已恢复对已保存活动的编辑。**&#x200B;解决了导致用户在保存修改后无法编辑活动的问题。 受影响的活动在“[!UICONTROL Applying initial modifications]”中仍然卡住，阻止进一步更新并隐藏[!UICONTROL Cancel]按钮。 (TGT-53631)
* **VEC不再在“[!UICONTROL Applying initial modifications]”上停止。**&#x200B;解决了VEC中的一个性能问题，该问题在加载具有大量修改的体验时导致长时间延迟。 受影响的用户看到UI在“[!UICONTROL Applying initial modifications]”上停滞了数分钟，尤其是在体验B场景中。 (TGT-53727)
* **VEC现在加载修改时不含根元素。**
解决了VEC中的一个问题，在加载缺少明确根元素的修改时，该问题会导致体验停滞。 这些修改以前导致UI无限期地在“A[!UICONTROL pplying initial modifications]”上挂起。 (TGT-53799)
* **在活动中保存更改现在可按预期工作。**&#x200B;解决了新创建UI中与权限相关的问题，该问题阻止用户在编辑活动中的目标和高级设置时保存更改。 尽管具有适当的访问权限，受影响用户仍看到红色错误功能区和“Forbidden.Resource”消息。 (TGT-53816)
* **VEC UI现在保留跨视图的体验修改。**&#x200B;解决了更新后的VEC中影响体验开发的多个问题。 修改无法正确持久保留，尤其是在使用HTML选件或在视图之间切换时。 (TGT-53825)
* **现在，当修改跨越多个体验时，所有视图均可正确显示。**&#x200B;解决了在活动创建UI中，当修改应用于多个视图时只显示一个视图的问题。 即使正确应用了修改，悬停工具提示仍无法列出所有关联的视图。 (TGT-53827)
* **VEC不再在“[!UICONTROL Applying initial modifications]”上间歇性停止。**&#x200B;解决了VEC中的一个间歇性问题，该问题导致体验加载失败并停留在“[!UICONTROL Applying initial modifications]”上。 此行为不一致，有时会触发重定向循环或需要手动清除缓存。 (TGT-53916)
* 无法重现&#x200B;**VEC加载问题。**&#x200B;我们调查了一个报告的问题，即在编辑现有活动时，VEC停留在“[!UICONTROL Applying initial modifications]”上。 此行为疑似与缺少父元素的HTML内容有关。 我们将继续监控复发，并建议为HTML选件使用结构化容器以确保稳定性。 (TGT-53972)
* VEC中的&#x200B;**[!UICONTROL Design]模式不再像[!UICONTROL Browse]模式那样间歇性地工作。**&#x200B;解决了UI中[!UICONTROL Design]模式间歇性地表现为[!UICONTROL Browse]模式的问题，该问题允许可单击的`<a>`链接并阻止元素选择。 这会导致悬停框消失并阻止修改工作流。 (TGT-53136)
* 在&#x200B;**模式下的[!UICONTROL Composer]按钮点击不再触发页面重定向。**&#x200B;解决了更新后的VEC UI中的一个问题：在[!UICONTROL Composer]模式下单击按钮会导致意外重定向到该按钮的目标URL。 这会阻止用户编辑call-to-action (CTA)元素，并中断创作工作流。 (TGT-53137)
* **自动个性化活动中的选件代码更新现在保存无误。**&#x200B;解决了在更新[!UICONTROL Invalid user input]活动中的优惠代码时，在新建用户界面中导致“[!UICONTROL Automated Personalization]”错误的问题。 该错误阻止用户保存更改，即使输入有效也是如此。 (TGT-53586)
* VEC中的&#x200B;**[!UICONTROL Design]模式现在阻止可编辑组件的链接导航。**&#x200B;解决了更新后的VEC中存在的一个问题，即在[!UICONTROL Design]模式下，可单击元素（如按钮和链接）会触发页面重定向。 此行为模拟[!UICONTROL Browse]模式并阻止用户修改关键组件。 (TGT-53696)
* **“[!UICONTROL Clicked an element]”量度现在无需重定向或错误即可工作。**&#x200B;解决了在新的创建UI中，选择“[!UICONTROL Clicked an element]”转化量度时导致意外重定向和空白屏幕的问题。 在安装期间单击某个按钮会触发导航而不是注册元素，从而导致“[!UICONTROL element not found]”错误。 (TGT-53817)
* **编辑期间现有活动不再卡在无限加载循环中。**&#x200B;解决了新创建UI中的一个问题，该问题导致在VEC中编辑现有活动导致页面停留在无限加载循环中。 此问题不会影响新创建的活动，是由页面上预先存在的修改触发的。 (TGT-53913)
* **现在可在VEC中正确加载包含修改的现有活动页面。**&#x200B;解决了在更新的VEC中，使用保存的修改编辑现有活动时导致页面停滞在加载阶段的问题。 新活动已加载且没有问题，但之前配置的活动无法呈现。 (TGT-53967)

+++

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| [文档更改](/help/main/r-release-notes/doc-change.md) | 查看这些发行说明中未包括的关于本指南的更新的详细信息。 |
| [以前版本的发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。 |
| [Adobe Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans){target=_blank} | 查看 Adobe Experience Cloud 解决方案的最新发行说明。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| [Adobe 优先产品更新](https://www.adobe.com/cn/subscription/priority-product-update.html){target=_blank} | 提前收到有关 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案的即将发行产品增强功能的通知。 |
| [Target 发行说明 - 预发行版本](/help/main/r-release-notes/target-release-notes.md){target=_blank} | 有关当月的 Target 版本的信息，包括预发行信息。 |
