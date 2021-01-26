---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content;url type
description: 我是否可以使用远程优惠托管外部内容？
title: 创建远程选件
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 48c49f764c4f2c2804230481c431a837776278a6
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 57%

---


# 创建远程选件

可使用远程选件在 [!DNL Adobe Target] 以外托管内容，[!DNL Target] 会引用这些内容并将其交付到用户网站。此内容可能位于内容管理(CMS)或其他系统中，这是为了易于使用，或是出于安全原因。

>[!NOTE]
>
>远程优惠可以在“优惠”>“代码优惠”页面或[基于Forms的体验书写器](/help/c-experiences/form-experience-composer.md)中创建。 无法在可视体验书写器(VEC)中创建远程优惠。 内容将插入到[!DNL Target]请求位置，因此这些位置很可能不适合全局[!DNL Target]请求。
>
>[!DNL Target Classic] 中提供了类似功能：[!UICONTROL 站内选件]和 [!UICONTROL Test&amp;Target 外部选件]。

下面是远程选件的一些示例：

* 不同版本的交叉销售
* 动态购物车消息
* 表单
* 计算器
* 利率更新

## 从“代码优惠”页创建远程优惠

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。

   ![优惠>代码优惠](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 远程选件]**。

   ![“创建远程优惠”对话框](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. 指定重定向URL类型。

   请参阅[重定向URL类型：有关详细信息，请在下面缓存或Dynamic](#url-type)。

1. 指定远程优惠的远程URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 使用基于表单的体验书写器创建远程优惠

1. 使用[基于表单的体验书写器](/help/c-experiences/form-experience-composer.md)创建活动时，选择显示&#x200B;**[!UICONTROL 内容]**&#x200B;部分的位置。

   ![基于表单的体验书写器中的内容部分](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. 单击&#x200B;**[!UICONTROL 默认内容]**&#x200B;下拉列表，然后单击&#x200B;**[!UICONTROL 更改远程优惠]**。

   ![更改远程优惠选项](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 单击&#x200B;**[!UICONTROL 创建]** > **[!UICONTROL 远程选件]**。

   ![“创建远程优惠”对话框](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. 指定重定向URL类型。

   请参阅[重定向URL类型：有关详细信息，请在下面缓存或Dynamic](#url-type)。

1. 指定远程优惠的远程URL。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 重定向URL类型：缓存或动态{#url-type}

以下信息可帮助您了解两个选项之间的差异：

### 缓存的URL类型

已缓存的远程选件的内容是从 [!DNL Target] 中提供的。

[!DNL Target] 每两小时从远程 URL 中提取一次内容，然后将该内容存储到 [!DNL Target] 中。如果访客加载的网站中具有包含远程选件的体验，则该选件会由 [!DNL Target] 交付。

缓存的远程优惠提供增强的安全性，因为登录到[!DNL Target]的某人无法更改内容。 要更改内容，用户需登录到内容管理系统或其他系统并在其中更改内容。

您能够为已缓存的远程选件指定绝对 URL 或相对 URL。

### 动态URL类型

动态远程选件的内容是从内容管理系统或其他系统中提供的，而不是从 [!DNL Target] 中提供。

当访客加载的网站具有包含远程选件的体验时，您可能不希望由 [!DNL Target] 定期缓存并交付内容。相反，您需要调用托管内容的系统，可能会传递特定信息，以便为每个用户动态（或不同）返回的优惠。 例如，如果某位用户登录到一个信用卡网站，且该网站中具有包含动态远程选件的体验，则您能够将相应参数传递到 URL 中，以获取该用户的帐户信息。随后，网站便会提供特定于该用户的信息，例如账户余额。

单击&#x200B;**[!UICONTROL 添加参数]**&#x200B;可添加一个或多个[!DNL Target]请求或请求参数。

## 使用远程优惠{#section_7718512D08E14121B6F6B8C38134F4BC}的最佳实践

在活动中使用远程选件时需遵循以下最佳实践：

* 如果优惠与[!DNL Target]请求位于同一域中，则使用[!UICONTROL  Cached]选项，可以使用相对URL描述优惠位置。

   这意味着您将活动从测试服务器移到生产服务器后，无需手动更改 URL 即可自动访问内容。

* 如果您的测试中包含由服务器动态生成的数据，则选择“[!UICONTROL 动态]”选项可能是正确的做法。
* 如果您打算只测试现有远程选件内容的外观，请使用[!UICONTROL 可视化体验编辑器]来更改从内容管理系统返回的内容的外观。
* 使用远程优惠选择列表（如下所示）帮助您选择最适合您特定情况的优惠。 如果您有任何问题，请咨询客服专员。

## 动态远程优惠的工作方式{#concept_CC2A969420B34364A9FA78C1CE251818}

动态远程选件使用动态页面技术来向选件传递值。

选件会在您提交页面后执行。不可见的iframe会收集数据，将其从框架中复制出来，并插入页面中，从而加载传递的值。

![](assets/remote_offer_howitworks_2.jpeg)

## 远程优惠选择矩阵{#reference_B23BEDD29DDD47709A7651AFD27E776B}

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