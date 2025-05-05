---
keywords: Target 故障诊断;默认内容;测试未处于实时状态;活动未处于实时状态;定位无法运行;显示之前的体验;无法创建活动;创建活动;页面结构发生更改;页面结构已修改;错误消息;删除配置文件脚本时出错;ajax 无法运行
description: 查找如果您的网站上不显示您的 Adobe [!DNL Target] 活动的故障排除建议。
title: 如何为活动排除故障？
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 44%

---

# 活动故障诊断

如果您的网站上不显示您的 [!DNL Adobe Target] 活动，这些故障排除建议应该能帮助您找到解决方案。

>[!NOTE]
>
>除了以下故障诊断信息之外，还可以参阅 [Target 故障诊断](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839)，以获取指向以下内容的链接：其他故障诊断主题、常见问题解答，以及有关 [!DNL Adobe Target] 中活动故障诊断以及其他功能的其他有用信息。

以下各节包含您可能遇到的问题及建议的解决方案。

## 我使用 [!DNL Target] UI 创建了一个活动，但无法通过 API 更新它。

应通过[!DNL Target] UI更新使用[!DNL Target] UI创建的活动。 应通过 API 更新通过 API 创建的活动。例如，如果您最初使用API创建活动，但随后又通过[!DNL Target] UI编辑该活动，则并非所有更改都会更新。 所有更改都存储在后端，可通过再次调用API更新这些更改。

作为最佳实践，请尝试使用最初用于创建该活动的相同方法（UI 或 API）更新该活动。

## 您看到的是默认内容。

确保您的活动已完成且已激活。

## 活动未处于实时状态。

**验证：**&#x200B;转到[!UICONTROL Overview]选项卡，然后查看测试是否标记为不活动或草稿。

**选项：**

* 激活测试。
* 使用“预览链接”显示不活跃的测试。

## 您不符合受众定位条件。

**验证：**&#x200B;查看“概述”页面上的定位条件。

**选项：**

* 符合条件后重试。
* 使用“预览链接”绕过定位条件。

## 页面不符合页面定位条件。

**验证：**&#x200B;在[!UICONTROL Overview]页面上，确定页面是否在定位条件之外。

**选项：**

* 转到[!UICONTROL Visual Experience Composer]，单击“URL”>“高级”>“当前页面”。

## 显示的是之前的体验而不是新体验。

**验证：**&#x200B;尝试使用以下任一选项，然后重新尝试查看体验。

**选项：**

* 清除缓存和 Cookie，然后重试。
* 尝试使用其他浏览器。
* 使用私密/隐身模式。

## 您最近已被添加到 [!DNL Target]，但无法创建活动。

**验证：**&#x200B;单击[!UICONTROL Create Activity]。 如果此选项不可用，很可能是因为您未获得足够的权限来创建活动。

**选项：**

在[!DNL Target]中将您添加为用户后，您需要具有[!UICONTROL Approver]角色才能创建活动。

* 要求帐户管理员将您设为批准者。
* 如果您是管理员，请在[!DNL Target]中授予&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**&#x200B;中的[!UICONTROL Approver]角色。

  请参阅[为您自己分配“审批者”角色](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

## 设置活动后，页面的结构发生了更改。

**验证：**&#x200B;转到现有活动的[!UICONTROL Visual Experience Composer]。 查找指示选择器（或结构）已发生更改的警告消息。

**选项：**

* 重新构建活动。

有关页面修改如何影响[!DNL Target]显示能力的详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 页面的结构在页面加载期间（运行时）发生了修改。

**验证：**&#x200B;询问开发人员。

**注意：**&#x200B;为使[!DNL Target]能够识别应应用活动更改的位置，请避免动态插入具有相同类的元素或动态修改任何同级的类。

**选项：**

* 更新页面代码以唯一标识每个测试的元素（使用id）。
* 停止对上述类或同级元素进行动态修改。

有关页面修改如何影响[!DNL Target]显示能力的详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)。

## 同一页面上有其他活动在运行。

**验证：**&#x200B;使用[!UICONTROL Collisions]选项卡查看其他活动是否正在运行。

**注意：**&#x200B;[!UICONTROL Collisions]选项卡不适用于模板测试模块。

**选项：**

* 提高此活动的优先级。
* 降低其他活动的优先级。
* 停用其他活动。

## 删除配置文件脚本时出现错误消息。

**验证：**&#x200B;从[!DNL Target]中删除配置文件脚本将显示错误消息“无法删除配置文件脚本”。

**选项：**

执行以下操作之一：

* 再次删除配置文件脚本。 显示成功删除消息。
* 等待大约10分钟，以运行[!DNL Target]导入程序。 导入程序会更新配置文件脚本列表。

## 某些 ajax [!DNL Target] 调用不起作用。

**注意：**&#x200B;同名但参数不同的多个ajax [!DNL Target]调用无法在同一页面上工作。 只进行第一次调用。

## 您使用[!DNL Target] API激活了一个活动，但该活动在[!DNL Target] UI中显示[!UICONTROL Inactive]状态。

执行某些操作时，例如使用[!DNL Target] API在UI外部激活活动，可能需要最多10分钟才能将更新传播到UI。

## 活动转换后，访客没有任何体验。

在极少数情况下，如果在与活动资格相同的请求中发送了活动用于判断体验资格的转化量度，则在发送请求后，访客可能不在任何体验中。 在此情况下，访客会看到默认内容，且通过令牌捕获的体验ID将为–1。 [!DNL Adobe]不建议在同一[!DNL Target]请求中发送活动资格和转化。

如果要在同一请求中发送这两个量度，则可以使用[!UICONTROL Advanced Settings]指定在转换后访客保持相同的体验。
