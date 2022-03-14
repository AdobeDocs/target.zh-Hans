---
keywords: 故障诊断;常见问题解答;FAQ;全局;全局 mbox
description: 阅读有关Adobe的常见问题解答(FAQ)和答案 [!DNL Target] 全局mbox。
title: 有关全局mbox的常见问题解答有哪些？
feature: at.js
role: Developer
exl-id: ec8399df-5222-44bd-9e61-dfce8fd1694d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 81%

---

# 全局 mbox 常见问题解答

有关全局 mbox 的常见问题解答 (FAQ) 列表。

## 如果 [!DNL Target] 跨多个域设置帐户？ {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

您的帐户仅支持一个全局 mbox。

您可以通过向活动中添加 URL 规则来限制活动运行的位置。有关更多信息，请参阅[在相似页面上包含相同体验](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)。

您还可以在页面上使用 [targetPageParams](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) 来传递参数，然后在 [!UICONTROL 可视化体验编辑器] (VEC) 的“配置 URL”部分选择这些参数，或者在基于表单的体验编辑器中通过将参数添加为“细化”来选择这些参数。

## 如何在 [!DNL Target] 全局mbox? {#section_17AEA933BADA4D169CCEDF5833C41306}

要在 target-global-mbox 中收集收入和订单信息，必须将“mbox 参数”发送到 Target。这些参数是名称/值对，用于将更多信息发送到 Target。Target 会自动查找这些参数（保留名称），以使用它们来填充收入数据。

对于 `orderConfirmPage`，您应该传入 `orderTotal`、`orderId` 和 `productPurchasedId`。

这些参数必须通过 `targetPageParams()`. 有关更多信息，请参阅[将参数传递到全局 Mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)。

您可能还想要向转化中添加定位功能，以便 Target 仅在有人查看了订单确认页面后才在 target-global-mbox 中计入转化次数，如下所示：

![](assets/revenue1.png)

上图所示的“网站页面”部分包含以下几个选项：“当前页面”、“URL”、“包含”及“orderconfirm”。

![](assets/revenue2.png)

上图中的选项包含以下设置：

* **您希望如何衡量此活动：**&#x200B;收入
* **报表的默认视图：**&#x200B;每位访客带来的收入 (RPV)
* **受众采取的哪项操作可指示您的目标已达到？** 已查看 mbox，target-global-mbox
