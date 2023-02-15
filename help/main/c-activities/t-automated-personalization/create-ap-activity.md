---
keywords: 自动个性化；AP；受众；组合；随机林；残差方差；误差方差；存留期值
description: 了解如何创建 [!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] 使用 [!UICONTROL 可视化体验编辑器].
title: 如何创建 [!UICONTROL Automated Personalization] 活动？
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 8a791d4266cb03fef498ac6f852d4a5755ba66a6
workflow-type: tm+mt
source-wordcount: '1854'
ht-degree: 60%

---

# ![PREMIUM](/help/main/assets/premium.png) 创建自动个性化活动

创建 [!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] 使用 [!UICONTROL 可视化体验编辑器] (VEC)。

的 [!UICONTROL Automated Personalization] (AP) [!DNL Adobe Target] 会因其他活动类型的工作流而异。

1. 从 [!DNL Target] [!UICONTROL 活动] 列表，单击 **[!UICONTROL 创建活动]** > **[!UICONTROL Automated Personalization]**.

   ![创建活动：自动个性化](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. 要使用VEC，请单击 **[!UICONTROL 可视（默认）]**.

   ![“创建自动个性化活动”对话框](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   使用 [!UICONTROL 基于表单的体验编辑器]，选择 [!UICONTROL 表单]. 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基于表单的体验编辑器], [!DNL Target] 选件 [!UICONTROL 单页应用程序VEC]. 有关各种编辑器的更多信息，请参阅[体验和选件](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅 [可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （视情况而定） [选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. 验证或输入活动 URL，然后单击&#x200B;**[!UICONTROL 下一步]**。

   >[!NOTE]
   >
   >[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://wwww.adobe.com`] 均匹配。

   此时会在VEC中打开具有指定URL的页面。

1. 要命名活动，请单击 **[!UICONTROL 名称]** 字段，然后键入活动名称。

   ![名称字段](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   活动名称不能以以下任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

   此外，活动名称不能包含以下任意字符序列：&#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;[&quot;&#39;, &#39;&quot;]&#39;, &#39;[&quot;, &quot;]&#39;。

1. 按照[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中所述，修改页面元素。

   您可以从资产管理器中一次选择多个图像。这使您能够快速查找包含为活动配置的每个图像的页面。您还可以轻松编辑选件中的文本元素。当您编辑某个元素时，该元素上会出现一个条块，指示您对它进行了更改。

1. 单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;以配置可用的组合。

   ![“管理内容”选项](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   此时会出现一个对话框，屏幕顶部有三个选项： [!UICONTROL 体验], [!UICONTROL 选件]和 [!UICONTROL 排除组].

   ![“管理内容”对话框](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >尽管您在 AP 活动中最多可以创建 30,000 个体验，但只有当使用的体验少于 5,000 个时，活动效果才会最佳。即使为活动启用了[!UICONTROL 不允许重复项]选项后，也适用同样的限制。

   的 [!UICONTROL 体验] 列表显示了为活动选择的每个内容块以及该活动被分配到的位置。

   您可以通过将鼠标悬停在所需体验上，然后单击 [!UICONTROL 排除] 图标。

   ![“排除”图标悬停](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以批量排除/包含体验，方法是选中相关体验的复选框，然后单击 [!UICONTROL 排除] 图标。

   ![批量排除选项](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以通过单击[!UICONTROL 状态]下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

1. （视情况而定）单击&#x200B;**[!UICONTROL 选件]**&#x200B;以选择内容片段并将其分配给报表组，或通过定位仅允许特定访客查看特定选件。

   有关报表组的更多信息，请参阅 [Automated Personalization中的选件报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. （视情况而定）单击&#x200B;**[!UICONTROL 排除组]**&#x200B;以选择要从活动中排除的任何元素组合。

   ![“管理内容”对话框的“排除组”选项卡](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   尽管您在 AP 测试中最多可以创建 30,000 个体验，但只有当使用的不同体验少于 10,000 个时，算法才能提供最佳运算结果。即使为活动启用了[!UICONTROL 不允许重复项]选项后，也适用同样的限制。

   如果活动中当前未包含任何排除组，请单击&#x200B;**创建排除组**。您可以进行筛选以创建一个仅显示要排除的组合的列表。命名排除组，然后单击&#x200B;**保存**。

   要编辑现有的排除组，请将鼠标悬停在要编辑的组上，然后单击铅笔图标。

1. 完成活动内容的设置后，单击&#x200B;**[!UICONTROL 完成]**。

1. 的 **定位** 如果您使用其他 [!DNL Target] 活动类型。 在此，您可以选择受众，并通过单击 **[!UICONTROL 自定义分配]** 下拉列表，然后单击 **下一个**.

   “[!UICONTROL 自定义分配]”下拉列表可让您从以下选项中进行选择：

   ![“流量分配目标”下拉列表](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL 评估个性化算法(50/50)]:** 如果您的目标是测试算法，则在控制和目标算法之间按50/50%的比例拆分访客。 这种拆分可让您对提升进行最精确的评估。建议将“随机体验”用作控制。
   * **[!UICONTROL 最大化个性化流量(90/10)]:** 如果您的目标是创建“一直开启”的活动，则可以将10%的访客置于控制中。 此选项可确保算法有足够的数据来随着时间的推移继续学习。 请注意，这里做出的权衡是，为了对较大比例的流量进行个性化，提升度的准确度会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议按此比例拆分流量。
   * **[!UICONTROL 自定义分配]:** 根据需要手动拆分百分比。

1. （视情况而定）从“[!UICONTROL 控制]”下拉列表中，[选择要用作控制的特定体验](/help/main/c-activities/t-automated-personalization/experience-as-control.md)，或选择“[!UICONTROL 随机体验]”。

   控制体验通过比较来确定自动化测试所带来的提升量。

   [!UICONTROL 自动个性化始终针对控制组来衡量性能。]最佳做法是在控制组中至少放入 10% 的参加者。如果您的目标是测试针对所提供数据的个性化算法产生的效果是否优于非个性化（即随机提供控制），则实现此目标的最快、最准确的方式是在控制和个性化算法之间按 50/50 的百分比来拆分流量。如果您希望最大化个性化流量，并且您不太关心活动所产生的确切提升度，则实现此目标的最快、最准确的方式是在控制和个性化算法之间按 10/90 的百分比来拆分流量。

   >[!NOTE]
   >
   >在 [!UICONTROL Automated Personalization] 会为每个请求评估活动、登入标准（URL定位、模板规则和受众目标）。 在以前的版本中，每个会话会评估一次参加标准。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以显示&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面。
1. 使用以下设置配置活动，然后单击&#x200B;**[!UICONTROL 保存并关闭]**。

   | 设置 | 描述 |
   |--- |--- |
   | [!UICONTROL 名称] | 命名活动。为活动指定一个足以让团队成员在 [!UICONTROL 活动] 列表。 请参阅上面的表格，查看在活动名称中不允许使用的字符。 |
   | [!UICONTROL 目标] | （可选）键入测试的目标。此目标可帮助您记住活动的用途。 |
   | [!UICONTROL 优先级] | 根据您的设置，UI 和“[!UICONTROL 优先级]”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。<br>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<br>如果 [!UICONTROL 管理] > [!UICONTROL 报表] （默认），指定优先级：“低”、“中”或“高”。<br>要启用细粒度优先级，请单击 [!UICONTROL 管理] > [!UICONTROL 报表]，然后切换 [!UICONTROL 启用细粒度优先级] 选项。<br>如果已启用此选项，请指定一个介于 0 到 999 之间值：<ul><li>0 = 低</li><li>999 = 高</li></ul>对于在以前的 [!DNL Target Standard/Premium] 版本中创建的活动，“低”优先级会转换为 0，“中”优先级会转换为 5，“高”优先级会转换为 10。您可以根据需要调整这些值。<br>****&#x200B;注意：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为 0、5、10。 |
   | [!UICONTROL 持续时间] | 设置活动的开始和结束日期。您可以选择 [!UICONTROL 激活时] 或者，您可以指定特定的日期和时间。 |
   | [!UICONTROL 优化目标] | 指定优化目标，该目标包含两个参数：<ul><li>您想要通过活动衡量哪些指标</li><li>活动参加者采取的哪项操作可指示目标已达到。</li></ul>您可以通过选择右侧的三个圆点来命名优化目标 [!UICONTROL 我的主要目标]. [!UICONTROL Automated Personalization] 活动可衡量 [!UICONTROL 转化] 或 [!UICONTROL 收入]. 转化可通过查看页面或查看 mbox 来实现。点击次数也可以进行跟踪。<br>主要目标也可作为建模系统用来计算体验是否成功的建模量度。<br>达到建模目标后，出于跟踪目的，可以将访客保留在活动中。例如， [!UICONTROL Automated Personalization] 活动用于提高点击率，并将其设置为建模目标。 然而，重要的是要了解增加的点击率是如何导致最终转化的，因此通过最终转化进行跟踪必不可少。<br>您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。<br>在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。<br>通过“添加依赖项”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。<br>要添加依赖项，请执行以下操作：<ol><li>添加其他量度后，单击 **[!UICONTROL 高级设置]** 在右侧的三点菜单下 [!UICONTROL 其他目标].</li><li>单击[!UICONTROL 报表设置]章节底部的&#x200B;**[!UICONTROL 添加依赖项]**&#x200B;选项。</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL 已实现]，以在[!UICONTROL 已实现]和[!UICONTROL 未实现]之间进行切换。</li></ol>添加依赖项后，您可以编辑或删除依赖项。 |
   | [!UICONTROL 转化量度] | 默认情况下，转化量度与优化目标量度相同。但是，您可以通过取消选中[!UICONTROL 与优化目标相同]选项来定义单独的转化量度。 |
   | [!UICONTROL 其他量度] | 添加您要使用的任何其他报表量度。 您可以添加转化或收入量度。<br>**注意**：不支持将“参与度”量度添加为其他量度。UI可能允许您选择 [!UICONTROL 参与度] 量度，但数据无法在报表中准确显示。 |
   | [!UICONTROL 报表的受众] | 添加受众以在报表中启用按受众筛选功能。默认情况下，报表会显示所有符合条件的访客结果。添加受众可筛选结果，从而获得更具体的访客子集。<br>**注意**:与其他活动类型不同， [!UICONTROL Automated Personalization] 不能使用 [!UICONTROL Adobe Analytics] 作为报表源(A4T)。 |
   | [!UICONTROL 注释] | 键入有关您活动的任何信息，以便您自己或其他团队成员可随时使用这些信息。的 [!UICONTROL 注释] 窗格的大小。 |

   命名或重命名量度时，不允许使用以下字符：

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

在单击 **[!UICONTROL 保存并关闭]**，该活动的 [!UICONTROL 概述] 页面。 单击 **预览体验** 以预览体验在交付时的外观。 此时会显示一个弹出窗口，您可以使用该弹出窗口查看和共享您网站上的AP体验的链接，以“真正预览”外部的体验 [!UICONTROL Target]的可视化体验编辑器(VEC)。 您必须通过共享消息中的链接来共享预览。单击链接，然后直接从浏览器复制URL将不起作用。 复制链接会导致URL包含一个参数，该参数仅在您从消息中的链接访问页面时才正确显示页面。

有关报表的信息，请参阅 [Automated Personalization报表](/help/main/c-reports/personalization-reports/reports-ap.md).
