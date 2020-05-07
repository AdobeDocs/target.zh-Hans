---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 21%

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含目标API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!NOTE]
>
>* **mbox.js弃用**: 2020年8月30日，Adobe目标将不再支持mbox.js库。 2020年8月30日之后，mbox.js发出的所有呼叫都将失败，并影响您的目标活动正在运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). 请参 *阅Adobe目标技能生成器： 开发人员聊天，将Adobe目标的mbox.js迁移到下面的at* .js以获取信息。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。


括号中的问题编号供 [!DNL Adobe] 内部使用。

## Adobe目标技能构建器： 开发人员聊天，将Adobe目标的mbox.js迁移到at.js {#skill-builder}

随着mbox.js即将于2020年8月30日弃用，Adobe目标产品经理David Son最近主持了一个开发人员聊天，讨论将mbox.js迁移到at.js的好处。 在接下来的30天内，您可以 [视图网络研讨会录制](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。

## 目标at.js（2020年3月25日）

以下新版目标at.js JavaScript库可用：

* at.js版本2.3.0
* at.js版本1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1（2020 年 3 月 23 日）

>[!IMPORTANT]
>
>请参阅上面有关mbox.js弃用的信息。

此版本包含以下增强、修复和更改：

* 修复了客户在执行目录搜索时无法选择集合的问题。 (TGT-36230)
* 修复了通过API创建但未由在目标UI中创建的活动引用的条件可能会从UI中错误删除的问题。 (TGT-35917)
* 对内容安全策略(CSP)实施了安全改进。 (TGT-36190)
* 修复了在将“属性加权”百分比栏滑至最左侧时，导致“NaN%”显示的问题。 (TGT-36211)
* 解决了本地化问题，以便正确显示各种语言的UI文本。
* 我们通过弃用当前版本的Adobe Analytics API不支持的Adobe Analytics列表，标准化了Adobe Analytics的目标(A4T)活动可用指标的标准化。 这将使我们能够在未来的Adobe目标版本中扩展我们的A4T支持。

   进行了以下更改：

   * “平均页面停留时间”已替换为“平均站点停留时间”。 任何将此用作主要目标量度的活动都将具有“在站点上花费的平均时间”(注： 以分钟而非秒为单位)，在下次编辑活动时，将其选作主要目标量度。
   * “访客”已被“唯一访客”所取代。 使用此度量作为主要目标量度的任何活动在下次编辑该活动时都将选择“唯一访客”作为主要目标量度。

* 以下指标已弃用，在创建新的A4T活动时，不再能选作主目标指标。

   | 已弃用的度量 | 建议的替换指标 |
   |--- |--- |
   | 每日访客、每小时访客、每月访客、季度访客、每周访客、每年访客 | 独特访客 |
   | 平均访问深度 | n/a 不建议作为主要目标指标 |
   | 机器人 | n/a 不建议作为主要目标指标 |
   | 移动崩溃率、移动平均上一会话长度、移动App商店平均排名、移动App性能崩溃率、移动App商店平均评级 | n/a 不建议作为主要目标指标 |

## Adobe Experience Cloud导航（2019年2月22日）

* 登录到时，您 [!DNL Adobe Experience Cloud]将转到新的标题导航。 它看起来与上一个导航非常相似，顶部有黑条，但它提供了以下改进：

   * 更轻松地在 [!DNL Identity Management System] (IMS)组织之间切换或切换到其他解决方案。
   * 改进的用户帮助： 搜索结果包括产品文档 [!DNL Target] 中的结果、社区论坛和更多视频内容，让您能够更轻松地访问更多内容，从而帮助您发挥最大价值 [!DNL Target]。 我们还在“帮助”菜单中添加了 [!UICONTROL 反馈机] 制，使报告问题或分享您的想法更简单。

   * 改进了Net Promoter Score(NPS)反馈功能，因此调查模式不会干扰您的工作流。
   * 改进了登录流程。 以前，所 [!DNL Target] 有客户在单击标题中的图标后 [!DNL Target] 都登录到目标登陆页。 然后，此页允许客户继续执行 [!DNL Target Standard/Premium]、 [!DNL Search&Promote]或 [!DNL Recommendations Classic]，如下所示：

      ![登陆页面](/help/r-release-notes/assets/landing.png)

      我们为所有客户消除了此登陆页。 现在，您始终可以通过单击新 [!UICONTROL 标题导航栏] 中的图 [!DNL Target] 标，直接转到活动列表页。

      如果您使 [!DNL Recommendations Classic]用，您可以直接转到解决方案，也可以从在“推荐”选项卡上创建的简短链 [!UICONTROL 接] ，如下所示：

      ![Recs Classic深层链接](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，您需要直接转 [到Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)。 从内部到 [!DNL Search&Promote] 达的路 [!DNL Adobe Target] 径已完全删除。

   * 标题 [!DNL Target] 的“通知”下 [!UICONTROL 拉框] 中当前不提供通知。
   >[!NOTE]
   >
   >作为新导航栏转出的一部分，您还会注意到一些URL更改。 所有以前已添加书签的链接都可以继续工作，但我们建议您为新链接加入书签，以便更快地打开。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明-目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe目标的服务器端API相关的发行说明。 |
| [发行说明-目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe目标的Node.js SDK相关的发行说明。 |
| [发行说明-目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe目标的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关各版本Adobe目标at.js JavaScript库中更改的详细信息。 |
| [mbox.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | 此页面显示对 mbox.js 的每个版本所做的更改。<br>请注意，mbox.js库不再在开发中。 所有客户都应该从 mbox.js 迁移到 at.js。 |

## 文档更改、以往的发行说明和 Experience Cloud 发行说明 {#section_1BC5F5208DA548E9B4344A0836E4B943}

除了针对每个发行的说明外，以下资源还提供更多其他信息：

| 资源 | 详细信息 |
|--- |--- |
| 文档更改 | 查看可能未包含在这些发行说明中的针对该指南的详细更新信息。<br>有关更多信息，请参阅[文档更改](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)。 |
| 以前版本的发行说明 | 查看与以前版本的 Target Standard 和 Target Premium 中的新增功能和增强功能相关的信息。<br>有关更多信息，请参阅[以前版本的发行说明](../r-release-notes/release-notes-for-previous-releases.md)。 |
| Adobe Experience Cloud 发行说明 | 查看 Adobe Experience Cloud 解决方案的最新发行说明。<br>有关详细信息，请参 [阅Experience Cloud发行说明](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## 预发行信息 {#section_5D588F0415A2435B851A4D0113ACA3A0}

您可以通过以下资源了解下一个 Target 版本即将包含的功能。

| 资源 | 详细信息 |
|--- |--- |
| Adobe 优先产品更新列表 | 若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| 即将推出的发行说明 | 有关当月 Target 发行版本的信息（包括预发行信息），请参阅 [Target 发行说明 - 预发行](/help/r-release-notes/target-release-notes.md)页面。 |
