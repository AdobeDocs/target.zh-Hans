---
keywords: 主机；主机；主机组；故障排除；最佳实践；ubox；重定向；重定向；白名单；允许列表；黑名单；阻止列表
description: 了解如何在Adobe Target中组织网站和预生产环境，以便轻松管理和分隔报表。
title: 什么是主机以及如何使用它们？
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 17%

---

# 主机

在[!DNL Adobe Target]中组织您的站点和生产前环境，以便轻松管理和分隔报表。

主机管理的主要目标是确保网站上不会意外出现任何不活跃的内容。主机管理还允许您按[环境](/help/main/administrating-target/environments.md)来分隔报表数据。

主机是从中发出[!DNL Target]请求的任何域。 在网站上，它通常是发出[!DNL Target]请求的URL的`location.hostname`属性。

默认情况下，[!DNL Target]不限制可以发出[!DNL Target]请求并接收[!DNL Target]响应的主机。 当新主机发出请求时，它们会自动工作。 此流程还支持对您不知道或无法预料到的不同域进行测试。 如果要覆盖此默认行为，可以设置允许列表或阻止列表以限制哪些主机可以使用[!DNL Target]。

{{permissions-update}}

要管理主机，请单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Hosts]**。

## 识别主机 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要识别主机并将其添加到[!UICONTROL Hosts]列表，必须满足以下条件：

* 主机上必须至少存在一个[!DNL Target]请求
* 主机上的页面必须包含以下内容：

   * 准确的at.js参考
   * [!DNL Target]请求或自动生成的全局[!DNL Target]请求

* 必须在浏览器中查看具有[!DNL Target]请求的页面

查看页面后，该主机列在[!UICONTROL Hosts]列表中，允许您在环境中管理该主机，并预览和启动活动和测试。

>[!NOTE]
>
>其中包含所有个人开发服务器。

将主机添加到[!UICONTROL Host]列表后，请确保该主机已被识别。

1. 单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Hosts]**。
1. 如果您的主机不在列表中，请刷新浏览器。

   默认情况下，将新识别的主机放在[!UICONTROL Production]环境中。 [!UICONTROL Production]环境是最安全的环境，因为它不允许从这些主机查看非活动环境。

1. （有条件）单击&#x200B;**[!UICONTROL Move]**&#x200B;图标（ ![移动图标](/help/main/administrating-target/assets/icon-move.png) ）将主机移动到[!UICONTROL Development]、[!UICONTROL Staging]或其他环境中。

>[!NOTE]
>
>无法删除[!UICONTROL Production]环境，即使对其重命名也是如此。 我们假定在此环境中可以提供最终的活动和测试。 该环境默认不允许查看不活跃的营销活动。

## 对主机列表进行排序或搜索 {#section_068B23C9D8224EB78BC3B7C8580251B0}

要对[!UICONTROL Hosts]列表进行排序，请单击任意列标题（[!UICONTROL Name]、[!UICONTROL Environment]或[!UICONTROL Last Requested]）以对列表进行升序或降序排序。

要搜索[!UICONTROL Hosts]列表，请在[!UICONTROL Search Hosts]框中键入搜索词。

## 创建允许列表以指定有权将[!DNL Target]请求发送到[!DNL Target]的主机。{#allowlist}

您可以创建一个允许列表，指定有权向[!DNL Target]发送[!DNL Target]请求的主机（域）。 所有其他生成请求的主机都会收到一个注释掉的授权错误响应。 默认情况下，任何包含[!DNL Target]请求的主机都会在[!UICONTROL Production]环境中向[!DNL Target]进行注册，它们有权访问所有活跃的已批准活动。 列入允许列表如果不希望使用此方法，您可以改为使用来记录有权发出[!DNL Target]请求并接收[!DNL Target]内容的特定主机。 所有主机继续显示在[!UICONTROL Hosts]列表中，并且环境仍可用于对这些主机进行分组，并为每个主机分配不同的级别，例如该主机是否可以看到活动和/或非活动的活动。

