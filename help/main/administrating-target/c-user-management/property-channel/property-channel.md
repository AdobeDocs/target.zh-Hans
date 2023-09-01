---
keywords: 工作区；管理属性；权限；产品配置；产品配置文件；角色；项目；观察者；编辑者；审批者；发布者
description: 了解如何创建单独的工作区（产品配置文件），然后为各个页面、属性或网站为用户分配不同的角色和权限。
title: 什么是企业用户权限？如何使用企业用户权限？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="请参阅Target Premium中包含的内容。"
feature: Administration & Configuration
role: Admin
exl-id: 838abe87-dba7-4274-97b4-31a7905846dc
source-git-commit: 273143c5b2157948eee464ee0514e04a0105e978
workflow-type: tm+mt
source-wordcount: '3232'
ht-degree: 57%

---

# 企业用户权限

企业用户权限是对企业范围内的用户访问权限进行正式管理的一种方法。 [!DNL Adobe Target]. 将用户添加到 [!DNL Target]，根据其角色分配权限，并根据不同的部门、全球位置、渠道和其他逻辑分组为团队创建工作区。 您可以为用户分配以下角色 [!UICONTROL 观察者]， [!UICONTROL 编辑者]， [!UICONTROL 审批者]，或 [!UICONTROL 发布者].

## 确定您是否有权访问企业用户权限

>[!NOTE]
>
>[!UICONTROL 属性和权限]功能作为 [!DNL Target] Premium 解决方案的一部分提供。如果没有 [!DNL Target] Premium 许可证，它们将无法在 [!DNL Target] Standard 中使用。
>
>您的 [!DNL Target] 实施可以使用任何版本的at.js，或者 [!DNL Adobe Experience Platform Web SDK].

您可以在 [!DNL Target] UI 的顶部单击[!UICONTROL 管理]链接，确定组织使用的是 Standard 还是 Premium 许可。

* **[!DNL Target Standard]客户**：如果您看到[!UICONTROL 用户]选项卡（[!UICONTROL 管理 > 用户]）（而不是[!UICONTROL 属性]选项卡），则组织具有 [!DNL Target Standard] 许可。[!DNL Target Standard] 客户应按照中的相关说明进行操作 [用户](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) 在中添加用户和分配权限 [!DNL Adobe Admin Console].

* **[!DNL Target Premium]客户**：如果您看到 [!UICONTROL 属性] 选项卡([!UICONTROL 管理>属性])和 [!UICONTROL 用户] 选项卡，您的组织具有 [!DNL Target Premium] 许可证。 [!DNL Target Premium] 客户应按照本文章和[配置企业权限](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md)中的相关说明进行操作。

## 开始使用企业权限之前

>[!IMPORTANT]
>
>请务必阅读 [注意事项](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) 部分，然后再继续使用企业权限。

## 本节使用的术语和定义 {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

本节使用了以下术语，想要在中使用属性和权限功能的用户可能对这些术语比较陌生 [!DNL Target] 高级。

### 属性

物业性质与以下各项内之物业类似： [!DNL Adobe Experience Platform] 因为它们使用唯一的代码片段来区分它们。

Web 属性是一个规则库和一种嵌入代码。Web 属性可以是一个或多个域和子域的任意组合。

属性可通过将特定的名称/值对作为参数通过任何调用（Target调用、api调用等）添加到来启用 [!DNL Target].

属性属于特定渠道（Web、移动设备、电子邮件或 API/其他）。

### 工作区（产品配置文件）

工作区允许组织为一组特定用户分配一组特定属性。工作区在许多方面与 [!DNL Adobe Analytics] 中的报表包相似。

注意：工作区称为 [!UICONTROL 产品配置文件] 在 [!DNL Adobe Admin Console for Enterprise].

如果您所在的组织是跨国组织，则您可能拥有两个工作区：一个用于欧洲网页、属性或网站，而另一个用于美国网页、属性或网站。如果您所在的组织拥有多个品牌，则您的每个品牌可能有其独立的工作区。

用户可以包含在多个工作区中，甚至可以在每个工作区拥有不同的角色。

用户可以拥有不同的视图 [!DNL Adobe Target] 通过在工作区之间移动，类似于如何 [!DNL Analytics] 用户在以下内容中有不同的视图： [!DNL Analytics] 在报表包之间移动。

工作区可以包括完全不同的受众、代码选件和活动。

在迁移新的企业权限模型之前创建的所有受众和活动都分组到“默认工作区”中，如下所述。

通过创建的所有活动 [!DNL Adobe Experience Manager] (AEM)， [!DNL Adobe Mobile Services]、和 [!DNL Adobe Target Classic] 是“默认工作区”的一部分。

### 默认工作区

中的所有现有工作区（产品配置文件） [!DNL Admin Console] 在组织迁移到新的企业权限模型期间，这些权限将合并到名为“默认工作区”的单个工作区中。

>[!IMPORTANT]
>
>请勿删除默认工作区。

所有用户角色和对所有用户的访问权限 [!DNL Target] 功能与迁移到新的企业权限模型之前相同。

### 用户组

您可以创建用户组，例如开发人员、分析人员、营销人员、执行人员等。 然后，您可以跨多个Adobe产品和工作区分配权限。 为新团队成员分配不同 Adobe 产品中的所有相应权限的过程就像将他们添加到某个特定用户组一样简单。

### 角色和权限 {#roles-permissions}

角色和权限决定了用户在 [!DNL Target] 实施中创建和管理活动所需的访问权限级别。在 [!DNL Target] 中，角色包括：

| 角色 | 描述 |
|--- |--- |
| [!UICONTROL 审批者] | 可以创建、编辑，以及激活或停止活动。 |
| [!UICONTROL 编辑者] | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
| [!UICONTROL 观察者] | 可以查看活动，但不能创建或编辑活动。 |
| [!UICONTROL 发布者] | 类似于 [!UICONTROL 观察者] 角色（可以查看活动，但不能创建或编辑活动）。 但是，[!UICONTROL 发布者]角色另有激活活动的权限。 |

### 渠道

渠道是指用于传递 [!DNL Target] 活动的内容类型：网页、移动设备应用程序、电子邮件等。

创建活动时，会在当前选定的工作区中创建该活动。 在第一个对话框中，您会看到渠道选择选项，从中可为活动选择所需的渠道：Web、移动设备应用程序、电子邮件或其他/API。

## 权限概述 {#section_DC2172520DA84605B218A5E9FB6D187A}

以下信息说明了先前在 [!DNL Target] 中强制执行权限的方式，以及如何使用“[!UICONTROL 属性]”和“[!UICONTROL 权限]”功能强制执行这些权限。

新 [!UICONTROL 权限] 利用功能，可创建不同的项目（在中称为“产品配置文件”） [!DNL Adobe Admin Console for Enterprise])。 通过项目，可为单个用户分配不同的权限，而这些权限规定该用户对于每个项目的访问权限。 这些不同的项目好比 [!DNL Adobe Analytics] 中各个报表包的工作方式。每个项目都可以拥有其特定用户，而这些用户可以具有适用于一组属性的特定角色。结果是客户能够根据区域、环境（开发/暂存/生产）、渠道或其他自定义标准限制其用户的查看、编辑和审批访问权限，如下所示：

![权限图像](assets/permissions.png)

例如，某一位特定用户可能在美国网站上具有“批准”访问权限，但在欧洲移动设备应用程序上仅具有“查看”访问权限。该用户可能无法访问甚至无法查看亚太地区的 Web 和移动设备属性上提供的活动。

当前 [!DNL Target][!UICONTROL “权限]”模型具有三种权限角色（观察者、编辑者和审批者），如下图所示：

![permissions_1图像](assets/permissions_1.png)

每个角色都具有不同级别的权限：

| 角色 | 描述 |
|--- |--- |
| 审批者 | 可以创建、编辑，以及激活或停止活动。 |
| 编辑者 | 可以在活动激活前创建和编辑活动，但不能批准启动活动。 |
| 观察者 | 可以查看活动，但不能创建或编辑活动。 |
| 发布者 | 类似于观察者角色（可查看活动，但无法创建或编辑活动）。但是，发布者角色另有激活活动的权限。 |

请注意，每个用户的角色都适用于您帐户中包含 [!DNL Target] 标记的每个页面、属性或网站，如下所示：

![permissions_2图像](assets/permissions_2.png)

新的 [!DNL Target][!UICONTROL “权限]”模型具有相同的三种权限角色（观察者、编辑者和审批者）；但是，您可以为各个页面、属性或网站分别分配用户的权限角色，如下所示：

![permissions_3图像](assets/permissions_3.png)

在此示例中，Jan 拥有美国主页和美国网站的审批者权限，拥有法国网站的观察者权限。

此外，Jan在中看不到页面、属性或网站 [!DNL Target] 她没有权限查看的区段，如下所示：

![permissions_4图像](assets/permissions_4.png)

在此示例中，Jan 无法查看产品页面、俄罗斯网站和职业网站。

## 用例方案 {#section_F3CE8576959E4F4CB13BEEED38311DD8}

以下用例可能有助于了解属性、项目、角色和权限如何帮助您通过 [!DNL Target] 实现营销目标：

### 跨国组织

如果您所在的组织是跨国组织，则您可能拥有两个工作区：一个用于欧洲网页、属性或网站，而另一个用于美国网页、属性或网站。重组后，使用上图中的人物，您可以设置类似于以下所述的工作区和权限：

* **Jan**：Jan 是该组织美国网页、属性和网站的卓越中心优化负责人。她可能在 Adobe Experience Cloud 中拥有系统管理员权限。

  在她的角色中，她拥有美国主页和美国网站的审批者权限。在拥有审批者权限的情况下，她可以创建、编辑以及激活或停止活动。

  Jan 还需要咨询法国的优化团队，因此她拥有法国网站的观察者权限，对活动拥有只读访问权限。Jan 可以查看活动，但不能创建或编辑这些活动。

  由于 Jan 不具有允许她查看产品页面、俄罗斯网站或职业网站的角色，因此她无法查看这些网站的活动。

* **Ernie**：Ernie 是该组织的营销经理，负责美国市场的营销工作。

  由于Ernie是组织的新人，并且没有使用Target的经验，因此他具有美国主页、美国网站和产品页面的编辑者权限。 拥有编辑器权限的Ernie可以在活动上线之前创建和编辑活动。他无法批准活动的启动 — 具有批准权限的用户（如Jan）必须先批准该活动，然后才能将其投入生产。

  由于 Ernie 不具有允许他查看俄罗斯网站、法国网站或职业网站的角色，因此他无法查看这些网站的活动。

* **Diana**：Diana 现在是该组织的分析师，并拥有美国主页、美国网站、产品页面、俄罗斯网站和法国网站的观察者权限，因此她能够以只读方式访问活动。Diana 可以查看活动，但不能创建或编辑这些活动。

  由于 Diana 不具有允许她查看职业网站的角色，因此她无法查看这些网站的活动。

### 多品牌组织

如果您是多品牌组织的成员，则可以为每个品牌的网页、属性或网站设置单独的工作区。

重组后，使用上图中的人物，您可以设置类似于以下所述的项目和权限：

* **Jan**：Jan 是一家医疗保健组织卓越中心的优化负责人，该组织在医院产品和消费品领域开展业务。她可能在 Adobe Experience Cloud 中拥有系统管理员权限。

  在她的角色中，她拥有医院网站的审批者权限。在拥有审批者权限的情况下，她可以创建、编辑以及激活或停止活动。

  Jan 还需要咨询客户产品领域的优化团队，因此拥有该网站的观察者权限，对活动拥有只读访问权限。Jan 可以查看活动，但不能创建或编辑这些活动。

* **Ernie**：Ernie 是组织的营销经理，负责客户产品领域的市场营销。

  由于Ernie是组织的新人，并且没有使用Target的经验，因此他具有消费者网站的编辑者权限。 拥有编辑器权限的Ernie可以在活动上线之前创建和编辑活动。他无法批准活动的启动 — 对于具有“消费者网站”的批准权限（在此场景中不是Jan）的用户，必须先批准该活动，然后才能将其投入生产。

  因为 Ernie 不具有允许他查看医院网站的角色，所以他无法查看该网站的活动。

* **Diana**：Diana 现在是该组织的分析师，并获得了医院网站和客户网站的观察者权限，因此她能够对活动进行只读访问。Diana 可以查看活动，但不能创建或编辑这些活动。

## Target UI属性和权限接触点 {#section_3414371393BB42999A268628B5456EC9}

您可以在 [!DNL Target] UI 中的各个位置看到新的权限功能。

* **“工作区”（“产品配置文件”）下拉列表：**“工作区”下拉列表显示在“[!UICONTROL 活动]”、“[!UICONTROL 受众]”和“[!UICONTROL 选件]”页面的顶部。选择所需的工作区对列表进行筛选，可以只显示所选工作区中的项目。

  ![workspace_drop下拉图像](assets/workspace_drop-down.png)

