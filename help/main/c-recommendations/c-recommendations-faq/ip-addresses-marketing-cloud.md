---
keywords: IP 地址;IP 地址;列入允许列表;允许列表;防火墙;推荐;信息源;服务器;adobe marketing cloud;推荐
description: 查看在 [!DNL Target] 推荐信息源处理服务器中使用的 IP 地址的列表，以帮助您将防火墙配置为允许来自 Adobe 服务器的 IP 地址。
title: 推荐信息源处理服务器使用什么 IP 地址？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: be5b3158c758fa08802c1dc0541c9e989a2c7740
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 35%

---

# [!DNL Recommendations]信息源处理服务器使用的IP地址

[!DNL Adobe Target] [!DNL Recommendations]信息源处理服务器中使用的IP地址列表，可帮助您将防火墙配置为允许源自[!DNL Adobe]服务器的IP地址。

>[!IMPORTANT]
>
>[!DNL Target]团队当前正在更新用于下载[!DNL Recommendations]源的NAT网关地址。 如果实施IP列入允许列表，请确保您允许列表以下新的AWS主机。 现有主机将于2024年6月30日停用。 为确保平稳过渡，请允许列表所有九个地址。 无需急迫删除现有地址。

[!DNL Target] [!UICONTROL Recommendations]活动在访问客户的FTP服务器时使用以下AWS主机：

**新主机**：

| 位置 | 主机 |
| --- | --- |
| 俄勒冈 | `52.40.124.129` |
| 俄勒冈 | `54.148.219.69` |
| 俄勒冈 | `54.189.208.212` |
| 俄勒冈 | `44.230.236.35` |
| 俄勒冈 | `54.190.78.243` |
| 俄勒冈 | `52.41.73.133` |

**现有主机**：

| 位置 | 主机 |
| --- | --- |
| 俄勒冈 | `44.241.237.28` |
| 俄勒冈 | `44.232.167.82` |
| 俄勒冈 | `52.41.252.205` |

[!DNL Target] [!UICONTROL Recommendations] API也使用相同的AWS主机。
