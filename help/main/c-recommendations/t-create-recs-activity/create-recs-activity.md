---
keywords: 创建推荐;推荐活动;新建推荐;推荐概述
description: 了解如何使用 [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC)创建 [!DNL Recommendations] 活动。
title: 如何创建 [!DNL Recommendations] 活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 51%

---

# 创建[!DNL Recommendations]活动

使用[!DNL Target] [!UICONTROL Visual Experience Composer] (VEC)直接在启用了[!DNL Target]的页面上创建[!DNL Recommendations]活动，并在[!DNL Target]内修改页面的各个部分。

1. 单击&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**。

1. 根据需要选择&#x200B;**[!UICONTROL Visual]**。

   如果您希望使用[!UICONTROL Form-Based Experience Composer]，请选择[!UICONTROL Form]。 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]之外，[!DNL Target]还提供[!UICONTROL Single Page Application] VEC。 有关各种编辑器的更多信息，请参阅[体验和产品建议](/help/main/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定）选择[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定活动URL，然后单击&#x200B;**[!UICONTROL Create]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`]和[!DNL `https://wwww.adobe.com`]都匹配。

   活动URL是显示推荐的页面。

   单击[!UICONTROL Create]后，VEC将打开并显示您的页面。 您可以将当前元素替换为推荐，也可以插入推荐。

1. 单击页面上的某个元素，如果该元素所在的位置有可用推荐，请单击&#x200B;**[!UICONTROL Replace w/ Recommendations]**、**[!UICONTROL Insert Recommendations Before]**&#x200B;或&#x200B;**[!UICONTROL Insert Recommendations After]**。

   只有访问您网站的访客符合推荐资格时，他们才会看到推荐的内容。 不符合推荐条件的访客将看到默认内容。

   ![“推荐”选项](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Replace w/ Recommendations]**：将元素替换为推荐会删除当前内容并将其替换为推荐。 当访客访问您的网站并符合推荐资格时，他们将在指定区域看到推荐项目，而不是现有内容。
   * **[!UICONTROL Insert Recommendations Before]**：在选定元素之前插入推荐，将推荐的内容置于该元素之前。 根据您的页面结构，推荐会显示在所选元素的上方或左侧。
   * **[!UICONTROL Insert Recommendations After]**：在选定元素之后插入推荐，会将推荐的内容放在该元素之后。 根据页面结构，推荐将显示在所选元素的下方或右侧。

   通过&#x200B;**[!UICONTROL Expand Selection]**&#x200B;选项，可展开所选位置（父容器），以帮助您更轻松地识别和包含所需的页面元素。

1. 选择页面类型。

   页面类型可以包括：

   * 购物车页面
   * 类别页面
   * 首页
   * 登录页面
   * 产品页面
   * 搜索结果页面
   * 感谢页面
   * 其他

   ![“选择页面类型”选项](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 选择一个或多个[标准](/help/main/c-recommendations/c-algorithms/algorithms.md)。

   标准会以卡片的形式显示，卡片中提供了每个标准的相关信息。默认情况下，[!UICONTROL Select Criteria]屏幕显示的标准与您的垂直行业以及您在上一步中选择的页面类型兼容。 您可以更改这些选项以显示其他标准。

   >[!NOTE]
   >
   >并非每个标准都能在每个页面上正常运行。页面或 mbox 需要传入 `entity.id` 或 `entity.categoryId`，才能兼容当前项目/当前类别推荐。一般来说，最好只显示兼容的标准。但是，如果您希望不兼容的标准也可用于该活动，请清除&#x200B;**[!UICONTROL Compatible]**&#x200B;复选框。 根据您的Recommendations设置( **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL Filter Incompatible Criteria]**)，可能不会显示[!UICONTROL Compatible]选项。 有关详细信息，请参阅[设置](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}。

   ![“选择标准”对话框](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   如果选择多个标准，则流量会平均拆分到选择的标准中。例如，如果您选择了两个标准，且您的活动设计为将默认内容显示给 20% 的活动参加者，那么 40% 的活动参加者将看到由每个标准控制的推荐。没有选项可以用来更改每个标准的百分比。

   * 要搜索现有标准（例如，如果显示了许多标准卡片），请在搜索字段中键入相应内容直到显示所需标准为止，然后选择该标准，并单击&#x200B;**[!UICONTROL Next]**。

     [!DNL Recommendations] 中提供了一些自带标准。您和您的团队也可以创建自己的自定义标准。

   * 要创建新标准，请单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**，然后填写有关新标准的信息。 有关创建新标准的信息，请参阅[创建标准](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)。
   * 您还可以将标准分组到序列中。要创建新标准序列，请单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**。 有关详细信息，请参阅[创建标准序列](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md)。

1. 单击 **[!UICONTROL Next]**。
1. 选择一个[设计](/help/main/c-recommendations/c-design-overview/design-overview.md)。

   设计是一种模板，可决定页面上各个位置的外观。[!DNL Target]包含多个预配置的设计。 您也可以创建自己的自定义设计。有关详细信息，请参阅[创建设计](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)和[自定义设计](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59)。

   ![“选择设计”对话框](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   每个设计都会以图表形式显示其外观，并且还会显示相应图标来反映当前使用该设计的活跃活动和不活跃活动的数量。

   * 要选择一个或多个现有的设计，请单击这些设计，然后单击&#x200B;**[!UICONTROL Next]**。

     如果您选择了多个标准，则只能选择一个设计。

   * 要创建自定义设计，请单击&#x200B;**[!UICONTROL Create Design]**，然后填写新设计的名称和代码。 单击&#x200B;**[!UICONTROL Next]**，然后选择或上传图像并单击&#x200B;**[!UICONTROL Done]** > **[!UICONTROL Done]**。 有关创建新设计的信息，请参阅[创建设计](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。

1. 单击 **[!UICONTROL Next]**。

   您可以选择向推荐中添加促销活动。有关添加前端促销活动和后端促销活动的详细信息，请参阅[添加促销活动](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。

1. 单击 **[!UICONTROL Save]**。

   VEC 屏幕会显示页面上的推荐设计。

1. （可选）单击&#x200B;**[!UICONTROL Preview]**&#x200B;以查看将向访客显示的活动的外观。

   [!UICONTROL Preview]模式允许您与推荐进行交互，就像访客所做的那样。

   预览完推荐后，单击&#x200B;**[!UICONTROL Compose]**。

1. 在VEC中查看推荐，然后单击&#x200B;**[!UICONTROL Next]**。

1. 在流程图中查看 [!DNL Recommendations] 活动，并做出任何必需的更改。

   ![“推荐”流程图](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   流程图会引导您完成以下步骤：选择活动的受众、设置体验以及指定成功量度。

   在流程图中，您可以执行以下操作：

   * 更改将看到推荐的受众

     >[!NOTE]
     >
     >除了选择现有受众之外，您还可以[创建仅限该活动的受众](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)或[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以创建临时受众，而不是创建新的受众。

     默认情况下，所有用户都会看到推荐。但是，您可以将推荐定位到特定的受众。

     对于 [!DNL Recommendations] 活动，控制组会看到没有任何推荐的页面。

   * 查看标准
   * 更改收藏集（[!UICONTROL Criteria]标签旁边）
   * 更改看到控制体验的参加者所占的百分比
   * 查看设计代码
   * 更改或删除设计

1. 完成后单击&#x200B;**[!UICONTROL Next]**。
1. 指定活动设置。

   例如，键入活动的名称（必填）和目标（可选）。有关设置的信息，请参阅[Recommendations活动设置](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)。

   >[!NOTE]
   >
   >如果您指定的 [!DNL Recommendation] 活动名称已被 [!DNL Recommendations Classic] 中的其他活动使用，则会使用新名称重新同步新活动。新名称是在原始名称后附加一个时间戳，以使其具有唯一性。此新名称会同时显示在 [!DNL Target Standard/Premium] 和 [!DNL Recommendations Classic] 中。

1. 完成后，单击&#x200B;**[!UICONTROL Save & Close]**。

   此时会显示活动概述。

   从[!UICONTROL Overview]页面，您可以：

   * 激活活动
   * 编辑活动
   * 将活动共享到Experience Cloud信息源
   * QA活动
   * 查看体验 URL
   * 下载数据
   * 更改看到控制体验的活动参加者所占的百分比
   * 显示或隐藏标准详细信息
   * 查看设计的代码

1. （可选）打开[!UICONTROL Reports]页面以查看显示[!DNL Recommendations]活动性能的报表。

1. （可选）打开[!UICONTROL Collisions]页面以查看可能会发生的任何[活动冲突](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md)。

   如果设置了多个活动来向同一个页面交付内容，则会发生活动冲突，这可能导致页面显示意外内容。

## 培训视频：创建Recommendations活动(7:15) ![教程徽章](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)
