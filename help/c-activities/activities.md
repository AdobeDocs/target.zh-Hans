---
keywords: activities list;activities;activity;activity types;edit activity;activity actions;activity attribute;activity list filter;activity limitations;personalize;personalization
description: Adobe Target中的活动可让您向特定受众个性化内容并测试页面设计
title: Adobe Target中的活动可让您向特定受众个性化内容并测试页面设计。
topic: Standard
uuid: 89dca5b4-c23d-4dfa-8f13-f1b05c7ab22c
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# 活动{#activities}

Adobe Target中的活动可让您向特定受众个性化内容并测试页面设计。

例如，您可能会设计一个活动以对两个不同的登陆页面进行测试，其中一个页面着重显示夏季女鞋的相关信息，而另一个登陆页面则重点展示更广泛的夏季服饰信息。此活动确定了用于控制这两个登陆页面分别何时显示的条件，以及用于决定哪个页面更为成功的量度。此活动配置为在满足特定条件时开始和结束，例如在具体日期开始和结束，或者在活动得到批准后开始并在活动停用后结束。

设计活动时，您应该仔细规划。首先要确定活动的开始时间及其持续时长。然后，列出您的选件并为每个选件分配一组目标顾客。

## 活动类型

Target 包括多种活动类型。下表提供了每种活动类型的概述，其中包含可帮助您了解更多信息的链接。为了帮助您更好地选择符合要求的最佳活动类型，我们还创建了 [Adobe Target 活动指南](/help/c-activities/target-activities-guide.md)。

