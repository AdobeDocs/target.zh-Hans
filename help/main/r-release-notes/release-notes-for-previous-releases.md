---
keywords: 发行说明；预发行说明；未来增强；未来修复；未来功能；即将发布的版本
description: 查看 Adobe Target 早期版本中包括的功能、增强和修补的列表。
title: 早期版本中包括什么功能？
feature: Release Notes
exl-id: e4d261a1-d3aa-46ea-b1ce-efa76a90dc71
TQID: 'https://experienceleague.adobe.com/cjheajZKokzwCNspfQckh6PHh5ecetdj7vZrrq9IqXw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
    internal-label: Administration and configuration
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
    internal-label: Analytics integration
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: c5abb976-5170-45d6-bcac-66d15d10a4d4
    internal-label: Release notes
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
    internal-label: Experimentation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: e6ff21d3-dec6-4298-8590-7c749fffaf78
    internal-label: Content and assets
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
    internal-label: Web experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '6587'
ht-degree: 2%
---
# 以前版本的发行说明

以前 [!DNL Adobe Target] 版本的发行说明，包括 [!DNL Target Standard/Premium]、[!DNL Target] 平台和 [!DNL Target] JavaScript 库 (at.js) 的发行说明。

发行说明按发布年月以降序列出。

>[!NOTE]
>
>请参阅 [Target 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A)，以了解有关当月 Target 发行版本（平台和 Target Standard/Premium）的信息。

## 发行说明 — 2026

## [!DNL Target Standard/Premium] 26.9.8（2026年9月30日）

### 功能

<table>
<thead>
<tr>
<th><strong>样本量计算器</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>样本量计算器可以估计所需的流量、测试持续时间、体验数量或您可以可靠检测到的最小影响，从而帮助您在启动前计划试验。 它通过“活动”菜单提供，使用输入帮助您确定测试所需的资源和运行时间。</p>
<p>样本量计算器功能目前作为测试版功能提供。</p>
<p>有关更多信息，请参阅此<a href="../c-activities/sample-size-calculator.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI Insights</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI分析通过手动流量分配，为A/B测试活动提供AI生成的试验学习和优化机会。 一旦试验达到统计显着性，分析会突出显示可能对其性能有所贡献的入选体验的属性。 建议的机会包括新的体验想法、假设和实施指导，以帮助提高转化率。</p>
<p>AI分析功能目前作为测试版功能提供。</p>
<p>有关更多信息，请参阅此<a href="../c-activities/ai-insights.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改进功能

**[!UICONTROL 管理]**

+++ 查看详细信息

* **无法向用户授予AI权限**。 具有产品管理员和系统管理员访问权限的用户无法将AI权限授予其他用户。 尝试启用AI权限导致`Unauthorized`错误，即使为组织启用了AI也是如此。 (TGT-56261)

+++

## [!DNL Target Standard/Premium] 26.9.7（2026年9月28日）


**[!UICONTROL 推荐]**

+++ 查看详细信息

* 可视化体验编辑器&#x200B;**中出现**“用户输入无效”错误。 在可视化体验编辑器中编辑“推荐”活动时，在尝试保存并关闭活动时出现“无效用户输入”错误。

+++


## [!DNL Target Standard/Premium] 26.9.6（2026年9月24日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 通过可视化体验编辑器&#x200B;**访问经SSO验证的页面时，出现**&#x200B;无尽的重定向循环。 当加载到可视化体验编辑器的页面URL经历SSO/登录重定向流程时，可视化体验编辑器进入无限重定向循环，从未到达预期页面。 (TGT-56233)

+++

## [!DNL Target Standard/Premium] 26.9.5（2026年9月21日）

### 功能

<table>
<thead>
<tr>
<th><strong>内容预隐藏</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>内容预隐藏仅隐藏Adobe Target个性化即将更改的部分，从而有助于减少页面闪烁，在内容加载时可提供更顺畅的体验。 此方法可避免隐藏整个页面，并有助于在启动新活动时最大限度地减少实施工作。</p>
<p>此功能以前以“有限可用性”发布，现在可用于所有环境（一般可用性）。</p>
<p>有关更多信息，请参阅此<a href="../administrating-target/content-pre-hiding.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

### 改进功能

**[!UICONTROL 目标分析]**

+++查看详细信息

* **A4T报告链接未在[!DNL Target] UI**&#x200B;中生成。 对于[!DNL A4T]活动，未在&#x200B;**[!UICONTROL 报表]**&#x200B;分区中生成报表链接，即使基础报表数据在[!DNL Target] UI和[!DNL Adobe Analytics] UI中均可见。 (TGT-56247)

+++

## [!DNL Target Standard/Premium] 26.9.4（2026年9月17日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 在最顶部的页面元素&#x200B;**上的[!DNL Experience Fragments]无法访问**[!UICONTROL &#x200B;此项前插入]控件。 在可视化体验编辑器中，选择页面上最顶部的元素将页面向上滚动，导致&#x200B;**[!UICONTROL 此项前插入]**&#x200B;控件在无法选择该控件的可见视区上方渲染。 (TGT-55829)

+++

## [!DNL Target Standard/Premium] 26.9.3（2026年9月16日）

**[!UICONTROL 报表]**

+++查看详细信息

* **某些[!DNL A4T Auto-Target]报表中缺少[!UICONTROL 提升]和[!UICONTROL 置信度]值**。 对于使用&#x200B;**[!UICONTROL 最大访问转化率]**&#x200B;优化目标的[!DNL A4T Auto-Target]活动，默认的&#x200B;**[!UICONTROL 我的主要量度]**&#x200B;报告量度未正确解析，将&#x200B;**[!UICONTROL 提升度]**&#x200B;和&#x200B;**[!UICONTROL 置信度]**&#x200B;留空。 (TGT-56137)

+++

**[!UICONTROL 目标分析]**

+++查看详细信息

* 对于没有[!DNL Analytics]访问权限的实时活动，**[!UICONTROL 报告Source]字段现在为只读**。 以前，当实时活动的所有者无权访问[!DNL Adobe Analytics]时，**[!UICONTROL 报告Source]**&#x200B;字段及其相关字段保持可编辑状态。 (TGT-56089)

+++

## [!DNL Target Standard/Premium] 26.9.2（2026年9月8日）


**[!UICONTROL 推荐]**

+++查看详细信息

* **[!DNL New]用户界面对信息源URL的编码不正确**。 从新[!DNL Target]界面中的URL创建推荐信息源时，信息源URL编码不正确，导致信息源创建失败，出现未知错误。 (TGT-56084)

