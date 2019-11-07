---
keywords: 创建推荐;推荐活动;新建推荐;推荐概述
description: 使用 Target 可视化体验编辑器 (VEC)，可直接在启用了 Target 的页面上创建“推荐”活动，并在 Target 中修改页面的各个部分。
title: 创建“推荐”活动
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) 创建推荐活动{#create-a-recommendations-activity}

使用 Target 可视化体验编辑器 (VEC)，可直接在启用了 Target 的页面上创建“推荐”活动，并在 Target 中修改页面的各个部分。

1. 单击&#x200B;**[!UICONTROL 创建活动]** &gt; **[!UICONTROL 推荐]**。

   ![创建“推荐”活动](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![“创建‘推荐’活动”对话框](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   如果您希望使用基于表单的体验编辑器，请选择[!UICONTROL 表单]。请参阅[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了 VEC 和基于表单的体验编辑器之外，Target 还提供单页应用程序 VEC 和适用于移动设备应用程序的 VEC。有关各种编辑器的更多信息，请参阅[体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的[!UICONTROL [选择工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。如果您看不到此选项，则表明贵组织具有 Target Standard 许可证。]

1. （视情况而定）如果您是一位 [Target Premium 客户](/help/c-intro/intro.md#premium)，请选择一个[工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定活动 URL，然后单击&#x200B;**[!UICONTROL 下一步]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 均匹配。

   活动 URL 是指将显示推荐的页面。

   单击“[!UICONTROL 下一步]”后，VEC 将会打开并显示您的页面。您可以将当前元素替换为推荐，也可以插入推荐。

1. 单击页面上的某个元素，如果该元素所在的位置有可用推荐，请单击&#x200B;**[!UICONTROL 替换为推荐]**、**[!UICONTROL 在之前插入推荐]**&#x200B;或&#x200B;**[!UICONTROL 在之后插入推荐]**。

   ![“推荐”选项](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   将元素替换为推荐时，会删除当前内容并将其替换为推荐。

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
   ![“选择页面类型”选项](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. 选择一个或多个[标准](/help/c-recommendations/c-algorithms/algorithms.md)。

   标准会以卡片的形式显示，卡片中提供了每个标准的相关信息。默认情况下，“[!UICONTROL 选择标准]”屏幕会显示您所属的垂直行业的兼容标准以及您选择的页面类型。您可以更改这些选项以显示其他标准。

   >[!NOTE]
   >
   >并非每个标准都能在每个页面上正常运行。页面或 mbox 需要传入 `entity.id` 或 `entity.categoryId`，才能兼容当前项目/当前类别推荐。一般来说，最好只显示兼容的标准。但是，如果您希望不兼容的标准也可用于活动，请清除&#x200B;**[!UICONTROL 兼容]复选框。**[!UICONTROL 兼容]选项可能不会显示，具体取决于您的“推荐”设置（**[!UICONTROL 推荐]** &gt; **[!UICONTROL 设置]** &gt; **[!UICONTROL 筛选不兼容的标准]**）。有关更多信息，请参阅[设置](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)。

   ![“选择标准”对话框](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   如果选择多个标准，则流量会平均拆分到选择的标准中。例如，如果您选择了两个标准，且您的活动设计为将默认内容显示给 20% 的活动参加者，那么 40% 的活动参加者将看到由每个标准控制的推荐。没有选项可以用来更改每个标准的百分比。

   * 要搜索现有标准（例如，如果显示了许多标准卡片），请在搜索字段中键入相应内容直到显示所需标准为止，然后选择该标准，并单击&#x200B;**[!UICONTROL 下一步]**。

      [!DNL Recommendations] 中提供了一些自带标准。您和您的团队也可以创建自己的自定义标准。

   * 要创建新标准，请单击&#x200B;**[!UICONTROL 创建标准]** &gt; **[!UICONTROL 创建标准]**，然后填写有关新标准的信息。有关创建新标准的信息，请参阅[创建标准](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)。
   * 您还可以将标准分组到序列中。要创建新标准序列，请单击&#x200B;**[!UICONTROL 创建标准]** &gt; **[!UICONTROL 创建标准序列]**。有关更多信息，请参阅[创建标准序列](../../c-recommendations/c-algorithms/create-criteria-sequence.md#task_8A9CB465F28D44899F69F38AD27352FE)。

1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 选择一个[设计](/help/c-recommendations/c-design-overview/design-overview.md)。

   设计是一种模板，可决定页面上各个位置的外观。[!DNL Target] 中包含多个预配置的设计。您也可以创建自己的自定义设计。有关更多信息，请参阅[创建设计](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)和[自定义设计](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59)。

   ![“选择设计”对话框](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   每个设计都会以图表形式显示其外观，并且还会显示相应图标来反映当前使用该设计的活跃活动和不活跃活动的数量。

   * 要选择一个或多个现有的设计，请单击相应设计，然后单击&#x200B;**[!UICONTROL 下一步]**。

      如果您选择了多个标准，则只能选择一个设计。

   * 要创建自定义设计，请单击&#x200B;**[!UICONTROL 创建设计]**，然后填写新设计的名称和代码。单击&#x200B;**[!UICONTROL 下一步]**，选择或上传图像，然后单击&#x200B;**[!UICONTROL 完成]** &gt; **[!UICONTROL 完成]**。有关创建新设计的信息，请参阅[创建设计](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。

1. 单击&#x200B;**[!UICONTROL 下一步]**。

   您可以选择向推荐中添加促销活动。有关添加前端和后端促销活动的更多信息，请参阅[添加促销活动](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)。
1. 单击&#x200B;**[!UICONTROL 保存]**。

   VEC 屏幕会显示页面上的推荐设计。

1. （可选）单击&#x200B;**[!UICONTROL 预览]**&#x200B;以查看将向访客显示的活动的外观。

   在“[!UICONTROL 预览]”模式下，您可以像访客一样与推荐进行交互。

   预览完推荐后，单击&#x200B;**[!UICONTROL 撰写]**。

1. 在 VEC 中查看推荐，然后单击&#x200B;**[!UICONTROL 下一步]**。

1. 在流程图中查看 [!DNL Recommendations] 活动，并做出任何必需的更改。

   ![“推荐”流程图](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   流程图会引导您完成以下步骤：选择活动的受众、设置体验以及指定成功量度。

   在流程图中，您可以执行以下操作：

   * 更改将看到推荐的受众

      >[!NOTE]
      >
      >除了选择现有受众之外，您还可以[创建仅限该活动的受众](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)或[合并多个受众](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)以创建临时受众，而不是创建新的受众。

      默认情况下，所有用户都会看到推荐。但是，您可以将推荐定位到特定的受众。

      对于 [!DNL Recommendations] 活动，控制组会看到没有任何推荐的页面。

   * 查看标准
   * 更改收藏集（位于“[!UICONTROL 标准]”标签旁边）
   * 更改看到控制体验的参加者所占的百分比
   * 查看设计代码
   * 更改或删除设计

1. 完成后，单击&#x200B;**[!UICONTROL 下一步]**。
1. 指定活动设置。

   例如，键入活动的名称（必填）和目标（可选）。有关设置的信息，请参阅[“推荐”活动设置](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)。

   >[!NOTE]
   >
   >如果您指定的 [!DNL Recommendation] 活动名称已被 [!DNL Recommendations Classic] 中的其他活动使用，则会使用新名称重新同步新活动。新名称是在原始名称后附加一个时间戳，以使其具有唯一性。此新名称会同时显示在 [!DNL Target Standard/Premium] 和 [!DNL Recommendations Classic] 中。

1. 完成后，单击&#x200B;**[!UICONTROL 保存并关闭]**。

   此时会显示活动概述。

   在“[!UICONTROL 概述]”页面中，您可以：

   * 激活活动
   * 编辑活动
   * 将活动固定到 Experience Cloud 功能板
   * 查看体验 URL
   * 下载数据
   * 更改看到控制体验的活动参加者所占的百分比
   * 显示或隐藏标准详细信息
   * 查看设计的代码

1. （可选）打开[!UICONTROL 报表]页面以查看显示 [!DNL Recommendations] 活动性能的报表。
1. （可选）打开“[!UICONTROL 冲突]”页面以查看可能会发生的任何[活动冲突](/help/c-experiences/c-visual-experience-composer/activity-collisions.md)。

   如果设置了多个活动来向同一个页面交付内容，则会发生活动冲突，这可能导致页面显示意外内容。

## 培训视频：创建“推荐”活动 (7:15)

>[!VIDEO](https://video.tv.adobe.com/v/27688?captions=chi_hans)