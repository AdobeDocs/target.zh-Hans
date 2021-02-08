---
keywords: IP地址；IP地址；白名单允许列表;；防火墙；recs;feed;servers;adobe marketing cloud;recommendations
description: 视图目标Recommendations源处理服务器中使用的列表IP地址，以帮助您配置防火墙以允许来自Adobe服务器的IP地址。
title: Recommendations源处理服务器使用哪些IP地址？
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png)“推荐”信息源处理服务器使用的 IP 地址{#ip-addresses-used-by-recommendations-feed-processing-servers}

位于俄勒冈数据中心的“推荐”信息源处理服务器中使用的 IP 地址列表，可帮助您配置防火墙以允许源自 Adobe 服务器的 IP 地址。

访问客户的 FTP 服务器时，[!DNL Target][!UICONTROL “推荐]”活动会使用以下位于俄勒冈数据中心的 IP 地址（请务必查看以下链接，以了解最新信息）：

| CIDR 表示法 | 起始 IP | 终止 IP |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

[!DNL Target][!UICONTROL “推荐]”API 会使用以下位于俄勒冈数据中心的 IP 地址（请务必查看以下链接，以了解最新信息）：

| CIDR 表示法 | 起始 IP | 终止 IP |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>有关完整、最新的列表，请参阅Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html)中使用的[ IP地址。

