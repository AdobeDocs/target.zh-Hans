---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content
description: 可使用远程选件在 Target 以外托管内容，Target 会引用这些内容并将其交付到用户网站。出于方便使用或安全原因，这些内容可能位于内容管理或其他系统中。
title: 创建远程选件
feature: offers
topic: Standard
uuid: 5aaff281-e96c-41a6-849e-2c3b0e35f161
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 92%

---


# 创建远程选件{#create-remote-offers}

可使用远程选件在 Target 以外托管内容，Target 会引用这些内容并将其交付到用户网站。出于方便使用或安全原因，这些内容可能位于内容管理或其他系统中。

>[!NOTE]
>
>远程选件只能在基于表单的编辑器中创建。Content will be injected in the [!DNL Target] request locations, so these are most likely not appropriate for a global [!DNL Target] request.
>
>[!DNL Target Classic] 中提供了类似功能：[!UICONTROL 站内选件]和 [!UICONTROL Test&amp;Target 外部选件]。

下面是远程选件的一些示例：

* 不同版本的交叉销售
* 动态购物车消息
* 表单
* 计算器
* 利率更新

**创建远程选件：**

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 远程选件]**。

   ![](assets/remote_offer_ui.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. 为远程选件指定远程 URL：

   | 选项 | 描述 |
   |--- |--- |
   | 已缓存 | 已缓存的远程选件的内容是从 Target 中提供的。<br>[!DNL Target] 每两小时从远程 URL 中提取一次内容，然后将该内容存储到 Target 中。如果访客加载的网站中具有包含远程选件的体验，则该选件会由 Target 交付。<br>已缓存的远程选件可提供增强的安全性，因为用户在登录到 Target 后便无法更改内容。要更改内容，用户需登录到内容管理系统或其他系统并在其中更改内容。<br>您能够为已缓存的远程选件指定绝对 URL 或相对 URL。 |
   | 动态 | 动态远程选件的内容是从内容管理系统或其他系统中提供的，而不是从 Target 中提供。<br>当访客加载的网站具有包含远程选件的体验时，您可能不希望由 Target 定期缓存并交付内容。您而是可能希望调用托管内容的系统，然后传入特定信息，以便能够为每位用户返回动态或不同的选件。<br>例如，如果某位用户登录到一个信用卡网站，且该网站中具有包含动态远程选件的体验，则您能够将相应参数传递到 URL 中，以获取该用户的帐户信息。随后，网站便会提供特定于该用户的信息，例如账户余额。<br>单击 [!UICONTROL 添加参数] ，以添加一个或多个 [!DNL Target] 请求或请求参数。 |

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 使用远程选件的最佳实践 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活动中使用远程选件时需遵循以下最佳实践：

* If your offer resides in the same domain as the [!DNL Target] requests, using the [!UICONTROL Cached] option lets you use relative URLs in describing your offer location.

   这意味着您将活动从测试服务器移到生产服务器后，无需手动更改 URL 即可自动访问内容。

* 如果您的测试中包含由服务器动态生成的数据，则选择“[!UICONTROL 动态]”选项可能是正确的做法。
* 如果您打算只测试现有远程选件内容的外观，请使用[!UICONTROL 可视化体验编辑器]来更改从内容管理系统返回的内容的外观。
* 使用远程选件选择表可帮助您选出最适合您的特定用例的选件。如果您有任何问题，请咨询客服专员。

## 动态远程选件的工作原理 {#concept_CC2A969420B34364A9FA78C1CE251818}

动态远程选件使用动态页面技术来向选件传递值。

选件会在您提交页面后执行。一个看不见的 iframe 内置框架能够收集数据、将数据复制到框架外及插入到页面中，并加载传递的值。

![](assets/remote_offer_howitworks_2.jpeg)

## 远程选件选择表 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

远程选件选择表可帮助您确定选择哪种类型的远程选件：“[!UICONTROL 已缓存]”或“[!UICONTROL 动态]”。

| 功能 | 已缓存 | 动态 |
|--- |--- |--- |
| 每次访客发出请求时更新 | 否 | 是 |
| 内容更新 | 每两小时缓存一次 | 每次请求时立即更新 |
| 加载时间 | 更快 | 由于请求处理原因加载时间较慢 |
| 可以查看页面上的 JavaScript | 是 | 否，但可以通过 URL 传递 |
| 选件可以包含 JavaScript | 是 | 是 |
| 选件 URL | 绝对或相对 | 相对 |
| 请求计算机 | Adobe 服务器 | 带有访客 Cookie 的访客计算机 |