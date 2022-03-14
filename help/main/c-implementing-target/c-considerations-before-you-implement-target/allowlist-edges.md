---
keywords: 实施；白名单；;允许列表允许列表；边缘；边缘
description: 查看主机列表以帮助您允许列表Adobe [!DNL Target] 边（地理上分布的服务节点，可确保最佳响应时间的最终用户）。
title: 如何允许列表 [!DNL Target] 边缘节点？
feature: Privacy & Security
role: Developer
exl-id: 2d8399b9-eec8-40b0-8b35-2812f83ff4dc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# 允许列表 [!DNL Target] 边缘节点

可帮助您进行的信息和最新主机列允许列表表 [!DNL Adobe Target] 边缘。

边缘是分布在不同地理位置的服务架构，不论请求内容的最终用户位于何处，均可确保为他们提供最佳响应时间。 每个边缘节点都具有响应用户的内容请求和跟踪该请求中的分析数据所需的所有信息。 用户请求将路由到最近的边缘节点。 有关更多信息，请参阅 [边缘网络](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) in *如何Adobe [!DNL Target] 作品*.

您可以允许列表 [!DNL Target] 边缘节点（如果需要）。

## 网络地址转换(NAT)的IP地址 [!DNL Target] 边缘

出口IP地址列表 [!DNL Target] 边缘。 如允许列表果您计划让Target联系您的服务，请这些IP。

| 边缘位置 | 出口IP地址 |
| --- | --- |
| Edge31（孟买） | 13.126.131.246<br>13.234.229.8 |
| Edge32（东京） | 3.115.154.28<br>3.115.227.146 |
| Edge34（美国东海岸） | 34.232.149.249<br>52.21.139.93 |
| Edge35（美国西海岸） | 52.10.11.139<br>44.231.171.161 |
| Edge36（悉尼） | 13.237.227.20<br>13.210.93.142 |
| Edge37（爱尔兰） | 54.72.21.68<br>52.208.139.19 |
| Edge38（新加坡） | 18.141.132.96<br>54.179.187.167 |

## 目标边缘IP地址

的IP地址列表 [!DNL Target] 边缘。 如果允许列表要对Target边缘进行API调用，请这些IP。

| 边缘位置 | 域 | IP 地址 |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(其中CLIENTCODE是您的 [!DNL Target] 客户端ID) |  |
| Edge31（孟买） | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.201 |
| Edge32（东京） | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34（美国东海岸） | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.93<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35（美国西海岸） | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162.74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36（悉尼） | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37（爱尔兰） | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>52.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38（新加坡） | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |
