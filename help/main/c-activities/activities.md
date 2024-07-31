---
keywords: 活动列表；活动；活动类型；编辑活动；活动操作；活动属性；活动列表筛选器；活动限制；个性化；个性化
description: 了解 [!DNL Target] 中的活动如何允许您针对特定受众使内容个性化并测试页面设计。
title: 如何使用 [!DNL Target]个性化内容和测试页面设计？
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 0e2bc5c96671b47532b90f3ecb525a6a0506eb8d
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 36%

---

# 活动

通过[!DNL Adobe Target]中的活动，可针对特定受众使内容个性化并测试页面设计。

例如，您可能会设计一个活动以对两个不同的登陆页面进行测试，其中一个页面着重显示夏季女鞋的相关信息，而另一个登陆页面则重点展示更广泛的夏季服饰信息。此活动确定了用于控制这两个登陆页面分别何时显示的条件，以及用于决定哪个页面更为成功的量度。此活动配置为在满足特定条件时开始和结束，例如在具体日期开始和结束，或者在活动得到批准后开始并在活动停用后结束。

设计活动时，您应该仔细规划。确定活动何时开始以及持续时间。然后，列出您的选件并为每个选件分配一组目标顾客。

## 活动列表 {#section_DE8E2DB30D534962A931EF8BB48240F5}

打开[!DNL Target]时，[!UICONTROL Activities]列表是默认视图。 您可以从此页面创建活动并管理现有活动。

您还可以通过单击[!DNL Target] UI顶部的[!UICONTROL Activities]选项卡来显示[!UICONTROL Activities]列表。

![Activities list（活动列表）](/help/main/c-activities/assets/activities-list-new.png)

[!UICONTROL Activities]列表提供了所有活动的概览，并允许您执行各种操作：

