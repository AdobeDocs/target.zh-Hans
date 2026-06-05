---
keywords: 远程选件；缓存的内容；动态内容；URL类型
description: 了解如何利用 [!DNL Target] 中的远程选件来托管来自CMS或其他系统的外部内容。
title: 如何创建远程选件？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
TQID: https://experienceleague.adobe.com/maKcis5ROOKMcc3-axxGv1qJIQzC6o-Qc-Cjl8clQ1I
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1145
ht-degree: 24%

---

# 创建远程产品建议

使用远程选件在[!DNL Adobe Target]之外托管内容，允许[!DNL Target]引用此内容并将其交付到用户网站。 出于易用性或安全原因，此内容可以驻留在内容管理系统(CMS)或其他系统中。

可以在[!UICONTROL 选件] > [!UICONTROL 代码选件]页面或[基于Forms的体验编辑器](/help/main/c-experiences/form-experience-composer.md)中创建远程选件。 无法在[!UICONTROL 可视化体验编辑器] (VEC)中创建或应用远程选件。 内容被插入到[!DNL Target]请求位置，因此这些位置可能不适合全局[!DNL Target]请求。

下面是远程选件的一些示例：

* 不同版本的交叉销售
* 动态购物车消息
* 表单
* 计算器
* 利率更新
* 电子邮件
* 信息亭
* 语音助理

## 使用远程选件的最佳实践 {#section_7718512D08E14121B6F6B8C38134F4BC}

在活动中使用远程选件时需遵循以下最佳实践：

* 支持远程选件：

   * A/B活动
   * 体验定位 (XT) 活动
   * 基于表单的工作流

