---
keywords: automated personalization;Audiences;ensemble;random forest;residual variance;error variance;lifetime value
description: 自动个性化活动工作流与其他活动类型的工作流有所不同。
title: 创建自动个性化活动
feature: null
topic: Advanced
uuid: 7d301dc3-6076-4e05-8abc-4978075a881e
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '2039'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) 创建自动个性化活动{#create-an-automated-personalization-activity}

自动个性化活动工作流与其他活动类型的工作流有所不同。

1. 从 Target Standard 的“活动”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 自动个性化]**。

   ![创建活动：自动个性化](/help/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. 要使用可视化体验编辑器 (VEC)，请单击&#x200B;**[!UICONTROL 可视（默认）]**。

   ![“创建自动个性化活动”对话框](/help/c-activities/t-automated-personalization/assets/ap_url-new.png)

   如果您希望使用基于表单的体验编辑器，请选择“[!UICONTROL 表单]”。请参阅[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了 VEC 和基于表单的体验编辑器之外，Target 还提供单页应用程序 VEC 和适用于移动设备应用程序的 VEC。有关各种编辑器的更多信息，请参阅[体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[!UICONTROL 选择工作区]”选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。如果您看不到此选项，则表明贵组织具有 Target Standard 许可证。

1. （视情况而定）如果您是一位 Target Premium 客户，请[选择一个工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 验证或输入活动 URL，然后单击&#x200B;**[!UICONTROL 下一步]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 均匹配。

   此时会在可视化体验编辑器中打开具有指定 URL 的页面。

1. 要命名活动，请单击“名称”字段并键入活动名称。

   ![名称字段](/help/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   活动名称中不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | / | 正斜线 |
   | ? | 问号 |
   | # | 数字符号 |
   | : | 冒号 |
   | = | 等号 |
   | + | 加号 |
   | - | 减号 |
   | @ | @ 符号 |

1. 按照[可视化体验编辑器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)中所述，修改页面元素。

   您可以从资产管理器中一次选择多个图像。这使您能够快速查找包含为活动配置的每个图像的页面。您还可以轻松编辑选件中的文本元素。当您编辑某个元素时，该元素上会出现一个条块，指示您对它进行了更改。

1. 单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;以配置可用的组合。

   ![“管理内容”选项](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   此时会显示一个对话框，屏幕顶部提供了三个选项：“体验”、“选件”和“排除组”。

   ![“管理内容”对话框](/help/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >尽管您在 AP 活动中最多可以创建 30,000 个体验，但只有当使用的体验少于 5,000 个时，活动效果才会最佳。

   “[!UICONTROL 体验]”列表显示了为活动选择的每个内容块以及该活动被分配到的位置。

   要排除特定的体验，您可以将鼠标悬停在所需体验上，然后单击“排除”图标。

   ![“排除”图标悬停](/help/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以批量排除/包含体验，方法是选中相关体验的复选框，然后单击对话框右上角的“排除”图标。

   ![批量排除选项](/help/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以通过单击&#x200B;**状态**&#x200B;下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

1. （视情况而定）单击&#x200B;**[!UICONTROL 选件]**&#x200B;以选择内容片段并将其分配给报表组，或通过定位仅允许特定访客查看特定选件。

   有关更多信息，请参阅[自动个性化中的选件报表组](../../c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C)。

   使用[!UICONTROL 位置]列表可按位置筛选选件。使用[!UICONTROL 报表组]列表可按报表组筛选选件。您还可以使用“[!UICONTROL 报表组]”来筛选“[!UICONTROL 未分配选件]”，以便将某个报表组分配给当前未分配给任何报表组的选件。

   您可以将特定体验添加到报表组，方法是将鼠标悬停在所需的选件上，然后单击文件夹图标。

   ![文件夹图标悬停](/help/c-activities/t-automated-personalization/assets/icon-folder.png)

   您可以在报表组中批量添加体验，方法是选中相关体验的复选框，然后单击对话框右上角的“报表组”文件夹图标按钮。

   ![“报表组”选项](/help/c-activities/t-automated-personalization/assets/report-group-options.png)

   请务必注意，报表组会影响 Target 构建其模型的方式。因此，我们建议只有当您计划在活动上线期间替换选件或添加新选件时才使用报表组。在向实时活动中添加新选件时，通过将新选件放置到包含现有类似选件的组中，计算机可以使用已为该组中其他选件收集的数据来了解新选件。您绝不应该将所有选件都放置到一个报表组中。

   有关将选件定位到特定受众的信息，请参阅 [Target AP 选件](../../c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E)。

1. （视情况而定）单击&#x200B;**[!UICONTROL 排除组]**&#x200B;以选择要从活动中排除的任何元素组合。

   ![“管理内容”对话框的“排除组”选项卡](/help/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   尽管您在 AP 测试中最多可以创建 30,000 个体验，但只有当使用的不同体验少于 10,000 个时，算法才能提供最佳运算结果。

   如果活动中当前未包含任何排除组，请单击&#x200B;**创建排除组**。您可以进行筛选以创建一个仅显示要排除的组合的列表。命名排除组，然后单击&#x200B;**保存**。

   要编辑现有的排除组，请将鼠标悬停在要编辑的组上，然后单击铅笔图标。

1. 完成活动内容的设置后，单击&#x200B;**[!UICONTROL 完成]**。

1. 如果您使用过其他 Target 活动类型，那么&#x200B;**定位**&#x200B;步骤看起来会很熟悉。在此步骤中，您可以选择受众，并通过单击&#x200B;**[!UICONTROL 自定义分配]**&#x200B;下拉列表来指定将会看到控制体验的访客百分比，然后单击&#x200B;**下一步**。

   “[!UICONTROL 自定义分配]”下拉列表可让您从以下选项中进行选择：

   ![“流量分配目标”下拉列表](/help/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **评估个性化算法 (50/50)：**&#x200B;如果您的目标是测试算法，则可以在控制和目标算法之间按 50/50 的百分比拆分访客。这种拆分可让您对提升进行最精确的评估。建议将“随机体验”用作控制。
   * **最大化个性化流量 (90/10)：**&#x200B;如果您的目标是创建“一直开启”的活动，则可以在控制中放入 10% 的访客，以确保算法有足够的数据来不断学习。请注意，这里做出的权衡是，为了对更大一部分的流量进行个性化，提升度的准确性将会降低。无论您的目标如何，在使用特定体验作为控制时，都建议按此比例拆分流量。
   * **自定义分配：**&#x200B;根据需要手动拆分百分比。

1. （视情况而定）从“[!UICONTROL 控制]”下拉列表中，[选择要用作控制的特定体验](/help/c-activities/t-automated-personalization/experience-as-control.md)，或选择“[!UICONTROL 随机体验]”。

   控制体验通过比较来确定自动化测试所带来的提升量。

   自动个性化始终针对控制组来衡量性能。最佳做法是在控制组中至少放入 10% 的参加者。如果您的目标是测试针对所提供数据的个性化算法产生的效果是否优于非个性化（即随机提供控制），则实现此目标的最快、最准确的方式是在控制和个性化算法之间按 50/50 的百分比来拆分流量。如果您希望最大化个性化流量，并且您不太关心活动所产生的确切提升度，则实现此目标的最快、最准确的方式是在控制和个性化算法之间按 10/90 的百分比来拆分流量。

   >[!NOTE]
   >
   >在自动个性化活动中，将评估每个请求的参加标准（URL 定位、模板规则和受众目标）。在以前的版本中，每个会话会评估一次参加标准。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以显示&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面。
1. 使用以下设置配置活动，然后单击&#x200B;**[!UICONTROL 保存并关闭]**。

   | 设置 | 描述 |
   |--- |--- |
   | 名称 | 命名活动。为活动提供一个可让团队成员在“活动”列表中识别该活动的描述性名称。请参阅上面的表格，查看在活动名称中不允许使用的字符。 |
   | 目标 | （可选）键入测试的目标。此目标可帮助您记住活动的用途。 |
   | 优先级 | 根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。<br>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<br>如果“管理”>“ [!UICONTROL 报告] ”中未启 [!UICONTROL 用] 此选项（默认值），请指定优先级：低、中或高。<br>要启用细粒度优先级，请单 [!UICONTROL 击“管理] ”> [!UICONTROL “报告]”，然后将  “启用细粒度优先级”选项切换到“开启”位置。<br>如果已启用此选项，请指定一个介于 0 到 999 之间值：<ul><li>0 = 低</li><li>999 = 高</li></ul>对于在以前的 Target Standard/Premium 版本中创建的活动，“低”优先级会转换为 0，“中”优先级会转换为 5，“高”优先级会转换为 10。您可以根据需要调整这些值。<br>****注意：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。 |
   | 持续时间 | 设置活动的开始和结束日期。 |
   | 优化目标 | 指定优化目标，该目标包含两个参数：<ul><li>您想要通过活动衡量哪些指标</li><li>活动参加者采取的哪项操作可指示目标已达到。</li></ul>您可以通过选择“我的主要目标”右侧的三个圆点来选择命名优化目标。自动个性化活动可以衡量转化、RPV 和 AOV。转化可通过查看页面或查看 mbox 来实现。点击次数也可以进行跟踪。<br>主要目标也可作为建模系统用来计算体验是否成功的建模量度。<br>达到建模目标后，出于跟踪目的，可以将访客保留在活动中。例如，通常会使用自动个性化活动来提高点击率，并将其设置为建模目标。然而，重要的是要了解增加的点击率是如何导致最终转化的，因此通过最终转化进行跟踪必不可少。<br>您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。<br>在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。<br>通过“添加依赖项”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。<br>要添加依赖项，请执行以下操作：<ol><li>添加其他量度后，单击“其他目标”右侧的三个圆点式菜单下的[!UICONTROL 高级设置]。</li><li>单击[!UICONTROL 报表设置]章节底部的[!UICONTROL 添加依赖项]选项。</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL 已实现]，以在[!UICONTROL 已实现]和[!UICONTROL 未实现]之间进行切换。</li></ol>添加依赖项后，您可以编辑或删除依赖项。 |
   | 转化量度 | 默认情况下，转化量度与优化目标量度相同。但是，您可以通过取消选中[!UICONTROL 与优化目标相同]选项来定义单独的转化量度。 |
   | 其他量度 | 添加要使用的任何其他报表量度。您可以添加转化或收入量度。<br>**注意&#x200B;**：不支持将“参与度”量度添加为其他量度。用户界面可能允许您选择“参与度”量度，但报表中无法正确显示该数据。 |
   | 报表的受众 | 添加受众以在报表中启用按受众筛选功能。默认情况下，报表会显示所有符合条件的访客结果。添加受众可筛选结果，从而获得更具体的访客子集。<br>**注意&#x200B;**：与其他活动类型不同，自动个性化无法使用 Adobe Analytics 作为报表源。 |
   | 注释 | 键入有关您活动的任何信息，以便您自己或其他团队成员可随时使用这些信息。“注释”窗格的大小可以调整。 |

   请注意，在命名或重命名量度时，不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | / | 正斜线 |
   | ? | 问号 |
   | # | 数字符号 |
   | : | 冒号 |
   | = | 等号 |
   | + | 加号 |
   | - | 减号 |
   | @ | @ 符号 |

单击&#x200B;**[!UICONTROL 创建]**&#x200B;后，将显示“活动摘要”。单击&#x200B;**预览体验**&#x200B;可预览体验在交付时的外观。您可以使用显示的弹出窗口在您的网站上查看 AP 体验和共享该体验的链接，以便在 Target 的可视化体验编辑器以外“真正预览”体验。您必须通过共享消息中的链接来共享预览。如果单击链接，然后直接从页面复制 URL，则不会起作用，因为 URL 包含只有在从消息中的链接访问页面时才会正确显示页面的参数。

有关报表的信息，请参阅[自动个性化报表](../../c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A)。
