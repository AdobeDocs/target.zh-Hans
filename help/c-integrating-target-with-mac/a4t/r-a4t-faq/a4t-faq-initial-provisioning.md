---
description: 本主题包含有关将 Analytics 配置为 Target 报表源 (A4T) 的常见问题解答。
keywords: FAQ;常见问题解答;Analytics for Target;A4T;配置;Adobe Experience Cloud
seo-description: 本主题包含有关将 Analytics 配置为 Target 报表源 (A4T) 的常见问题解答。
seo-title: 初始配置 - A4T 常见问题解答
solution: Target
title: 初始配置 - A4T 常见问题解答
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 初始配置 - A4T 常见问题解答{#initial-provisioning-a-t-faq}

本主题包含有关将 Analytics 配置为 Target 报表源 (A4T) 的常见问题解答。

## 如何设置多页A4T活动？

要实施基本的多页A4T用例，请执行以下操作：

* 在活动登陆URL/页面上为目标(at. js或mbox. js)和Analytics实施JavaScript库。实施这两个解决方案将为每个访客的Analytics数据拼接Target数据。此数据保留在Analytics中，直到默认过期期设置为90天。

* 对于网站上的剩余页面，只需跟踪Analytics指标，即可在这些页面上实施Analytics。无需在这些页面上实施Target。在这些页面中捕获的Analytics量度会自动缝合到用户最初符合从先前项目符号附加到该访客的目标信息的“目标”活动。

## 如何判断我的 Target 帐户是否启用了 A4T？{#section_4437D284448F4313BF953D4B6EDBACA6}

您需要具有一个 Analytics 用户帐户和一个 Target 用户帐户，才能在定义 Analytics 活动时选择报表包。必须按照相应文档中的所述来配置您的用户帐户。请参阅[用户权限要求](../../../c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

如果您所在的一个或多个 Experience Cloud 组拥有 Analytics 和 Target 访问权限，并且您自己也有权访问所有报表包，则您应会在**[!UICONTROL 创建活动]**下看到用于使用 Analytics 创建 A/B 测试的选项。

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
