---
keywords: 创建自定义标准；算法；标准；推荐标准；CSV；FTP；SFTP；上传CSV
description: 了解如何上传CSV文件以自定义Adobe [!DNL Target]推荐中的推荐。
title: 上传自定义标准
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: 'https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 14%
---
# 上传自定义标准 {#upload-custom-criteria}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何上传推荐的CSV文件以在[!DNL Adobe Target Recommendations]中创建自定义标准。

>[!ENDSHADEBOX]

自定义标准使用已上传到[!DNL Target]的推荐的CSV文件。 这允许在[!DNL Target]之外计算的推荐在[!DNL Recommendations]活动中交付。 有关自定义标准如何工作的更多信息，请参阅[Target的推荐算法背后的科学](/help/main/c-recommendations/c-algorithms/recommendations-algorithms.md)。

自定义标准是从&#x200B;**[!UICONTROL 新建标准]**&#x200B;屏幕创建的。 有关访问此屏幕的方法，请参阅[访问“创建新标准”屏幕](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#access-create-criteria)。 以下步骤从&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;库屏幕开始。

1. 单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 标准]**。

1. 单击&#x200B;**[!UICONTROL 创建标准]** > **[!UICONTROL 创建标准]**。

   ![创建条件菜单打开的标准页面，其中显示“创建标准”和“创建标准序列”](../assets/criteria_create_1.png)

1. 在[基本信息](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)部分中填写信息。

1. 从&#x200B;**[!UICONTROL Select算法类型]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 自定义标准]**。 从&#x200B;**[!UICONTROL 算法]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 自定义算法]**。

   将自定义标准作为算法类型并将自定义算法作为算法的推荐算法部分![](../assets/criteria_create_9.png)

1. （视情况而定）在[备份内容](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)和[包含规则](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)部分中填写信息。

1. 在&#x200B;**[!UICONTROL 上传CSV]**&#x200B;部分中，选择CSV文件的&#x200B;**[!UICONTROL 位置]**。

   要成功上传，CSV 文件的格式设置必须正确。 若要获取格式正确的CSV文件，请单击&#x200B;**[!UICONTROL 下载CSV模板]**。

   可以使用以下位置选项：

   * **FTP**：若要从FTP服务器上传CSV文件，请选择&#x200B;**[!UICONTROL FTP]**，然后输入所需信息。 SSL使用FTPS协议来安全地传输CSV文件。

   * **SFTP**：要从SFTP服务器上传CSV文件，请选择&#x200B;**[!UICONTROL SFTP]**，然后输入主机名或IP地址、端口（默认为22）、用户名、密码和/或SSH私钥、目录和文件名。 有关详细信息，请参阅[支持的SFTP服务器设置](/help/main/c-recommendations/c-products/feeds.md#steps)。

     SFTP不会更改自定义标准CSV格式。 使用`# Key,Recommendation_1,...`格式。 采用其他信息源格式的CSV文件会导致导入失败。

   * **URL**：若要从URL上传CSV文件，请选择&#x200B;**[!UICONTROL URL]**，然后输入信息源URL。

     ![使用高亮显示的位置选项FTP、SFTP和URL以及选定的SFTP上传CSV部分](../assets/criteria_create_10.png)

1. 单击&#x200B;**[!UICONTROL 创建]**。

## 注意事项

* 自定义标准实体（行）最多可包含 1,000 个推荐项目（列）。

* 默认情况下，自定义标准更新是“累积的”。 CSV上传文件中新的键值对会覆盖现有的键值对。 其键不在CSV上传中的现有键值对仍可用于交付，并在上次作为CSV文件的一部分上传这些键值对31天后过期。

  要丢弃未包含在下次CSV上传中的现有结果，请联系客户关怀以启用相应的设置。 启用此设置后，只有自定义CSV馈送文件中存在的键可用于交付。 此设置适用于所有自定义标准。

* 自定义标准信息源每 24 小时更新一次。

  每个自定义标准上传的上传和同步状态将显示在&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 标准]**&#x200B;页面上。 编辑自定义条件时，状态也会显示在&#x200B;**[!UICONTROL 编辑]**&#x200B;对话框中。

* 无错误上传的流程为&#x200B;**[!UICONTROL 已计划]** > **[!UICONTROL 正在下载信息源文件]** > **[!UICONTROL 正在导入]** > **[!UICONTROL 成功]**。

* 如果[!DNL Target]在上传时遇到问题，则可能会出现以下错误消息：

  | 错误消息 | 详细信息 |
  |--- |--- |
  | 未知错误 | 指示出现内部技术错误。 |
  | 解析错误 | 信息源文件格式可能出现问题。 更正文件格式并重新保存算法，这会重新启动文件下载过程。 |
  | 未找到服务器 | 提供在Internet上可见的IP或主机名。 |
  | 凭据错误 | 请提供服务器上某个活跃帐户的有效用户名和密码。 |
  | 未找到目录 | 请提供服务器上存在的目录。 |
  | 未找到文件 | 提供服务器上指定目录中存在的文件的名称。 |
