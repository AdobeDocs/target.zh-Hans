---
source-git-commit: 87c0d2aa67d54dcbc2963be63d2d7ad9c02b6aa9
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 5%
---
# 代码片段

## Target Premium 功能 {#premium-note}

>[!NOTE]
>
>此功能作为 [Target Premium](/help/main/c-intro/intro.md#premium) 许可证的一部分提供。 [!DNL Target Standard] 中没有此功能。

## Target权限更新 {#permissions-update}

>[!IMPORTANT]
>
>具有[!UICONTROL 产品管理员]和[!UICONTROL 系统管理员]权限的[!DNL Target]用户可以编辑[!UICONTROL 管理]页面上的所有设置，无论他们在[!DNL Target]中的角色如何。 没有这些权限的用户对这些设置具有只读访问权限。

## 更新了Target UI {#updated-ui}

>[!NOTE]
>
>2025年新增功能，[!DNL Target]引入了更新的UI和[!UICONTROL 可视化体验编辑器] (VEC)。 单击以下链接以了解详情：
>
>* [[!DNL Target Standard/Premium] 25.2.1（2025年2月17日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：提供[!UICONTROL 活动]、[!UICONTROL 推荐]和[!UICONTROL 可视化体验编辑器] (VEC)在[!DNL Target]中的主要UI更改摘要。
>
>* [[!DNL Target Standard/Premium] 25.1.1（2025年1月9日）发行说明](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：提供[!UICONTROL 选件库]在[!DNL Target]中关键UI更改的摘要。
>
>* [了解 [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md)：提供简要概述以帮助您熟悉[!DNL Target]，并提供更深入的信息和分步说明的链接。
>
>* [[!UICONTROL 可视化体验编辑器]更改](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)： [!DNL Adobe Target Standard/Premium] 25.2.1版本（2015年2月17日）引入了更新的[!UICONTROL 可视化体验编辑器] (VEC)。 本文介绍VEC旧版本与更新版本之间的差异。
>
>* [[!UICONTROL 可视化体验编辑器]选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：本文介绍更新的VEC UI及其选项。
>
>* [[!DNL Target] UI更新常见问题解答](/help/main/c-intro/updated-ui-faq.md)：此常见问题解答是关于新的[!DNL Target] UI和[!UICONTROL 可视化体验编辑器] (VEC)的常见问题，包括导航更改、功能位置以及弃用临时UI版本切换。 无论您是营销人员、开发人员还是管理员，此常见问题解答都可以帮助您顺利过渡并充分利用更新后的UI。

## 活动名称规则 {#activity-name-rules}

活动名称不能以`=`、`+`、`-`或`@`开头。 活动名称也不能包含以下任何字符序列：`;=`、`;+`、`;-`、`;@`、`,=`、`,+`、`,-`、`,@`、`["`或`"]`。

## 在定位步骤中选择受众 {#audience-selection-steps}

1. 要更改受众，请单击右框架中的&#x200B;**[!UICONTROL 替换]**&#x200B;图标（![替换图标](/help/main/assets/icons/Retweet.svg)）。

1. 在&#x200B;**[!UICONTROL 添加受众]**&#x200B;对话框中，[选择所需的受众](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)，然后单击&#x200B;**[!UICONTROL 分配受众]**。

   要创建组合多个受众的受众，请单击&#x200B;**[!UICONTROL 组合受众]**。 有关详细信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md)。

   若要新建一个在[!UICONTROL 受众库]中没有的受众，请单击&#x200B;**[!UICONTROL 创建受众]**。 在[创建受众工作流](/help/main/c-target/c-audiences/audiences.md)中，选择以下选项之一：

   * **[!UICONTROL 受众库]**：创建保存到[!UICONTROL 受众库]的按需受众，该受众可在其他活动中重复使用。
   * **[!UICONTROL 仅限此活动]**：创建未保存到[!UICONTROL 受众库]且只能用于当前活动的[特定活动受众](/help/main/c-target/creating-activity-only-audience.md)。

1. 单击右框中的&#x200B;**[!UICONTROL 访客百分比]**，然后选择您希望参加活动的符合条件的访客所占的百分比。


