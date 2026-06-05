---
keywords: 活动列表；活动；活动类型；编辑活动；活动操作；活动属性；活动列表筛选器；活动限制；个性化；个性化
description: 通过 [!DNL Adobe Target] 活动为特定受众个性化内容并测试页面设计。
title: 如何使用 [!DNL Target]个性化内容和测试页面设计？
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
TQID: https://experienceleague.adobe.com/q3-Z8r2eEWTISBkZBBJTJ8XarLi-lTa2qsqj961hhEQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2633
ht-degree: 25%

---

# 活动概述

通过[!DNL Adobe Target]活动为特定受众个性化内容和测试页面设计。

例如，您可能会设计一个活动以对两个不同的登陆页面进行测试，其中一个页面着重显示夏季女鞋的相关信息，而另一个登陆页面则重点展示更广泛的夏季服饰信息。 活动可确定控制每个登陆页面显示时间的条件，以及确定哪个页面更成功的量度。 该活动配置为在满足特定条件时开始和结束，如在特定日期之间。 或者，您可以选择在批准活动时开始，在停用活动时结束。

设计活动时，您应该仔细规划。 确定活动何时开始以及持续时间。 然后，列出您的产品建议并为每个建议分配一组目标受众。

## 活动列表 {#section_DE8E2DB30D534962A931EF8BB48240F5}

打开[!DNL Target]时，[!UICONTROL 活动]列表是默认视图。 您可以从此页面创建活动并管理现有活动。

您还可以通过单击[!DNL Target] UI顶部的[!UICONTROL 活动]选项卡来显示[!UICONTROL 活动]列表。

[!UICONTROL 活动]列表提供了[!DNL Target]实施中所有活动的概览，并允许您执行各种操作。

下表可帮助您了解[!DNL Target] UI中[!UICONTROL 活动]列表中的各种元素：

