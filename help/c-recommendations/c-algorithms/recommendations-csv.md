---
keywords: 创建自定义标准;算法;标准;推荐标准;CSV;FTP;上传 CSV
description: 了解如何在Adobe [!DNL Target] Recommendations中上传CSV文件以自定义您的推荐。
title: 如何在Recommendations中上传自定义标准？
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 7a52f7c046fb00672ef1b13704308be39f89c7ad
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/assets/premium.png) 上传自定义标准

上传CSV文件以在[!DNL Adobe Target]中自定义您的推荐。

可通过多种方式来访问“[!UICONTROL 创建新标准]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**。 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 使用[!UICONTROL 可视化体验编辑器](VEC)创建[!DNL Recommendations]活动时，在页面上选择某个元素并单击[!UICONTROL 替换w/ Recommendations]、 [!UICONTROL 在]之前插入Recommendations或[!UICONTROL 在]之后插入Recommendations后，您会立即转到[!UICONTROL 选择标准]屏幕。 然后，您可以选择可用的标准，也可以单击&#x200B;**[!UICONTROL 创建标准]**。 如果您创建新标准，则可以保存标准以供与其他[!DNL Recommendations]活动一起使用。 有关更多信息，请参阅[创建Recommendations活动](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 编辑 [!DNL Recommendations] 活动时，在页面上的[!UICONTROL 推荐位置]框中单击，然后选择&#x200B;**[!UICONTROL 更改标准]**。在[!UICONTROL 选择标准]屏幕上，单击&#x200B;**[!UICONTROL 创建标准]**。 您可以保存新标准，以便与其他[!DNL Recommendations]活动一起使用。

以下步骤假定您使用第一种方法访问[!UICONTROL Create New Criteria]屏幕：**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**&#x200B;库屏幕。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**。

1. 单击&#x200B;**[!UICONTROL 创建标准]**。

1. 填写[基本信息](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info)部分中的信息。

   1. 从&#x200B;**[!UICONTROL 选择算法]**&#x200B;类型下拉列表中，选择&#x200B;**[!UICONTROL 自定义标准]**。

   1. 从&#x200B;**[!UICONTROL 算法]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 自定义算法]**。

      >[!NOTE]
      >
      >上述步骤会导致[!UICONTROL 上传CSV]部分显示在[!UICONTROL 创建新标准]对话框的底部。

1. （视情况而定）填写[备份内容](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)部分中的信息。

1. （视情况而定）填写[包含规则](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)部分中的信息。

1. 在&#x200B;**[!UICONTROL 上传CSV]**&#x200B;部分中，选择CSV文件的&#x200B;**[!UICONTROL 位置]**。

   ![上传CSV部分](assets/upload-csv.png)

   要成功上传，CSV 文件的格式设置必须正确。单击&#x200B;**[!UICONTROL 下载 CSV 模板]**，可获取格式正确的 CSV 文件。

   您可以选择以下两个位置：

   * **FTP：**&#x200B;要通过 FTP 服务器上传 CSV 文件，请选择 **[!UICONTROL FTP]**，然后输入所需信息。您可以使用SSL，SSL使用FTPS协议安全地传输CSV文件。
   * **URL:** 要通过URL上传CSV文件，请选择 **[!UICONTROL URL]**，然后输入一个信息源URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 注意事项

* 自定义标准实体（行）最多可包含 1,000 个推荐项目（列）。

* 自定义标准更新默认为“累计”。CSV 上传文件中指定的新键值对会覆盖现有的键值对。没有在CSV上传中指定键的现有键值对仍可用于交付，并会在31天内过期，从它们上次作为CSV文件的一部分上传时算起。

   要使设置能够放弃下一次 CSV 上传中未包含的现有结果，请与客户关怀团队联系。如果启用了此设置，则只有自定义CSV信息源文件中存在的键可用于交付。 此设置适用于所有自定义标准。

* 自定义标准信息源每 24 小时更新一次。

   您可以在[!UICONTROL Recommendations] > [!UICONTROL 标准]页面上的每个标准卡片的底部查看自定义标准上传的上传和同步状态。 编辑自定义标准时，您还可以在[!UICONTROL 编辑]对话框中看到状态。

* 无错误上传的流程应为[!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful]。

* 如果[!DNL Target]在上传时遇到问题，您可能会收到以下错误消息：

   | 错误消息 | 详细信息 |
   |--- |--- |
   | 未知错误 | 指示出现内部技术错误。 |
   | 解析错误 | 信息源文件格式可能出现问题。更正文件格式并重新保存算法，这会重新启动文件下载过程。 |
   | 未找到服务器 | 请提供 Internet 上可见的 IP 或主机名称。 |
   | 凭据错误 | 请提供服务器上某个活跃帐户的有效用户名和密码。 |
   | 未找到目录 | 请提供服务器上存在的目录。 |
   | 未找到文件 | 请提供服务器上所指示目录中存在的文件名称。 |

## 培训视频：在“推荐”中创建标准 (12:33) ![教程徽章](/help/assets/tutorial.png)

此视频包含以下信息（有关上传自定义标准的详细信息，开始于11:43）：

* 创建标准
* 创建标准序列
* 上传自定义标准

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
