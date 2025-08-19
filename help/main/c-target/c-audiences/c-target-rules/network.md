---
keywords: 定位;网络;定位网络;ISP;域名;连接速度;定位 ISP;定位域名;定位连接速度
description: 了解如何在 [!DNL Adobe Target] 中基于网络详细信息创建受众。
title: 我可以根据网络选项定位访客吗？
feature: Audiences
exl-id: 0a479d6d-ca17-43b8-9a42-8e68f31d4d54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 68%

---

# 网络

您可以在[!DNL Adobe Target]中基于网络详细信息（如ISP、域名和连接速度）创建受众。

1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 命名受众并添加可选描述。
1. 将&#x200B;**[!UICONTROL Network]**&#x200B;拖放到受众生成器窗格中。
1. 单击&#x200B;**[!UICONTROL Select]**，然后选择以下选项之一：

   * **ISP：** ISP 是指向订户提供 Internet 接入服务的组织，订户需按月或按年向该组织缴纳相应费用。很多 ISP 还提供其他服务项目，例如 Web 托管或电子邮件服务。“ISP”字段中填写的内容可以是一个商业 ISP（例如 Comcast 或 TimeWarner），也可以是其他实体（例如企业或教育机构）。

     下面列举了美国常用的一些 ISP：

     | 常用名 | ISP 名称 | 域名 | 示例 IP 地址 |
     |---|---|---|---|
     | Cablevision | Cablevision Systems Corp. | &#42;.optonline.net | 68.196.130.239 |
     | CenturyLink | Qwest Communications Company, LLC | &#42;.centurylink.net | 64.40.65.0 |
     | Charter Communications | Charter Communications | &#42;.charter.com | 71.85.225.124 |
     | Comcast | Comcast Cable Communications, Inc. | &#42;.comcast.net | 76.27.24.28 |
     | Cox | Cox Communications Inc. | &#42;cox.net | 68.224.174.22 |
     | Speakeasy | MegaPath Corporation | &#42;.speakeasy.net | 66.93.240.0 |
     | Time Warner | Time Warner Cable Internet LLC | &#42;.res.rr.com | 72.229.28.185 |
     | Verizon FiOS | MCI Communications Services, Inc. d/b/a Verizon Business | &#42;.fios.verizon.net | 173.68.112.34 |
     | Vivint | Smartrove Inc. | &#42;.vivintwireless.net | 170.72.26.105 |
     | AT&amp;T Wireless | AT | &#42;.mycingular.net |  |
     | Sprint mobile | Sprint Personal Communications Systems | IP 地址 |  |
     | T-Mobile | T-Mobile USA, Inc. | IP 地址 | 208.54.86.0 |
     | Verizon Wireless | Cellco Parternship DBA Verizon Wireless | &#42;.myvzw.com | 70.195.74.199 |

     >[!NOTE]
     >
     >基于 ISP 进行定位时，请使用 ISP 名称，而不要使用通用名。此外，还请确保您构建的规则不区分大小写，或者始终使用小写格式。

     您可以对 ISP 和域名值进行测试。[https://www.whoismyisp.org](https://www.whoismyisp.org)是用于定位的有用资源。 您可以使用上表中给出的示例 IP 地址，也可以输入您自己的 IP 地址。然后，使用 `mboxOverride.browserIp= URL` 参数来模拟该 IP 地址。

   * **域名：**&#x200B;此名称是访客IP地址的域名。 此名称不是您在[!DNL Target]中使用的网站的域名。 此域名与访客的 IP 地址有关，有时也称为主机名。它与ISP名称类似。 有时，主机名会引用公司在变更其 ISP 名称之前使用的旧名称，而不引用域名。
   * **连接速度：**&#x200B;此速度是访客连接到Internet的速度。 选项包括：宽带、有线、拨号、移动、oc3、oc12、卫星、t1、t2、无线和 xdsl。

     此字段基于连接类型，而并非实际速度本身。[!DNL Target] 无法确定各种连接方式的精确连接速度。如果没有迹象显示使用了其他连接类型，则会使用宽带连接类型，因此无法选择特定的类型。

1. （可选）为受众设置其他规则。
1. 单击 **[!UICONTROL Done]**。

下图显示了一个受众，它定位的是使用AT&amp;T且连接速度为[!UICONTROL Mobile]的访客。

![锁定网络](assets/target_network.png)

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
