---
keywords: 主机；主机；主机组；故障排除；最佳实践；ubox；重定向；重定向；白名单；；黑名单；允许列表 阻止列表
description: 了解如何在Adobe Target中组织网站和预生产环境，以便轻松管理和分隔报表。
title: 什么是主机以及如何使用它们？
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 22%

---

# 主机

组织您的站点和预生产环境，以便在中轻松管理和分隔报告 [!DNL Adobe Target].

主机管理的主要目标是确保网站上不会意外出现任何不活跃的内容。主机管理还允许您按以下方式分隔报表数据 [环境](/help/main/administrating-target/environments.md).

主机是从中进行 [!DNL Target] 已发出请求。 在网站上，它通常是 `location.hostname` 用于创建 [!DNL Target] 请求。

默认情况下， [!DNL Target] 不限制可以生成的主机 [!DNL Target] 请求和接收 [!DNL Target] 响应。 当新主机发出请求时，它们会自动工作。 此流程还支持对您不知道或无法预测的不同域进行测试。 如果要覆盖此默认行为，可以设置或允许列表阻止列表以限制使用哪些主机 [!DNL Target].

要管理主机，请单击 **[!UICONTROL 管理]** > **[!UICONTROL 主机]**.

![hosts_list图像](assets/hosts_list.png)

## 识别主机 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

识别主机并将其添加到 [!UICONTROL 主机] 列表，必须满足以下条件：

* 至少一个 [!DNL Target] 请求必须存在于主机上
* 主机上的某个页面必须具有以下项：

   * 精确的at.js引用
   * A [!DNL Target] 请求或自动生成的全局 [!DNL Target] 请求

* 具有的页面 [!DNL Target] 必须在浏览器中查看请求

查看页面后，该主机将列在 [!UICONTROL 主机] 列表，允许您在环境中管理它，并预览和启动活动和测试。

>[!NOTE]
>
>其中包含所有个人开发服务器。

将某个主机添加到“[!UICONTROL 主机]”列表后，请确保该主机已被识别。

1. 单击 **[!UICONTROL 管理]** > **[!UICONTROL 主机]**.
1. 如果您的主机不在列表中，请刷新浏览器。

   默认情况下，新识别的主机将放在 [!UICONTROL 生产] 环境。 此 [!UICONTROL 生产] 环境是最安全的环境，因为它不允许从这些主机查看非活动的活动。

1. （视情况而定）单击 **[!UICONTROL 移动]** 图标( ![移动图标](/help/main/administrating-target/assets/icon-move.png) )，以将主机移入 [!UICONTROL 开发]， [!UICONTROL 暂存]或其他环境。

>[!NOTE]
>
>此 [!UICONTROL 生产] 无法删除环境，即使对其重命名也是如此。 我们假定您在此环境中提供最终的活动和测试。 该环境默认不允许查看不活跃的营销活动。

## 对主机列表进行排序或搜索 {#section_068B23C9D8224EB78BC3B7C8580251B0}

要对 [!UICONTROL 主机] 列表中，单击任意列标题([!UICONTROL 名称]， [!UICONTROL 环境]，或 [!UICONTROL 上次请求时间])，以对列表进行升序或降序排序。

要搜索 [!UICONTROL 主机] 列表中，键入搜索词 [!UICONTROL 搜索主机] 盒子。

## 创建指定有权发送的主机的允许列表 [!DNL Target] 请求 [!DNL Target]. {#allowlist}

您可以创建一个指定有权发送的主机（域）的允许列表 [!DNL Target] 请求 [!DNL Target]. 所有其他生成请求的主机都会收到一个注释掉的授权错误响应。 默认情况下，任何包含 [!DNL Target] 请求注册位置 [!DNL Target] 在 [!UICONTROL 生产] 环境，并可访问所有活跃和已批准的活动。 允许列表如果不希望采用这种方法，您可以改用来记录有资格制作的特定主机 [!DNL Target] 请求和接收 [!DNL Target] 内容。 所有主机继续显示在 [!UICONTROL 主机] 列表和环境中，仍可以使用对这些主机进行分组，并为每个主机分配不同的级别，例如主机是否可以看到活动和/或非活动的活动。