+++

**[!UICONTROL 报表]**

+++查看详细信息

* **自动化区段报表无法一致地显示属性值**。 自动化区段报表显示[!DNL Automated Personalization]和[!DNL Auto-Target]活动的属性值和范围不一致。 某些自动化区段仅显示属性名称，而不是关联的值或范围。 (TGT-55855)

+++

## [!DNL Target Standard/Premium] 26.9.1（2026年9月1日）

**[!UICONTROL 受众]**

+++查看详细信息

* **复制仅包含活动受众的活动无法保存**。 当A/B活动使用仅活动（本地范围）受众规则和自定义代码修改时，复制它并保存副本会失败并出现“受众ID无效”错误。 (TGT-55785)

+++

**[!DNL Adobe Target]MCP服务器 — 推荐工具（公共Beta）**

+++查看详细信息

[!DNL Adobe Target] MCP服务器现在公开推荐工具，允许您列出、检查、创建和更新标准、收藏集、设计、促销和排除项，并直接从AI助手搜索产品目录。

此功能需要具有&#x200B;**Target Premium**&#x200B;且启用了Recommendations的租户；此功能在非Premium帐户上不可用。

有关详细信息，请参阅[MCP服务器工具引用](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md)。

+++

## [!DNL Target Standard/Premium] 26.8.5（2026年8月18日）

**推荐**

+++查看详细信息

* 排除项和集合的&#x200B;**Null值筛选器。** 在[!DNL Recommendations]中定义排除规则和集合筛选器时，您现在可以使用&#x200B;**Value present**&#x200B;和&#x200B;**Value not present**&#x200B;运算符。 (TGT-55790)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **保存活动后，单击VEC编辑器中未显示的量度元素。** 修复了以下问题：当您在[!UICONTROL 可视化体验编辑器]中编辑活动的目标和量度时，即使继续在活动报表中正确跟踪量度，先前配置的点击量度仍不会显示。 (TGT-55826)

* **VEC中间歇性的“无修改”消息。** 修复了&#x200B;**[!UICONTROL 修改]**&#x200B;面板对活动体验定位活动中的现有修改间歇性显示“无修改”的问题。 (TGT-55842)

+++

## [!DNL Target Standard/Premium] 26.8.3（2026年8月13日）

**活动、选件和受众**

+++查看详细信息

* **为API/MCP创建的活动、选件和受众启用了“编辑”。** 通过[!DNL Adobe Target]管理员API和[!DNL Target] MCP创建的活动、选件和受众现在可以在[!DNL Target] UI中进行编辑。 在UI中编辑由API创建的活动后，该活动将被视为由UI修改的活动。 以前受限制的操作（包括[!UICONTROL 复制]和[!UICONTROL 删除]）变为可用，具体取决于您的权限和活动状态。 (TGT-55116)

+++

## [!DNL Target Standard/Premium] 26.8.2（2026年8月11日）

**受众**

+++查看详细信息

* **无法在使用仅限该活动的受众的活动中复制和保存自定义代码修改。** 修复了在添加自定义代码修改后，复制使用仅限该活动的受众的活动时无法保存并出现“无效受众ID”错误的问题。 (TGT-55785)

+++

**本地化**

+++查看详细信息

* **活动URL中的损坏的多字节字符。** 修复了活动URL中的多字节字符在[!UICONTROL 可视化体验编辑器]中和&#x200B;**[!UICONTROL 冲突]**&#x200B;选项卡上显示已损坏的问题。 (TGT-55708)

* **打开已删除的设计时出现未本地化的错误消息。** 修复了在尝试打开已被其他用户删除的设计时，找不到&#x200B;**[!UICONTROL 请求的资源]**&#x200B;错误消息未本地化的问题。 (TGT-50902)

+++

## [!DNL Target Standard/Premium] 26.8.1（2026年8月4日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **在[!UICONTROL 体验受众]面板中截断的图标。** 修复了在活动创建期间&#x200B;**[!UICONTROL 体验受众]**&#x200B;面板中隐藏或截断&#x200B;**[!UICONTROL 添加]**&#x200B;和展开/折叠图标的问题。 (TGT-55372)

+++

## [!DNL Target Standard/Premium] 26.7.5（2026年7月30日）

**活动**

+++查看详细信息

* **针对[!DNL A/B Test (Manual)]活动的贝叶斯统计信息** [!DNL A/B Test (Manual)]活动现在支持贝叶斯统计信息作为Welch的t测试的替代方法。 在[!UICONTROL 目标和设置]中选择统计方法：贝叶斯活动的报表显示基于概率的决策量度（如[!UICONTROL 成功控制的机会]）和可信区间而不是频率置信区间。

* **[!DNL Customer Journey Analytics]报告[!DNL Auto-Allocate]活动。** 除[!DNL Target]和[!DNL Adobe Analytics] (A4T)之外，[!DNL Auto-Allocate]活动现在还可以使用[!DNL Customer Journey Analytics]作为其报表源。

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **无法选择或修改活动中的HTML选件。** 修复了向活动添加某些HTML或体验片段选件会导致[!UICONTROL 可视化体验编辑器]崩溃，从而阻止选择或修改选件的问题。 (TGT-55732)

+++

## [!DNL Target Standard/Premium] 26.7.4（2026年7月23日）

**报表**

+++查看详细信息

* **转化率图表不适用于特定的移动受众。** 修复了[!UICONTROL 转化率]图形未针对某些移动设备受众呈现的问题。 (TGT-55611)

* 从下拉列表中选择&#x200B;**时，“已查看mbox”转化目标不起作用。** 修复了从[!UICONTROL 目标和设置]中下拉列表为“已查看mbox”转化目标选择mbox时无法正确保存mbox名称，从而无法记录转化的问题。 (TGT-55588)

+++

**受众**

+++查看详细信息

* 受众库页面上的&#x200B;**布局问题。** 修复了在侧面导航折叠时在[!UICONTROL 受众库]页面上启用过滤器时发生的布局问题。 (TGT-55502)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **移动设备版本未正确加载。** 修复了[!UICONTROL 可视化体验编辑器]未提供刷新方式，导致移动设备视图无法正确加载的问题。 (TGT-54408)

* **编辑或删除修改操作不起作用。** 修复了无法从[!UICONTROL 编辑体验]视图编辑或删除修改的问题。 (TGT-55250)

