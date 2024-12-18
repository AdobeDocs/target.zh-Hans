---
keywords: 自动个性化；ap
description: 了解如何使用[!UICONTROL Visual Experience Composer]创建[!UICONTROL Automated Personalization] (AP)活动。
title: 如何创建[!UICONTROL Automated Personalization]活动？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
hide: true
hidefromtoc: true
exl-id: fe6e5130-53a0-4254-8299-b52086c20004
source-git-commit: 48dcf100228beb160179e5bb7cfe7db36419b832
workflow-type: tm+mt
source-wordcount: '1769'
ht-degree: 27%

---

# 创建[!UICONTROL Automated Personalization]活动

使用[!UICONTROL Visual Experience Composer] (VEC)在[!DNL Adobe Target]中创建[!UICONTROL Automated Personalization] (AP)活动。

[!DNL Target]中的[!UICONTROL Automated Personalization] (AP)活动工作流与其他活动类型的工作流有所不同。

1. 从[!DNL Target] [!UICONTROL Activities]列表中，单击&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**。

1. 要使用[!UICONTROL Visual Experience Composer] (VEC)，请单击&#x200B;**[!UICONTROL Visual]**。

   要使用[!UICONTROL Form-Based Experience Composer]，请选择[!UICONTROL Form]。 请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]之外，[!DNL Target]还提供[!UICONTROL Single Page Application VEC]。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定） [选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 在&#x200B;**[!UICONTROL Enter Activity URL]**&#x200B;框中，指定您的[活动URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)。

   如果您的帐户[配置了默认 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认URL更改为其他URL。

   [!DNL Target]不区分URL协议（[!DNL https]和[!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://wwww.adobe.com`]都匹配。

1. 单击 **[!UICONTROL Create]**。

   此时将在VEC中打开具有指定URL的页面。

1. 单击&#x200B;**[!UICONTROL Rename]**&#x200B;图标（![重命名图标](/help/main/assets/icons/MoreSmallListVert.svg)），单击&#x200B;**[!UICONTROL Rename]**，指定活动的名称，然后单击&#x200B;**[!UICONTROL Save]**。

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
   | ；= | 分号，等于 |
   | ；+ | 分号，加号 |
   | ；- | 分号，减号 |
   | ；@ | 分号， At sign |
   | ，= | 逗号，等于 |
   | ，+ | 逗号，加号 |
   | ，- | 逗号，减 |
   | ，@ | 逗号， At sign |
   | `[`” | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 按照[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)中所述，修改页面元素。

   您可以从资产管理器中一次选择多个图像。这样，您就可以快速查看页面，以及为该活动配置的每个映像。 您还可以轻松编辑选件中的文本元素。当您编辑某个元素时，该元素上会出现一个条块，指示您对它进行了更改。

1. 单击&#x200B;**[!UICONTROL Manage Content]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）以配置可用的组合。

   此时将显示一个对话框，屏幕顶部有三个选项： [!UICONTROL Experiences]、[!UICONTROL Offers]和[!UICONTROL Exclusion Groups]。

   ![“管理内容”对话框](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >尽管您在AP活动中最多可以创建30,000个体验，但只有当使用的体验少于5,000个时，活动效果才会最佳。 即使活动启用了[!UICONTROL Disalow Duplicates]选项，也应用同样的限制。

   [!UICONTROL Experiences]列表显示了为活动选择的每个内容块以及该活动被分配到的位置。

   您可以通过将鼠标悬停在所需体验上，然后单击[!UICONTROL Exclude]图标来排除特定体验。

   ![“排除”图标悬停](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   您可以批量排除或包含体验，方法是选中相关体验的复选框，然后单击对话框右上角的[!UICONTROL Exclude]图标。

   ![批量排除选项](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   您可以通过单击[!UICONTROL Status]下拉列表来筛选此列表视图，以仅查看排除或包含的活动。

1. （视情况而定）单击&#x200B;**[!UICONTROL Offers]**&#x200B;以选择内容片段并将其分配给报表组，或只允许特定访客查看特定具有定位的选件。

   有关报表组的详细信息，请参阅[Automated Personalization中的选件报表组](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)。

1. （视情况而定）单击&#x200B;**[!UICONTROL Exclusion Groups]**&#x200B;以选择要从活动中排除的任何元素组合。

   ![“管理内容”对话框的“排除组”选项卡](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   尽管您在AP测试中最多可以创建30,000个体验，但只有当使用的不同体验少于10,000个时，算法才会发挥最佳性能。 即使活动启用了[!UICONTROL Disalow Duplicates]选项，也应用同样的限制。

   如果活动中当前未包含任何排除组，请单击&#x200B;**创建排除组**。您可以进行筛选以创建一个仅显示要排除的组合的列表。命名您的排除组，然后单击&#x200B;**保存**。

   要编辑现有的排除组，请将鼠标悬停在要编辑的组上，然后单击铅笔图标。

1. 完成活动内容的设置后，单击&#x200B;**[!UICONTROL Done]**。

1. 如果您使用过其他[!DNL Target]活动类型，则&#x200B;**定位**&#x200B;步骤看起来会很熟悉。 在此处，您可以通过单击&#x200B;**[!UICONTROL Custom Allocation]**&#x200B;下拉列表来选择一个受众，并指定查看控制体验的访客百分比，然后单击&#x200B;**下一步**。

   [!UICONTROL Custom Allocation]下拉列表允许您从以下选项中进行选择：

   ![“流量分配目标”下拉列表](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]：**&#x200B;如果您的目标是测试算法，则可以在控制和目标算法之间按50/50的百分比拆分访客。 这种拆分可让您对提升进行最精确的评估。建议将“随机体验”用作控制。
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]：**&#x200B;如果您的目标是创建“一直开启”的活动，请将10%的访客放入控制。 此选项确保算法有足够的数据来不断学习。 这里做出的权衡是，为了对更大比例的流量进行个性化，提升度的准确性将会降低。 无论您的目标如何，在使用特定体验作为控制时，都建议使用此选项。
   * **[!UICONTROL Custom Allocation]：**&#x200B;根据需要手动拆分百分比。

1. （视情况而定）从[!UICONTROL Control]下拉列表中[选择要用作控制的特定体验](/help/main/c-activities/t-automated-personalization/experience-as-control.md)或选择[!UICONTROL Random Experience.]

   控制体验通过比较来确定自动化测试所带来的提升量。

   [!UICONTROL Automated Personalization]始终针对控制组测量性能。 最佳做法是在控制组中至少放入 10% 的参加者。如果您的目标是测试给定数据上的个性化算法是否比无个性化（例如，随机提供的控制）的执行得更好，则控制和个性化算法之间的50/50流量分摊是实现此目标的最快和最准确的方法。 如果您希望最大化个性化的流量量，并且不太关注了解您的活动正在产生的确切提升度，则控制和个性化算法之间的10/90流量分摊是实现此目标的最快、最准确的方法。

   >[!NOTE]
   >
   >在[!UICONTROL Automated Personalization]活动中，将评估每个请求的进入条件（URL定位、模板规则和受众目标）。 在以前的版本中，每个会话会评估一次参加标准。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;以显示&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;页。
1. 使用以下设置配置活动，然后单击&#x200B;**[!UICONTROL Save & Close]**。

   | 设置 | 描述 |
   |--- |--- |
   | [!UICONTROL Name] | 命名活动。为活动提供一个描述清楚的名称，以便团队成员能够在[!UICONTROL Activities]列表中识别该活动。 请参阅上面的表格，查看在活动名称中不允许使用的字符。 |
   | [!UICONTROL Objective] | （可选）键入测试的目标。此目标可帮助您记住活动的用途。 |
   | [!UICONTROL Priority] | 根据您的设置，[!UICONTROL Priority]的[!DNL Target] UI和选项会有所不同。 您可以使用[!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]的旧版设置，也可以启用0到999的细粒度优先级。<P>如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。<P>如果未在[!UICONTROL Administration] > [!UICONTROL Reporting]（默认）中启用此选项，请指定优先级： [!UICONTROL Low]、[!UICONTROL Medium]或[!UICONTROL High]。<P>要启用细粒度优先级，请单击[!UICONTROL Administration] > [!UICONTROL Reporting]，然后将[!UICONTROL Enable Fine-Grained Priorities]选项切换到“开”位置。<P>如果已启用此选项，请指定从0到999的值：<ul><li>0 = 低</li><li>999 = 高</li></ul>对于在以前的[!DNL Target Standard/Premium]版本中创建的活动，[!UICONTROL Low]优先级已转换为0，[!UICONTROL Medium]优先级已转换为5，[!UICONTROL High]优先级已转换为10。 您可以根据需要调整这些值。<P>**注意**：在使用细粒度优先级后，您可以禁用此选项，但在此之前，必须将所有优先级重新设置为0、5、10。 |
   | [!UICONTROL Duration] | 设置活动的开始和结束日期。 您可以选择[!UICONTROL When Activated]，也可以指定特定的日期和时间。 |
   | [!UICONTROL Optimization Goal] | 指定优化目标，该目标包含两个参数：<ul><li>您想要通过活动衡量哪些指标</li><li>活动参加者采取的哪项操作可指示目标已达到。</li></ul>您可以通过选择[!UICONTROL My Primary Goal]右侧的三个圆点来命名优化目标。 [!UICONTROL Automated Personalization]活动可以测量[!UICONTROL Conversion]或[!UICONTROL Revenue]。 可以通过查看页面或查看mbox来实现转换。 点击次数也可以进行跟踪。<P>主要目标也可作为建模系统用来计算体验是否成功的建模量度。<P>达到建模目标后，出于跟踪目的，可以将访客保留在活动中。例如，通常使用[!UICONTROL Automated Personalization]活动来提高点击率，并且已设置为建模目标。 然而，重要的是要了解增加的点击率是如何导致最终转化的，因此通过最终转化进行跟踪必不可少。<P>您可以提供对多个量度的依赖关系，并且还可以灵活选择是否应实现指定的量度才能递增计数。<P>在使一个量度依赖于另一个量度之前，您必须定义两个（或多个）成功量度。<P>[!UICONTROL Add Dependency]选项允许在已达到另一个成功量度或尚未达到时递增成功量度。<P>要添加依赖项，请执行以下操作：<ol><li>添加其他量度后，单击[!UICONTROL Additional Goal]右侧的三个圆点式菜单下的&#x200B;**[!UICONTROL Advanced Settings]**。</li><li>单击[!UICONTROL Reporting Settings]部分底部的&#x200B;**[!UICONTROL Add Dependency]**&#x200B;选项。</li><li>将所需量度从左侧窗格拖放到右侧窗格中，然后单击[!UICONTROL Reached]以在[!UICONTROL Reached]和[!UICONTROL Not Reached]之间切换设置。</li></ol>添加依赖项后，您可以编辑或删除依赖项。 |
   | [!UICONTROL Conversion Metric] | 默认情况下，转化量度与优化目标量度相同。 但是，您可以通过取消选中[!UICONTROL Same as Optimization Goal]选项来定义单独的转化量度。 |
   | [!UICONTROL Additional Metrics] | 添加任何其他要使用的报表量度。 您可以添加转化或收入量度。<P>**注意**：不支持[!UICONTROL Engagement]量度作为其他量度。 [!DNL Target] UI可能允许您选择[!UICONTROL Engagement]量度，但数据在报表中无法准确显示。 |
   | [!UICONTROL Audiences for Reporting] | 添加受众以在报表中启用按受众筛选功能。默认情况下，报表会显示所有符合条件的访客结果。添加受众可筛选结果，从而获得更具体的访客子集。<P>**注意**：与其他活动类型不同，[!UICONTROL Automated Personalization]不能使用[!UICONTROL Adobe Analytics]作为其报表源(A4T)。 |
   | [!UICONTROL Notes] | 键入对您或其他团队成员有用的有关活动的任何信息。 [!UICONTROL Notes]窗格可调整大小。 |

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

单击&#x200B;**[!UICONTROL Save & Close]**&#x200B;后，将显示该活动的[!UICONTROL Overview]页面。 单击&#x200B;**预览体验**&#x200B;以预览您的体验在交付时的外观。 此时会出现一个弹出窗口，您可以使用它查看和共享指向网站上您的AP体验的链接，从而获得[!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC)外部体验的“真实预览”。 您必须通过共享消息中的链接来共享预览。单击链接然后直接从浏览器复制URL不起作用。 复制链接会导致URL包含一个参数，只有在您从消息中的链接访问页面时，该参数才会正确显示页面。

有关报表的信息，请参阅[Automated Personalization报表](/help/main/c-reports/personalization-reports/reports-ap.md)。
