---
keywords: 定位
description: 活动 URL 可决定多变量测试 (MVT) 中使用的页面，以及在 Adobe Target 中设计测试时打开的页面。
title: 活动 URL
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 活动 URL{#activity-url}

活动 URL 可决定[!UICONTROL 多变量测试] (MVT) 中使用的页面，以及在 [!DNL Adobe Target] 中设计测试时打开的页面。

在[活动创建](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)过程中，如果收到相应的提示，请指定活动 URL。键入完整的 URL（包括 `https://`），然后单击&#x200B;**[!UICONTROL 下一步]**。

>[!NOTE]
>
>[!DNL Target] 不区分 URL 协议（[!DNL https] 和 [!DNL http]）。因此，[!DNL `https://www.adobe.com`] 和 [!DNL `http://www.adobe.com`] 均匹配。

默认情况下，[!UICONTROL 可视化体验编辑器] (VEC) 会打开您的[帐户首选项](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)中指定的页面。在活动创建过程中，您可以指定其他页面。

要在 VEC 打开后显示其他页面，请单击&#x200B;**[!UICONTROL 配置]**&#x200B;图标，选择&#x200B;**[!UICONTROL 页面交付]**，然后指定相应的 URL。

![“页面交付”对话框](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

单击&#x200B;**[!UICONTROL 添加模板规则]，为活动添加更多页面和部分。**

其他规则可以基于以下任何一项：

* URL
* 域
* 路径
* 话题标签 (#) 片段
* 查询
* 参数

可以使用 AND 或 OR 将其他规则连接到活动 URL。您添加的所有规则将使用 AND 进行相互评估。

完成后单击&#x200B;**[!UICONTROL 保存]。**

>[!NOTE]
>
>如果您输入的 URL 所对应的网站不包含 Target Standard JavaScript 代码，则您将无法选择页面元素。

默认情况下，VEC 不允许更改包含 JavaScript 的元素，如旋转横幅。如果您希望能够使用&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;更改这些元素，可以关闭[!UICONTROL 使用 JavaScript 渲染]。

>[!NOTE]
>
>在对一个或多个体验的页面进行更改后，如果您更改了 URL，则系统将使用新页面重置体验，而且您所做的更改也会丢失。