* **活动加载后，浏览模式无响应。** 修复了以下问题：[!UICONTROL 浏览]模式对包含修改的体验无响应，从而阻止进一步的导航和创作。 (TGT-55306)

* **无法选择Salesforce LWC （影子DOM）中的元素。** 修复了[!UICONTROL 可视化体验编辑器]无法选择使用影子DOM嵌套在Salesforce Lightning Web组件中的元素的问题，从而导致“未找到选择器”错误。 (TGT-54956)

* **在[!UICONTROL 可视化体验编辑器]中出现重复的选件。** 修复了在活动创作UI中修改和选件间歇性重复显示的问题。 (TGT-55685)

+++

**管理**

+++查看详细信息

* **已将内容生成助理重命名为[!UICONTROL 生成内容]。** 已将“AI助手”内容生成功能重命名为[!UICONTROL 跨[!DNL Target]用户界面表面]生成内容。 (TGT-55689)

+++

**推荐**

+++查看详细信息

* **使用配置文件属性的基于热门程度的推荐。** [!DNL Target]现在支持按访客个人资料属性（如国家/地区、首选语言或成员级别）动态地对热门程度推荐、“查看次数最多”和“最畅销商品”进行分组。 (TAPER-7614)

* **推荐集合在[!UICONTROL 集合]和活动配置之间不匹配。** 修复了与[!UICONTROL 推荐] > [!UICONTROL 收藏集]视图相比，从活动配置查看时，[!UICONTROL 推荐]收藏集返回了额外的不符合条件的实体的问题。 (TGT-55554)

+++

## [!DNL Target Standard/Premium] 26.7.2（2026年7月16日）

**活动**

+++查看详细信息

* **[!UICONTROL 活动概述]页面上的目标信息不正确。** 修复了[!DNL Automated Personalization]活动的[!UICONTROL 活动概述]页面显示其他目标而非优化目标的问题。 (TGT-55553)

* 在[!UICONTROL 浏览]模式下导航页面时，**屏幕无响应。** 修复了在[!UICONTROL 浏览]模式下的页面之间导航时，屏幕无响应的问题。 (TGT-55565)

+++

**主页**

+++查看详细信息

* [!UICONTROL 最佳执行者]和[!UICONTROL 保存]的&#x200B;**UI更改。** 更新了表现最好的UI并保存体验。 (TGT-54975)

+++

**受众**

+++查看详细信息

* **在[!UICONTROL 创建配置文件脚本]对话框中未本地化的字符串。** 修复了[!UICONTROL 创建配置文件脚本]对话框中的字符串未本地化的问题。 (TGT-51527)

+++

## [!DNL Target Standard/Premium] 26.7.1（2026年7月9日）

**活动**

+++查看详细信息

* **在[!UICONTROL 活动]、[!UICONTROL 受众]和[!UICONTROL 选件]页面中显示源不一致。** 修复了源在[!UICONTROL 活动]、[!UICONTROL 受众]和[!UICONTROL 选件]页面中显示不一致的问题。 (TGT-55247)

* 通过UI编辑时&#x200B;**活动源更改。** 修复了通过UI编辑活动会更改原始活动源的问题。 (TGT-55248)

+++

**受众**

+++查看详细信息

* **编辑受众时默认工作区不正确。** 修复了在编辑受众后默认工作区不正确的问题。 (TGT-55510)

+++

**报表**

+++查看详细信息

* 5月报告的&#x200B;**CSV下载失败。** 修复了下载5的CSV报表失败的问题。 (TGT-55524)

+++

## [!DNL Target Standard/Premium] 26.6.8（2026年6月24日）

**活动**

+++查看详细信息

* 针对API和MCP已创建资源的&#x200B;**Source筛选器。** 修复了按[!UICONTROL Adobe Target API]或[!UICONTROL Adobe Target MCP]进行筛选在活动、受众和优惠列表页面上不起作用的问题。 (TGT-55236)

* **活动源筛选器值。** 修复了[!UICONTROL Adobe Target API]或[!UICONTROL Adobe Target MCP]源筛选器未显示新API创建的受众的问题。 (TGT-55237)

+++

**本地化**

+++查看详细信息

* **[!UICONTROL 创建JSON选件]模式中的未本地化字符串。** 修复了在活动创建期间未本地化[!UICONTROL 创建JSON选件]模式中的字符串（包括[!UICONTROL Name]和[!UICONTROL Workspace]）的问题。 (TGT-50084)

* **在[!UICONTROL 推荐]活动中未本地化的Toast消息。** 修复了在基于表单的[!UICONTROL 推荐]活动中添加推荐时出现未本地化的toast消息的问题。 (TGT-50463)

* [!UICONTROL 收藏集]和[!UICONTROL 排除项]对话框中的&#x200B;**未本地化的字符串。** 修复了“项目有效负载”字符串在[!UICONTROL 推荐]中的[!UICONTROL 收藏集]和[!UICONTROL 排除项]对话框中未本地化的问题。 (TGT-51542)

* [!UICONTROL 受众]选项卡中的&#x200B;**未本地化的“审批者”字符串。** 修复了“[!UICONTROL 受众库]”页面上的[!UICONTROL Workspace]列中的“审批者”字符串未本地化的问题。 (TGT-51751)

+++

## [!DNL Target Standard/Premium] 26.6.5（2026年6月17日）

**活动**

+++查看详细信息

* **活动使用在源中删除的受众时出错。** 修复了以下问题：当活动使用一个或多个已从来源中删除的受众时，可能会显示错误。 (TGT-55272)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++查看详细信息

* **A4T报告不可见。** 修复了[!UICONTROL Analytics for Target] (A4T)报表不显示的问题。 (TGT-55432)

+++ 

## [!DNL Target Standard/Premium] 26.6.4（2026年6月16日）

**活动**

+++查看详细信息

* 在更新的[!DNL Target] UI中&#x200B;**[!UICONTROL 保存并关闭]。** 已在更新的[!DNL Target] UI中恢复&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;选项。 (TGT-55152)

* 更新的[!DNL Target] UI中的&#x200B;**QA URL。** 修复了QA URL在更新的[!DNL Target] UI中无法正常工作的问题。 ([TGT-55110](https://jira.corp.adobe.com/browse/TGT-55110))

+++

**本地化**

+++查看详细信息

* **活动概述图形报表中存在未本地化的百分比格式。** 修复了百分比格式在&#x200B;**[!UICONTROL 活动概述]**&#x200B;页面的&#x200B;**[!UICONTROL 报告]**&#x200B;选项卡上的&#x200B;**[!UICONTROL 图形视图]**&#x200B;的图表中未本地化的问题。 (TGT-50100)

