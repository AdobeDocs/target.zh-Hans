---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: 可上传 CSV 文件以自定义您的推荐。
title: 上传自定义标准
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1893'
ht-degree: 65%

---


# ![PREMIUM](/help/assets/premium.png) 上传自定义标准{#upload-custom-criteria}

可上传 CSV 文件以自定义您的推荐。

## 访问“创建新条件”屏幕

可通过多种方式来访问“[!UICONTROL 创建新标准]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 当您使用可视体验 [!DNL Recommendations] 书写器(VEC)活动 [!UICONTROL 时，您会立即进入“Visual Experience Composer] (Visual Experience Composer [!UICONTROL )”屏幕，在选择Visual Experience Composer(VEC)后，单击“Deplace W/] Recommendations/InsereresetInserise Insert Insert Inse In Insert Inse Be Vide Vide Vide Inse BeSe Be Inser IneDes Inse Bite Vid In Ber Be Vid Inse Vid Ber Vid In In Inse Inse  Pro Pr   Co  然后，您可以选择可用的条件，也可以单击“创 **[!UICONTROL 建条件”]**。 如果创建了新标准，则可以选择保存标准以便与其他活动一起 [!DNL Recommendations] 使用。 For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 编辑 [!DNL Recommendations] 活动时，在页面上的[!UICONTROL 推荐位置]框中单击，然后选择&#x200B;**[!UICONTROL 更改标准]**。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 您将可以选择保存新建的标准，以供在其他 [!DNL Recommendations] 活动中使用。

以下步骤假定您使用第 [!UICONTROL 一种方法访问] “创建新条件”屏幕：“ **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]** ”库屏幕。

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击 **[!UICONTROL 创建条件]** >上 **[!UICONTROL 传自定义条件]**。

1. 在以下各节中配置信息。

## 基本信息 {#info}

