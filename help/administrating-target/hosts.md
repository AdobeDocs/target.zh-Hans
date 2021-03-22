---
keywords: 主机；主机；主机组；疑难解答；最佳实践；ubox；重定向；重定向；白名单；允许列表；黑名单；阻止列表
description: 了解如何在Adobe Target中组织网站和预制环境，以便轻松管理和分离报告。
title: 什么是主持人以及如何使用他们？
feature: 管理和配置
role: 管理员
translation-type: tm+mt
source-git-commit: 86102ed5b49d102660ed38fe0a71612cefcd2caf
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 22%

---


# 主机

在[!DNL Adobe Target]中组织您的站点和预制作环境，以便轻松管理和分离报告。

主机管理的主要目标是确保网站上不会意外出现任何不活跃的内容。主机管理还允许您按[环境](/help/administrating-target/environments.md)分隔报告数据。

主机是从中发出[!DNL Target]请求的任何域。 在网站上，它通常是发出[!DNL Target]请求的URL的`location.hostname`属性。

默认情况下，[!DNL Target]不限制可发出[!DNL Target]请求并接收[!DNL Target]响应的主机。 新主机发出请求时，它们会自动工作。 此过程还允许在您不知道或无法预料的不同域上进行测试。 如果要覆盖此默认行为，可设置允许列表或阻止列表以限制哪些主机与[!DNL Target]一起使用。

要管理主机，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 主机]**。

![](assets/hosts_list.png)

## 正在识别主机{#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要识别主机并将其添加到[!UICONTROL Hosts]列表，必须满足以下条件：

* 主机上必须至少存在一个[!DNL Target]请求
* 主机上的某个页面必须具有以下项：

   * 准确的at.js参考
   * [!DNL Target]请求或自动生成的全局[!DNL Target]请求

* 必须在浏览器中查看具有[!DNL Target]请求的页面

查看页面后，主机将列在[!UICONTROL  Hosts]列表中，以便您在环境中管理它，并预览和启动活动和测试。

>[!NOTE]
>
>其中包含所有个人开发服务器。

将某个主机添加到“[!UICONTROL 主机]”列表后，请确保该主机已被识别。

1. 单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 主机]**。
1. 如果您的主机不在列表中，请刷新浏览器。

   默认情况下，新识别的主机将放置在[!UICONTROL Production]环境中。 [!UICONTROL 生产]环境是最安全的环境，因为它不允许从这些主机查看非活动活动。

1. （视情况而定）单击&#x200B;**[!UICONTROL 移动]**&#x200B;图标（![移动图标](/help/administrating-target/assets/icon-move.png)），将主机移入[!UICONTROL 开发]、[!UICONTROL 暂存]或其他环境。

>[!NOTE]
>
>无法删除[!UICONTROL Production]环境，即使您重命名它也是如此。 假定此环境是您提供最终活动活动和测试的位置。 该环境默认不允许查看不活跃的营销活动。

## 排序或搜索主机列表{#section_068B23C9D8224EB78BC3B7C8580251B0}

要对[!UICONTROL Hosts]列表进行排序，请单击任意列标题([!UICONTROL Name]、[!UICONTROL 环境]或[!UICONTROL Last Requested])以按升序或降序对列表排序。

要搜索[!UICONTROL Hosts]列表，请在[!UICONTROL 搜索Hosts]框中键入搜索词。

## 创允许列表建，指定有权向目标发送目标请求的主机。{#allowlist}

您可以创建一允许列表个，它指定有权向[!DNL Target]发送[!DNL Target]请求的主机（域）。 所有生成请求的其他主机都会收到注释的授权错误响应。 默认情况下，任何包含[!DNL Target]请求的主机都会在[!UICONTROL 生产]环境中注册到[!DNL Target]，并有权访问所有活动和已批准的活动。 如果不需要此方法，您可以改允许列表用此记录有资格发出[!DNL Target]请求并接收[!DNL Target]内容的特定主机。 所有主机继续显示在[!UICONTROL  Hosts]列表中，而且仍可以使用环境对这些主机进行分组，并为每个主机分配不同的级别，例如主机是否可以看到活动和/或非活动活动。

