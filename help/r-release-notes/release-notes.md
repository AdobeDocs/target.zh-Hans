---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: 这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能、修复信息和已知问题。
title: 'Adobe Target 发行说明（当前版本） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: dd8d7dfe058114183b75d104206393309bb8a789

---


# Target 发行说明（当前版本）{#target-release-notes-current}

这些发行说明介绍了每个 Target Standard 和 Target Premium 版本的功能、增强功能和修复信息。此外，还包含Target API、SDK、JavaScript库(at.js)的发行说明以及其他平台更改（如果适用）。

>[!NOTE]
>
>* **TLS支持更改**:从2020年3月1日开始，Target将禁用对TLS 1.1和TLS 1.0加密的支持。 传输层安全性 (TLS) 是当前使用的部署最广泛的安全协议，可用于 Web 浏览器和其他需要通过网络安全交换数据的应用程序。需要进行此更改以符合TLS 1.2或更高版本的公认安全合规标准。 检查您当前使用的TLS版本。 如果您的版本低于1.2，请在2020年3月1日之前实施所需的更改，以便继续按预期使用Target。
   >
   >   
   有关可能的影响以及更新实施时可能需要采取的步骤的详细信息，请参阅 [TLS（传输层安全）加密更改](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)。
   >
   >
* **mbox.js弃用**:2020年8月30日，Adobe Target将不再支持mbox.js库。 2020年8月30日之后，从mbox.js发出的所有调用都将失败，并会影响已运行Target活动的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   尽管目前支持mbox.js，但自2017年7月以来，我们尚未对此库提供功能更新。 较新的at.js比mbox.js有许多优势。 除其他优势外，at.js还缩短了Web实施的页面加载时间，提高了安全性，并为单页应用程序提供了更好的实施选项。
   >
   >   
   通过将所有客户迁移到at.js，我们的工程师和支持人员将能够为您提供新功能并为您提供Adobe所期望的支持。
   >
   >
* 括号中的问题编号供 [!DNL Adobe] 内部使用。


## Target Standard/Premium 20.2.1（2020 年 3 月 9 日）

>[!IMPORTANT]
>
>请参阅上述关于mbox.js弃用的信息。

此版本包含以下增强、修复和更改：

* 修复了客户在执行目录搜索时无法选择集合的问题。 (TGT-36230)
* 修复了通过API创建的条件（但未由在目标UI中创建的活动引用）可能从UI中错误删除的问题。 (TGT-35917)
* 对内容安全策略(CSP)实施了安全改进。 (TGT-36190)
* 修复了在将“属性加权”百分比条滑向最左侧时，导致显示“NaN%”的问题。 (TGT-36211)
* 解决了本地化问题，以便正确显示不同语言的UI文本。
* 对于2020年3月发布的Analytics for Target(A4T)，不再支持以下Adobe Analytics指标：
   * averagevisdepth
   * 机器人
* 不再支持以下度量，并在用户首次修改包含度量的活动时自动转换为度量的新版本：

   | 已弃用的度量 | 新建量度 |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (附注：以分钟而非秒为单位) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Adobe Experience Cloud导航（2019年2月22日）

* 登录到时，您 [!DNL Adobe Experience Cloud]将转到新的标题导航。 它看起来与上一个导航非常相似，顶部有黑条，但它提供了以下改进：

   * 更轻松地在 [!DNL Identity Management System] (IMS)组织之间切换或切换到其他解决方案。
   * 改进的用户帮助：搜索结果包括产品文档中的结 [!DNL Target] 果、社区论坛和更多视频内容，让您能够更轻松地访问更多内容，从而帮助您发挥最大作用 [!DNL Target]。 我们还在“帮助”菜单中添加了反 [!UICONTROL 馈机制] ，使报告问题或分享您的想法更加容易。

   * 改进了Net Promoter Score(NPS)反馈功能，因此调查模式不会干扰您的工作流。
   * 改进了登录流程。 以前，所 [!DNL Target] 有客户在单击标题中的图标后都登 [!DNL Target] 录到Target登录页面。 然后，此页允许客户继续执行 [!DNL Target Standard/Premium]、 [!DNL Search&Promote]或 [!DNL Recommendations Classic]，如下所示：

      ![登陆页面](/help/r-release-notes/assets/landing.png)

      我们为所有客户取消了此登录页面。 现在，您始终可以通过单击新标题导 [!UICONTROL 航栏中的图标，直][!DNL Target] 接转到“活动列表”页面。

      如果您使 [!DNL Recommendations Classic]用，您可以直接转到解决方案，也可以从在“推荐”选项卡上创建的简短链 [!UICONTROL 接] ，如下所示：

      ![Recs Classic深层链接](/help/r-release-notes/assets/recs-classic.png)

      如果您使 [!DNL Search&Promote]用，则需要直接转到 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)。 从内部到达 [!DNL Search&Promote] 的路径已 [!DNL Adobe Target] 完全删除。

   * 标题 [!DNL Target] 的“通知”下拉框 [!UICONTROL 中] ，当前不提供通知。
   >[!NOTE]
   >
   >作为新导航栏转出的一部分，您还会注意到一些URL更改。 所有以前已添加书签的链接将继续有效，但我们建议您为新链接加入书签以加快打开速度。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明——目标服务器端API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | 与Adobe Target的服务器端API相关的发行说明。 |
| [发行说明——目标Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | 与Adobe Target的Node.js SDK相关的发行说明。 |
| [发行说明——目标Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | 与Adobe Target的Java SDK相关的发行说明。 |
| [at.js 版本详细信息](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | 有关Adobe Target at.js JavaScript库各版本中更改的详细信息。 |
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
