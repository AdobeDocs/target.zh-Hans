---
keywords: IP 地址;IP 地址;列入允许列表;允许列表;防火墙;推荐;信息源;服务器;adobe marketing cloud;推荐
description: 查看在 [!DNL Target] 推荐信息源处理服务器中使用的 IP 地址的列表，以帮助您将防火墙配置为允许来自 Adobe 服务器的 IP 地址。
title: Recommendations 信息源处理服务器使用什么 IP 地址？
feature: 推荐
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%

---

# ![PREMIUM](/help/assets/premium.png)“推荐”信息源处理服务器使用的 IP 地址

[!DNL Adobe Target] [!DNL Recommendations]信息源处理服务器中使用的 IP 地址列表，以帮助您将防火墙配置为允许来自 Adobe 服务器的 IP 地址。

[!DNL Target] [!UICONTROL 推荐]活动在访问客户的 FTP 服务器时使用以下 AWS 主机：

| 位置 | 主机 |
| --- | --- |
| 俄勒冈 | `44.241.237.28` |
| 俄勒冈 | `44.232.167.82` |
| 俄勒冈 | `52.41.252.205` |

[!DNL Target] [!UICONTROL 推荐] API 也使用同样的 AWS 主机。

>[!NOTE]
>
>这些 IP 地址的上次更新时间为 2021 年 3 月 16 日。之前，访问 FTP 服务器的服务器处于 192.243.242.0/24 IP 地址 CIDR 区块中。托管推荐 API 的的服务器处于 192.243.224.0/20 IP 地址 CIDR 区块中。
