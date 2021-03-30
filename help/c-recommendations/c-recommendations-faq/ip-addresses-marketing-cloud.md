---
keywords: IP地址；IP地址；白名单；允许列表；防火墙；记录；源；服务器；adobe marketing cloud；推荐
description: 视图目标 Recommendations源处理服务器中使用的IP地址列表，以帮助您配置防火墙，以允许来自Adobe服务器的IP地址。
title: Recommendations源处理服务器使用哪些IP地址？
feature: Recommendations
translation-type: tm+mt
source-git-commit: d90069169a23bc432c7731b3129ca7c9572f6cf4
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 7%

---


# ![PREMIUM](/help/assets/premium.png)“推荐”信息源处理服务器使用的 IP 地址

列表[!DNL Adobe Target] [!DNL Recommendations]源处理服务器中使用的IP地址，以帮助您配置防火墙以允许来自Adobe服务器的IP地址。

[!DNL Target] [!UICONTROL 建] 议在访问客户的FTP服务器时，使用以下AWS主机：

| 位置 | 主机 |
| --- | --- |
| 俄勒冈州 | `44.241.237.28` |
| 俄勒冈州 | `44.232.167.82` |
| 俄勒冈州 | `52.41.252.205` |

[!DNL Target] [!UICONTROL RecommendationsAPI] 也使用相同的AWS主机。

>[!NOTE]
>
>这些IP地址上次更新时间为2021年3月16日。 以前，访问FTP服务器的服务器位于192.243.242.0/24 IP地址CIDR块中。 承载Recommendations API的服务器位于192.243.224.0/20 IP地址CIDR块中。

