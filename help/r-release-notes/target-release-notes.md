---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解 Adobe Target 即将发布的版本中包括的新功能、增强和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的版本中包括什么新功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd7032b915bf1b333fa5cc3cb4825eaa7e4f83fb
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 43%

---

# Target 发行说明（预发行版本）

本文包含预发行版本信息。发布日期、功能及其他信息如有更改，恕不另行通知。

**上次更新：2021 年 10 月 6 日**

要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

>[!IMPORTANT]
>
>**mbox.js 生命周期结束**：从 2021 年 3 月 31 日起，[!DNL Adobe Target] 将不再支持 mbox.js 库。2021 年 3 月 31 日之后，所有从 mbox.js 进行的调用都会失败，并影响您通过提供默认内容而运行 [!DNL Target] 活动的页面。
>
>请迁移到新 [!DNL Adobe Experience Platform Web SDK] 或 at.js JavaScript 库的最新版本，以避免您的网站出现任何潜在问题。有关更多信息，请参阅[概述：为客户端 Web 实现 Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)。

## [!DNL Target Standard/Premium] 21.10.1（2021年10月6日）

此版本包含以下新功能：

| 功能 | 详细信息 |
| --- | --- |
|  受众UI刷新 | 作为[!DNL Adobe Target]团队持续努力改善[!DNL Target]用户用户体验的一部分，此版本会刷新[!DNL Target] UI中的[!UICONTROL Audiences]和[!UICONTROL 配置文件脚本]页面。 此更新可统一和标准化以前不一致的设计模式，同时添加新的增强功能，例如：<ul><li>能够同时选择和删除多个受众</li><li>刷新的[受众生成器设计](/help/c-target/c-audiences/create-audience.md)</li><li>[!UICONTROL Audience]库规则生成器中支持排除规则</li><li>新的“受众源”过滤器，允许更快地发现受众</li><li>会话永久搜索和过滤选项</li></ul>有关更多信息，请参阅[受众](/help/c-target/target.md)。<br>**注意**:下周，  新的 [!UICONTROL 受众] 和配置文件脚本UI将推出到所有区域。 |
| [!UICONTROL 配置文] 件脚本UI刷新 | [!UICONTROL 配置文件脚本]库也已更新，其中包括更新的界面以及若干生产效率更新：<ul><li>能够同时选择和删除多个配置文件脚本</li><li>配置文件脚本的新代码编辑器</li><li>代码编辑器中的语法突出显示和错误检查</li><li>通过键盘快捷键自动完成令牌（mbox或配置文件）参数</li></ul>有关更多信息，请参阅[访客配置文件](/help/c-target/c-visitor-profile/visitor-profile.md)。<br>**注意**:下周，  新的 [!UICONTROL 受众] 和配置文件脚本UI将推出到所有区域。 |
| ![Premium徽](/help/assets/premium.png) 章推荐标准创建和编辑 | [!UICONTROL Recommendations标准]创建和编辑工作流已得到简化，可简化选择正确的推荐算法和设置以实现您的目标。<br>有关更多信息，请参阅 [创建标准](/help/c-recommendations/c-algorithms/create-new-algorithm.md)。 |
| ![Premium徽](/help/assets/premium.png) 章推荐回顾窗口和算法刷新率改进 | 您现在可以运行“查看次数最多”和“最畅销商品”算法，并在六小时的回顾时间范围内捕获最新趋势内容。 选择六小时回顾窗口后，每3到6小时更新一次推荐结果。<br>有关更多信息，请参 [阅创](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 建标 *准*&#x200B;中的数据源。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

若要提前了解有关 Target 和其他 Adobe Experience Cloud 解决方案即将推出的产品增强功能的通知，请注册“Adobe 产品更新早知道”：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