* 活动URL中有&#x200B;**个日语字符。** 修复了在保存活动后，活动URL中的&#x200B;**[!UICONTROL 活动概述]**&#x200B;页面和活动列表中的日语字符出现损坏的问题。 (TGT-53459)

* 默认活动名称中有&#x200B;**未本地化的时间戳。** 修复了在活动创建期间保留默认活动名称时，活动标题中时间戳未本地化的问题。 (TGT-53273)

+++

**[!UICONTROL 推荐]**

+++查看详细信息

* 创建馈送后URL中的&#x200B;**多字节字符。** 修复了在创建馈送后URL中的多字节字符似乎已损坏的问题。 (TGT-54793)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## [!DNL Target Standard/Premium] 26.6.3（2026年6月11日）

**本地化**

+++查看详细信息

* 在活动创建期间，**受众日历模式中一周的第一天未本地化。** 修复了在活动创建期间的&#x200B;**[!UICONTROL 创建]**、**[!UICONTROL 编辑]**&#x200B;和&#x200B;**[!UICONTROL 重复的受众]**&#x200B;模式中，星期的第一天未在日历中进行本地化的问题。 (TGT-50510)

* **活动概述报表中存在未本地化的百分比格式。** 修复了百分比格式在&#x200B;**[!UICONTROL 活动概述]**&#x200B;页面的&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡上的表中未本地化的问题。 (TGT-50094)

* **[!UICONTROL 创建标准]对话框中的数字格式未本地化。** 修复了在&#x200B;**[!UICONTROL 推荐]**&#x200B;的&#x200B;**[!UICONTROL 创建标准]**&#x200B;对话框中，数字格式未本地化的问题。 (TGT-52250)

+++

## [!DNL Target Standard/Premium] 26.6.1（2026年6月4日）

**活动**

+++查看详细信息

* [!UICONTROL 活动概述].**上的**&#x200B;不完整的活动URL 修复了[!UICONTROL 活动概述]未显示活动的完整URL的问题。 (TGT-54029)

* **活动报表中存在未本地化的日期格式。** 修复了从&#x200B;**[!UICONTROL 预设日期范围]**&#x200B;下拉列表中选择&#x200B;**最近X天**&#x200B;选项时，**[!UICONTROL 报表]**&#x200B;选项卡上未本地化日期格式的问题。 (TGT-51637)

* **无法在[!UICONTROL 位置].**&#x200B;保存具有某些GB18030字符的基于表单的活动 修复了当&#x200B;**[!UICONTROL 位置]**&#x200B;字段包含特定GB18030字符时无法保存基于表单的活动的问题。 (TGT-46980)

+++

**[!UICONTROL 受众]**

+++查看详细信息

* 创建简体中文和繁体中文受众流中的&#x200B;**未本地化的日历。** 修复了在创建受众流期间，**[!UICONTROL 时间范围]**&#x200B;属性的&#x200B;**[!UICONTROL 开始]**&#x200B;和&#x200B;**[!UICONTROL 结束]**&#x200B;字段中的日历未以简体中文(CHS)和繁体中文(CHT)区域设置进行本地化的问题。 (TGT-50619)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 更新后的活动生成器中的&#x200B;**未本地化的工具提示。** 修复了在更新的[!UICONTROL 可视化体验编辑器]活动生成器中&#x200B;**[!UICONTROL 细化]**&#x200B;和&#x200B;**[!UICONTROL 内容]**&#x200B;信息工具提示未本地化的本地化问题。 (TGT-53721)

* [!UICONTROL 体验受众].**中的**&#x200B;未本地化的[!UICONTROL 所有访客] 修复了左边栏中&#x200B;**[!UICONTROL 体验受众]**&#x200B;的&#x200B;**[!UICONTROL 所有访客]**&#x200B;字符串未在[!UICONTROL 可视化体验编辑器]中本地化的问题。 (TGT-50086)

+++

**[!UICONTROL 报表]**

+++查看详细信息

* [!UICONTROL 创建预设]窗口中的&#x200B;**未本地化的日期格式。** 修复了&#x200B;**[!UICONTROL 创建预设]**&#x200B;窗口的&#x200B;**[!UICONTROL 日期范围]**&#x200B;字段中的日期格式未本地化的问题。 (TGT-49239)

+++

**本地化**

+++查看详细信息

* 在多个区域显示&#x200B;**GB18030字符。** 修复了某些专用使用区域字符在&#x200B;**[!UICONTROL 受众]** UI、**[!UICONTROL 管理]** > **[!UICONTROL 属性]**、移动视区配置和Toast通知中错误显示为字母的问题。 （TGT-49622、TGT-49623、TGT-49624和TGT-49625）

+++

## [!DNL Target Standard/Premium] 26.5.2（2026年5月14日）

**管理**

+++查看详细信息

* **允许的URL的Regex验证。** 修复了在&#x200B;**[!UICONTROL 允许的URL]**&#x200B;字段中输入无效正则表达式而不进行正确验证的问题。 (TGT-55095)

+++

**受众**

+++查看详细信息

* [!UICONTROL 编辑受众]对话框中的&#x200B;**按钮。** 修复了&#x200B;**[!UICONTROL 编辑受众]**&#x200B;对话框中的按钮不再正确呈现的问题。 (TGT-54638)

+++

**[!DNL Adobe Target]MCP服务器（公共Beta）**

+++查看详细信息

[!DNL Adobe Target]现在提供了一个MCP（模型上下文协议）服务器，该服务器直接在任何与MCP兼容的应用程序中呈现实验、个性化和报告操作。 利用此集成，营销和技术人员可以检查A/B测试、分析性能报表以及浏览受众和选件 — 所有这些操作都使用自然语言提示，而不是导航多个UI屏幕或针对[!DNL Adobe Target] REST API编写查询。 此功能当前在&#x200B;**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**&#x200B;和&#x200B;**ChatGPT**&#x200B;中可用。

此功能适用于公共Beta中的所有客户。

有关详细信息，请参阅[[!DNL Adobe Target] MCP服务器](../c-integrating-target-with-mac/mcp/target-mcp.md)。

+++

## [!DNL Target Standard/Premium] 26.5.3（2026年5月21日）

**[!UICONTROL 新增功能]页面**

+++查看详细信息