| 活动类型 | 描述 |
|--- |--- |
| [A/B 测试](/help/c-activities/t-test-ab/test-ab.md) | A/B 测试可比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最能提高转化。<br>**注意：**现在，您可以[在 A/B 测试活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | 自动分配可在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选者重新分配更多流量以提高转化。<br>**注意：**现在，您可以[在自动分配活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动定位](/help/c-activities/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | 自动定位可使用先进的机器学习技术从营销人员定义的多个高性能体验中进行识别，并根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验，以便个性化内容并促进转化。<br>**注意：**现在，您可以[在自动定位活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [使用 Analytics 数据](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | 您可以将活动配置为使用 [!DNL Adobe Analytics] 作为报表源。此活动类型要求您将 [!DNL Adobe Experience Cloud] 帐户与 [!DNL Analytics] 和 [!DNL Target] 均关联。 |
| [多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | 多变量测试 (MVT) 可通过比较页面上各元素中的选件组合，来确定哪个组合对特定受众的效果最佳，以及哪个元素对活动成功的影响最大。 |
| [体验定位](/help/c-activities/t-experience-target/experience-target.md) | 体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。<br>**注意：**现在，您可以[在体验定位活动中包含推荐](/help/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有[Target Premium 许可证](/help/c-intro/intro.md#premium)。 |
| [自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | 自动个性化 (AP) 可将各种选件或消息进行组合，并且使用先进的机器学习技术，根据每位访客的个人客户配置文件将不同的变体与其匹配，以便个性化内容并促进转化。 |
| [推荐](/help/c-recommendations/recommendations.md)<br>![Target Premium](/help/assets/premium.png) | 推荐可根据网站用户在网站上的活动来确定向该用户推广产品的方式。<br>例如，您可能想要鼓励购买了背包的人也考虑购买登山鞋和登山杖。在这种情况下，您可以使用“购买了这个项目，也购买了那个项目的人”算法，创建一个推荐来显示通常一起购买的项目。或者，您可能想要鼓励访客在您的媒体网站上停留更长的时间，为此，您可以使用“查看了这个项目，也查看了那个项目的人”算法，向访客推荐与其正在观看的视频相似的视频。<br>**注意：**现在，您可以在 A/B 测试（包括自动分配和自动定位）和体验定位 (XT) 活动中包含推荐。请参阅[“推荐”作为选件](/help/c-recommendations/recommendations-as-an-offer.md)。 |

## Activities list（活动列表） {#section_DE8E2DB30D534962A931EF8BB48240F5}

打开 [!DNL Target] 时，[!UICONTROL 活动]列表是默认的视图。您可以从此页面创建新的活动并管理现有活动。

您还可以通过单击 [!DNL Target] UI 顶部的[!UICONTROL 活动]选项卡来显示[!UICONTROL 活动]列表。

![Activities list（活动列表）](/help/c-activities/assets/activities-list.png)

“活动”列表提供了所有活动的概览：

| 元素 | 描述 |
|--- |--- |
| 类型 | 活动类型，例如 A/B 或 MVT。 |
| 名称 | 活动的名称。 |
| URL | URL 以浅色文本显示在名称下方。<br>活动的 URL 可标识该活动在哪里显示。这可以帮助您快速识别活动，并确定某个特定页面是否已在该活动上运行测试。<br>如果测试在多个 URL 上运行，则会有一个链接显示使用的 URL 数量。单击该链接可查看该活动的完整 URL 列表。<br>您可以根据 URL 进行搜索。使用“搜索”框旁边的下拉列表，然后选择[!UICONTROL 搜索 URL]。 |
| 状态 | 活动的状态可以是下列状态之一：<ul><li>**实时**：该活动当前正在运行。</li><li>**草稿**：活动设置已开始，但尚未准备就绪来运行。</li><li>**已计划**：当到达指定的开始日期和时间时，该活动便可准备激活。</li><li>**不活跃**：该活动已暂停或停用。</li><li>**正在同步**：活动已经保存，并且正在同步到 Target 交付网络。</li><li>**已结束**：已到达指定的活动结束日期和时间，并且不再为该活动提供服务。</li><li>**已存档**：活动已经存档。您可以激活已存档的活动以便再次使用。</li></ul>**注意：**&#x200B;执行某些操作时，例如使用 API 方法在 UI 外部激活活动，可能需要最多 10 分钟才能将更新传播到 UI。 |
| 源 | 显示活动是在哪里创建的：<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager (AEM)</li><li>Adobe Mobile Services (AMS)</li></ul> |
| 属性 | 显示活动的[属性](/help/administrating-target/c-user-management/property-channel/property-channel.md)。 |
| 预计收入提升 | 如果 100% 的受众都看到了入选体验，则显示预计会有多少收入上的增长。<br>使用以下公式计算：<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>最多可以将得出的数值四舍五入到一位小数，但前提是四舍五入后小数点前面只有一位数字。例如：$1.6M、$60K、$900、$8.5K、$205K<br>此列显示“---”时，表示该活动没有足够的数据来确定入选者，或者没有成本估算。<br>请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。 |
| 上次更新 | 活动上次更新的时间以及执行更新操作的人员。 |

将鼠标悬停在活动上可查看可以执行的操作。

![活动列表悬停操作](/help/c-activities/assets/activities_list_hover.png)

以下操作可用（具体取决于您拥有的权限）：

| 操作 | 描述 |
| --- | --- |
| 编辑 | 更改活动。任何活动都可以编辑。<br>有关可编辑活动的各种方法的更多信息，请参阅[编辑活动或另存为草稿](/help/c-activities/edit-activity.md)。 |
| 停用 | 停止实时或计划的活动。可以重新激活或存档已停用的营销活动<br>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| 激活 | 启动不活跃或准备就绪的活动。 |
| 存档 | 将活动发送到存档中。默认情况下，已存档的活动不会再显示在“活动”列表中。要查看这些活动，请更改活动列表的筛选器使其包含已存档活动。您可以激活已存档的活动以便再次使用。<br>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| 复制 | 复制活动。任何活动都可以复制。复制活动将会创建一个具有相同名称的新活动，只不过新的活动名称会附加“副本”两个字。例如，名为“浏览器选件”的测试会被复制到“浏览器选件副本”。<br>可视化选件会与活动一起复制。您可以安全地编辑副本中的选件，而不会影响原始活动。唯一的例外是保存在“内容/资产”文件夹中的选件和图像。 |
| 删除 | 删除草稿或活动。<BR>**注意&#x200B;**：删除的活动将无法恢复。除非您确定再也不需要此活动，否则请使用“[!UICONTROL 存档]”操作。之后，您可以根据需要重新激活该活动。 |

请注意有关“活动”列表的以下详细信息：

* 已存档和已结束的活动不会显示在“[!UICONTROL 活动]”列表中。要查看这些活动，请使用左边栏上的高级筛选器设置对其进行筛选。
* 如果某个活动最初是在 [!DNL Target Classic] 中创建，那么一旦该活动被停用或删除，则它也会从 [!DNL Target Standard/Premium] 中删除。已删除的最初在 [!DNL Target Classic] 中创建的活动不会被发送到 [!DNL Target Standard/Premium] 中的[!UICONTROL 存档]文件夹。存档文件夹功能仅适用于在 [!DNL Target Standard/Premium] 中创建的活动。
* [!UICONTROL 自动个性化] (AP)、[!UICONTROL 自动分配]和[!UICONTROL 自动定位]以外的所有活动类型均允许您选择使用 [!DNL Target] 或 [!DNL Adobe Analytics] 作为数据源。[!UICONTROL AP]、[!UICONTROL 自动分配]和[!UICONTROL 自动定位]*始终*&#x200B;使用 [!DNL Target] 数据。
* 活动可用于多个渠道：

   * Web 和移动设备网站
   * 连接到 Internet 的屏幕和设备，包括自助服务终端和 ATM
   * 电子邮件和其他客户获取渠道或合作伙伴网站
   * 移动设备应用程序
   * 其他任何您可以交付已标记内容的地方

## 排序和筛选活动列表 {#section_41DAD479FFF740E2BB67BF4825955670}

默认情况下，列表按活动的上次修改日期排序，最近修改的活动排在最前面。但是，有几个筛选选项可帮助您自定义列表以显示您想要查看的活动。

### 搜索 {#search-heading}

使用搜索字段查找符合您搜索标准的活动。

![活动搜索](/help/c-activities/assets/activities_search_new.png)

搜索字段包含一个下拉菜单，可通过指定以下搜索筛选器之一来帮助缩小搜索范围：[!UICONTROL 活动名称]和 [!UICONTROL URL]。

### 活动列表筛选器

您可以通过选择列表筛选器来确定哪些活动可以显示在活动列表中。

![按类型筛选活动](/help/c-activities/assets/activities_filters_new.png)

您可以按以下选项进行筛选。在所有类别中，如果没有选择任何内容，则默认为“全部”。

| 筛选器类别 | 过滤器 |
|--- |--- |
| 类型 | A/B 测试：[手动](/help/c-activities/t-test-ab/test-ab.md)、[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)和[自动定位](/help/c-activities/auto-target-to-optimize.md)。<br>[自动个性化](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>[体验定位](/help/c-activities/t-experience-target/experience-target.md)<br>[多变量测试](/help/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[推荐](/help/c-recommendations/recommendations.md) |
| 状态 | 实时<br>草稿<br>已计划<br>不活跃<br>正在同步<br>已结束<br>已存档 |
| 报表源 | Target<br>Analytics |
| 体验编辑器 | 可视<br>基于表单 |
| 量度类型 | 转换<br>收入<br>参与度 |
| 活动源 | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### 按活动属性排序

单击以下标题之一，可切换活动是按照所选标题的升序或降序方式列出。

* 活动名称
* 活动类型

![活动列表升序](/help/c-activities/assets/activities_list_ascending.png)

## 提示和技巧 {#section_F77F30A246A14B538D9363B7F3639F97}

通过了解各种功能的更多信息以充分利用 Adobe Target，并了解为什么要尝试这样做。“提示和技巧”功能提供了指向视频、用例、博客、文档等的链接。

“提示和技巧”功能会定期显示在“活动”列表页面上。当阅读或取消提示后，在下一个提示可用之前，该提示不会再次显示。您可以通过单击“帮助”图标 >“[!UICONTROL 禁用每日提示]”，选择禁止显示所有提示。

![禁用每日提示](/help/c-activities/assets/tip-disable-new.png)

## 限制 {#section_049D4684403A4E07B998067EB8E9BE56}

每个 Target 活动都有以下内容限制：

| 项目 | 限制 |
|--- |--- |
| 唯一选择器 | 300如果一个选择器在不同的体验中重复，则只会被计数一次。但是，如果它在相同的体验中重复，则会被重复计数。 |
| 每个体验中的选件 | 350 |
| 量度中的点击跟踪选择器 | 50 |
| 量度中的 Mbox | 50 |
| 受众和位置 | 50受众和位置 (mbox) 组合不得超过 50 个。 |

如果超出其中任一限制，则无法保存活动。

如果活动中这些项目的数量增加，则在 Target 中同步活动所用的时间也会相应增加。

有关可视化体验编辑器的额外限制，请参阅[可视化体验编辑器限制](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

## 对于在 Target 外部更新的活动，其属性会导入到 Target 当中 {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果在 [!DNL Target] 中创建的活动从 [!DNL Target] 外部进行了更新（例如，通过 Adobe I/O），则下列活动属性将会导入到 [!DNL Target] 当中：

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

此导入作业将在活动页面打开时运行，最长会有 10 分钟延迟。(KB-1526)

## 培训视频 {#section_BE80D13A2E81460C885F902010E1AD87}

以下视频包含有关本文中所讨论概念的详细信息。

### 活动类型(9:03)概 ![述徽章](/help/assets/overview.png)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 管理活动(5:55)概 ![述徽章](/help/assets/overview.png)

本视频介绍了如何使用“活动”列表来管理活动。

* 定义术语“活动”**
* 在“活动”列表中查找活动
* 编辑、停用、复制和删除活动

>[!VIDEO](https://video.tv.adobe.com/v/18550)
