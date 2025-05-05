---
keywords: 创建自定义标准;算法;标准;推荐标准;CSV;FTP;上传 CSV
description: 了解如何上传CSV文件以在Adobe [!DNL Target] Recommendations中自定义您的推荐。
title: 如何在 [!DNL Recommendations]中上传自定义标准？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 33%

---

# 上传自定义标准

上传CSV文件以在[!DNL Adobe Target]中自定义您的推荐。

可通过多种方式访问[!UICONTROL Create New Criteria]屏幕。 某些屏幕选项会根据您访问该屏幕的方式而有所不同。

* 在&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕上，单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。 您在此处创建的标准会自动设置为可用于所有 [!DNL Recommendations] 活动。
* 使用[!UICONTROL Visual Experience Composer] (VEC)创建[!DNL Recommendations]活动时，在页面上选择一个元素并单击[!UICONTROL Replace w/ Recommendations]、[!UICONTROL Insert Recommendations Before]或[!UICONTROL Insert Recommendations After]后，您会立即转到[!UICONTROL Select Criteria]屏幕。 然后，您可以选择可用的标准，也可以单击&#x200B;**[!UICONTROL Create Criteria]**。 如果创建新标准，则可以保存标准以供其他[!DNL Recommendations]活动使用。 有关详细信息，请参阅[创建Recommendations活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。
* 编辑[!DNL Recommendations]活动时，单击页面上的[!UICONTROL Recommendations Location]框并选择&#x200B;**[!UICONTROL Change Criteria]**。 在[!UICONTROL Select Criteria]屏幕上单击&#x200B;**[!UICONTROL Create Criteria]**。 您可以保存新建的标准，以供在其他[!DNL Recommendations]活动中使用。

以下步骤假定您使用第一个方法访问[!UICONTROL Create New Criteria]屏幕： **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕。

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**。

1. 单击&#x200B;**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**。

1. 在[基本信息](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)部分中填写信息。

1. 从&#x200B;**[!UICONTROL Select Algorithm Type]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Custom Criteria]**。

1. 从&#x200B;**[!UICONTROL Algorithm]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Custom Algorithm]**。

   >[!NOTE]
   >
   >上述步骤导致[!UICONTROL Upload CSV]部分显示在[!UICONTROL Create Criteria]对话框的底部。

1. （视情况而定）在[备份内容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)部分中填写信息。

1. （视情况而定）在[包含规则](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)部分中填写信息。

1. 在&#x200B;**[!UICONTROL Upload CSV]**&#x200B;部分中，选择CSV文件的&#x200B;**[!UICONTROL Location]**。

要成功上传，CSV 文件的格式设置必须正确。单击&#x200B;**[!UICONTROL Download the CSV template]**&#x200B;可获取格式正确的CSV文件。

您可以选择以下两个位置：

    * **FTP：**&#x200B;若要从FTP服务器上传CSV文件，请选择&#x200B;**[!UICONTROL FTP]**，然后输入所需信息。 您可以使用SSL，SSL会使用FTPS协议安全地传输CSV文件。
    
    * **URL：**&#x200B;要通过URL上传CSV文件，请选择&#x200B;**[!UICONTROL URL]**，然后输入信息源URL。

1. 单击 **[!UICONTROL Create]**。

## 注意事项

* 自定义标准实体（行）最多可包含 1,000 个推荐项目（列）。

* 自定义标准更新默认为“累计”。CSV 上传文件中指定的新键值对会覆盖现有的键值对。没有在CSV上传中指定键的现有键值对仍可用于交付，并且会在上次将其作为CSV文件的一部分上传后的31天内过期。

  要使设置能够放弃下一次 CSV 上传中未包含的现有结果，请与客户关怀团队联系。如果启用此设置，则只有自定义CSV馈送文件中存在的键可用于交付。 此设置适用于所有自定义标准。

* 自定义标准信息源每 24 小时更新一次。

  您可以在[!UICONTROL Recommendations] > [!UICONTROL Criteria]页面上看到每个条件的自定义条件上传的上传和同步状态。 编辑自定义标准时，您还可以在[!UICONTROL Edit]对话框中查看状态。

* 无错误上载的流程应为[!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful]。

* 如果[!DNL Target]在上传时遇到问题，您可能会收到以下错误消息：

  | 错误消息 | 详细信息 |
  |--- |--- |
  | 未知错误 | 指示出现内部技术错误。 |
  | 解析错误 | 信息源文件格式可能出现问题。更正文件格式并重新保存算法，这会重新启动文件下载过程。 |
  | 未找到服务器 | 请提供 Internet 上可见的 IP 或主机名称。 |
  | 凭据错误 | 请提供服务器上某个活跃帐户的有效用户名和密码。 |
  | 未找到目录 | 请提供服务器上存在的目录。 |
  | 未找到文件 | 请提供服务器上所指示目录中存在的文件名称。 |