* **新[!UICONTROL 新增功能]页面。** 在[!DNL Adobe Target] UI中添加了一个新的&#x200B;**[!UICONTROL 新增功能]**&#x200B;页面，可帮助您在不离开产品的情况下发现最新功能、增强功能和更新。 (TGT-55137)

+++

**活动**

+++查看详细信息

* **在[!UICONTROL Automated Personalization]活动中编辑定位时选择了错误的体验。** 修复了在[!UICONTROL Automated Personalization] (AP)活动中编辑&#x200B;**[!UICONTROL 定位]**&#x200B;步骤时可能选择错误体验的问题。 (TGT-55176)

* **关闭计划活动时的较早日期。** 修复了导致无法选择较早日期关闭计划活动的问题。 (TGT-55163)

+++

<!--
* **Blank page or CORS errors with Enhanced Experience Composer.** Fixed an issue where the [!UICONTROL Visual Experience Composer] could fail to load when Enhanced Experience Composer (EEC) was enabled. (TGT-54576)

**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## [!DNL Target Standard/Premium] 26.5.1（2026年5月7日）

**活动**

+++查看详细信息

* **[!UICONTROL 图形视图]与表和下载不同步。** 修复了以下问题：即使&#x200B;**[!UICONTROL 表视图]**&#x200B;和下载的报表仍显示正确的值，活动报表仍会在某些日期范围的&#x200B;**[!UICONTROL 图形视图]**&#x200B;中显示缺失或零量度。 (TGT-54998)

+++

**[!UICONTROL 受众]**

+++查看详细信息

* **受众使用情况列表未完全呈现。** 修复了受众详细信息中的&#x200B;**[!UICONTROL 使用情况]**&#x200B;部分只能显示映射活动的子集的问题，即使其他活动与该受众关联也是如此。 (TGT-55094)

+++

**[!UICONTROL 管理]**

+++查看详细信息

* **对最后一个八位字节IP模糊化的确认更清晰。** 当您在&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 实现]**&#x200B;上将&#x200B;**[!UICONTROL 模糊处理访客IP地址]**&#x200B;更改为&#x200B;**[!UICONTROL 最后一个八位字节]**&#x200B;时，确认对话框现在会说明[!DNL Target]隐藏访客IP地址的最后一个八位字节。 (TGT-44821)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 使用增强型体验编辑器(EEC) **空白或不完整的页面。** 修复了在启用&#x200B;**[!UICONTROL 增强型体验编辑器]**&#x200B;时，[!UICONTROL 可视化体验编辑器]无法在编辑器中加载网站的问题。 (TGT-54576)

+++

## [!DNL Target Standard/Premium] 26.4.4（2026年4月28日）

**活动**

+++查看详细信息

* **报表中的受众筛选器出错。** 修复了更改&#x200B;**[!UICONTROL 目标和设置]**&#x200B;中的受众筛选器导致[!DNL Target]用户界面的“报表”部分出现错误的问题。 (TGT-55006)

* **按优先级排序活动。** 使用&#x200B;**[!UICONTROL 优先级]**&#x200B;列标题在活动列表中添加了按优先级排序，其升序和降序与其他可排序列一致。 (TGT-54948)

* **其他活动属性在保存后未保留。** 修复了保存并重新打开活动后，某些&#x200B;**[!UICONTROL 属性]**&#x200B;选择未保留的问题。 (TGT-53889)

+++

**本地化**

+++查看详细信息

* [!UICONTROL 页面交付]规则运算符的&#x200B;**日语标签。** 修复了日语UI中页面投放规则运算符标签无法读取或损坏的字符串。 (TGT-53097)

+++

**API**

+++查看详细信息

* **报告`segmentId`的[!DNL GraphQL] API支持。** 已将`segmentId`添加到报表[!DNL GraphQL] API。 (TGT-55021)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **在编辑器的错误体验上显示的修改。** 修复了在[!UICONTROL 可视化体验编辑器]中的体验之间切换后，删除或其他修改可能显示在错误体验上的问题。 (TGT-54955)

* **删除插入HTML时删除的修改。** 修复了以下问题：删除添加了&#x200B;**[!UICONTROL 此项前插入]**&#x200B;或&#x200B;**[!UICONTROL 此项后插入]**&#x200B;的额外&#x200B;**[!UICONTROL HTML]**&#x200B;块时，还删除了一个无CSS选择器的链接修改。 (TGT-54530)

+++

## [!DNL Target Standard/Premium] 26.4.3（2026年4月9日）

**活动**

+++查看详细信息

* **某些活动中缺少位置。** 修复了某些活动中缺少&#x200B;**[!UICONTROL 位置]**&#x200B;的问题。 (TGT-54951)

* **报告量度列顺序。** 更新的[!DNL Target]界面允许对报表量度重新排序，而无需清除完整的选择并按顺序重新添加量度。 以前，要求用户取消选择所有量度并按所需顺序再次选择它们，这在启用许多量度以及调整列放置以限制水平滚动时会很耗时。 (TGT-53044)

+++

<!--
**[!UICONTROL Visual Experience Composer] (VEC)**

+++See details

* **Click tracking for Experience B.** Fixed an issue where click tracking was not saved for **[!UICONTROL Experience B]** in the [!UICONTROL Visual Experience Composer]. (TGT-54843)

+++
-->

## [!DNL Target Standard/Premium] 26.4.2（2026年4月7日）

**活动**

+++查看详细信息

* **应用于其他视图时保留的自定义代码。** 修复了在同一&#x200B;**[!UICONTROL 活动]**&#x200B;中为另一个&#x200B;**[!UICONTROL 视图]**&#x200B;添加或保存自定义代码时，可能会删除应用于一个&#x200B;**[!UICONTROL 视图]**&#x200B;的自定义代码的问题。 (TGT-53933)
+++

## [!DNL Target Standard/Premium] 26.4.1（2026年4月2日）

**活动**

+++查看详细信息

* **在“活动”视图中可见的受众属性。** 修复了从&#x200B;**[!UICONTROL 活动]**&#x200B;查看的受众规则详细信息时，未显示从&#x200B;**[!UICONTROL 受众]**&#x200B;部分打开同一受众时显示的特定属性的问题。 (TGT-54742)

* **导出“活动”列表页面上的CSV。** 添加了&#x200B;**[!UICONTROL 导出CSV]**&#x200B;操作，以便您可以从用户界面导出活动列表，包括在应用过滤器时，而无需仅依赖API进行例行导出。 (TGT-51466)