* **活动创建：** 创建活动时，会在当前选定的工作区中创建该活动。 在第一个对话框中，您会看到渠道选择选项，从中可为活动选择所需的渠道：Web、移动设备应用程序、电子邮件或其他/API。

  ![channel_options图像](assets/channel_options.png)

* **受众创建：** 创建受众时，会在当前选定的工作区中创建该受众。
* **受众列表：** 您可以使用在工作区之间移动受众 [!UICONTROL 更多操作] > [!DNL Move] 上的选项 [!UICONTROL 受众] 页面。
* **选件创建：** 创建选件时，会在当前选定的工作区中创建该选件。
* **“属性”页（“管理”>“属性”）：** 您可以使用 [!UICONTROL Search] 框以搜索 [!UICONTROL 属性] 列表。

  ![properties_list图像](assets/properties_list.png)

## 注意事项 {#section_9714311B1CD9497A86F4910F8AE635E2}

在中使用或配置属性和权限时，请考虑以下事项 [!DNL Target] Premium：

* **重要信息**：请勿删除包含活动的工作区。如果删除包含活动的工作区，请与客户关怀团队合作以恢复这些活动。
* 在使用“我的所有工作区”视图时：

   * 您可以查看您拥有适当角色和访问权限的所有工作区的活动、受众和选件。
   * 当您选择 [!UICONTROL 我的所有工作区] 视图，则会在“活动”、“受众”和“选件”页面中添加新列。 此列列出项目的工作区以及与该项目关联的用户权限（观察者、编辑者或审批者），
   * 在“我的所有工作区”视图中创建活动、受众或选件时，必须选择要在其中创建项目的工作区。只能选择您拥有编辑者或审批者权限的工作区。
   * 在“我的所有工作区”视图中复制活动、受众或选件时，必须选择要在其中复制项目的工作区。只能选择您拥有编辑者或审批者权限的工作区。

* 以下内容上的任何设置 [!UICONTROL 管理] 页面可由任何 [!UICONTROL 审批者] 在任何工作区中：

   * 可视化体验编辑器
   * 报表
   * Scene7配置
   * 实施
   * 属性
   * 主机
   * 环境
   * 响应令牌
   * 用户

* 用户无法将资源从一个工作区（产品配置文件）移动到另一个工作区。但是，可以将资源从一个工作区（产品配置文件）复制到另一个工作区。
* 从 [!DNL Audiences] 页面查看受众时，页面加载速度低于预期。如果您以任何方式与搜索栏进行互动，则会加快受众的显示速度。此问题已知，并将在即将到来的更新中修复。 此问题不会影响在活动创建工作流中选择受众。
* 以下资源属于新的企业权限模型的一部分：

   * 在中创建的活动、受众和代码选件 [!DNL Target Standard/Premium] 在客户启用权限后即可使用。 (注意：客户必须有权享有 [!DNL Target Premium].)
   * 可以将属性添加到默认工作区中的现有活动；但是，此方法可能会发生更改。
   * 只有在Target Premium中创建的新资源（例如活动、代码选件和受众）才能按权限进行限制（启用企业权限后）。
   * 外部资源仅供默认工作区中的用户使用。默认工作区中的用户角色会应用到全局（适用于所有 Target 请求和所有 Target 资源）。

* 以下资源&#x200B;*不*&#x200B;属于新的企业权限模型的一部分：

   * 图像选件
   * 所有“推荐”资源，其中包括标准库、设计库、目录、推荐设置。
   * 在启用企业权限之前，可以复制在Target Premium中创建的现有资源（例如活动、代码选件和受众），但不能将这些资源移动到其他工作区。
   * 使用以下解决方案或方法创建的活动、受众、代码选件、图像选件或任何其他资源不受企业权限模型控制，但属于默认工作区的一部分：Target Classic、Adobe Experience Manager (AEM)、AdobeMobile Services以及通过API创建的资源。 通过 API 创建的资源（包括活动、受众、代码选件和图像选件）。
   * 图像选件（存储在以下位置的资产） `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library` 当前无法受企业权限模型控制。
   * 当目标链接或目标页面是包含在活动中的属性的一部分时，clickTracking和重定向会起作用。 此外，使用时，clickTracking可能无法正常工作 `targetPageParams()` 函数。 `targetPageParamsAll()` 是推荐的函数。

  [!DNL Target]目前， 要求执行跟踪的任何页面上都具有 `at_property` 令牌。如果令牌：(1)不存在，(2)在进行活动设置（在VEC内）时未被检测到，或者(3)未通过 `targetPageParamsAll()` 函数中，指标不递增，且显示为“0”。

  这同样适用于使用重定向的活动。目标页面必须具有 `at_property` 令牌，并可在 VEC 内进行设置时被识别。

  在将来的版本中，即使在不具有 `at_property` 令牌的页面或具有不同 `at_property` 令牌的页面上，Target 也将能正常工作。