1. 键入&#x200B;**[!UICONTROL 标准名称]**。

   这是用于描述标准的“内部”名称。例如，您可能希望将标准命名为“利润最高的产品”，但是不希望公开显示此名称。请参阅下一步骤，以设置公开显示的标题。

   ![“基本信息”部分](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. 为使用该标准的所有“推荐”键入一个要在页面上公开显示的&#x200B;**[!UICONTROL 显示标题]**。

   例如，使用此标准显示推荐时，您可能想要显示“查看了这个项目，也查看了那个项目的人”或“相似产品”。

1. 键入对标准的简短&#x200B;**[!UICONTROL 描述]**。

   说明应帮助您确定标准，并可能包含有关标准用途的信息。

1. 根据推荐活动的目标选择行业垂直。

   | 垂直行业 | 目标 |
   |--- |--- |
   | 零售/电子商务 | 转化促进完成购买 |
   | 潜在客户拓展/B2B/金融服务 | 转化但不购买 |
   | 媒体/出版 | 参与度 |

   根据您选择的垂直行业，其他标准选项将会发生相应的更改。

1. 选择&#x200B;**[!UICONTROL 页面类型]**。

   您可以选择多个页面类型。

   垂直行业和页面类型可一起用于对已保存的标准进行分类，从而使其更易于在其他 [!DNL Recommendations] 活动中重复使用。

1. 选择&#x200B;**[!UICONTROL 推荐键]**。

   有关基于键的标准的更多信息，请参阅[使推荐基于推荐键](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md)。

1. 选择&#x200B;**[!UICONTROL 推荐逻辑]**。

   有关推荐逻辑选项的更多信息，请参阅[标准](../../c-recommendations/c-algorithms/algorithms.md)。

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

## 内容 {#content}

Content rules determine what happens if the number of recommended items does not fill your [recommendations design](/help/c-recommendations/c-design-overview/design-overview.md). It is possible for [!DNL Recommendations] criteria to return fewer recommendations than your design calls for. 例如，如果您的设计有四个项目的插槽，但条件仅导致推荐两个项目，则可以将其余插槽留空，也可以使用备份建议来填充额外的插槽。

![内容部分](/help/c-recommendations/c-algorithms/assets/content.png)

1. （可选）将“部 **[!UICONTROL 分设计渲染]** ”切换滑至“开启”位置。

   将尽可能多地填充插槽，但设计模板可能包括剩余插槽的空白空间。 如果禁用此选项，且内容不足以填充所有可用插槽，则不提供建议，而是显示默认内容。

   如果希望推荐使用空的插槽，请启用此选项。 如果您希望推荐插槽中根据您的条件填充内容，而空插槽中填充了来自您网站的类似或热门内容，请使用备份推荐，如下一步所述。

1. （可选）将“显 **[!UICONTROL 示备份Recommendations]** ”切换到“打开”位置。

   从您网站中随机选择查看次数最多的产品，填充设计中剩余的空白插槽。

   使用备份推荐可确保您的推荐设计能够填满所有可用的插槽。 假设您有4 x 1设计，如下所示：

   ![4 x 1设计](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   假设您的条件仅建议两个项目。 如果启用“部 [!UICONTROL 分设计渲染] ”选项，则前两个插槽已填满，但其余两个插槽仍为空。 但是，如果启用“显 [!UICONTROL 示备份Recommendations] ”选项，则前两个插槽将根据您指定的条件填充，其余两个插槽则根据您的备份建议填充。

   下面的矩阵显示了使用“部分设计渲染”和“备 [!UICONTROL 份Recommendations”选项] 时 [!UICONTROL 将观察到的] 结果：

   | 局部设计渲染 | 备用 Recommendations | 结果 |
   |--- |--- |--- |
   | 禁用 | 禁用 | 如果返回的推荐少于设计所需的推荐，则推荐设计将被替换为默认内容，并且不显示任何推荐。 |
   | 启用 | 禁用 | 设计会进行渲染，但如果返回的推荐少于设计所需的推荐，则可能包含空白区域。 |
   | 启用 | 启用 | 备用推荐将填满可用的设计“版块”，从而完全渲染您的设计。<br>如果将包含规则应用于备用推荐时会限制符合条件的备用推荐的数量，以致于设计无法填满，则会局部渲染设计。<br>如果标准未返回任何推荐，并且包含规则将备用推荐限制为零，则设计将被替换为默认内容。 |
   | 禁用 | 启用 | 备用推荐将填满可用的设计“版块”，从而完全渲染您的设计。<br>如果将包含规则应用于备用推荐时会限制符合条件的备用推荐的数量，以致于设计无法填满，则设计将被替换为默认内容，并且不会显示任何推荐。 |

   有关详细信息，请参 [阅使用备份建议](/help/c-recommendations/c-algorithms/backup-recs.md)。

1. （视情况而定）如果您在上 **[!UICONTROL 一步中选择了]** “显示备份Recommendations” **[!UICONTROL ，则可以启用“应]**&#x200B;用包含规则”来备份建议。

   包含规则确定推荐中包含哪些项目。 可用的选项取决于您的垂直行业。

   有关更多详细信息，请参阅 [在下面指定包含规则](#inclusion) 。

1. （可选）将“推荐 **[!UICONTROL 先前购买的项目]** ”滑动至“开启”位置。

   此设置基于 `productPurchasedId`。默认行为是不推荐以前购买的项目。在大多数情况下，您不想促销客户最近购买的项目。如果您销售的是人们通常只买一次的物品，例如皮划艇，那么此选项很有用。如果您销售人们反复回来购买的物品，如洗发水或其他个人物品，您应启用此选项。

## 包含规则 {#inclusion}

提供一些选项帮助您减少推荐中显示的项目。您可以在创建标准或促销活动时使用包含规则。

![包含规则](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

包含规则是可选的；但是，通过设置这些详细信息，您可以更好地控制推荐中显示的项目。配置的每个详细信息都会进一步限定显示条件。

例如，您可以选择仅显示库存超过 50 双且价格在 25 美元至 45 美元之间的女鞋。您还可以对每个属性设置权重，以使对您的业务更为重要的项目最有可能显示出来。

再比如，您可以选择向仅从某些城市访问您的网站并且具有所需大学学位的访客显示职位空缺。

包含规则选项会因垂直行业而异。默认情况下，包含规则会应用于备用推荐。

>[!IMPORTANT]
>
>您应谨慎使用包含规则。在某些情况下动态属性筛选非常有用，例如您的组织设置了一些规则，要求不推荐某个品牌但显示另一品牌。但是，此功能存在机会成本。通过限制某些项目使其不显示（按活动标准通常会显示这些项目），您可能会损失一定比例的提升度。

包含规则会使用“与”连接在一起。所有规则都必须得到满足，才能在推荐中包含某个项目。

如前所述，要创建一个简单的包含规则以仅显示库存超过 50 双且价格在 25 美元至 45 美元之间的女鞋，请执行以下步骤：

1. 设置您要推荐的产品的价格范围。
1. 设置您要推荐的产品的最低库存量。
1. 将推荐配置为仅显示满足特定条件的项目。

   ![](assets/Recs_InclusionRules.png)

   您可以指定仅当列表中的某个属性符合或不符合一个或多个指定的条件时才包含项目。

   可用的计算器取决于您在第一个下拉列表中选择的值。您可以列出多个项目。这些项目会使用“或”进行评估。

   多个规则会使用“与”连接在一起。

   >[!NOTE]
   >
   >此选项限制了在推荐中显示的项目数。它不影响推荐在哪些页面上显示。要限制显示推荐的位置，请在体验编辑器中选择页面。

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## 上传CSV

1. 选择 CSV 文件的&#x200B;**[!UICONTROL 位置]**。

   ![上传CSV部分](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   要成功上传，CSV 文件的格式设置必须正确。单击&#x200B;**[!UICONTROL 下载 CSV 模板]**，可获取格式正确的 CSV 文件。

   您可以选择以下两个位置：

   * **FTP：**&#x200B;要通过 FTP 服务器上传 CSV 文件，请选择 **[!UICONTROL FTP]**，然后输入所需信息。您可以选择使用 SSL，SSL 会使用 FTPS 协议安全地传输 CSV 文件。
   * **URL:** 要从URL上传CSV文件，请选 **[!UICONTROL 择]** URL，然后输入源URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

   >[!NOTE]
   >
   >自定义标准实体（行）最多可包含 1,000 个推荐项目（列）。

自定义标准更新默认为“累计”。CSV 上传文件中指定的新键值对会覆盖现有的键值对。没有在 CSV 上传中指定键的现有键值对仍可用于交付，并且将 31 天内到期，从上次将其作为 CSV 文件的一部分上传的时间开始计算。

要使设置能够放弃下一次 CSV 上传中未包含的现有结果，请与客户关怀团队联系。如果启用此设置，则只有自定义 CSV 信息源文件中存在的键才可用于交付。此设置适用于所有自定义标准。

自定义标准信息源每 24 小时更新一次。

您可以在“推荐”>“标准”页面上各标准卡片的底部查看自定义标准的上传状态和同步状态。您还可以在编辑自定义标准时在“编辑”对话框中查看状态。

正确无误的上传流程应当为“已计划”>“正在下载信息源文件”>“正在导入”>“成功”。

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| 错误消息 | 详细信息 |
|--- |--- |
| 未知错误 | 指示出现内部技术错误。 |
| 解析错误 | 信息源文件格式可能出现问题。请更正文件格式，然后重新保存算法，这将重新启动文件下载流程。 |
| 未找到服务器 | 请提供 Internet 上可见的 IP 或主机名称。 |
| 凭据错误 | 请提供服务器上某个活跃帐户的有效用户名和密码。 |
| 未找到目录 | 请提供服务器上存在的目录。 |
| 未找到文件 | 请提供服务器上所指示目录中存在的文件名称。 |

## 培训视频：在“推荐”中创建标准 (12:33) ![教程徽章](/help/assets/tutorial.png)

此视频包含以下信息（有关上传自定义条件的详细信息从11:43开始）:

* 创建标准
* 创建标准序列
* 上传自定义标准

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)