要创建允许列表，请执行以下操作：

1. 从[!UICONTROL Hosts]列表中，单击&#x200B;**[!UICONTROL Authorize Hosts]**。
1. 启用&#x200B;**[!UICONTROL Enable Authorized Hosts for content delivery]**&#x200B;切换。
1. 根据需要在&#x200B;**[!UICONTROL Host contains]**&#x200B;框中添加所需主机。

   可列出多个主机，每个主机单独占一行。

1. 根据需要在&#x200B;**[!UICONTROL Host does not contains]**&#x200B;框中添加所需主机。

   可列出多个主机，每个主机单独占一行。

1. 单击 **[!UICONTROL Save]**。

如果对未授权的主机发出[!DNL Target]请求，则该调用将做出响应： `/* no display - unauthorized mbox host */`。

>[!IMPORTANT]
>
>**安全最佳实践**：如果您使用[!DNL Target]的ubox功能，此允许列表还将控制[重定向器](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=zh-Hans){target=_blank}可以导航到的域的列表。 确保在将ubox用作实现的一部分时添加要重定向的任何域。 如果未指定允许列表，[!DNL Adobe]将无法验证重定向URL并防止潜在的恶意重定向。
>
>允许列表优先于环境。 在使用allowlist功能之前，请清除所有主机，只有允许列表允许的主机才会显示在主机列表中。 然后，您可以将主机移到所需的环境中。

有时，您的环境中会显示来自其他网站的域。如果某个域调用at.js，则该域会显示在列表中。 例如，如果某人将您的一个网页复制到其服务器，那么该域便会显示在您的环境中。您也可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域名。

如果 `mboxHost` 在 API 调用中进行传递，则会为传入的环境记录转化。如果未传递任何环境，则调用中的主机默认为[!UICONTROL Production]。

您还可以通过在[!UICONTROL Host Does Not Contain]框中添加所需的主机来创建一个阻止列表，以指定不能向[!DNL Target]发送[!DNL Target]请求的主机（域）。

>[!NOTE]
>
>[!UICONTROL Authorized Hosts]列表同时用于[!DNL Target]主机和默认重定向主机。 添加已批准使用[!DNL Adobe Target] JavaScript SDK (at.js) *和*&#x200B;所有在ubox默认重定向URL中使用的现有域。 将来，将任何新的类似域添加到允许列表中。

## 删除主机 {#section_F56355BA4BC54B078A1A8179BC954632}

如果您不再需要某个主机，您可以删除该主机。

1. 从[!UICONTROL Hosts]列表中，单击&#x200B;**[!UICONTROL Delete]**&#x200B;图标。
1. 单击“**[!UICONTROL Delete]**”以确认删除。

>[!NOTE]
>
>如果有人浏览到主机上包含[!DNL Target]请求的页面，则该主机将再次列出。

## 主机故障诊断 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主机方面的问题，请尝试使用以下故障诊断提示解决问题：

**主机未出现在您帐户的列表中。**

* 刷新浏览器中的[!UICONTROL Hosts]页面。
* 确认[!DNL Target]请求正确，包括at.js引用。
* 尝试浏览到主机上的[!DNL Target]请求之一。 主机上可能从未在浏览器中呈现任何[!DNL Target]请求。

**随机域或未知域出现在[!UICONTROL Host]列表中。**

如果从某个域向[!DNL Target]发出请求，则该域会显示在此列表中。 您常常可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域。如果列出的域不是您的团队使用的域，您可以单击[!UICONTROL Delete]将其删除。

**我的[!DNL Target]请求返回/&#42;无显示 — 未授权的mbox主机&#42;/.**

如果对未授权的主机发出[!DNL Target]请求，则该请求将以/&#42; no display - unauthorized mbox host &#42;/进行响应。