要创建允许列表，请执行以下操作：

1. 从 [!UICONTROL 主机] 列表，单击 **[!UICONTROL 授权主机]**.
1. 启用 **[!UICONTROL 为内容交付启用授权的主机]** 切换。
1. 将所需主机添加到 **[!UICONTROL 主机包含]** 框（如果需要）。

   可列出多个主机，每个主机单独占一行。

1. 将所需主机添加到 **[!UICONTROL 主机不包含]** 框（如果需要）。

   可列出多个主机，每个主机单独占一行。

1. 单击&#x200B;**[!UICONTROL 保存]**。

如果 [!DNL Target] 在未经授权的主机上进行请求，调用将做出响应 `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**安全最佳实践**：如果您使用的ubox功能 [!DNL Target]，此允许列表还控制 [重定向器](https://developer.adobe.com/target/implement/email/working-with-redirectors/){target=_blank} 可以导航。 确保在实施中使用ubox时添加要重定向到的任何域。 如果将允许列表保留为未指定， [!DNL Adobe] 无法验证重定向URL并防止潜在的恶意重定向。
>
>允许列表优先于环境。 允许列表 允许列表在使用功能之前，请清除所有主机，然后只有由允许的主机才会显示在主机列表中。 然后，您可以将主机移到所需的环境中。

有时，您的环境中会显示来自其他网站的域。如果域调用at.js，则该域会显示在列表中。 例如，如果某人将您的一个网页复制到其服务器，那么该域便会显示在您的环境中。您也可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域名。

如果 `mboxHost` 在 API 调用中进行传递，则会为传入的环境记录转化。如果未传递任何环境，则调用中的主机默认为 [!UICONTROL 生产].

阻止列表您还可以创建一个指定无法发送的主机（域）的 [!DNL Target] 请求 [!DNL Target] 通过将所需的主机添加到 [!UICONTROL 主机不包含] 盒子。

>[!NOTE]
>
>此 [!UICONTROL 授权的主机] 列表用于两者 [!DNL Target] 主机和默认重定向主机。 添加已批准使用的所有现有域 [!DNL Adobe Target] JavaScript SDK (at.js) *和* ubox中使用的所有域默认重定向URL。 将来，向允许列表中添加任何新的相似域。

## 删除主机 {#section_F56355BA4BC54B078A1A8179BC954632}

如果您不再需要某个主机，您可以删除该主机。

1. 从 [!UICONTROL 主机] 列表中，单击 **[!UICONTROL 删除]** 图标。
1. 单击&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

>[!NOTE]
>
>如果有人浏览的页面包含 [!DNL Target] 请求。

## 主机故障诊断 {#concept_B3D7583FA4BB480382CC7453529FE1B7}

如果遇到主机方面的问题，请尝试使用以下故障诊断提示解决问题：

**主机未出现在您帐户的列表中。**

* 在浏览器中刷新“[!UICONTROL 主机]”页面。
* 确认 [!DNL Target] 请求正确，包括at.js引用。
* 尝试浏览到其中一个 [!DNL Target] 请求数。 有可能，不 [!DNL Target] 主机上的请求从未在浏览器中呈现。

**“[!UICONTROL 主机]”列表中出现随机或未知的域。**

如果向以下用户发出请求，则此列表中会显示一个域： [!DNL Target] 是从域中创建的。 您常常可以看到来自蜘蛛引擎、语言翻译网站或者本地磁盘驱动器的域。如果列出的域不是您的团队所使用的域，则可以单击“[!UICONTROL 删除]”将其移除。

**我的 [!DNL Target] 请求返回/&#42; 无显示 — 未授权的mbox主机 &#42;/.**

如果 [!DNL Target] 在未经授权的主机上进行请求，该请求将以/进行响应&#42; 无显示 — 未授权的mbox主机 &#42;/.
