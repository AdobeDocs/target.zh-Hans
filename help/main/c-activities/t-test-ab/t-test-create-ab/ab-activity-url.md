---
keywords: 活动URL；URL；其他URL
description: 了解如何指定活动URL，以确定测试中使用的页面，以及在使用设计测试时打开的页面 [!DNL Adobe Target].
title: A/B活动中的活动URL是什么？
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 6bca763d24649349dbc7cdf6e5f2dbc4ac0a480d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 64%

---

# 活动 URL

活动URL可决定测试中使用的页面，以及在使用Adobe Target设计测试时打开的页面。

在活动创建过程中，如果收到相应的提示，请指定活动 URL。应键入完整的 URL（包括 `https://`**[!UICONTROL ），然后单击创建]**。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `http://www.adobe.com`] 和 [!DNL `https://www.adobe.com`] 均匹配。

## 指定其他 URL

默认情况下， [!UICONTROL 可视化体验编辑器] 打开中指定的页面 [可视化体验编辑器设置](/help/main/administrating-target/visual-experience-composer-set-up.md). 在活动创建过程中，您可以指定其他页面。

1. 要在页面之后显示其他页面，请执行以下操作 [!UICONTROL 可视化体验编辑器] 打开，位于 **[!UICONTROL 体验]** 页面上，单击 **[!UICONTROL 配置]** 齿轮图标，然后选择 **[!UICONTROL 页面交付]**.

1. 在中指定URL **[!UICONTROL URL]** 字段。

   ![“页面交付”对话框](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

1. （视情况而定）单击&#x200B;**[!UICONTROL 添加模板规则]**，为活动添加更多页面或部分。

   其他规则可以基于以下任何一项：

   * URL
   * 域
   * 路径
   * 话题标签 (#) 片段
   * 查询
   * mbox 参数

   可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

1. 完成后单击&#x200B;**[!UICONTROL 保存]**。

如果您输入的 URL 所对应的网站不包含 [!DNL Target] Standard JavaScript 代码，则您将无法选择页面元素。

默认情况下，[!UICONTROL 可视化体验编辑器]不允许更改包含 JavaScript 的元素，如旋转横幅。如果您希望能够使用&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;更改这些元素，可以关闭[!UICONTROL 使用 JavaScript 渲染]。

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。
