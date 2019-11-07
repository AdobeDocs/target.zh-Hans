---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;配置;Adobe Experience Cloud
description: 本主题包含有关将 Analytics 配置为 Target 报表源 (A4T) 的常见问题解答。
title: 初始配置 - A4T 常见问题解答
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 初始配置 - A4T 常见问题解答{#initial-provisioning-a-t-faq}

本主题包含有关将 Analytics 配置为 Target 报表源 (A4T) 的常见问题解答。

## 如何设置多页面 A4T 活动？

要实施基本的多页面 A4T 用例，请执行以下操作：

* 在活动登陆 URL/页面上为 Target（at.js 或 mbox.js）和 Analytics 实施 JavaScript 库。实施这两个解决方案会将每个访客的 Target 数据与 Analytics 数据拼合在一起。如果默认过期时间设置为 90 天，则在此时间之前，此数据会一直保留在 Analytics。

* 对于网站上将仅跟踪 Analytics 量度的其余网页，则在这些页面上实施 Analytics。无需在这些页面上实施 Target。根据上一步中附加到该访客的 Targe 信息，在这些页面中捕获的 Analytics 量度会自动拼合到用户最初有资格参加的 Target 活动。

## 如何判断我的 Target 帐户是否启用了 A4T？{#section_4437D284448F4313BF953D4B6EDBACA6}

您需要具有一个 Analytics 用户帐户和一个 Target 用户帐户，才能在定义 Analytics 活动时选择报表包。必须按照相应文档中的所述来配置您的用户帐户。请参阅[用户权限要求](../../../c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

如果您所在的一个或多个 Experience Cloud 组拥有 Analytics 和 Target 访问权限，并且您自己也有权访问所有报表包，则您应会在&#x200B;**[!UICONTROL 创建活动]**&#x200B;下看到用于使用 Analytics 创建 A/B 测试的选项。

如果出现配置问题，请检查是否对 A4T 进行了正确配置。

## 我的报表包为何没有加载？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

如果出现任何此类问题，请检查以下各项：

* 确保您已在 Experience Cloud 中关联了自己的 Analytics 和 Target 帐户。
* 如果您使用了多个 Analytics 公司帐户登录同一个 Experience Cloud 公司帐户，请确保您最后一次登录所使用的 Analytics 公司帐户是绑定到用于集成的 Target 帐户的 Analytics 公司帐户。
* 如果您登录 Experience Cloud 的时间长达数小时，Analytics 会话有时可能会终止。为此，请注销并重新登录，以再次尝试操作。

## 为何在 Target 中看不到 Analytics 选项？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

请参阅“我的报表包为何没有加载？”（见上文）。这个问题的根本原因同上。

## 为何在 Analytics 中看不到 A4T 报表？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

请参阅“我的报表包为何没有加载？”（见上文）。这个问题的根本原因同上。

## 为何我在 Target 中的报表是空的？ {#section_3837104757464CB488C5A83014A669A1}

请参阅“我的报表包为何没有加载？”（见上文）。这个问题的根本原因同上。
