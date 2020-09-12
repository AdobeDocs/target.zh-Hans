---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: 可上传 CSV 文件以自定义您的推荐。
title: 上传自定义标准
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 108bbe65732b7df20caf9df6b3e5b77e3c31c457
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) 上传自定义标准{#upload-custom-criteria}

可上传 CSV 文件以自定义您的推荐。

可通过多种方式来访问“[!UICONTROL 创建新标准]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 当您使用可视体验 [!DNL Recommendations] 书写器(VEC)活动 [!UICONTROL 时，您会立即进入“Visual Experience Composer] (Visual Experience Composer [!UICONTROL )”屏幕，在选择Visual Experience Composer(VEC)后，单击“Deplace W/] Recommendations/InsereresetInserise Insert Insert Inse In Insert Inse Be Vide Vide Vide Inse BeSe Be Inser IneDes Inse Bite Vid In Ber Be Vid Inse Vid Ber Vid In In Inse Inse  Pro Pr   Co  然后，您可以选择可用的条件，也可以单击“创 **[!UICONTROL 建条件”]**。 如果创建了新标准，则可以选择保存标准以便与其他活动一起 [!DNL Recommendations] 使用。 For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 编辑 [!DNL Recommendations] 活动时，在页面上的[!UICONTROL 推荐位置]框中单击，然后选择&#x200B;**[!UICONTROL 更改标准]**。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 您将可以选择保存新建的标准，以供在其他 [!DNL Recommendations] 活动中使用。

以下步骤假定您使用第 [!UICONTROL 一种方法访问] “创建新条件”屏幕：“ **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]** ”库屏幕。

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击 **[!UICONTROL 创建条件]** >上 **[!UICONTROL 传自定义条件]**。

1. Fill in the information in the [Basic Information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

1. 在“数据源”部分 [中填写信](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 息。

1. 在“内容”部分中 [填写](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) 。

1. （视情况而定）填写“内容相似 [性”部分中](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity) 的信息。

1. （视情况而定）填写“包含规则” [部分中的](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 信息。

1. (条件填写属性权重部分 [中的信息](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting) 。

1. 在“上 **[!UICONTROL 传CSV]** ”部分，选 **[!UICONTROL 择CSV]** 文件的位置。

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