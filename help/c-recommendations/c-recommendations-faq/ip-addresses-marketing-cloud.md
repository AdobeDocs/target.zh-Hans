---
keywords: IP地址；IP地址；白名单；允许列表；防火墙；记录；源；服务器；adobe marketing cloud；推荐
description: 视图目标 Recommendations源处理服务器中使用的IP地址列表，以帮助您配置防火墙，以允许来自Adobe服务器的IP地址。
title: Recommendations源处理服务器使用哪些IP地址？
feature: Recommendations
translation-type: tm+mt
source-git-commit: 55b246f5f0d660e6c4f71352c5b638347d55ac28
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 13%

---


# ![PREMIUM](/help/assets/premium.png)“推荐”信息源处理服务器使用的 IP 地址

列表[!DNL Adobe Target] [!DNL Recommendations]源处理服务器中使用的IP地址，以帮助您配置防火墙以允许来自Adobe服务器的IP地址。

[!DNL Target] [!UICONTROL 建] 议在访问客户的FTP服务器时，活动使用以下IP地址：

| CIDR 表示法 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

[!DNL Target]  RecommendationsAPI使用以下IP地址：

| CIDR 表示法 |
|---|
| 44.241.237.28/32 |
| 44.232.167.82/32 |
| 52.41.252.205/32 |

>[!NOTE]
>
>这些IP地址上次更新时间为2021年3月16日。 以前，访问FTP服务器的服务器位于192.243.242.0/24 IP地址CIDR块中。 承载Recommendations API的服务器位于192.243.224.0/20 IP地址CIDR块中。

