---
keywords: 多页面;历程测试;多页面活动
description: 了解如何在Adobe [!DNL Target]中创建多页面活动，允许您使用特定于每个页面的设计跨多个页面创建故事。
title: 如何创建多页面活动？
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# 多页面活动 {#multipage-activity}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何使用多页面活动创建跨多个页面的故事，以及特定于每个页面的设计。

>[!ENDSHADEBOX]

[!DNL Adobe Target]中的多页面活动会跨多个页面创建一个故事，并且每个页面都具有特定的设计。

例如，可以测试购买量超过一定金额的免费送货优惠。 选件可显示在登陆页面、类别页面和某些产品页面上，且大小不同，位置也不同。 突出的选件可以显示在主页上，然后在其他相关页面上通过较小的选件进行强化。

多页面活动还可以为桌面网站和无响应移动网站定义不同的布局。 如果网站具有独立的移动设备网站，例如[!DNL m.mysite.com]而不是[!DNL `www.mysite.com`]，请创建一个多页面活动，将[!DNL m.mysite.com]添加为独立的页面，然后应用移动设备编辑，以便对同一体验中的桌面版和移动设备版做出适当的更改。 对于响应式移动设备网站，应使用[移动体验编辑](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)。

>[!NOTE]
>
>当同一产品建议在多个页面上具有不同的外观时，需要设计多页面活动。 如果同一产品建议在所有页面上具有相同的外观，则使用[测试模板](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)更为有效。

可以为多页面测试中的每个页面指定模板规则。 例如，通过将模板规则应用于多页面测试中的类别页面，可以在主页和所有类别页面中运行多页面测试。 请参阅[在相似页面上包含相同体验](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)。

## 将页面添加到活动 {#add-pages}

添加到活动的每个页面都可以拥有自己的选件设计。

1. 单击&#x200B;**[!UICONTROL 配置]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg)）。

1. 单击&#x200B;**[!UICONTROL 添加其他页面]**。

   屏幕左侧显示一个&#x200B;**[!UICONTROL 页面]**&#x200B;窗格。

   ![配置图标](assets/vec_edit_4.png)

1. 指定页面并设置默认页面。

   单击&#x200B;**[!UICONTROL 添加页面]** （![添加图标](/help/main/assets/icons/Add.svg) ）以添加其他页面，指定页面名称和URL，然后单击&#x200B;**[!UICONTROL 保存]**。

1. 使用[!UICONTROL 可视化体验编辑器]设计选件在每个页面上的外观。