* **未找到选择器时标记的Experience修改。** 体验修改现在运行选择器存在性检查；在页面上未找到选择器时，修改将被标记为无效。 (TGT-54815)

* **[!UICONTROL 自动个性化]活动。** 修复了阻止用户可靠地创建、编辑或管理自动个性化活动的界面和活动加载问题，这些问题会阻止活动设置并延迟个性化用例。 (TGT-54421)

+++

**受众**

+++查看详细信息

* **从活动创建受众时显示的受众名称和描述。** 修复了在从活动流创建或编辑受众时，受众&#x200B;**[!UICONTROL 名称]**&#x200B;和&#x200B;**[!UICONTROL 描述]**&#x200B;字段与直接在&#x200B;**[!UICONTROL 受众]**&#x200B;下创建受众相比，无法清晰脱颖而出的问题。 (TGT-54837)

+++

**分析**

+++查看详细信息

* **[!UICONTROL 实时活动]计入分析。** 修复了分析功能板上的&#x200B;**[!UICONTROL 实时活动]**&#x200B;量度报告的总数可能高于&#x200B;**[!UICONTROL 所有活动]**&#x200B;中显示为实时的活动数的问题。 (TGT-54788)

+++

**推荐**

+++查看详细信息

* [!UICONTROL 全局排除].**中的**&#x200B;长ID列表 修复了以下问题：与旧版相比，**[!UICONTROL 全局排除项]**&#x200B;中粘贴或输入较长ID列表的ID在更新后的界面中可能会被截断，从而导致排除列表不完整。 (TGT-54422)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* [!UICONTROL 可视化体验编辑器]中的&#x200B;**增强型体验编辑器(EEC)状态指示器。** EEC指示器指示是否启用增强型体验编辑器。 其演示文稿已修订，不再类似于交互式切换，因为它仅用作非交互式状态显示。 (TGT-54828)

* **可视体验编辑器[!UICONTROL 中的可折叠左边栏]。** 现在，当活动处于打开状态以进行编辑时，可以折叠左边栏。 这改进了对于包含多个受众和页面的活动（包括在较小的显示器上）的&#x200B;**[!UICONTROL 组件]**&#x200B;和&#x200B;**[!UICONTROL 属性]**&#x200B;的访问权限。 (TGT-54269)

+++

## [!DNL Target Standard/Premium] 26.3.7（2026年3月26日）

**受众**

+++查看详细信息

* **受众界面中的受众源标签准确性。** 修复了以下问题：在Adobe Experience Platform中，来自Adobe Target v2目标的受众可能会显示为将&#x200B;**Adobe Experience Cloud**&#x200B;作为源，而不是&#x200B;**Adobe Experience Platform**。 此更新改进了筛选和查看受众时的源标签一致性。 (TGT-54802)

+++

## [!DNL Target Standard/Premium] 26.3.6（2026年3月23日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **在新的可视化体验编辑器UI中进行身份验证后出现间歇性灰色屏幕。** 修复了以下问题：用户登录新的可视化体验编辑器后，可能会间歇性地看到灰色屏幕，导致无法进一步编辑。 此更新提高了身份验证后加载的可靠性。 (TGT-54626)

+++

## [!DNL Target Standard/Premium] 26.3.4（2026年3月19日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **可视化体验编辑器Web编辑器中可见的设计/浏览模式选择。** 此修复程序解决了在“设计”、“浏览”和“预览”模式之间切换可正常工作，但界面中未明确指示活动模式的问题。 所选模式现在会突出显示，以便您查看所处的模式。 (TGT-54790)

* 可视化体验编辑器(Chrome)中的&#x200B;**专用网络URL。** 除非允许本地网络访问，否则Chrome可能会阻止专用网络上的页面。 **[!UICONTROL 可视化体验编辑器]**&#x200B;现在会请求在框架Experience Cloud中使用的权限，这样Chrome可以显示允许提示而不是静默失败。 在允许访问后，如果您的环境支持VEC，则可以在VEC中加载内部URL。 (TGT-54346)

+++

## [!DNL Target Standard/Premium] 26.3.2（2026年3月10日）

**活动**

+++查看详细信息

* **体验中的直接优惠更改未保存。** 此修复了无法保存对活动体验中的直接优惠所做的修改的问题。 以前，当用户打开直接选件、做出更改并保存它时，更改似乎在开始时反映出来，但在重新打开选件时丢失。 此修复程序可确保正确保存对直接选件所做的更改，并在重新打开选件时保留这些更改。 (TGT-54653)

+++

**实施**

+++查看详细信息

* **在实施屏幕上添加闪烁管理切换。** 已向[!UICONTROL 实现]屏幕添加新的切换开关以控制启用闪烁管理设置。 此切换允许管理员直接从“实施”屏幕配置闪烁管理。 (TGT-52247)

+++

**概述**

+++查看详细信息

* **在概述页面中显示受众和体验的全名。** 此增强功能会更新[!UICONTROL 概述]页面以显示受众和体验的全名。 以前，长名称会被截断并且无法完全显示，因此需要用户通过三次单击来选择所有文本，以查看完整名称。 此更新可确保完整受众和体验名称可见，从而使用户更容易识别和审查活动配置。 (TGT-53323)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **VEC更改未反映在使用Shadow DOM （Salesforce Lightning Web组件）的网站上。** 此修复程序解决了在使用Lightning Web Components (LWC)的基于Salesforce的站点的实时站点上未保存或反映在Adobe Target中所做的更改（例如CTA颜色更改）的问题。 CMS不接受来自Target活动的更新，此问题在A/B测试和其他活动类型中始终出现。 (TGT-54059)

+++

### [!DNL Target Standard/Premium] 26.3.1（2026年3月3日）

**活动**

+++查看详细信息

* **自定义代码在应用于其他视图时丢失。** 此修复了将自定义代码添加到其他视图并将这些代码应用于其他视图时，应用于一个视图的自定义代码丢失的问题。 以前，当用户将自定义代码应用于活动中的多个视图时，以前应用的自定义代码将会消失。 此修复方法可确保在将修改应用于其他视图时，在所有视图间正确保留自定义代码。 (TGT-54230)

+++

**标准**

+++查看详细信息

* **配置文件参数“介于”规则未保存在条件中。** 此修复解决了对配置文件参数使用&#x200B;**In Between**&#x200B;运算符的标准规则无法正确保存的问题。 以前，当用户使用&#x200B;**介于**&#x200B;之间运算符配置规则并输入范围值时，条件似乎已成功保存，但在重新打开或编辑条件时，规则将消失。 此修复确保正确保存&#x200B;**In Between**&#x200B;规则，并在重新打开标准时保留这些规则。 (TGT-54498)

