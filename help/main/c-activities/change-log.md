---
keywords: 活动更改日志；更改日志
description: 访问Adobe [!DNL Target]中的活动更改日志，以查看活动更改人员和更改时间的记录。
title: 如何查看活动更改日志？
feature: Activities
exl-id: 72a901c1-4fba-4044-b72b-393cab56b936
TQID: 'https://experienceleague.adobe.com/YmadzVwbj4Hy1bk3Q7a0hp9oZ7-lSgl12ImQaEsiDwU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 10%
---
# 活动更改日志 {#change-log}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何查看对活动执行的操作、执行者以及执行时间。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL 更改日志]**&#x200B;记录对活动执行的操作，包括更改内容、更改人员和更改时间。 它提供了活动的清晰历史记录，并且填充了&#x200B;**[!UICONTROL 更改日志]**&#x200B;页面以进行实时分析。

要访问&#x200B;**[!UICONTROL 更改日志]**&#x200B;页，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 活动]**，然后单击列表中的活动。
1. 单击左边栏中的&#x200B;**[!UICONTROL 更改日志]**。

   该页面列出了在创建、更新、激活或停用活动时执行的操作、操作的日期以及执行操作的用户。 此外，还会列出对活动中使用的自定义目标和选件所做的更改。

   ![更改日志菜单](assets/change_logs.png)

1. 要以升序或降序列出操作，请单击&#x200B;**[!UICONTROL Date]**&#x200B;列标题。

1. 刷新页面可看到状态更改。

## 目标审核日志API

* [修订版本：按上一个作者的名称和修改后的时间戳获取审核日志](https://developer.adobe.com/target/administer/admin-api/#tag/Revisions){target=_blank}
* [列出活动更改日志](https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/getChangelog){target=_blank}
