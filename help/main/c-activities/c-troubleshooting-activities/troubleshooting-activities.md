---
keywords: Target故障诊断；默认内容；测试未处于实时状态；活动未处于实时状态；定位无法运行；显示之前的体验；无法创建活动；创建活动；页面结构发生更改；页面结构已修改；错误消息；删除配置文件脚本时出错；ajax无法运行
description: 查找如果您的网站上不显示您的Adobe [!DNL Target]活动的故障排除建议。
title: 如何为活动排除故障？
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
TQID: 'https://experienceleague.adobe.com/L-011t7q6c3aICs0ZrM01m9pZByH86FKGiLG1A7Rl2s'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9621044454d3e1b47c06cac2ad5d08cba8e482c0
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 7%
---
# 活动故障诊断入门 {#troubleshooting-activities}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;查找当[!DNL Adobe Target]活动未出现在您的网站上或行为与预期不符时常见问题的解决方案。

>[!ENDSHADEBOX]

有几种原因可能会阻止您的网站上出现[!DNL Adobe Target]活动。 使用以下问题和建议的解决方案来确定原因并应用修复。

>[!NOTE]
>
>除了以下故障诊断信息之外，请参阅[Target故障诊断](/help/main/r-troubleshooting-target/troubleshooting-target.md)，以获取指向以下内容的链接：其他故障诊断主题、常见问题解答，以及有关[!DNL Adobe Target]中活动故障诊断及其他功能的其他有用信息。

## 活动未按预期显示 {#not-displayed}

+++ 您正在查看默认内容

确保您的活动已完成且已激活。

+++

</br>

+++ 活动未处于实时状态

**验证：**&#x200B;在&#x200B;**[!UICONTROL 概述]**&#x200B;选项卡上，检查该活动是否标记为不活跃或草稿。

**选项：**

* 激活活动。
* 使用预览链接显示不活动的活动。

+++

</br>

+++ 您不符合受众定位条件

**验证：**&#x200B;查看&#x200B;**[!UICONTROL 概述]**&#x200B;页面上的定位条件。

**选项：**

* 符合受众条件，然后重试。
* 使用预览链接可绕过定位条件。

+++

</br>

+++ 页面不符合页面定位条件

**验证：**&#x200B;在&#x200B;**[!UICONTROL 概述]**&#x200B;页面上，确定该页面是否在定位条件之外。

**选项：**

* 转到&#x200B;**[!UICONTROL 可视化体验编辑器]**，然后单击“URL”>“高级”>“当前页面”。

+++

</br>

+++ 此时会显示以前的体验，而不是新的体验

**验证：**&#x200B;请尝试以下选项之一，然后尝试再次查看体验。

**选项：**

* 清除缓存和Cookie，然后重试。
* 尝试使用其他浏览器。
* 使用私密或无痕模式。

+++

</br>

+++ 自设置活动以来，页面结构发生了更改

**验证：**&#x200B;转到现有活动的&#x200B;**[!UICONTROL 可视化体验编辑器]**，并查找指示选择器（或结构）已更改的警告消息。

**选项：**

* 重新构建活动。

有关页面修改如何影响[!DNL Target]显示内容的功能的详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md)。

+++

</br>

+++ 页面结构会在页面加载期间（运行时）进行修改

**验证：**&#x200B;询问您的开发人员。

**注意：**&#x200B;若要让[!DNL Target]识别必须应用活动更改的位置，请避免动态插入具有相同类的元素，或动态修改任何同级的类。

**选项：**

* 更新页面代码，以使用ID唯一标识每个测试的元素。
* 停止动态修改类或同级，如上所述。

有关页面修改如何影响[!DNL Target]显示内容的功能的详细信息，请参阅[页面修改方案](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md)。

+++

</br>

+++ 其他活动在同一页面上运行

**验证：**&#x200B;使用&#x200B;**[!UICONTROL 冲突]**&#x200B;选项卡查看其他活动是否正在运行。

**注意：**&#x200B;**[!UICONTROL 冲突]**&#x200B;选项卡不适用于模板测试模块。

**选项：**

* 提高此活动的优先级。
* 降低其他活动的优先级。
* 取消激活其他活动。

+++

## 用户、API和用户界面 {#users-api-ui}

+++ 我使用[!DNL Target] UI创建了一个活动，但无法通过API更新它

应通过[!DNL Target] UI更新使用[!DNL Target] UI创建的活动。 应通过 API 更新通过 API 创建的活动。 例如，如果您使用API创建活动，但稍后通过[!DNL Target] UI编辑该活动，则不会更新所有更改。 所有更改都存储在后端，可通过再次调用API更新这些更改。

作为最佳实践，请使用用于创建该活动的相同方法（UI或API）更新该活动。

+++

</br>

+++ 您最近已被添加到[!DNL Target]，但无法创建活动

**验证：**&#x200B;单击&#x200B;**[!UICONTROL 创建活动]**。 如果此选项不可用，很可能是因为您未获得足够的权限来创建活动。

**选项：**

将您添加为[!DNL Target]中的用户后，您需要&#x200B;**[!UICONTROL 审批者]**&#x200B;角色才能创建活动。

* 要求帐户管理员将您设为批准者。
* 如果您是管理员，请在[!DNL Target]中授予&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 用户]**&#x200B;中的&#x200B;**[!UICONTROL 审批者]**&#x200B;角色。 查看[为您自己分配审批者角色](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)。

+++

</br>

+++ 您使用[!DNL Target] API激活了一个活动，但该活动在[!DNL Target] UI中显示[!UICONTROL 不活动]状态

执行某些操作时，例如使用[!DNL Target] API在UI外部激活活动，可能需要最多10分钟才能将更新传播到UI。

+++

</br>

+++ 删除配置文件脚本时出现错误消息

**验证：**&#x200B;从[!DNL Target]中删除配置文件脚本时，显示错误消息“无法删除配置文件脚本”。

**选项：**

执行以下操作之一：

* 再次删除配置文件脚本。 显示成功删除消息。
* 等待大约10分钟，以运行[!DNL Target]导入程序。 导入程序会更新配置文件脚本列表。

+++

## 调用和转换 {#calls-and-conversion}

+++ 某些ajax [!DNL Target]调用不起作用

**注意：**&#x200B;同名但参数不同的多个ajax [!DNL Target]调用不能在同一页面上工作。 只进行第一次调用。

+++

</br>

+++ 活动转换后，访客没有任何体验

在极少数情况下，如果在与活动资格相同的请求中发送了使访客有资格参加某个体验的活动的转化量度，则该访客在发送请求后可能不在任何体验中。 在此情况下，访客会看到默认内容，且通过令牌捕获的体验ID为–1。 [!DNL Adobe]不建议在同一[!DNL Target]请求中发送活动资格和转化。

如果要在同一请求中发送这两个量度，可以使用&#x200B;**[!UICONTROL 高级设置]**&#x200B;来指定转化后访客保持相同的体验。

+++