+++

**分析**

+++查看详细信息

* **在所有活动后更改分析页面位置。** **分析页面**&#x200B;位置已更新为显示在导航中的&#x200B;**所有活动**&#x200B;页面之后。 “所有活动”页面现在是Target应用程序的默认页面。 (TGT-54672)

+++

**导航**

+++查看详细信息

* **使左侧导航可折叠。** 现在，所有选项卡的左侧导航均可折叠和展开。 折叠时，将显示带有工具提示的图标。 展开时，将显示图标和文本。 此增强功能可在用户需要时为其提供更多屏幕空间，同时保持对导航选项的快速访问。 (TGT-54608)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* 当后端返回null时，**将experienceEditorType默认为“visual”。** 此修复程序解决了在某些情况下将`experienceEditorType`值返回为null的问题，该问题会导致编辑器类型未正确初始化的UI中出现意外行为。 (TGT-54690)

+++

### [!DNL Target Standard/Premium] 26.2.2（2026年2月16日）

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **无法将图像添加到活动 — 未知错误。** 此修复程序解决了用户在尝试在活动中添加或替换图像时遇到“未知错误”的问题。 该问题与Scene7 URL同步和身份验证失败有关。 此修复确保可以在可视化体验编辑器中正确添加和替换图像。 (TGT-54137)

+++

### [!DNL Target Standard/Premium] 26.2.1（2026年2月8日）

**属性**

+++查看详细信息

* 删除后未自动重新添加&#x200B;**属性令牌。** 此修复了在编辑活动时，会自动重新添加用户已取消选择的属性令牌的问题。 以前，当用户删除自动检测到的属性并在步骤之间导航时，系统将重新引入已删除的属性，而不会出现任何警报或提示，从而导致在意外的属性上启用活动。 此更新可确保删除资产令牌后，该令牌将在所有后续编辑和导航期间保持被删除状态。 (TGT-54040)

+++

### [!DNL Target Standard/Premium] 26.1.2（2026年1月30日）

**Adobe Target Insights仪表板**

+++查看详细信息

Adobe Target现在包含一个新的见解仪表板，可让您从较高的层次了解您的组织如何使用Target进行试验性和个性化。 仪表板会显示关键量度，例如实时活动、实时活动和已修改的活动、已完成的活动、已发布的活动和A/B测试活动。 使用时间范围选择器浏览不同时段的趋势，包括2025年的回顾视图。 该信息板仍会持续提供以跟踪一段时间内的采用情况和活动。

查看[Adobe Target Insights仪表板](/help/main/c-activities/insights-dashboard.md)
+++

**管理**

+++查看详细信息

* **已列入允许列表的URL管理功能。** 已向[!UICONTROL 管理]部分添加新的“列入允许列表的URL”管理功能，以管理允许的远程选件URL模式。 此功能包括在表中显示列入允许列表的URL、搜索和过滤URL、通过模式对话框添加新URL以及在确认后删除URL的功能。 该功能可帮助客户控制哪些URL可用于远程选件，从而提高安全性和合规性。 (TGT-54486)

+++

**分析**

+++查看详细信息

* **在GraphQL中支持按createdAt和modifiedAt进行筛选。** GraphQL API中添加了对按`createdAt`和`modifiedAt`日期字段筛选活动的支持。 此增强功能可以在Target UI中进行准确筛选，减少客户端数据处理，并且无需多个API调用即可检索筛选后的活动数据。 (TGT-54499)

+++


### [!DNL Target Standard/Premium] 26.1.1（2026年1月18日）

**活动**

+++查看详细信息

* **无法复制活动 — 用户输入无效。** 已修复在复制活动时导致用户看到无帮助的“用户输入无效”错误的问题。 以前，在复制活动时，不会保留其特定于工作区的属性分配，从而导致后端拒绝保存请求，因为ABActivity至少需要一个属于非默认工作区的属性。 这种不匹配在UI中触发了常规错误，使用户没有指南。 此修复程序可确保在复制操作期间正确地保留工作区分配，使用户能够保存复制的活动而不进行修改，并防止出现误导性的验证错误。 (TGT-54282)
* **为Web编辑器选件启用工作区列。** 此更新解决了Web编辑器中的其他工作区中出现[!UICONTROL 默认Workspace]的选件所造成的客户混淆。 虽然此行为按预期工作，但[!UICONTROL 默认Workspace]选件有意在所有工作区中均可见，但客户报告UI未明确工作区来源，尤其是在非默认工作区（如“审批者”）中创建活动时更是如此。 为了提高清晰度，Web编辑器的选件列表中现已启用[!UICONTROL Workspace]列，这使用户能够轻松区分每个选件属于哪个工作区，并防止误解显示的其他选件。 (TGT-54138)
* 在新选项卡中打开具有target=&quot;_blank&quot;的&#x200B;**链接。** 此修复了包含具有~target=&quot;_blank&quot;~的链接的已创作网站在单击[!UICONTROL 浏览]模式时将在新的浏览器选项卡中打开，中断编辑器内预览体验的问题。 出现此行为是因为创作页面的本机链接属性未被扩展插入的JavaScript截获，这与旧版UI不同，在旧版UI中，锚点元素会进行转换并覆盖其目标以保留在编辑器中导航。 此更新现在确保在Web编辑器中正确处理使用~target=&quot;_blank&quot;~的链接，以便在创作过程中不再打开外部选项卡。 (TGT-54134)
* **取消选择属性警告。** 此更新引入了可视警告，当用户在活动编辑器中取消选择自动检测到的属性时，该警告会明确通知用户。 以前，删除自动检测到的属性不会指示该属性将被永久删除，这可能会导致意外丢失定位配置。 此修复程序会添加一个警告图标（与旧版UI中的行为一致），以通知用户取消选择资产会将其从活动中移除。 (TGT-54121)
* **[!UICONTROL 工作区]下拉列表在[!UICONTROL 用户]部分中限制为20个。** 此修复程序解决了以下问题：[!UICONTROL 管理] > [!UICONTROL 用户]部分中的[!UICONTROL 工作区]下拉菜单仅显示20个工作区，即使用户有权访问更多工作区也是如此。 `licenseGroups`的基础GraphQL调用也被限制为20个结果，这会导致UI显示不完整的列表，尽管用户有权访问组织中的更多工作区。 更新会移除此硬限制，以便现在可以正确返回并显示整组可用工作区。 (TGT-53820)
* **修复了选件模式未显示工作区列的问题。** 修复了选件模式在更新的UI中不显示Workspace列的问题。 这会给客户带来困惑，因为[!UICONTROL 默认Workspace]的选件与选定工作区中的选件一起显示，但未指明它们的来源。 工作区列现在已启用，以便客户可以清楚地识别每个选件属于哪个工作区。 (TGT-52320)

