---
keywords: 远程选件；远程选件选择表；缓存的内容；动态内容；URL类型
description: 了解如何在Adobe中使用远程选件 [!DNL Target] 托管外部内容（CMS或其他系统中的内容）。 了解为何要使用远程选件。
title: 如何创建远程选件？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 47%

---

# 创建远程选件

可使用远程选件在 [!DNL Adobe Target] 以外托管内容，[!DNL Target] 会引用这些内容并将其交付到用户网站。出于方便使用或安全原因，此内容可能位于内容管理(CMS)或其他系统中。

>[!NOTE]
>
>远程选件可以在 [!UICONTROL 选件] > [!UICONTROL 代码选件] 页面或 [基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md). 您无法在可视化体验编辑器(VEC)中创建或应用远程选件。 内容将插入 [!DNL Target] 请求位置，因此这些位置很可能不适合全局 [!DNL Target] 请求。
>
>[!DNL Target Classic] 中提供了类似功能：[!UICONTROL 站内选件]和 [!UICONTROL Test&amp;Target 外部选件]。

下面是远程选件的一些示例：

* 不同版本的交叉销售
* 动态购物车消息
* 表单
* 计算器
* 利率更新
* 电子邮件
* 网亭
* 语音助理

## 使用远程选件的最佳实践 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活动中使用远程选件时需遵循以下最佳实践：

* 如果您的选件位于与 [!DNL Target] 请求，使用 [!UICONTROL 已缓存] 选项允许您在描述选件位置时使用相对URL。

   这意味着您将活动从测试服务器移到生产服务器后，无需手动更改 URL 即可自动访问内容。

* 如果您的测试中包含由服务器动态生成的数据，则选择“[!UICONTROL 动态]”选项可能是正确的做法。
* 如果您打算只测试现有远程选件内容的外观，请使用[!UICONTROL 可视化体验编辑器]来更改从内容管理系统返回的内容的外观。
* 使用 [远程选件选择表](#reference_B23BEDD29DDD47709A7651AFD27E776B) （下面）帮助您选择最适合您具体情况的选件。 如果您有任何问题，请咨询客服专员。

## 从代码选件页面创建远程选件

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。

   ![选件>代码选件](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 远程选件]**。

   ![“创建远程选件”对话框](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. 指定重定向URL类型。

   请参阅 [重定向URL类型：缓存或动态](#url-type) 下面以了解更多信息。

1. 为远程选件指定远程URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 使用基于表单的体验编辑器创建远程选件

1. 在使用 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，选择显示 **[!UICONTROL 内容]** 中。

   ![基于表单的体验编辑器中的“内容”部分](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击 **[!UICONTROL 默认内容]** 下拉列表，然后单击 **[!UICONTROL 更改远程选件]**.

   ![更改远程选件选项](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 远程选件]**。

   ![“创建远程选件”对话框](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. 指定重定向URL类型。

   请参阅 [重定向URL类型：缓存或动态](#url-type) 下面以了解更多信息。

1. 为远程选件指定远程URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 重定向URL类型：缓存或动态 {#url-type}

以下信息可帮助您了解这两个选项之间的差异：

### 缓存的URL

已缓存的远程选件的内容是从 [!DNL Target] 中提供的。

[!DNL Target] 每两小时从远程 URL 中提取一次内容，然后将该内容存储到 [!DNL Target] 中。如果访客加载的网站中具有包含远程选件的体验，则该选件会由 [!DNL Target] 交付。

已缓存的远程选件可提供增强的安全性，因为用户已登录到 [!DNL Target] 无法更改内容。 要更改内容，用户需登录到内容管理系统或其他系统并在其中更改内容。

您能够为已缓存的远程选件指定绝对 URL 或相对 URL。

### 动态URL

动态远程选件的内容是从内容管理系统或其他系统中提供的，而不是从 [!DNL Target] 中提供。

当访客加载的网站具有包含远程选件的体验时，您可能不希望由 [!DNL Target] 定期缓存并交付内容。您而是希望调用托管内容的系统，可能会传入特定信息，以便返回的选件可以针对每个用户是动态的（或不同的）。 例如，如果某位用户登录到一个信用卡网站，且该网站中具有包含动态远程选件的体验，则您能够将相应参数传递到 URL 中，以获取该用户的帐户信息。随后，网站便会提供特定于该用户的信息，例如账户余额。

您可以单击 **[!UICONTROL 添加参数]** 添加一个或多个 [!DNL Target] 请求或请求参数。

## 在活动中使用远程选件

您必须使用 [!UICONTROL 基于表单的体验编辑器]. 当前无法使用VEC应用远程选件。

的 [!DNL Adobe Target] [!UICONTROL 基于表单的体验编辑器] 是一个非可视化体验和选件创建界面，在创建要在中使用的体验时非常有用 [!UICONTROL A/B测试], [!UICONTROL 体验定位] (XT)、 [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL Recommendations] 活动。 例如，您可以使用 [!UICONTROL 基于表单的体验编辑器] 创建使用远程选件的体验。

1. 在 [!UICONTROL 基于表单的体验编辑器].

   请参阅 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 详细的分步说明。

1. 指定所需的位置并根据需要添加任何受众细化。

1. 单击 **[!UICONTROL 内容]** ，然后单击 **[!UICONTROL 更改远程选件]**.

   ![更改远程选件选项](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 从 [!UICONTROL 选择远程选件] 对话框，然后单击 **[!UICONTROL 完成]**.

1. 完成活动配置。

## 动态远程选件的工作原理 {#concept_CC2A969420B34364A9FA78C1CE251818}

动态远程选件使用动态页面技术来向选件传递值。

选件会在您提交页面后执行。不可见的iframe会收集数据，将其从框架中复制出来，然后插入到页面中，从而加载传递的值。

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

## 培训视频：基于表单的编辑器 ![教程徽章](/help/main/assets/tutorial.png)

此视频演示了基于表单的编辑器，您可以使用该编辑器创建远程选件。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