* 不支持远程选件：

   * [高级功能](/help/main/c-intro/intro.md#premium) (Automated Personalization (AP)、自动定位和推荐)
   * Multivariate Testing (MVT)，由于依赖于VEC，它不支持远程选件。

* 如果选件与[!DNL Target]请求位于同一域中，则使用[!UICONTROL Cached]选项可使用相对URL描述选件位置。

  这意味着在将活动从暂存服务器移至生产服务器时，无需手动更改URL即可自动访问内容。

* 如果您的测试中包含由服务器动态生成的数据，则选择“[!UICONTROL 动态]”选项可能是正确的做法。
* 如果您打算只测试现有远程选件内容的外观，请使用[!UICONTROL 可视化体验编辑器]来更改从内容管理系统返回的内容的外观。
* 使用[远程选件选择表](#reference_B23BEDD29DDD47709A7651AFD27E776B)（如下）帮助您选择最适合您特定案例的选件。 如果您有任何问题，请咨询客服专员。

## 从[!UICONTROL 代码选件]页面创建远程选件

1. 单击&#x200B;**[!UICONTROL 选件]**，然后选择&#x200B;**[!UICONTROL 代码选件]**&#x200B;选项卡。

1. 单击&#x200B;**[!UICONTROL 创建选件]** > **[!UICONTROL 远程选件]**。

1. 在[!UICONTROL 创建远程选件]对话框中，提供选件的描述性名称。

   描述性名称可帮助您和其他人在[!UICONTROL 选件]库中快速找到该选件。

1. （视情况而定）如果您拥有[Target Premium帐户](/help/main/c-intro/intro.md#premium)，请选择所需的[工作区](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定重定向URL类型。

   有关详细信息，请参阅下面的[重定向URL类型： [!UICONTROL 现场缓存]或[!UICONTROL 现场动态]](#url-type)。

1. 指定远程选件的绝对远程URL。

1. 单击&#x200B;**[!UICONTROL 创建]**。

## 使用[!UICONTROL 基于表单的体验编辑器]创建远程选件

1. 使用基于[表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)创建活动时，请选择要显示&#x200B;**[!UICONTROL 内容]**&#x200B;部分的位置。
1. 单击&#x200B;**[!UICONTROL 内容]**&#x200B;下拉列表，单击&#x200B;**[!UICONTROL 列表]**&#x200B;图标（![列表](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL 更改远程选件]**。

1. 单击&#x200B;**[!UICONTROL 创建选件]** > **[!UICONTROL 远程选件]**。

1. 为选件提供一个描述性名称。

   描述性名称可帮助您和他人在[!UICONTROL 资产]库中快速找到所需的选件。

1. （视情况而定）如果您拥有[Target Premium帐户](/help/main/c-intro/intro.md#premium)，请选择所需的[工作区](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)。

1. 指定重定向URL类型。

   有关详细信息，请参阅下面的[重定向URL类型： [!UICONTROL 现场缓存]或[!UICONTROL 现场动态]](#url-type)。

1. 指定远程选件的远程URL。

1. 单击&#x200B;**[!UICONTROL 创建]**。

## 重定向URL类型： [!UICONTROL 现场缓存]或[!UICONTROL 现场动态] {#url-type}

以下信息可帮助您了解这两个选项之间的差异：

### [!UICONTROL 现场缓存] URL

缓存的远程选件的内容是从[!DNL Target]提供的。

每两小时，[!DNL Target]从远程URL中提取内容，然后将该内容存储在[!DNL Target]中。 当访客加载的网站具有包含远程选件的体验时，[!DNL Target]会提供该选件。

缓存的远程选件提供了增强的安全性，因为登录到[!DNL Target]的人员无法更改内容。 要更改内容，用户需要登录到内容管理或其他系统，然后在其中更改内容。

您能够为已缓存的远程选件指定绝对 URL 或相对 URL。

### [!UICONTROL 现场动态] URL

动态远程选件由内容管理或其他系统提供，而不是从[!DNL Target]提供。

当访客加载的网站具有包含远程选件的体验时，您可能不希望由[!DNL Target]定期缓存并交付内容。 您而是可能希望调用托管内容的系统，然后传入特定信息，以便每个用户能够返回动态（或不同的）选件。 例如，如果某位用户登录到一个信用卡网站，且该网站中具有包含动态远程选件的体验，则您能够将相应参数传递到 URL 中，以获取该用户的帐户信息。 随后，网站便会提供特定于该用户的信息，例如账户余额。

您可以单击&#x200B;**[!UICONTROL 添加参数]**&#x200B;以添加一个或多个[!DNL Target]请求或请求参数。

## 在活动中使用远程选件

使用基于[!UICONTROL 表单的体验编辑器]应用远程选件。 您当前无法使用[!UICONTROL 可视化体验编辑器] (VEC)应用远程选件。

[!DNL Adobe Target] [!UICONTROL 基于表单的体验编辑器]是非可视化体验和选件创建界面，当[!UICONTROL 可视化体验编辑器]不可用或不实用时，它有助于创建在[!UICONTROL A/B测试]、[!UICONTROL 体验定位] (XT)、[!UICONTROL Automated Personalization] (AP)和[!UICONTROL 推荐]活动中使用的体验。 例如，您可以使用[!UICONTROL 基于表单的体验编辑器]创建使用远程选件的体验。

1. 在[!UICONTROL 基于表单的体验编辑器]中创建或编辑活动。

   有关详细的分步说明，请参阅[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)。

1. 指定所需位置并根据需要添加任何受众细化。

1. 单击&#x200B;**[!UICONTROL 内容]**&#x200B;下拉列表，单击&#x200B;**[!UICONTROL 列表]**&#x200B;图标（![列表](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL 更改远程选件]**。

1. 从[!UICONTROL 更改远程选件]对话框中选择所需的远程选件，然后单击&#x200B;**[!UICONTROL 创建选件]** > **[!UICONTROL 远程选件]**。

1. 配置完活动。

## 动态远程选件的工作原理 {#concept_CC2A969420B34364A9FA78C1CE251818}

动态远程选件使用动态页面技术来向选件传递值。

选件会在您提交页面后执行。 不可见的iFrame会收集数据，将其从框架中复制出来，然后插入到页面中，从而加载您传递的值。

![remote_offer_howitworks_2图像](assets/remote_offer_howitworks_2.jpeg)

1. 访客的浏览器向您的服务器请求一个页面。

2. 浏览器渲染页面，包括mbox。

3. `mboxCreate`调用包含呈现动态内容所需的参数。

4. [!DNL Target]返回包含动态内容位置及其参数的URL。 在mbox区域中设置iFrame。

5. 浏览器请求URL并在页面中呈现。

## 远程选件选择表 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

远程选件选择矩阵可帮助您决定要选择的远程选件类型： [!UICONTROL 现场缓存]或[!UICONTROL 现场动态]。

| 功能 | 现场缓存 | 现场动态 |
|--- |--- |--- |
| 每次访客发出请求时更新 | 否 | 是 |
| 内容更新 | 每两小时缓存一次 | 每次请求时立即更新 |
| 加载时间 | 更快 | 由于请求处理原因加载时间较慢 |
| 可以查看页面上的 JavaScript | 是 | 否，但可以通过 URL 传递 |
| 选件可以包含 JavaScript | 是 | 是 |
| 选件 URL | 绝对或相对 | 相对 |
| 请求计算机 | Adobe 服务器 | 带有访客 Cookie 的访客计算机 |