| 元素 | 描述 |
|--- |--- |
| [!UICONTROL 显示筛选器]图标<P>![显示筛选器图标](/help/main/assets/icons/Filter.svg) | 通过单击列表顶部附近的&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标访问筛选器，以按[!UICONTROL 类型]、[!UICONTROL 状态]、[!UICONTROL 报告Source]、[!UICONTROL 体验编辑器]、[!UICONTROL 量度类型]、[!UICONTROL 决策Source]、[!UICONTROL 活动Source]和[!UICONTROL 属性]筛选活动。<P>您配置的过滤器在当前会话中是持久性的。<P>有关详细信息，请参阅下面的[将筛选器应用到下面的[!UICONTROL 活动]列表](#filters)。 |
| 搜索字段 | 快速查找活动或减少[!UICONTROL 活动]列表中显示的活动数。 您可以使用下拉列表按[!UICONTROL 活动名称]、[!UICONTROL URL]或[!UICONTROL ID]进行搜索。<P>您配置的搜索选项在当前会话中是永久性的。 |
| [!UICONTROL 创建活动] | 创建一个活动。<P>有关创建各种活动类型的详细信息，请参阅： <ul><li>[创建[!UICONTROL A/B测试]活动](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[创建[!UICONTROL 自动分配]活动](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[创建[!UICONTROL 自动定位]活动](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[创建[!UICONTROL Automated Personalization]活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[创建[!UICONTROL 体验定位]活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[创建活动](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[创建[!UICONTROL 推荐]活动](/help/main/c-recommendations/recommendations.md)</li></ul>有关每种类型的详细信息，请参阅下面的[活动类型](#types)。 |
| [!UICONTROL 创建移动设备预览链接]<P>![更多操作菜单](/help/main/assets/icons/MoreVertical.svg) | 使用[移动设备预览链接](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview)为移动设备应用程序活动执行简单的端到端QA。<P>单击&#x200B;**更多选项**&#x200B;图标，选择&#x200B;**创建移动设备预览链接**，然后选择要测试在移动设备上的活动。 |
| 自定义表<P>![自定义表格图标](/help/main/assets/icons/ColumnSetting.svg) | 通过单击页面右上角的&#x200B;**[!UICONTROL 自定义表]**&#x200B;图标，然后选择或取消选择所需的列，更改[!UICONTROL 活动]列表中显示的列。<P>更改将应用于您的帐户，并在您注销[!DNL Target]后保持活动状态。 |
| “批量操作”复选框<P>![批量操作图标](/help/main/assets/icons/Rectangle.svg) | 对所有活动或选定活动执行批量操作。<P>有关可用操作的列表（取决于您的权限和活动状态），请参阅下面的[执行快速操作](#quick-actions)。 |
| [!UICONTROL 类型] | 活动类型。 [!UICONTROL 类型]列允许您按类型快速识别每个活动。 <ul><li>**AB-M**：手动[!UICONTROL A/B测试]</li><li>**AB-AA**： [!UICONTROL 自动分配]</li><li>**AB-AT**： [!UICONTROL 自动定位]</li><li>**AP**： [!UICONTROL Automated Personalization]</li><li>**XT**： [!UICONTROL 体验定位]</li><li>**MVT**： [!UICONTROL 多变量测试]</li><li>**REC**： [!UICONTROL 推荐]</li></ul>有关每种类型的详细信息，请参阅下面的[活动类型](#types)。 |
| [!UICONTROL 名称] | 活动的名称。 单击每个活动名称旁边的&#x200B;**[!UICONTROL 快速信息]**&#x200B;图标（![快速信息图标](/help/main/assets/icons/InfoOutline.svg)）可在弹出卡片中查看有关该活动的更多信息，包括[!UICONTROL 活动ID]、[!UICONTROL 活动目标]、[!UICONTROL 活动位置]、[!UICONTROL 目标]和[!UICONTROL 状态]。<P>单击每个活动名称旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）以打开一个菜单，允许您对活动执行快速操作。 以下操作可用（取决于您的权限和活动状态）： [!UICONTROL 编辑]、[!UICONTROL 激活]、[!UICONTROL 停用]、[!UICONTROL 复制]、[!UICONTROL 删除]和[!UICONTROL 存档]。<P>有关每个操作的详细信息，请参阅下面的[执行快速操作](#quick-actions)。<P>单击表标题可按名称的字母升序或降序对列表进行排序。 |
| [!UICONTROL 状态] | 活动的状态可以是下列状态之一：<ul><li>**[!UICONTROL 实时]**：该活动当前正在运行。</li><li>**[!UICONTROL 已计划]**：当到达指定的开始日期和时间时，该活动已准备好激活。</li><li>**[!UICONTROL 不活动]**：该活动已暂停或停用。</li><li>**[!UICONTROL 已结束]**：已到达指定的活动结束日期和时间，并且不再为该活动提供服务。</li><li>**[!UICONTROL 已存档]**：活动已存档。 您可以激活已存档的活动以便再次使用。</li></ul>**注意**：执行某些操作时，例如使用API方法在[!DNL Target] UI外部激活活动，更新最多可能需要10分钟才能传播到[!DNL Target] UI。 |
| [!UICONTROL 上次更新时间] | 上次更新活动的日期和时间，以及更新者。<P>单击表标题可按日期对列表进行升序或降序排序。 |
| [!UICONTROL 优先级] | 活动的优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。 如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>根据您的[设置](/help/main/administrating-target/reporting.md)，[!UICONTROL 优先级]的[!DNL Target] UI和选项会有所不同。 您可以使用[!UICONTROL 低]、[!UICONTROL Medium]或[!UICONTROL 高]的旧设置，也可以启用0到999的细粒度优先级。<P>有关优先级设置的详细信息，请参阅&#x200B;*目标和设置*&#x200B;中&#x200B;*活动设置*&#x200B;下的[优先级](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)。 |
| [!UICONTROL 属性] | 显示活动的[属性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。<P>企业用户权限是[Target Premium](/help/main/c-intro/intro.md#premium)功能。 |
| [!UICONTROL 预计收入提升] | 如果 100% 的受众都看到了入选体验，则显示预计会有多少收入上的增长。<P>使用以下公式计算：<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>如果以简写的形式表示数字，且小数点前只有一个数字，则该数字将四舍五入至小数点后一位，保留最大值。 例如：$1.6M、$60K、$900、$8.5K、$205K<P>此列显示“---”时，表示该活动没有足够的数据来确定入选者，或者没有成本估算。<P>请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)以了解更多信息。 |
| [!UICONTROL 来源] | 显示创建该活动的位置： [!DNL Adobe Target]、[Adobe Target API](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview)、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html)、[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)或[Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/)。 |
| [!UICONTROL 作者] | 创建活动的人员的姓名。 |
| [!UICONTROL 决策方法] | 每个活动中使用的决策方法： [服务器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)或[客户端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)。 |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## 活动类型 {#types}

[!DNL Target]包含多种活动类型。 下表提供了每种活动类型的概述，其中包含可帮助您了解更多信息的链接。 为了帮助您更好地选择符合要求的最佳活动类型，请使用[Adobe Target Activities Guide](/help/main/c-activities/target-activities-guide.md)。

| 活动类型 | 描述 |
|--- |--- |
| [[!UICONTROL A/B 测试]](/help/main/c-activities/t-test-ab/test-ab.md) | A/B测试可比较两个或更多版本的网站内容，以查看在预先指定的测试期间，哪个版本最有利于提高转化。 |
| [[!UICONTROL 自动分配]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL 自动分配]是一种A/B测试，它可以在两个或更多体验中标识一个入选者，并在测试继续运行和学习期间，自动为入选者重新分配更多流量以提高转化。 |
| [[!UICONTROL Auto-Target（自动定位）]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | 自动定位是一种A/B测试，它使用先进的机器学习技术从营销人员定义的多个高性能体验中进行识别，并根据每位访客的个人客户配置文件和具有相似配置文件的先前访客的行为，向每位访客提供量身定制的体验，以便个性化内容并促进转化。 |
| [[!UICONTROL 多变量测试]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT)可通过比较页面上各元素中的选件组合，来确定哪个组合对特定受众的效果最佳，以及哪个元素对活动成功的影响最大。 |
| [[!UICONTROL 体验定位]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL 体验定位] (XT)根据一组营销人员定义的规则和条件向特定受众提供内容。 |
| [[!UICONTROL 自动个性化]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP)将选件或消息组合在一起，并使用高级机器学习根据每位访客的个人客户配置文件将不同的变体与其匹配，以便个性化内容并促进转化。 |
| [[!UICONTROL 推荐]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | 推荐可根据网站访客在网站上的活动，来确定向该访客推荐产品的方式。<P>例如，您可能想要鼓励购买了背包的人也考虑购买登山鞋和登山杖。 在这种情况下，您可以使用“购买了这个项目，也购买了那个项目的人”算法，创建一个推荐来显示通常一起购买的项目。 或者，您可能希望使用“观看了这个项目，也观看了那个项目”算法，将类似的视频推荐给观看视频，从而鼓励访客在媒体网站上多花些时间。<P>**注意**：您还可以在[!UICONTROL A/B测试]、[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 体验定位] (XT)活动中包含推荐。 有关更多信息，请参阅[将推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)。 要使用此功能，您需要拥有 [Target Premium 许可证](/help/main/c-intro/intro.md#premium)。 |

## 将过滤器应用于“活动”列表 {#filters}

通过单击列表顶部附近的&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;图标（![显示筛选器图标](/help/main/assets/icons/Filter.svg)）访问筛选器。

利用菜单，可按以下属性筛选活动：

| 属性 | 详细信息 |
| --- | --- |
| [!UICONTROL 类型] | 按[活动类型](#types)筛选。 |
| [!UICONTROL 状态] | 按活动状态筛选。<ul><li>**[!UICONTROL 实时]**：该活动当前正在运行。</li><li>**[!UICONTROL 已计划]**：当到达指定的开始日期和时间时，该活动已准备好激活。</li><li>**[!UICONTROL 不活动]**：该活动已暂停或停用。</li><li>**[!UICONTROL 已结束]**：已到达指定的活动结束日期和时间，并且不再为该活动提供服务。</li><li>**[!UICONTROL 已存档]**：活动已存档。 您可以激活已存档的活动以便再次使用。</li></ul>有关已弃用的[!UICONTROL 另存为草稿]和[!UICONTROL 正在同步]状态的详细信息，请参阅此表下面的说明。 |
| [!UICONTROL 报告Source] | 按报表源筛选。<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md)：显示使用[!UICONTROL Analytics for Target] (A4T)作为报表源的活动。</li><li>[[!DNL Target]](/help/main/c-reports/reports.md)：显示使用[!DNL Target]作为报表源的活动。</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)：显示使用[!DNL Adobe Customer Analytics]作为报表源的活动。</li></ul> |
| [!UICONTROL 体验编辑器] | 活动创建期间使用体验编辑器的筛选条件：<ul><li>[可视化](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)：显示使用[!UICONTROL 可视化体验编辑器] (VEC)创建的活动。</li><li>[基于表单](/help/main/c-experiences/form-experience-composer.md)：显示使用基于表单的体验编辑器[!UICONTROL 创建的活动]。</li></ul> |
| [!UICONTROL 量度类型] | 用于在活动创建期间选择[成功量度](/help/main/c-activities/r-success-metrics/success-metrics.md)的筛选器。<ul><li>[!UICONTROL 转化]</li><li>[!UICONTROL 收入]</li><li>[!UICONTROL 参与]</li><li>[!UICONTROL 使用Analytics量度]</lI></ul> |
| [!UICONTROL 决策方法] | 按每个活动中使用的决策方法进行筛选。<ul><li>[服务器端](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html)：显示使用服务器端决策的活动。</li><li>[客户端](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html)：显示使用客户端决策的活动。</li></ul> |
| [!UICONTROL 活动Source] | 按用于创建每个活动的活动源进行筛选。<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=zh-Hans)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL 属性] | 按创建该活动的[属性](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)筛选。 |


>[!NOTE]
>
>**更新UI中的活动状态**：随着用户界面的最新更新，[!UICONTROL 另存为草稿]和[!UICONTROL 同步]状态将不再可用。 这是因为所有活动创建和编辑现在都使用GraphQL层直接在后端[!DNL Target]投放系统中进行，从而确保流程更加精简和有效。
>
>以前，活动先保存在[!DNL Target]前端中，然后同步到后端[!DNL Target]交付系统，这需要这些中间状态。 由于情况已发生了变化，这些州已被删除。
>
>[!DNL Adobe]了解一些客户已表示对[!UICONTROL 另存为草稿]功能感兴趣。 虽然我们很感谢您提供此反馈，但目前不支持此功能。

## 执行快速操作 {#quick-actions}

单击每个活动名称旁边的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作菜单](/help/main/assets/icons/MoreVertical.svg)）以打开允许您对活动执行快速操作的菜单。

以下操作可用（具体取决于您的权限和活动状态）：

| 操作 | 描述 |
| --- | --- |
| [!UICONTROL 编辑] | 更改活动。 任何活动都可以编辑。<P>有关各种活动编辑方式的更多信息，请参阅[编辑活动或另存为草稿](/help/main/c-activities/edit-activity.md)。 |
| [!UICONTROL 停用] | 停止实时或计划的活动。 可以重新激活或存档已停用的活动。<P>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。 在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| [!UICONTROL 激活] | 启动不活动的活动或准备激活的活动。 |
| [!UICONTROL 存档] | 将活动发送到存档中。 默认情况下，已存档的活动不再出现在[!UICONTROL 活动]列表中。 更改[!UICONTROL 活动]列表的筛选器以包含已存档的活动以查看它们。 您可以激活已存档的活动以便再次使用。<P>如果您停用活动或将活动存档，稍后又重新激活它，并且在停用活动或将活动存档之前有访客处于活动中，则该访客在重新激活活动后将继续成为该活动的一部分。 在这两个事件之间的时段内记录的任何转化量度不会归因于该活动。 |
| [!UICONTROL 复制] | 复制活动。 任何活动都可以复制。 复制活动将会创建一个具有相同名称的新活动，只不过新的活动名称会附加“副本”两个字。 例如，名为“浏览器选件”的测试会被复制到“浏览器选件副本”。<P>可视化选件会与活动一起复制。 您可以安全地编辑副本中的选件，而不会影响原始活动。 唯一的例外是保存在“内容/资产”文件夹中的选件和图像。 |
| [!UICONTROL 删除] | 删除草稿或活动。<P>**注意**：无法恢复已删除的活动。 除非您确定再也不需要此活动，否则请使用[!UICONTROL 存档]操作。 之后，您可以根据需要重新激活该活动。 |

## 注意事项

请注意有关[!UICONTROL 活动]列表的以下详细信息：

* [!UICONTROL 已存档]和[!UICONTROL 已结束]的活动未出现在[!UICONTROL 活动]列表中。 要查看这些活动，请使用列表顶部的[筛选器图标](#filters) （ ![显示筛选器图标](/help/main/assets/icons/Filter.svg) ）筛选它们。
* 当最初在[!DNL Target Classic]中创建的活动被停用或删除时，它将从[!DNL Target Standard/Premium]中删除。 已删除的最初在[!DNL Target Classic]中创建的活动未发送到[!DNL Target Standard/Premium]中的[!UICONTROL 存档]文件夹。 存档文件夹功能仅适用于在 [!DNL Target Standard/Premium] 中创建的活动。
* 除[!UICONTROL Automated Personalization] (AP)、[!UICONTROL 自动分配]和[!UICONTROL 自动定位]之外的所有活动类型均允许您选择使用[!DNL Target]或[!DNL Adobe Analytics]作为数据源。 [!UICONTROL Automated Personalization]、[!UICONTROL 自动分配]和[!UICONTROL 自动定位] *始终*&#x200B;使用[!DNL Target]数据。
* 活动可用于多个渠道：

   * Web 和移动设备网站
   * 连接到 Internet 的屏幕和设备，包括自助服务终端和 ATM
   * 电子邮件和其他客户获取渠道或合作伙伴网站
   * 移动设备应用程序
   * 其他任何您可以交付已标记内容的地方

## 限制 {#section_049D4684403A4E07B998067EB8E9BE56}

每个[!DNL Target]活动都有以下内容限制：

| 项目 | 限制 |
|--- |--- |
| 唯一选择器 | 如果一个选择器在不同体验中重复，则计算一次。 但是，如果它在相同的体验中重复，则会被重复计数。 |
| 每个体验中的选件 | 350 |
| 量度中的点击跟踪选择器 | 50 |
| 量度中的 Mbox | 50 |
| 受众和位置 | 50个受众和位置(mbox)组合不得超过50个。 |

如果超出其中任一限制，则无法保存活动。

增加活动中的这些项目的数量也会增加跨[!DNL Target]同步活动所需的时间。

有关[!UICONTROL 可视化体验编辑器] (VEC)的其他限制，请参阅[可视化体验编辑器限制](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721)。

## 对于在[!DNL Target]外部更新的活动，属性导入到[!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

如果在[!DNL Target]中创建的活动从[!DNL Target]外部进行了更新（例如，通过API），则以下活动属性将导入回[!DNL Target]： `thirdpartyId`、`startDate`、`endDate`、`status`、`priority`和`marketingCloudMetadata(remoteModifiedBy)`。

此导入作业在[!UICONTROL 活动]列表打开时运行，最大延迟为10分钟。

