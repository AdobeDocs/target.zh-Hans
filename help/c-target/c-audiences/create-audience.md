---
keywords: audience;audience rules;create audience;creating audience
description: 您可以创建自定义受众并将其保存到 Target 库，以供在活动中使用。您可以复制现有受众，然后对其进行编辑以创建类似受众；此外，也可以合并多个受众。
title: 在 Target 中构建受众
feature: audiences
topic: Advanced,Standard,Classic
uuid: 496dbb9d-cb13-47ee-88bd-ba5920b2ca1c
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 99%

---


# 在 Target 中构建受众{#build-audiences-in-target}

您可以创建自定义受众并将其保存到 Target 库，以供在活动中使用。您可以复制现有受众，然后对其进行编辑以创建类似受众；此外，也可以合并多个受众。

## 受众概述

受众由确定在 [!DNL Target] 活动中包含或排除哪些访客的规则来定义。一个受众定义可以包含多个规则，而每个规则可以包含多个参数。复杂的受众定义使用布尔运算符 AND 和 OR 来连接多个规则和参数，从而允许您精确地控制将哪些网站访客计为活动参加者。

如果使用 AND 连接规则或参数，则任何潜在的受众成员必须满足“所有”**&#x200B;定义条件，才能将其作为参加者包含在内。例如，如果您定义了一个操作系统规则和一个浏览器规则，并使用 AND 连接这两个规则，则只能将同时使用了定义的操作系统“和”**&#x200B;定义的浏览器的访客包含在活动中。

如果使用 OR 连接规则或参数，则任何潜在的受众成员只需满足任一定义条件，即可将其作为参加者包含在内。例如，如果您定义了多个移动设备规则，并使用 OR 连接这些规则，则会将满足“任一”**&#x200B;定义标准的访客包含在活动中。

您可以将两种布尔运算符混合使用来创建复杂的规则；但是，同一规则级别的运算符必须一致。用户界面会自动应用正确的运算符。

例如，以下规则可定位在 Windows 计算机上使用 Chrome *或* Firefox 的访客：

![创建受众](assets/audience_create.png)

>[!NOTE]
>
>务必要避免创建会将所有潜在受众成员都排除在外的规则。例如，某个人不可能同时使用 Chrome *和* Firefox 来访问页面。

## 创建新受众

1. 单击顶部菜单栏中的&#x200B;**[!UICONTROL 受众]**。

   ![](assets/audiences_list.png)

1. 从[!UICONTROL 受众]列表中，单击 **[!UICONTROL + 创建受众]**。

   或

   在[!UICONTROL 受众]列表中，将鼠标悬停在所需受众上，然后单击&#x200B;**[!UICONTROL 复制]**&#x200B;图标，以复制现有受众。然后，您可以对受众进行编辑以创建一个类似的受众。

1. 键入唯一的描述性受众名称。
1. 单击 **[!UICONTROL + 添加规则]**。

   规则可将您的受众限制为网站访客的子集。
1. 选择规则类型。

   每种规则类型都有其自身的参数。请参阅[受众类别](../../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D)，以详细了解如何配置每种类型的受众规则。
1. 定义规则参数。
1. 单击&#x200B;**[!UICONTROL 保存]**。

   新创建的受众需经过几秒钟的处理后才会显示在列表中。如果受众未立即显示在列表中，请尝试搜索该受众或刷新列表。

## 培训视频：创建受众 ![概述徽章](/help/assets/overview.png)

以下视频包含有关创建受众的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)