| 元素 | 描述 |
|--- |--- |
| 左侧导航边栏 | 在已保存或已上线的活动与失败的或[草稿活动](/help/main/c-activities/edit-activity.md)之间切换。 |
| [!UICONTROL Show filters]图标<P>![显示筛选器图标](/help/main/c-activities/assets/show-filters-icon.png) | 通过单击列表顶部附近的&#x200B;**[!UICONTROL Show Filters]**&#x200B;图标访问筛选器。<P>有关详细信息，请参阅下面的[将筛选器应用到活动列表](#filters)。 |
| 搜索框 | 快速查找活动或减少[!UICONTROL Activity]列表中显示的活动数。 您可以按[!UICONTROL Name]、[!UICONTROL URL]或[!UICONTROL ID]进行搜索。 |
| [!UICONTROL Create Activity] | 创建活动。 有关创建各种活动类型的详细信息，请参阅： <ul><li>[创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[创建自动分配活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[创建自动定位活动](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[创建自动个性化活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[创建多变量测试](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[创建“推荐”活动](/help/main/c-recommendations/recommendations.md)</li></ul>有关每种类型的详细信息，请参阅下面的[活动类型](#types)。 |
| [!UICONTROL Create mobile preview link]<P>![更多操作菜单](/help/main/c-activities/assets/icon-create-mobile-link.png) | 使用[移动设备预览链接](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html)为移动设备应用程序活动执行简单的端到端QA。<P>单击&#x200B;**更多选项**&#x200B;图标（垂直省略号），选择&#x200B;**创建移动设备预览链接**，然后选择要测试在移动设备上的活动。 |
| 自定义表<P>![自定义表格图标](/help/main/c-activities/assets/icon-customize-table.png) | 通过单击表右上角的&#x200B;**[!UICONTROL Customize Table]**&#x200B;图标，然后选择或取消选择所需的列，更改[!UICONTROL Activity]列表中显示的列。<P>更改将应用于您的帐户，并在您注销[!DNL Target]后保持活动状态。 |
| “批量操作”复选框 | 对所有活动或选定活动执行批量操作。<P>有关可用操作的列表（取决于您的权限和活动状态），请参阅下面的[执行快速操作](#quick-actions)。 |
| [!UICONTROL Type] | 活动类型。 [!UICONTROL Type]列允许您按类型快速识别每个活动。 <ul><li>AB-M：手动[!UICONTROL A/B Test]</li><li>AB-AA： [!UICONTROL Auto-Allocate]</li><li>AB-AT： [!UICONTROL Auto-Target]</li><li>AP： [!UICONTROL Automated Personalization]</li><li>XT： [!UICONTROL Experience Targeting]</li><li>MVT： [!UICONTROL Multivariate Test]</li><li>记录： [!UICONTROL Recommendations]</li></ul>有关每种类型的详细信息，请参阅下面的[活动类型](#types)。 |
| [!UICONTROL Name] | 活动的名称。 单击某个活动名称以显示该活动的[!UICONTROL Overview]页面。 <P>单击每个活动名称旁边的&#x200B;**[!UICONTROL Quick Info]**&#x200B;图标可在弹出卡片中查看有关该活动的更多信息。<p>单击每个活动名称旁边的&#x200B;**[!UICONTROL More actions]**&#x200B;图标（水平省略号）以打开一个菜单，允许您对活动执行快速操作。 以下操作可用（取决于您的权限和活动状态）： [!UICONTROL Edit]、[!UICONTROL Activate]、[!UICONTROL Deactivate]、[!UICONTROL Copy]、[!UICONTROL Delete]和[!UICONTROL Archive]。 有关每个操作的详细信息，请参阅下面的[执行快速操作](#quick-actions)。<P>单击表标题可按名称的字母升序或降序对列表进行排序。 |
| [!UICONTROL Status] | 活动的状态可以是下列状态之一：<ul><li>**实时**：该活动当前正在运行。</li><li>**草稿**：活动安装程序已启动，但该活动处于[草稿模式](/help/main/c-activities/edit-activity.md)，尚未准备好运行。</li><li>**已计划**：当到达指定的开始日期和时间时，该活动便可准备激活。</li><li>**不活跃**：该活动已暂停或停用。</li><li>**正在同步**：活动已保存，正在同步到[!DNL Target]投放网络。</li><li>**已结束**：已到达指定的活动结束日期和时间，并且不再为该活动提供服务。</li><li>**已存档**：活动已经存档。您可以激活已存档的活动以便再次使用。</li></ul>**注意**：执行某些操作时，例如使用API方法在[!DNL Target] UI外部激活活动，更新最多可能需要10分钟才能传播到[!DNL Target] UI。 |
| [!UICONTROL Last Updated] | 上次更新活动的日期和时间，以及更新者。<P>单击表标题可按日期对列表进行升序或降序排序。 |
| [!UICONTROL Priority] | 活动的优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>根据您的[设置](/help/main/administrating-target/reporting.md)，[!UICONTROL Priority]的[!DNL Target] UI和选项会有所不同。 您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。 |
| [!UICONTROL Property] | 显示活动的[属性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。<P>企业用户权限是一项[Target Premium](/help/main/c-intro/intro.md#premium)功能。 |
| [!UICONTROL Estimated Lift in Revenue] | 如果 100% 的受众都看到了入选体验，则显示预计会有多少收入上的增长。<P>使用以下公式计算：<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>如果以简写的形式表示数字，且小数点前只有一个数字，则该数字将四舍五入至小数点后一位，保留最大值。例如：$1.6M、$60K、$900、$8.5K、$205K<P>此列显示“---”时，表示该活动没有足够的数据来确定入选者，或者没有成本估算。<P>请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。 |
| [!UICONTROL Source] | 显示创建活动的位置： [!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=zh-Hans)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)或[AdobeMobile Services](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL Location] | 活动的 URL 可标识该活动在哪里显示。此列可帮助您快速识别活动，并确定某个特定页面是否已在该活动上运行。<P>如果活动在多个URL上运行，则会有一个链接显示使用的URL数量。 单击该链接可查看该活动的完整 URL 列表。<P>您可以根据URL进行搜索。 使用搜索框旁边的下拉列表并选择[!UICONTROL URL]。 |
| 作者 | 创建活动的人员的姓名。 |
| [!UICONTROL Decisioning Method] | 每个活动中使用的决策方法： [服务器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)或[客户端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)。 |

## 活动类型 {#types}

[!DNL Target]包含多种活动类型。 下表提供了每种活动类型的概述，其中包含可帮助您了解更多信息的链接。为了帮助您更好地选择符合要求的最佳活动类型，我们还创建了 [Adobe Target 活动指南](/help/main/c-activities/target-activities-guide.md)。

| 活动类型 | 描述 |
|--- |--- |
| [A/B 测试](/help/main/c-activities/t-test-ab/test-ab.md) | A/B测试可比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最有利于提高转化。 |
| [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate]是一种A/B测试，它可以在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选者重新分配更多流量以提高转化。 |
| [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | 自动定位是一种A/B测试，它使用先进的机器学习技术从营销人员定义的多个高性能体验中进行识别，并根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验，以便个性化内容并促进转化。 |
| [多变量测试](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT)比较页面上各元素中的选件组合，以确定哪个组合对特定受众的效果最佳，并标识哪个元素对活动成功的影响最大。 |
| [体验定位](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT)根据一组营销人员定义的规则和条件向特定受众提供内容。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP)将各种选件或消息组合在一起，并使用先进的机器学习技术，根据每位访客的个人客户配置文件将不同的变体与其匹配，以便个性化内容并促进转化。 |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | 推荐可根据网站访客在网站上的活动，来确定向该访客推荐产品的方式。<P>例如，您可能想要鼓励购买了背包的人也考虑购买登山鞋和登山杖。在这种情况下，您可以使用“购买了这个项目，也购买了那个项目的人”算法，创建一个推荐来显示通常一起购买的项目。或者，您可能希望使用“观看了这个项目，也观看了那个项目”算法，将类似的视频推荐给观看视频，从而鼓励访客在媒体网站上多花些时间。<P>**注意**：您还可以在[!UICONTROL A/B Test]、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target]和[!UICONTROL Experience Targeting] (XT)活动中包含推荐。 有关更多信息，请参阅[将 Recommendations 作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。要使用此功能，您需要拥有 [Target Premium 许可证](/help/main/c-intro/intro.md#premium)。 |

## 将过滤器应用于“活动”列表 {#filters}

通过单击列表顶部附近的&#x200B;**[!UICONTROL Show Filters]**&#x200B;图标访问筛选器。

![筛选器选项](/help/main/c-activities/assets/show-filters-options.png)

利用菜单，可按以下属性筛选活动：

| 属性 | 详细信息 |
| --- | --- |
| [!UICONTROL Type] | 按[活动类型](#types)筛选。 |
| [!UICONTROL Status] | 按活动状态筛选。 |
| [!UICONTROL Reporting Source] | 按报表源筛选。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)：显示使用[!UICONTROL Analytics for Target] (A4T)作为报表源的活动。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md)：显示使用[!DNL Target]作为报表源的活动。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)：显示使用[!DNL Adobe Customer Analytics]作为报表源的活动。</li></ul> |
| [!UICONTROL Experience Composer] | 活动创建期间使用体验编辑器的筛选条件：<ul><li>[可视](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)：显示使用[!UICONTROL Visual Experience Composer] (VEC)创建的活动。</li><li>[基于表单](/help/main/c-experiences/form-experience-composer.md)：显示使用[!UICONTROL Form-Based Experience Composer]创建的活动。</li></ul> |
| [!UICONTROL Metrics Type] | 用于在活动创建期间选择[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的筛选器。<ul><li>转化</li><li>收入</li><li>参与度</li></ul> |
| [!UICONTROL Decisioning Method] | 按每个活动中使用的决策方法筛选<ul><li>[服务器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)：显示使用服务器端决策的活动。</li><li>[客户端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：显示使用客户端决策的活动。</li></ul> |
| [!UICONTROL Activity Source] | 按用于创建每个活动的活动源进行筛选。<ul><li>[!DNL Adobe Target]</li><li>[Adobe Target API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=zh-Hans)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[Adobe Mobile 服务](https://developer.adobe.com/client-sdks/documentation/)</li></ul> |
| [!UICONTROL Property] | 按创建该活动的[属性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)筛选。 |

## 执行快速操作 {#quick-actions}

单击每个活动名称旁边的&#x200B;**[!UICONTROL More actions]**&#x200B;图标（水平省略号）以打开一个菜单，允许您对活动执行快速操作。

![快速操作选项](/help/main/c-activities/assets/quick-actions.png)

以下操作可用（具体取决于您的权限和活动状态）：

| 操作 | 描述 |
| --- | --- |
| [!UICONTROL Edit] | 更改活动。任何活动都可以编辑。<P>有关各种活动编辑方式的更多信息，请参阅[编辑活动或另存为草稿](/help/main/c-activities/edit-activity.md)。 |
| [!UICONTROL Deactivate] | 停止实时或计划的活动。可以重新激活或存档已停用的活动。<P>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| [!UICONTROL Activate] | 启动不活动的活动或准备激活的活动。 |
| [!UICONTROL Archive] | 将活动发送到存档中。默认情况下，已存档的活动不再出现在[!UICONTROL Activities]列表中。 要查看这些活动，请更改活动列表的筛选器使其包含已存档活动。您可以激活已存档的活动以便再次使用。<P>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。 在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| [!UICONTROL Copy] | 复制活动。任何活动都可以复制。复制活动将会创建一个具有相同名称的新活动，只不过新的活动名称会附加“副本”两个字。例如，名为“浏览器选件”的测试会被复制到“浏览器选件副本”。<P>可视化选件会与活动一起复制。您可以安全地编辑副本中的选件，而不会影响原始活动。唯一的例外是保存在“内容/资产”文件夹中的选件和图像。 |
| [!UICONTROL Delete] | 删除草稿或活动。<P>**注意**：无法恢复已删除的活动。 除非您确定再也不需要此活动，否则请使用[!UICONTROL Archive]操作。 之后，您可以根据需要重新激活该活动。 |

## 注意事项

请注意有关[!UICONTROL Activity]列表的以下详细信息：

* 已存档和已结束的活动未出现在[!UICONTROL Activities]列表中。 要查看这些活动，请使用列表顶部的[筛选器图标](#filters)筛选它们。
* 当最初在[!DNL Target Classic]中创建的活动被停用或删除时，它将从[!DNL Target Standard/Premium]中删除。 已删除的最初在[!DNL Target Classic]中创建的活动未发送到[!DNL Target Standard/Premium]中的[!UICONTROL Archive]文件夹。 存档文件夹功能仅适用于在 [!DNL Target Standard/Premium] 中创建的活动。
* 除[!UICONTROL Automated Personalization] (AP)、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]之外的所有活动类型都允许您选择使用[!DNL Target]或[!DNL Adobe Analytics]作为数据源。 [!UICONTROL AP]、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target] *始终*&#x200B;使用[!DNL Target]数据。
* 活动可用于多个渠道：

   * Web 和移动设备网站
   * 连接到 Internet 的屏幕和设备，包括自助服务终端和 ATM
   * 电子邮件和其他客户获取渠道或合作伙伴网站
   * 移动设备应用程序
   * 其他任何您可以交付已标记内容的地方

## 限制 {#section_049D4684403A4E07B998067EB8E9BE56}

每个 Target 活动都有以下内容限制：

| 项目 | 限制 |
|--- |--- |
| 唯一选择器 | 如果一个选择器在不同体验中重复，则计算一次。 但是，如果它在相同的体验中重复，则会被重复计数。 |
| 每个体验中的选件 | 350 |
| 量度中的点击跟踪选择器 | 50 |
| 量度中的 Mbox | 50 |
| 受众和位置 | 50个受众和位置(mbox)组合不得超过50个。 |

如果超出其中任一限制，则无法保存活动。

增加活动中的这些项目的数量也会增加跨[!DNL Target]同步活动所需的时间。

有关V[!UICONTROL isual Experience Composer] VEC的其他限制，请参阅[可视化体验编辑器限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

## 对于在[!DNL Target]外部更新的活动，属性导入到[!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果在[!DNL Target]中创建的活动从[!DNL Target]外部进行了更新（例如，通过API），则以下活动属性将导入回[!DNL Target]： `thirdpartyId`、`startDate`、`endDate`、`status`、`priority`和`marketingCloudMetadata(remoteModifiedBy)`。

此导入作业在活动页面打开时运行，最大延迟为10分钟。

## 培训视频 {#section_BE80D13A2E81460C885F902010E1AD87}

以下视频包含有关本文中所讨论概念的更多信息。

### 活动类型 (9:03)

以下视频介绍了 [!DNL Target Standard/Premium] 中可用的活动类型。

* 介绍 [!DNL Adobe Target] 中包含的活动类型
* 选择相应的活动类型以实现目标
* 介绍适用于所有活动类型的三步引导式工作流

>[!VIDEO](https://video.tv.adobe.com/v/17386)

