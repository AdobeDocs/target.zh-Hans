---
keywords: 重定向；重定向url；发送到其他页面
description: 了解当您希望将访客发送到其他页面而不是在同一页面上显示内容时，如何使用Adobe [!DNL Target]中的“重定向到URL”选项。
title: 能否将页面重定向到其他URL？
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# 重定向到 URL {#redirect-to-url}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何使用&#x200B;**[!UICONTROL 重定向到URL]**&#x200B;选项将访客发送到其他页面，而不是在同一页面上显示内容。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的&#x200B;**[!UICONTROL 重定向到URL]**&#x200B;选项将访客发送到其他页面，而不是在同一页面上显示内容。 它适合比较两个完全不同的页面，而不是一个页面中的内容片段。 然后，A/B测试将页面A与页面B进行比较：一个体验指向默认页面A，另一个体验重定向到页面B。

重定向选件运行可重定向浏览器的JavaScript代码。 该代码使用`window.location.replace();`方法，因此从中对访客进行重定向的页面不会存储在浏览器历史记录中。 因此，访客仍然可以使用浏览器的返回按钮。

## 创建重定向选件 {#create-redirect-offer}

重定向的体验定义访客将发送到的页面，以及（可选）重定向的条件。

1. 创建一个体验。

1. 在&#x200B;**[!UICONTROL 体验]**&#x200B;框架中，单击重定向体验的&#x200B;**[!UICONTROL 更多操作]**&#x200B;图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）。

1. 单击&#x200B;**[!UICONTROL 重定向到URL]**。

   ![更多操作图标](assets/redirect_1.png)

1. 在&#x200B;**[!UICONTROL 重定向到URL]**&#x200B;对话框中，输入页面B的URL。

   ![更多操作图标](assets/redirect_2.png)

1. （可选）Select用于包含当前查询参数的选项。

   如果选择此选项，则访客URL中`?`之后的所有内容都会在重定向时附加到重定向URL。

## 限制

重定向选件具有以下限制：

* **A4T：**&#x200B;使用A4T的活动中的重定向选件需要满足特定最低要求的实施，并且其他重要信息也适用。 请参阅[重定向选件 — A4T常见问题解答](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)。
* **基于表单的体验编辑器：**&#x200B;不在页面所包含的mbox中使用重定向选件。 仅使用来自HTML `<head>`中脚本标记的重定向选件，并始终使用自动创建并为全局mbox设置重定向选件。

>[!NOTE]
>
>要传递登陆页面的反向链接值，请使用HTML选件，而不是重定向选件。

## 已知问题

at.js实施中的重定向活动可能会导致预览URL进入循环，并重复提供选件。 请改用[QA模式](/help/main/c-activities/c-activity-qa/activity-qa.md)预览和测试该活动。 此问题不会影响选件的实际交付。 (TGT-23019)
