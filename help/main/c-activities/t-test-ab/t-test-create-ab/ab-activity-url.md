---
keywords: 活动URL；URL；其他URL
description: 了解如何在A/B、体验定位或多变量测试活动中设置[!UICONTROL 活动URL]以定义测试页面并确保准确的测试设计。
title: A/B、体验定位或多变量测试活动中的活动URL是什么？
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# 活动 URL {#ab-activity-url}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何指定A/B、体验定位(XT)或多变量测试(MVT)活动的活动URL，如何显示其他页面，以及如何为更多页面或部分添加规则。

>[!ENDSHADEBOX]

[!UICONTROL 活动URL]确定活动中使用的页面。 在[!DNL Adobe Target]中设计活动时，此页面将在[!UICONTROL 可视化体验编辑器] (VEC)或[!UICONTROL 基于表单的体验编辑器]中打开。

## 指定活动URL {#specify-url}

在活动创建过程中，如果收到相应的提示，请指定活动 URL。 键入完整的URL（包括`https://`），然后单击&#x200B;**[!UICONTROL 创建]**。

>[!NOTE]
>
>[!DNL Target]不区分URL协议（[!DNL https]和[!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://www.adobe.com`]都匹配。

如果您指定的URL所对应的网站不包含[!DNL Target] [at.js JavaScript库或 [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}，则您将无法选择页面元素。

## 显示其他页面 {#different-page}

默认情况下，VEC或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)会打开[可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。

要在VEC打开后显示其他页面，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 体验]**&#x200B;页面上，单击页面顶部的&#x200B;**[!UICONTROL 配置]**，然后选择&#x200B;**[!UICONTROL 页面交付]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;字段中指定URL。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。

默认情况下，VEC 不允许更改包含 JavaScript 的元素，如旋转横幅。 如果您希望能够使用VEC更改这些元素，可以关闭&#x200B;**[!UICONTROL 使用JavaScript渲染]**。

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。

## 为更多页面或部分添加规则 {#add-rules}

若要向活动添加更多页面或部分，请在&#x200B;**[!UICONTROL 页面交付]**&#x200B;设置中单击&#x200B;**[!UICONTROL 添加规则]**，完成后，单击&#x200B;**[!UICONTROL 保存]**。

其他规则可以基于以下任何一项：

* URL
* 域
* 路径
* 话题标签 (#) 片段
* 查询
* mbox 参数
* 自定义

其他规则可以通过AND或OR连接到活动URL。 您添加的所有规则将使用 AND 进行相互评估。
