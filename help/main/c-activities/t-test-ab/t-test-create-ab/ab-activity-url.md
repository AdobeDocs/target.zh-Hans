---
keywords: 活动URL；URL；其他URL
description: 了解如何设置[!UICONTROL 活动URL]以定义测试页面并确保准确的测试设计。
title: A/B活动中的活动URL是什么？
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 305
ht-degree: 38%

---

# 活动 URL

活动URL可确定测试中使用的页面，以及在使用[!DNL Adobe Target]设计测试时打开的页面。

在活动创建过程中，如果收到相应的提示，请指定活动 URL。 键入完整的URL（包括`https://`），然后单击&#x200B;**[!UICONTROL 创建]**。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。 因此，[!DNL `http://www.adobe.com`]和[!DNL `https://www.adobe.com`]都匹配。

## 指定其他 URL

默认情况下，[!UICONTROL 可视化体验编辑器]会打开[可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md)中指定的页面。 在活动创建过程中，您可以指定其他页面。

1. （视情况而定）要在[!UICONTROL 可视化体验编辑器]打开后显示其他页面，请在&#x200B;**[!UICONTROL 体验]**&#x200B;页面上单击页面顶部的&#x200B;**[!UICONTROL 配置]**，然后选择&#x200B;**[!UICONTROL 页面交付]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;字段中指定URL。

1. （视情况而定）单击&#x200B;**[!UICONTROL 添加规则]**&#x200B;以向活动添加更多页面或部分。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数
   * 自定义

   其他规则可以通过AND或OR连接到活动URL。 您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。

   如果您输入的URL所对应的网站不包含[!DNL Target]s JavaScript代码，则您将无法选择页面元素。

   默认情况下，[!UICONTROL 可视化体验编辑器]不允许更改包含 JavaScript 的元素，如旋转横幅。 如果您希望能够使用[!UICONTROL 可视化体验编辑器]更改这些元素，可以关闭&#x200B;**[!UICONTROL 使用JavaScript渲染]**。—>

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。
