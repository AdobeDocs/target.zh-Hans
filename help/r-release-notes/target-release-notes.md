---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 92f5953a96b92175784600d1b04a23ec4d7152ec
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 11%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新日期：2020 年 9 月 15 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>* **Adobe再次被评为Gartner个性化引擎魔力象限的领导者**:在Gartner 2020年个性化引擎魔力象限报告中，Adobe再次被评为领导者。 Gartner个性化引擎魔力象限评估了属于两个类别的15个供应商：愿景和执行能力的完整性。 [在Adobe博客上阅读相关信息](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js弃用**:2021年1月18日，Adobe Target将不再支持mbox.js库。 2021年1月18日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响目标活动运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请 [参阅At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能构建器：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **目标通知**:有关即将进行的目标的信息，请参阅事件公告页，包括目标技能生成器会话、开发人员聊天、网络研讨会和目标咖啡休息会话。 有关详细信息，请参阅 [目标公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.8.3（2020 年 9 月 15 日）

| 功能 | 详细信息 |
| --- | --- |
| ![针对目标](/help/assets/premium.png) (A4T)的高级徽章分析支持自动目标活动 | [!UICONTROL 自动目标] 活动现在支 [持Analytics进行目标](/help/c-integrating-target-with-mac/a4t/a4t.md)。<br>此集成允许您使用自动 [!UICONTROL 目标集成机器学习算法] ，根据每个访客的用户档案、行为和上下文为其选择最佳体验。<br>如果您已实 [施A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) ，以与A/B测试和体验定位活动配合使用，您就可以了！<br>有关详细信息，请 [参阅目标分析(A4T)支持在创建活动时自动分配和自动目标](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)*活动*。 |

## Target Standard/Premium 20.8.2（2020 年 9 月 10 日）

| 功能 | 详细信息 |
| --- | --- |
| ![高级徽章](/help/assets/premium.png) ，控制标准序列中的推荐插槽 | 标准序列现在允许您控制每个推荐标准占用的槽数，使您能够混合和匹配不同类型的项目或不同的算法逻辑。<br>请参 [阅创建条件序列](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) ，了解更多信息。 |

## Target Standard/Premium 20.8.1（2020 年 9 月 2 日）

此版本包含以下增强、修复和更改：

* 修复了在切换组织后加载新的“管理”页面时 [!UICONTROL 导致] 显示错误的问题。 (TGT-37730)
* 修复了导致“管理”>“实施”页上显示错误客户端代 [!UICONTROL 码的显示问] 题。 (TGT-37849)
* 修复了成功加载VEC后，用户有时无法在 [!UICONTROL 可视体验书写器] (VEC)中使用编辑功能的问题。 (TGT-37162)
* 修复了即使安装了VEC Helper扩展，也无法在VEC和增强体验书写器(EEC)中加载页面的问题。 这是由于Google Chrome 80+中的更改。 下载更 [新的VEC Helper扩展](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)。 (TGT-37893)
* 修复了在切换组织后，有时会阻止用户从“管理”>“ [!UICONTROL 实施”页面] 下载at.js的问题。 (TGT-37668)
* 加载时，如果用户多次单击“下载”按钮，则 [!DNL Target] 将禁用“at.js下载”按钮，以阻止发送多个请求。 (TGT-37633)
* 修复了体验 [!UICONTROL 定位] (XT)活动中导致体验在较长时间内显示“获取结果”的问题。 (TGT-37684)
* 改进了仅键盘用户的导航和功能。 （TGT-34479 和 TGT-34473）
* 在UI中添加了标签以帮助用户使用辅助技术。 (TGT-34480)
* 改进了删除活动中当前使用的移动视图端口时的错误消息。 错误消息现在显示：&quot;此视区当前与一个或多个活动关联。 您需要先从这些活动中删除视区，然后才能删除它。” (TGT-37030)
* 在VEC中添加了支持，以允许在与页面中多个元素匹配的css选择器上单击跟踪。 (TGT-37323)
* 修复了阻止特定用户显示活动 [!UICONTROL 列表的问] 题。 显示以下错误消息：&quot;无法获取URL建议。&quot; 在Adobe后端系统中，使用回车符返回其FirstName(FirstName/r/n)的用户发生错误。 (TGT-37330)
* 修复了当工作区名称(在Enterprise中指 [!UICONTROL 定] )包含撇号时，用户无法显 [!UICONTROL 示活动页面]的问题。 (TGT-37709)
* 修复了在选择优 [!UICONTROL 化和转换量度时] ，自动分配活动中出现错误消息告知用户选择报表包（即使已指定报表包）的问题。 (TGT-37689)
* 修复了在导航到定位页面然后返回 [!UICONTROL 后] ，有时会导致“目标和设置”页 [!UICONTROL 面上的量度] 为空的问题。 (TGT-37691)
* 修复了导致标准上次修改值不正确的 [!DNL Recommendations] 问题。 (TGT-37666)
* 修复了导致mbox ID显示在Mbox下拉列表而不是mbox名称中的问题。 (TGT-37739)

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