* Adobe I/O API 调用不支持企业用户权限功能。

## 常见问题解答 {#faqs}

关于企业权限的常见问题解答包含以下内容：

### 如果用户具有多个角色和权限会怎样？[#multiple-roles]

如果用户拥有多个角色和权限，则应用具有层级权限的角色。 例如，如果用户拥有 [!UICONTROL 观察者] 和 [!UICONTROL 审批者] 角色， [!UICONTROL 审批者] 角色已应用。

### 我是否可以将活动从一个工作区移动到另一个工作区？

很遗憾，您无法将活动从一个工作区移动到另一个工作区。但是，您可以在知道报告数据不会沿用原有内容的情况下将活动复制到任何工作区。 有关详细信息，请参阅[使用工作区时复制/编辑活动](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6)中的“使用工作区时复制/编辑活动”。

迁移之前创建的活动将继续在默认工作区中以相同的方式运行，除非已对它们进行编辑，已为它们分配属性。特定工作区下的活动会遵循分配给该工作区的属性，因此，行为可能与迁移之前不同。

### 我是否可以将受众从一个工作区移动到另一个工作区？ {#move-audience}

可以，您可以使用在工作区之间移动受众 [!UICONTROL 更多操作] 上的选项 [!UICONTROL 受众] 页面。

1. 单击 **[!UICONTROL 更多操作]** 按钮（三个省略号），然后单击 **[!UICONTROL 移动]**.

   ![更多操作>移动](/help/main/administrating-target/c-user-management/property-channel/assets/move-audience.png)

1. 从中选择所需的工作区 **[!UICONTROL 工作区]** 下拉列表，然后单击 **[!UICONTROL 移动]**.

   ![选择要移至新工作区的所需受众](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-move.png)

>[!NOTE]
>
>您必须具有相应的权限才能编辑受众。 此外，受众不得用于其他活动。 如果受众正在其他活动中使用，并且您仍希望将该受众移动到其他工作区，请从正在使用受众的其他活动中删除该受众。

### 为什么我会收到一则错误消息，指示没有与此活动相关联的属性，即使分配了属性也是如此？

如果您实施了 [!DNL Target] 带有标记的 [!DNL Adobe Experience Platform] 并收到一则错误消息，指示没有与活动关联的属性，请传递 `at_property` 参数和 `targetPageParams` 函数。

### 如果重定向页面和活动 URL 属于不同的属性，那么是否会记录点击跟踪转化？

如果页面和活动 URL 属于不同的属性，则不会在该页面上记录点击跟踪。

请考虑下列情景︰

* 页面 1 属于属性 1。
* 页面 2 属于属性 2。
* 在活动中，页面 1 重定向到包含点击跟踪的页面 2。

当访客在浏览器中打开页面1时，访客将被重定向到页面2。 由于页面 2 并不符合交付活动的条件，因此其 Target 调用在响应中不包含点击跟踪。

如果重定向页面和活动 URL 属于同一属性，则点击跟踪可按预期工作。有关更多信息，请参阅[点击跟踪](/help/main/c-activities/r-success-metrics/click-tracking.md)。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 培训视频：企业权限培训视频 ![“概述”标记](/help/main/assets/overview.png)

学习目标：

* Adobe Target 用户可以具有三个角色级别
* 属性和工作区的概念，以及这些边界和分组如何工作以允许控制用户的访问权限级别
* 贵组织需要考虑的不同属性示例

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### 办公时间： [!DNL Target] Premium工作区

此视频是“办公时间”的录像，“办公时间”是 Adobe 客户关怀团队发起的一项计划。

* 创建工作区（产品配置文件）
* 创建属性
* 添加用户
* 更新实现

>[!NOTE]
>
>[!DNL Target][!UICONTROL 管理] 菜单 UI（以前的[!UICONTROL 设置]）经过重新设计，以提供更好的性能、减少发布新功能时所需的维护时间并改善整个产品的用户体验。以下视频中的信息正确；但是，选项可能位于不同的位置。

>[!VIDEO](https://video.tv.adobe.com/v/23643/)