要创建允许列表:

1. 在[!UICONTROL  Hosts]列表中，单击&#x200B;**[!UICONTROL Authorize Hosts]**。
1. 启用&#x200B;**[!UICONTROL 为内容投放]**&#x200B;切换启用授权主机。
1. 根据需要，在&#x200B;**[!UICONTROL “主机包含]**”框中添加所需的主机。

   可列出多个主机，每个主机单独占一行。

1. 根据需要，在&#x200B;**[!UICONTROL 主机不包含]**&#x200B;框中添加所需的主机。

   可列出多个主机，每个主机单独占一行。

1. 单击&#x200B;**[!UICONTROL 保存]**。

如果对未授权的主机发出[!DNL Target]请求，则调用将以`/* no display - unauthorized mbox host */`作出响应。

>[!IMPORTANT]
>
>**安全最佳实践**:如果您使用的ubox功 [!DNL Target]能，此允许列表还控制重定向器导航到的域 [](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 的列表。确保在将ubox用作实施的一部分时添加要重定向到的任何域。 如果允许列表未指定此，[!DNL Adobe]将无法验证重定向URL并防止潜在的恶意重定向。
>
>该允许列表优先于环境。 使用功能之前清除所允许列表有主机，然后只有允许的主允许列表机才会显示在主机列表中。 然后，您可以将主机移到所需的环境中。

有时，您的环境中会显示来自其他网站的域。如果域调用at.js，则列表中将显示域。 例如，如果某人将您的一个网页复制到其服务器，那么该域便会显示在您的环境中。您也可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域名。

如果 `mboxHost` 在 API 调用中进行传递，则会为传入的环境记录转化。如果未传递环境，则调用中的主机默认为[!UICONTROL Production]。

您还可以创建一阻止列表个，通过在[!UICONTROL 主机不包含]框中添加所需主机，指定无法向[!DNL Target]发送[!DNL Target]请求的主机（域）。

>[!NOTE]
>
>[!UICONTROL 授权主机]列表同时用于[!DNL Target]主机和默认重定向主机。 添加所有已批准使用[!DNL Adobe Target] JavaScript SDK(at.js)*AND*&#x200B;的现有域，所有域均用于ubox默认重定向URL。 将来向添加任允许列表何新的类似域。

## 删除主机{#section_F56355BA4BC54B078A1A8179BC954632}

如果您不再需要某个主机，您可以删除该主机。

1. 在[!UICONTROL  Hosts]列表中，单击&#x200B;**[!UICONTROL 删除]**&#x200B;图标。
1. 单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

>[!NOTE]
>
>如果有人浏览到主机上包含[!DNL Target]请求的页面，则会再次列出主机。

## 主机故障诊断 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主机方面的问题，请尝试使用以下故障诊断提示解决问题：

**主持人不显示在您帐户的列表中。**

* 在浏览器中刷新“[!UICONTROL 主机]”页面。
* 确认[!DNL Target]请求正确，包括at.js引用。
* 尝试浏览到主机上的[!DNL Target]请求之一。 在浏览器中可能未呈现主机上的[!DNL Target]请求。

**“[!UICONTROL 主机]”列表中出现随机或未知的域。**

如果从域向[!DNL Target]发出请求，则此列表中将显示域。 您常常可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域。如果列出的域不是您的团队所使用的域，则可以单击“[!UICONTROL 删除]”将其移除。

**我的 [!DNL Target] 请求返回/*没有显示 — 未授权的mbox主机*/。**

如果对未授权的主机发出[!DNL Target]请求，则该请求将以/* no display - unauthorized mbox host */作出响应。
