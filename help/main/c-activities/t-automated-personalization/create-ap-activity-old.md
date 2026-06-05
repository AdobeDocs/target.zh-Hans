---
keywords: 自动个性化；ap
description: 了解如何使用[!UICONTROL 可视化体验编辑器]在 [!DNL Adobe Target] 中创建[!UICONTROL Automated Personalization] (AP)活动。
title: 如何创建[!UICONTROL Automated Personalization]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: c467f629596b37c334276d6f095f19b639a8518d
workflow-type: tm+mt
source-wordcount: '1927'
ht-degree: 30%

---

# 创建[!UICONTROL Automated Personalization]活动

在[!DNL Adobe Target]中使用[!UICONTROL 可视化体验编辑器] (VEC)创建[!UICONTROL Automated Personalization] (AP)活动。

[!DNL Target]中的[!UICONTROL Automated Personalization] (AP)活动工作流与其他活动类型的工作流有所不同。

1. 从[!DNL Target] [!UICONTROL 活动]列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL Automated Personalization]**。

   ![创建活动：自动个性化](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. 要使用[!UICONTROL 可视化体验编辑器] (VEC)，请单击&#x200B;**[!UICONTROL 可视化]**。

   若要使用[!UICONTROL 基于表单的体验编辑器]，请选择[!UICONTROL 表单]。 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL 基于表单的体验编辑器]之外，[!DNL Target]还提供[!UICONTROL 单页应用程序VEC]。 有关各种编辑器的更多信息，请参阅[体验和产品建议](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定） [选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 验证或输入活动URL，然后单击&#x200B;**[!UICONTROL 创建]**。

   >[!NOTE]
   >
   >[!DNL Target]不区分URL协议（[!DNL https]和[!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://wwww.adobe.com`]都匹配。

   此时将在VEC中打开具有指定URL的页面。

1. 单击&#x200B;**[!UICONTROL 名称]**&#x200B;字段并键入您的活动名称。

   ![名称字段](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   活动名称不能以下列任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

   活动名称不能包含以下任何字符序列：

   | 字符序列 | 描述 |
   |--- |--- |
   | ;= | 分号，等于 |
   | ;+ | 分号，加号 |
   | ;- | 分号，减号 |
   | ;@ | 分号， At sign |
   | ,= | 逗号，等于 |
   | ,+ | 逗号，加号 |
   | ,- | 逗号，减 |
   | ,@ | 逗号， At sign |
   | `[`&quot; | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 按照[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中所述，修改页面元素。

   您可以从资产管理器中一次选择多个图像。 这样，您就可以快速查看页面，以及为该活动配置的每个映像。 您还可以轻松编辑选件中的文本元素。 当您编辑某个元素时，该元素上会出现一个条块，指示您对它进行了更改。

1. 单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;以配置可用的组合。

   ![“管理内容”选项](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   屏幕上会显示一个对话框，其中具有三个选项：[!UICONTROL 体验]、[!UICONTROL 选件]和[!UICONTROL 排除组]。

   ![“管理内容”对话框](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >尽管您在AP活动中最多可以创建30,000个体验，但只有当使用的体验少于5,000个时，活动效果才会最佳。 即使活动启用了[!UICONTROL 不允许重复项]选项，此限制也适用。

   [!UICONTROL 体验]列表显示了为活动选择的每个内容块以及该活动被分配到的位置。

   您可以将鼠标悬停在所需体验上，然后单击[!UICONTROL 排除]图标，以排除特定体验。

   ![“排除”图标悬停](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以批量排除或包含体验，方法是选中相关体验的复选框，然后单击对话框右上角的[!UICONTROL 排除]图标。

   ![批量排除选项](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以通过单击[!UICONTROL 状态]下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

1. （视情况而定）单击&#x200B;**[!UICONTROL 选件]**&#x200B;以选择内容片段并将其分配给报表组，或只允许特定访客查看特定具有定位的选件。

   有关报表组的详细信息，请参阅[Automated Personalization中的选件报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)。

1. （视情况而定）单击&#x200B;**[!UICONTROL 排除组]**&#x200B;以选择要从活动中排除的任何元素组合。

   ![“管理内容”对话框的“排除组”选项卡](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   尽管您在 AP 测试中最多可以创建 30,000 个体验，但只有当使用的不同体验少于 10,000 个时，算法才能提供最佳运算结果。 即使活动启用了[!UICONTROL 不允许重复项]选项，此限制也适用。

   如果活动中当前未包含任何排除组，请单击&#x200B;**创建排除组**。 您可以进行筛选以创建一个仅显示要排除的组合的列表。 命名您的排除组，然后单击&#x200B;**保存**。

   要编辑现有的排除组，请将鼠标悬停在要编辑的组上，然后单击铅笔图标。

1. 完成活动内容的设置后，单击&#x200B;**[!UICONTROL 完成]**。

1. 如果您使用过其他[!DNL Target]活动类型，则&#x200B;**定位**&#x200B;步骤看起来会很熟悉。 在此处，您可以通过单击&#x200B;**[!UICONTROL 自定义分配]**&#x200B;下拉列表来选择一个受众，并指定查看控制体验的访客百分比，然后单击&#x200B;**下一步**。

   “[!UICONTROL 自定义分配]”下拉列表可让您从以下选项中进行选择：

   ![“流量分配目标”下拉列表](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL 评估Personalization算法(50/50)]：**&#x200B;如果您的目标是测试算法，则可以在控制和目标算法之间按50/50的百分比拆分访客。 这种拆分可让您对提升进行最精确的评估。 建议将“随机体验”用作控制。
   * **[!UICONTROL 最大化Personalization流量(90/10)]：**&#x200B;如果您的目标是创建“始终运行”的活动，请将10%的访客放入控制。 此选项确保算法有足够的数据来不断学习。 这里做出的权衡是，为了对更大比例的流量进行个性化，提升度的准确性将会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议使用此选项。
   * **[!UICONTROL 自定义分配]：**&#x200B;根据需要手动拆分百分比。

1. （视情况而定）从[!UICONTROL 控制]下拉列表中，[选择要用作控制的特定体验](/help/main/c-activities/t-automated-personalization/experience-as-control.md)或选择[!UICONTROL 随机体验。]

   控制体验通过比较来确定自动化测试所带来的提升量。

   [!UICONTROL Automated Personalization]始终针对控制组测量性能。 最佳做法是在控制组中至少放入 10% 的参加者。 如果您的目标是测试给定数据上的个性化算法是否比无个性化（例如，随机提供的控制）的执行得更好，则控制和个性化算法之间的50/50流量分摊是实现此目标的最快和最准确的方法。 如果您希望最大化个性化的流量量，并且不太关注了解您的活动正在产生的确切提升度，则控制和个性化算法之间的10/90流量分摊是实现此目标的最快、最准确的方法。

   >[!NOTE]
   >
   >在[!UICONTROL Automated Personalization]活动中，将评估每个请求的参加标准（URL定位、模板规则和受众目标）。 在以前的版本中，每个会话会评估一次参加标准。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;以显示&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面。
1. 使用以下设置配置活动，然后单击&#x200B;**[!UICONTROL 保存并关闭]**。

   | 设置 | 描述 |
   |--- |--- |
   | [!UICONTROL 名称] | 命名活动。 请为活动提供一个描述清楚的名称，以便团队成员能够在[!UICONTROL 活动]列表中识别该活动。 请参阅上面的表格，查看在活动名称中不允许使用的字符。 |
   | [!UICONTROL 目标] | （可选）键入测试的目标。 此目标可帮助您记住活动的用途。 |
   | [!UICONTROL 优先级] | 根据您的设置，[!UICONTROL 优先级]的[!DNL Target] UI和选项会有所不同。 您可以使用[!UICONTROL 低]、[!UICONTROL Medium]或[!UICONTROL 高]的旧设置，也可以启用0到999的细粒度优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。 如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>如果未在[!UICONTROL 管理] > [!UICONTROL 报告]中启用此选项（默认值），请指定优先级： [!UICONTROL 低]、[!UICONTROL Medium]或[!UICONTROL 高]。<P>要启用细粒度优先级，请单击[!UICONTROL 管理] > [!UICONTROL 报告]，然后将[!UICONTROL 启用细粒度优先级]选项切换到“开”位置。<P>如果已启用此选项，请指定从0到999的值：<ul><li>0 = 低</li><li>999 = 高</li></ul>对于在以前的[!DNL Target Standard/Premium]版本中创建的活动，[!UICONTROL 低]优先级已转换为0，[!UICONTROL Medium]优先级已转换为5，[!UICONTROL 高]优先级已转换为10。 您可以根据需要调整这些值。<P>**注意**：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为0、5、10。 |
   | [!UICONTROL 持续时间] | 设置活动的开始和结束日期。 您可以选择[!UICONTROL 激活时]，也可以指定特定的日期和时间。 |
   | [!UICONTROL 优化目标] | 指定优化目标，该目标包含两个参数：<ul><li>您想要通过活动衡量哪些指标</li><li>活动参加者采取的哪项操作可指示目标已达到。</li></ul>您可以通过选择[!UICONTROL 我的主要目标]右侧的三个圆点来命名优化目标。 [!UICONTROL Automated Personalization]活动可以测量[!UICONTROL 转化]或[!UICONTROL 收入]。 可以通过查看页面或查看mbox来实现转换。 点击次数也可以进行跟踪。<P>主要目标也可作为建模系统用来计算体验是否成功的建模量度。<P>达到建模目标后，出于跟踪目的，可以将访客保留在活动中。 例如，通常使用[!UICONTROL Automated Personalization]活动来提高点击率，并且设置为建模目标。 然而，重要的是要了解增加的点击率是如何导致最终转化的，因此通过最终转化进行跟踪必不可少。<P>您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。<P>在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。<P>通过“[!UICONTROL 添加依赖项]”选项，可以指定是否要先实现其他成功量度，然后才能递增该成功量度。<P>要添加依赖项，请执行以下操作：<ol><li>添加其他量度后，单击[!UICONTROL 其他目标]右侧的三个圆点式菜单下的&#x200B;**[!UICONTROL 高级设置]**。</li><li>单击[!UICONTROL 报表设置]部分底部的&#x200B;**[!UICONTROL 添加依赖项]**&#x200B;选项。</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL 已实现]，以在[!UICONTROL 已实现]和[!UICONTROL 未实现]之间进行切换。</li></ol>添加依赖项后，您可以编辑或删除依赖项。 |
   | [!UICONTROL 转化量度] | 默认情况下，转化量度与优化目标量度相同。 但是，您可以通过取消选中[!UICONTROL 与优化目标相同]选项来定义单独的转化量度。 |
   | [!UICONTROL 其他量度] | 添加任何其他要使用的报表量度。 您可以添加转化或收入量度。<P>**注意**： [!UICONTROL 参与度]量度不支持作为其他量度。 [!DNL Target] UI可能允许您选择[!UICONTROL 参与]量度，但数据在报表中无法准确显示。 |
   | [!UICONTROL 报表受众] | 添加受众以在报表中启用按受众筛选功能。 默认情况下，报表会显示所有符合条件的访客结果。 添加受众可筛选结果，从而获得更具体的访客子集。<P>**注意**：与其他活动类型不同，[!UICONTROL Automated Personalization]不能使用[!UICONTROL Adobe Analytics]作为其报表源(A4T)。 |
   | [!UICONTROL 注意] | 键入对您或其他团队成员有用的有关活动的任何信息。 [!UICONTROL 注释]窗格可调整大小。 |

   在命名或重命名指标时，不允许使用以下字符：

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

单击&#x200B;**[!UICONTROL 保存并关闭]**&#x200B;后，将显示该活动的[!UICONTROL 概述]页面。 单击&#x200B;**预览体验**&#x200B;以预览您的体验在交付时的外观。 此时会显示一个弹出窗口，您可以使用它查看和共享指向网站上您的AP体验的链接，从而在[!UICONTROL Target] [!UICONTROL 可视化体验编辑器] (VEC)之外获得体验的“真实预览”。 您必须通过共享消息中的链接来共享预览。 单击链接然后直接从浏览器复制URL不起作用。 复制链接会导致URL包含一个参数，只有在您从消息中的链接访问页面时，该参数才会正确显示页面。

有关报表的信息，请参阅[Automated Personalization报表](/help/main/c-reports/personalization-reports/reports-ap.md)。
