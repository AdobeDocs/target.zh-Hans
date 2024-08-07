---
keywords: FAQ;常见问题解答;Analytics for Target;A4T;配置;Adobe Experience Cloud
description: 查找有关为 [!DNL Target] (A4T)配置Analytics的常见问题解答，该功能允许您为 [!DNL Target] 活动使用Analytics报表。
title: 可在何处找到有关A4T初始配置的信息？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 46%

---

# 初始配置 - A4T 常见问题解答

本主题包含有关将[!DNL Adobe Analytics]配置为[!DNL Adobe Target] (A4T)的报表源的常见问题解答。

## 如何设置多页面 A4T 活动？

+++回答
要实施基本的多页面A4T用例，请执行以下操作：

* 在活动登陆URL/页面上为Target和Analytics实施JavaScript库。 实施这两个解决方案会将每个访客的 Target 数据与 Analytics 数据拼合在一起。如果默认过期时间设置为 90 天，则在此时间之前，此数据会一直保留在 Analytics。

* 对于网站上将仅跟踪 Analytics 量度的其余网页，则在这些页面上实施 Analytics。无需在这些页面上实施 Target。根据上一步中附加到该访客的 Targe 信息，在这些页面中捕获的 Analytics 量度会自动拼合到用户最初有资格参加的 Target 活动。

+++

## 如何判断我的[!DNL Target]帐户是否启用了A4T？ {#section_4437D284448F4313BF953D4B6EDBACA6}

+++回答
您需要具有Analytics用户帐户和Target用户帐户，才能在定义Analytics活动时选择报表包。 必须按照相应文档中的所述来配置您的用户帐户。请参阅[用户权限要求](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)。

如果您所在的一个或多个Experience Cloud组拥有Analytics和Target访问权限，并且您自己也有权访问所有报表包，则您应会在&#x200B;**[!UICONTROL Create Activity]**&#x200B;下看到用于使用Analytics创建A/B测试的选项。

如果出现配置问题，请检查是否对 A4T 进行了正确配置。

+++

## 我的报表包为何没有加载？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++回答
如果出现以下任何问题，请检查以下各项：

* 确保在Experience Cloud中关联Analytics和Target帐户。
* 某些客户在同一Experience Cloud公司中使用多个Analytics公司登录。 如果您使用多次登录，请确保您登录的上一个Analytics公司是与Target帐户绑定的公司，以实现集成。
* 如果您登录 Experience Cloud 的时间长达数小时，Analytics 会话有时可能会终止。为此，请注销并重新登录，以再次尝试操作。

+++

## 为何在 Target 中看不到 Analytics 选项？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++回答
请参阅“为什么我的报表包未加载？” 上面。 这个问题的根本原因同上。

+++

## 为何在 Analytics 中看不到 A4T 报表？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++回答
请参阅“为什么我的报表包未加载？” （见上文）。这个问题的根本原因同上。

+++

## 为什么[!DNL Target]中的报告为空？ {#section_3837104757464CB488C5A83014A669A1}

+++回答
请参阅“为什么我的报表包未加载？” （见上文）。这个问题的根本原因同上。

+++
