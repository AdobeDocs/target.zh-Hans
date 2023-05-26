---
keywords: 创建自定义标准;算法;标准;推荐标准;CSV;FTP;上传 CSV
description: 了解如何上传CSV文件以自定义Adobe中的推荐 [!DNL Target] Recommendations。
title: 如何在Recommendations中上传自定义标准？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 39%

---

# 上传自定义标准

上传CSV文件以在中自定义您的推荐 [!DNL Adobe Target].

可通过多种方式来访问“[!UICONTROL 创建新标准]”屏幕。某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在 **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]** 库屏幕，单击 **[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**. 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 创建时 [!DNL Recommendations] 使用 [!UICONTROL 可视化体验编辑器] (VEC)，您会立即转到 [!UICONTROL 选择标准] 屏幕上，然后在页面上选择一个元素并单击 [!UICONTROL 替换为Recommendations]， [!UICONTROL 在之前插入Recommendations]，或 [!UICONTROL 在后面插入Recommendations]. 然后，您可以选择可用的标准，也可以单击 **[!UICONTROL 创建标准]**. 如果创建新标准，则可保存标准以供其他人员使用 [!DNL Recommendations] 活动。 有关更多信息，请参阅 [创建Recommendations活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* 编辑 [!DNL Recommendations] 活动时，在页面上的[!UICONTROL 推荐位置]框中单击，然后选择&#x200B;**[!UICONTROL 更改标准]**。在 [!UICONTROL 选择标准] 屏幕，单击 **[!UICONTROL 创建标准]**. 您可以保存新建的标准，以供其他人员使用 [!DNL Recommendations] 活动。

以下步骤假定您访问 [!UICONTROL 创建新标准] 使用第一种方法筛选： **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]** 库屏幕。

1. 单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 标准]**.

1. 单击&#x200B;**[!UICONTROL 创建标准]**。

1. 将信息填入 [基本信息](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 部分。

   1. 从 **[!UICONTROL 选择算法]** “类型”下拉列表，选择 **[!UICONTROL 自定义标准]**.

   1. 从 **[!UICONTROL 算法]** 下拉列表，选择 **[!UICONTROL 自定义算法]**.

      >[!NOTE]
      >
      >上述步骤会导致 [!UICONTROL 上传CSV] 部分以显示在页面底部 [!UICONTROL 创建新标准] 对话框。

1. （视情况而定）将相应信息填入 [备份内容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) 部分。

1. （视情况而定）将相应信息填入 [包含规则](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 部分。

1. 在 **[!UICONTROL 上传CSV]** 部分，选择 **[!UICONTROL 位置]** CSV文件的属性。

   ![上传CSV部分](assets/upload-csv.png)

   要成功上传，CSV 文件的格式设置必须正确。单击&#x200B;**[!UICONTROL 下载 CSV 模板]**，可获取格式正确的 CSV 文件。

   您可以选择以下两个位置：

   * **FTP：**&#x200B;要通过 FTP 服务器上传 CSV 文件，请选择 **[!UICONTROL FTP]**，然后输入所需信息。您可以使用SSL，它使用FTPS协议安全地传输CSV文件。
   * **URL：** 要通过URL上传CSV文件，请选择 **[!UICONTROL URL]**，然后输入信息源URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 注意事项

* 自定义标准实体（行）最多可包含 1,000 个推荐项目（列）。

* 自定义标准更新默认为“累计”。CSV 上传文件中指定的新键值对会覆盖现有的键值对。没有在CSV上传中指定键的现有键值对仍可用于交付，并且可在上次作为CSV文件的一部分上传这些键值对后的31天内到期。

   要使设置能够放弃下一次 CSV 上传中未包含的现有结果，请与客户关怀团队联系。如果启用了此设置，则只有自定义CSV馈送文件中存在的密钥可用于交付。 此设置适用于所有自定义标准。

* 自定义标准信息源每 24 小时更新一次。

   您可以在上的每个条件卡底部查看自定义条件上传的上传和同步状态。 [!UICONTROL Recommendations] > [!UICONTROL 标准] 页面。 您还可以在 [!UICONTROL 编辑] 对话框。

* 无错误上传的流程应为 [!UICONTROL 已计划] > [!UICONTROL 正在下载信息源文件] > [!UICONTROL 正在导入] > [!UICONTROL 成功].

* 在以下情况下，您可能会收到以下错误消息： [!DNL Target] 上传时遇到问题：

   | 错误消息 | 详细信息 |
   |--- |--- |
   | 未知错误 | 指示出现内部技术错误。 |
   | 解析错误 | 信息源文件格式可能出现问题。更正文件格式并重新保存算法，这会重新启动文件下载过程。 |
   | 未找到服务器 | 请提供 Internet 上可见的 IP 或主机名称。 |
   | 凭据错误 | 请提供服务器上某个活跃帐户的有效用户名和密码。 |
   | 未找到目录 | 请提供服务器上存在的目录。 |
   | 未找到文件 | 请提供服务器上所指示目录中存在的文件名称。 |

## 培训视频：在“推荐”中创建标准 (12:33) ![教程徽章](/help/main/assets/tutorial.png)

本视频包含以下信息（有关上传自定义标准的详细信息从11:43开始）：

* 创建标准
* 创建标准序列
* 上传自定义标准

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