+++

**属性**

+++查看详细信息

* **如果已删除，Activity Edit则不应添加自动检测到的属性。** 此修复了以下问题：编辑活动会自动重新引入用户之前删除的自动检测属性。 重新打开活动进行编辑时，系统错误地还原了已删除的属性，导致[!UICONTROL 属性列表]中的行为不一致和混淆。 此更新可确保在删除自动检测到的属性后，该属性会在所有后续编辑期间保持被删除状态，并且除非用户明确将其添加回来，否则该属性不会重新出现。 (TGT-54182)
* **如果已删除，则不添加自动检测到的属性。** 此修复可确保，一旦用户手动从活动中移除自动检测到的属性，系统在活动编辑器中的后续导航期间将不再重新引入该属性。 以前，如果用户取消选择自动检测的属性，移至[!UICONTROL 定位]步骤，然后返回到[!UICONTROL 体验]，则编辑器将根据活动编辑器状态切片中存储的自动检测列表重新填充移除的属性。 更新后的逻辑现在将自动检测到的属性与~ActivityState~切片中的当前属性进行比较，并阻止重新添加用户已删除的任何自动检测到的属性。 这会导致各步骤之间出现一致的行为并尊重用户意图。 (TGT-54181)
* **将自动检测到的文本添加到属性列表。** 此增强功能会更新[!UICONTROL 属性列表]，以明确标记系统自动检测的任何属性。 当自动检测到的属性也出现在用户可见的[!UICONTROL 属性列表]中时，它现在会使用存储在~ActivityEditorSlice~状态中的值，在其名称旁边显示“（自动检测）”文本。 这反映了旧版UI的行为，并帮助用户轻松区分手动选择的属性和自动识别的属性。 (TGT-54120)
* **将自动检测到的[!UICONTROL 属性]添加到状态。** 此更新确保~ActivityEditorSlice.ExperienceEditor~状态一致地维护所有自动检测到的属性ID的最新列表，这些属性ID从Web编辑器传递到“活动[!UICONTROL 体验]”选项卡中。 每次用户导航到[!UICONTROL 体验]选项卡时，都会使用任何新检测到的属性刷新状态，同时会防止出现重复项，从而确保准确跟踪和可靠的下游行为。 (TGT-54119)

+++

**推荐**

+++查看详细信息

* **[!UICONTROL 环境]下拉列表仅显示100个结果。** 此修复解决了具有超过100个环境的客户在[!UICONTROL 推荐]中的[!UICONTROL 环境]下拉列表中只能看到前100个条目的限制。 基础GraphQL查询(~getEnvironmentsV2~)采用硬编码页面大小100分页，导致UI仅显示部分列表，即使有其他页面可用。 对于拥有超过100个环境的客户，此问题会导致缺少选项和不完整的选择体验。 更新将提高限制，以便返回并显示所有环境，从而确保完全可见，无论环境计数是多少。 (TGT-53903)

+++

**报表**

+++查看详细信息

* **修复了[!UICONTROL 报告]箭头未明确指示可展开列的问题。** 修复了报表表格未明确显示其他列可以在更新后的UI中展开的问题。 在列标题附近的[!UICONTROL 报表]箭头中添加了消失的工具提示，以帮助客户了解更多列可用。 (TGT-53479)

+++

**查看次数**

+++查看详细信息

* **无法删除应用于视图的修改。** 此修复解决了用户无法删除活动中的修改的问题，除非修改已首先重新应用于其他视图。 在编辑活动（例如，活动ID 302467）时，尝试删除任何修改不会产生任何效果，从而阻止用户删除不需要的更改。 但是，使用“应用于更多视图”重新应用修改并分配给`Page Load`事件后，删除操作会突然按预期运行。 (TGT-54088)

+++

**[!UICONTROL 可视化体验编辑器] (VEC)**

+++查看详细信息

* **[!UICONTROL 体验片段]名称在新VEC UI**&#x200B;中被截断(TGT-54312)
* **无法对[!UICONTROL 收入]指标使用[!UICONTROL 高级设置]。** 此修复了用户在[!UICONTROL 目标和设置]中为[!UICONTROL 收入]量度配置[!UICONTROL 高级设置]时遇到403“访问被拒绝”错误的问题。 添加与主目标关联的依赖项条件时，出现问题；后端错误地要求编辑者权限，即使用户已有足够的权限创建和编辑活动。 因此，尽管配置有效，但保存活动失败。 更新更正了权限检查，以便具有适当访问权限的用户可以成功添加收入量度依赖关系，而不会触发禁止的资源错误。 (TGT-54092)
* **修复了“添加”按钮未应用于选定图像的问题。** 修复了一个问题，该问题阻止客户在活动创建流程中选择或更新图像时添加某些图像。 例如，当客户搜索特定资产时，在搜索“ipp”时返回的图像，单击[!UICONTROL 添加]按钮未应用所选图像，并且未创建任何修改。 选择其他图像（如`Homepage-banner-1-moz.jpg`）可继续按预期工作。 此更新确保所有有效图像都可以在更新后的UI中一致应用。 (TGT-53610)
* **修复了删除URL条件会重置目标量度配置的问题。** 修复了删除[!UICONTROL 目标]量度中的单个URL条件导致整个配置在更新的UI中重置的问题。 当客户尝试删除[!UICONTROL 转化] > [!UICONTROL 查看了页面]下保存的URL条件时，目标类型意外切换为[!UICONTROL 查看了Mbox]，并且已删除所有之前配置的设置。 此更新确保仅删除选定的URL条件，并且所有剩余的目标设置保持不变。 (TGT-53271)
* **修复了搜索未查看子文件夹的问题。** 修复了在搜索选件时未从更新后的UI中的子文件夹返回结果的问题。 客户只有在手动导航到存储选件的文件夹时，才能找到该选件，这使得搜索行为与API功能不一致。 搜索功能现在支持递归查看文件夹，因此客户可以找到选件，而无需单独打开每个文件夹。 (TGT-51954)

+++
