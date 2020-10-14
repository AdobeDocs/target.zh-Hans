---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: 发行说明，提供有关最新或即将发布的DNLAdobe Target版本的功能、增强和修复的信息。
title: Adobe Target预发行说明
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 8b1f98e6c05844308e63e2c32255c32d0c126cba
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---


# Target 发行说明（预发行版本）{#target-release-notes-prerelease}

本文包含预发行信息。 发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新：2020 年 10 月 14 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。这些页面上的信息可能相同，具体取决于发布时间。 括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>* **Adobe再次被评为Gartner个性化引擎魔力象限的领导者**:在Gartner 2020年个性化引擎魔力象限报告中，Adobe再次被评为领导者。 Gartner个性化引擎魔力象限评估了属于两个类别的15个供应商：愿景和执行能力的完整性。 [在Adobe博客上阅读相关信息](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/)。
   >
   >
* **mbox.js终止使用**:2021年1月18日，Adobe Target将不再支持mbox.js库。 2021年1月18日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响目标活动运行的页面。 我们建议所有客户在此日期之前迁移到at.js库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请 [参阅At.js工作方式](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) 和 [Adobe Target技能构建器：开发人员聊天，将Adobe Target的mbox.js迁移到at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true)。
   >
   >   
   尽管目前支持mbox.js，但自2017年7月起，我们便未对此库提供功能更新。 较新的at.js比mbox.js具有许多优势。 at.js可缩短Web实施的页面加载时间，提高安全性，并为单页应用程序提供更好的实施选项。
   >
   >   
   通过将所有客户转移到at.js，我们的工程师和支持人员将能够为您提供新功能并优惠您期望从Adobe获得的支持。
   >
   >
* **目标通知**:有关即将进行的目标的信息，请参阅事件公告页，包括目标技能生成器会话、开发人员聊天、网络研讨会和目标咖啡休息会话。 有关详细信息，请参阅 [目标公告](/help/r-release-notes/target-announcements.md)。


## Target Standard/Premium 20.10.1（2020 年 10 月 27 日） 

此版本包含以下新增功能：

| 功能 | 详细信息 |
| --- | --- |
| 设备上决策 | 通过设备上决策，营销人员和产品开发人员可以在用户设备内跨渠道以接近零的延迟，进行实验和机器学习驱动的个性化。<br>速度和性能至关重要——在客户洞察和用户满意度方面。 通过设备上决策，营销人员和现在的产品开发人员可以直接在用户设备内测试和优化体验，从而将实时情境体验的决策和加载时间缩短到接近于零。<br>设备上决策允许您将所有个性化和试验说明编译到“优化对象”上，这些对象加载到客户设备上。 这些零延迟的伪像为营销人员提供一对一个性化、行为重定位以及实时产品和内容推荐，同时为开发人员和产品所有者提供直接代码访问权限，以测试用户体验和目标并分阶段产品发布，从而实时优化。 由于设备内决策与产品本机连接， [!DNL Adobe Experience Cloud] 用户 [!DNL Target] 可以快速分析并更快地体验迭代。<br>**立即注册参加实时网络研讨会。** 与Adobe Target产品专家一起讨论如何在设备上将关键体验优化决策移动到本地执行，同时保持零延迟，这将为激动人心的新用例敞开大门，同时为客户改善站点性能。<ul><li>2020年11月10日</li><li>上午10:00 PT /下午12:00 CT /下午1:00 ET</li><li>[在此处注册](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

此版本包含以下增强、修复和更改：

* 修复了阻止“Total” [!UICONTROL 行的“Average Lift] Confidence Interval [!UICONTROL ”(平均提] 升置信间隔 [!DNL Auto-Target] )和“Confidence [!UICONTROL ”（置信度）以报告显] 示的问题。 正确显示所有个体体验的度量值。 (TGT-37301)
* 修复了从9月 [!DNL Adobe Target Premium] 15日 [!UICONTROL 下午2:30开始影响用] 户自动目标报告的问题。(PDT)10月6日上午9点25分。(PDT)。 查看受影响转化量度的报告(使用“已查[!UICONTROL 看页面]”或“已[!UICONTROL 单击mbox”选项进行配置])时，转化率会错误报告。 此时不存在已知的投放问题。 有关如何重新同步和更正报告的信息，请参 [阅已解决问题和已解](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) 决问题中 ** 的“自动 *目标报告”*。
* 在“目录搜 [!UICONTROL 索”(Catalog Search] )表中添加了可选 [!UICONTROL 的“上次更新时间] ”(Last Updated At)列和“最 [!UICONTROL 后一次更新时间] ”(Last Updated At)筛选器。 此增强功能省时省力，因为您不必打开每个项目来查看上次更新的时间，并且您可以按上次更新项目的日期进行筛选。

   ![上次在列和滤镜处更新的插图](/help/r-release-notes/assets/column-and-filter.png)

* 改进了仅键盘用户的导航和功能。
* 在UI中添加了标签以帮助用户使用辅助技术。
* 改进了UI中图像和文本的文本和颜色对比度。

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
