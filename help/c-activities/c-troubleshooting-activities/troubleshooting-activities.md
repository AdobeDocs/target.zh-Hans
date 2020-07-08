---
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity not live;targeting not working;previous experience displays;cannot create activities;can't create activities;create activities;page structure changed;page structure modified;error message;error delete profile script;ajax not working
description: 如果您的活动未显示在网站上，这些故障诊断建议应该可以帮助您找到解决方法。
title: 活动故障诊断
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 81%

---


# 活动故障诊断{#troubleshoot-activities}

如果您的活动未显示在网站上，这些故障诊断建议应该可以帮助您找到解决方法。

>[!NOTE]
>
>除了以下故障诊断信息之外，还可以参阅 [Target 故障诊断](../../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839)，以获取指向以下内容的链接：其他故障诊断主题、常见问题解答，以及有关 [!DNL Adobe Target] 中活动故障诊断以及其他功能的其他有用信息。

以下章节包含您可能遇到的问题及建议的解决方案。

## 我使用活动UI创建了目标，无法通过API更新它。

使用目标UI创建的活动应通过目标UI进行更新。 通过API创建的活动应通过API更新。 例如，如果您最初使用API创建活动，但随后通过目标UI编辑活动，则并不更新所有更改。 所有更改都存储在后端，并可以通过进行另一个API调用来更新。

作为最佳实践，请尝试使用最初创建活动时所用的相同方法（UI或API）更新活动。

## 您看到的是默认内容。

确保您的活动已完成，且已激活。

## 活动未处于实时状态。

**验证：**&#x200B;转到“概述”选项卡，然后查看测试是否标记为不活跃或草稿。

**选项：**

* 激活测试。
* 使用“预览链接”显示不活跃的测试。

## 您不符合受众定位条件。

**验证：**&#x200B;查看“概述”页面上的定位条件。

**选项：**

* 符合条件后重试。
* 使用“预览链接”绕过定位条件。

## 页面不符合页面定位条件。

**验证：**&#x200B;在“概述”页面上，确定页面是否在定位条件范围之外。

**选项：**

* 转到可视化体验编辑器，然后单击“URL”>“高级”>“当前页面”。

## 显示的是之前的体验而不是新体验。

**验证：**&#x200B;尝试使用以下任一选项，然后重新尝试查看体验。

**选项：**

* 清除缓存和 Cookie，然后重试。

* 尝试使用其他浏览器。
* 使用私密/隐身模式。

## 您最近已被添加到 Target，但无法创建活动。

**验证：**&#x200B;单击创建活动。如果此选项不可用，很可能是因为您未获得足够的权限来创建活动。

**选项：**

作为用户添加到 Target 后，您需要拥有“审批者”角色才能创建活动。

* 请求您的帐户管理员将您设为“审批者”。
* 如果您是管理员，请通过 Target Standard 中的设置 > 用户，为您自己指定“审批者”角色。

   请参阅[为您自己分配“审批者”角色](../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 设置活动后，页面的结构发生了更改。

**验证：**&#x200B;转到现有活动的可视化体验编辑器。查找指示选择器（或结构）已发生更改的警告消息。

**选项：**

* 重新构建活动。

有关页面修改如何影响 Target 显示功能的更多信息，请参阅[页面修改方案](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 页面的结构在页面加载期间（运行时）发生了修改。

**验证：**&#x200B;询问开发人员。

**注意：**&#x200B;为使 Target 能够识别应当应用活动更改的位置，请避免动态插入具有相同类的元素，或避免动态修改任何同级元素的类。

**选项：**

* 更新页面代码，以使其唯一标识将测试的每个元素（使用 id）。
* 停止对上述类或同级元素进行动态修改。

有关页面修改如何影响 Target 显示功能的更多信息，请参阅[页面修改方案](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## mbox.js 使所有后续代码弹出标头部分，而进入主体部分。

**验证：**&#x200B;查看源代码，以确认是否有一个声明跟在 mbox.js 文件之后、结束 </body> 标记之前。

**选项：**

* 将 mbox.js 作为最后一项放入页面的 `<head>` 部分。
* 对主体内最高级别的元素使用唯一的 div id。

## 同一页面上有其他活动在运行。

**验证：**&#x200B;使用“冲突”选项卡，查看是否有其他活动在运行。

**注意：**“冲突”选项卡在“模板测试”模块中不可用。

**选项：**

* 提高此活动的优先级。
* 降低其他活动的优先级。
* 停用其他活动。

## 删除配置文件脚本时出现错误消息。

**验证：**&#x200B;从 Target Standard/Premium 中删除配置文件脚本时，显示错误消息：“未能删除配置文件脚本。”

**选项：**

执行以下操作之一：

* 重新删除。显示成功删除消息。
* 等待大约 10 分钟，以使 Target Standard/Premium 导入程序运行。导入程序会更新配置文件脚本列表。

## Some ajax [!DNL Target] calls are not working.

**注意：** 使用相同 [!DNL Target] 名称但不同参数的多个ajax调用将不能在同一页面上工作。 只有第一个调用可以运行。

## You activated an activity using the Target API, but the activity shows a status of [!UICONTROL Inactive] in the Target UI.

执行某些操作（例如使用 Target API 在 UI 外部激活活动）时，更新可能最多需要 10 分钟才能传播到 UI 中。