---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: 可组织您的网站和预生产环境，以便轻松管理和分隔报表。
title: 主机
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 1dc6fc4a9ad582cb4ace5394c5b9834aa8cd3f58
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 57%

---


# 主机{#hosts}

可组织您的网站和预生产环境，以便轻松管理和分隔报表。

主机管理的主要目标是确保网站上不会意外出现任何不活跃的内容。Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

主机是指在项目的任何阶段都可以提供内容服务的任意 Web 服务器（或 Web 域）。提供 mbox 的任何主机都可被识别。

为方便管理，可将多个主机捆绑在一起并将其放置到环境中。例如，您可以将数十个主机分组到两个或三个环境中。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 您可以根据需要添加新环境，以及对环境进行重命名。

One environment, the default environment, is pre-named [!UICONTROL Production]. 此默认环境无法删除，即使您将其重命名也是如此。[!DNL Target] 将此环境视为您将在其中提供批准的最终活动和测试的位置。

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. 通过主机管理，您在激活测试和开发环境中的新活动和内容之前，还可以轻松地确保这些活动和内容的质量。

[!DNL Target] 不限制可以发送和接收mbox的主机，因此当出现新的服务器或域时，它们会自动工作（除非您设置了allowlist或blocklist）。 这也让您能够在不了解或不可预测的各种域中进行广告测试。

要管理主机，请单击“管 **[!UICONTROL 理]** ”> **[!UICONTROL “主机]**”。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

要识别主机并将其添加到主 [!UICONTROL 机列表] ，必须满足以下条件：

* 主机中至少存在一个 mbox
* 主机上的某个页面必须具有以下项：

   * 准确的at.js或mbox.js引用
   * mbox 或自动生成的全局 mbox 调用

* 在浏览器中可以查看带有 mbox 的页面

查看该页面后，即会在“[!UICONTROL 主机]”列表中列出相应的主机，以便您能够在环境中对其进行管理，并预览和启动活动与测试。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>其中包含所有个人开发服务器。

将某个主机添加到“[!UICONTROL 主机]”列表后，请确保该主机已被识别。

1. 单击“ **[!UICONTROL 管理]** ” > **[!UICONTROL “主机]**”。
1. 如果您的主机不在列表中，请刷新浏览器。

   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. 这是最安全的环境，因为该环境不允许从这些主机中查看不活跃的活动。

1. （视情况而定）单击移动图 ![标](/help/administrating-target/assets/icon-move.png) （移动图标），将主机移 [!UICONTROL 入开发]、暂 [!UICONTROL 存]或其他环境。

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. 生产环境被视为您提供最终的活跃活动和测试的环境。该环境默认不允许查看不活跃的营销活动。

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send mbox calls to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send mbox calls to [!DNL Target]. 所有其他生成调用的主机都将收到一个注释掉的授权错误响应。默认情况下，任何包含 mbox 调用的主机都会在生产环境中向 [!DNL Target] 进行注册，它们有权访问所有活跃的已批准活动。If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make mbox calls and receive [!DNL Target] content. 所有主机将继续显示在“[!UICONTROL 主机]”列表中，并且环境仍可用来对这些主机进行分组，以及为每个主机分配不同的级别，例如主机是否可以看到活跃和/或不活跃的营销活动。

要创建允许列表，请执行以下操作：

1. 在“主机 [!UICONTROL ”列表] ，单击“对主 **[!UICONTROL 机授权”]**。
1. 启用“为 **[!UICONTROL 内容投放启用授权主机]** ”切换。
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   可列出多个主机，每个主机单独占一行。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   可列出多个主机，每个主机单独占一行。

1. 单击&#x200B;**[!UICONTROL 保存]**。

如果对未授权的主机进行 mbox 调用，则该调用将做出响应：`/* no display - unauthorized mbox host */`。

>[!IMPORTANT]
>
>**安全最佳实践**: 如果使用的ubox功 [!DNL Target]能，请注意，此allowlist还将控制重定向器可导航 [到的域](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 列表。 确保在将ubox用作实施的一部分时添加要重定向到的任何域。 如果未指定allowlist,Adobe将无法验证重定向URL并防止潜在的恶意重定向。
>
>allowlist优先于环境。 在使用allowlist功能之前，应清除所有主机，然后只有allowlist允许的主机才会显示在主机列表中。 然后，您可以将主机移到所需的环境中。

有时，您的环境中会显示来自其他网站的域。如果域调用您的at.js或mbox.js，则列表中将显示域。 例如，如果某人将您的一个网页复制到其服务器，那么该域便会显示在您的环境中。您也可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域名。

如果 `mboxHost` 在 API 调用中进行传递，则会为传入的环境记录转化。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

您也可以通过在“[!DNL Target]主机不包含[!UICONTROL ”框中添加所需的主机来创建黑名单，以指定不能向 ] 发送 mbox 调用的主机（域）。

>[!NOTE]
>
>由于“授权主机”列表同时用于mbox主机和默认重定向主机，因此您必须添加所有已批准使用Adobe目标Javascript SDK(at.js)的现有域 *，以及* ubox默认重定向URL中使用的所有域。 以后，您还必须向allowlist中添加任何新的类似域。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

如果您不再需要某个主机，您可以删除该主机。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. 单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

>[!NOTE]
>
>如果任何人浏览到该主机上启用了 mbox 的页面，则会再次列出该主机。

## 主机故障诊断 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

在 [!DNL Adobe Target] 中管理主机并对其进行故障诊断的最佳实践。

如果遇到主机方面的问题，请尝试使用以下故障诊断提示解决问题：

**主机未出现在您帐户的 mbox 列表中。**

* 在浏览器中刷新“[!UICONTROL 主机]”页面。
* 确认mbox代码正确，包括at.js或mbox.js引用。
* 尝试浏览主机上的某个 mbox。可能是因为主机上的 mbox 从来没有在浏览器中显示。

**“[!UICONTROL 主机]”列表中出现随机或未知的域。**

如果从某个域中调用了 [!DNL Target]，则该域会显示在此列表中。您常常可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域。如果列出的域不是您的团队所使用的域，则可以单击“[!UICONTROL 删除]”将其移除。

**我的 mbox 调用返回以下内容：/* 无显示 - 未授权的 mbox 主机 */。**

如果对未授权的主机进行 mbox 调用，则该调用将做出响应：/* 无显示 - 未授权的 mbox 主机 */。
