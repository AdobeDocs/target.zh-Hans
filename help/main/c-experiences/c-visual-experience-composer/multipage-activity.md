---
keywords: 多页面;历程测试;多页面活动
description: 了解如何在Adobe [!DNL Target] 中创建多页面活动，允许您使用特定于每个页面的设计跨多个页面创建故事。
title: 如何创建多页面活动？
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 54%

---

# 多页面活动

通过[!DNL Adobe Target]中的多页面活动，您可以跨多个页面创建一个故事，其设计特定于每个页面。

例如，您可能需要测试一个购买量超过一定数量后免运费的选件。您可能希望该选件显示在登陆页面、类别页面和某些产品页面上，但是对于每种类型的页面，您还希望以不同的大小、在不同的位置显示。您可以在主页上显示一个明显的选件，然后在其他相关页面上通过一些较小的选件来加强该选件。

您还可以使用多页面活动来为桌面和非响应式移动设备网站定义不同的布局。如果该网站具有独立的移动设备网站，例如[!DNL m.mysite.com]，而不是[!DNL `www.mysite.com`]，则您应该创建一个[多页面活动](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)，将[!DNL m.mysite.com]添加为独立的页面，然后应用移动编辑，以便对同一体验中的桌面版和移动设备版做出适当的更改。 对于响应式移动设备网站，应使用[移动体验编辑](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5)。

>[!NOTE]
>
>当同一产品建议在多个页面上具有不同的外观时，需要设计多页面活动。如果同一产品建议在所有页面上具有相同的外观，则使用[测试模板](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)更为有效。

在多页面测试中，您可以为每个页面指定模板规则。例如，在多页面测试中，您可以向类别页面应用模板规则，从而在主页和所有类别页面上运行多页面测试。请参阅[在相似页面上包含相同体验](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)。

要将页面添加到测试，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Configure]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg) ）。
1. 单击 **[!UICONTROL Add Additional Pages]**。

   屏幕左侧显示一个[!UICONTROL Pages]窗格。

1. 指定页面并设置默认页面。

   单击&#x200B;**[!UICONTROL Add Page]** （![添加图标](/help/main/assets/icons/Add.svg) ）以添加其他页面，指定页面名称和URL，然后单击&#x200B;**[!UICONTROL Save]**。

1. 使用[!UICONTROL Visual Experience Composer]设计选件在每个页面上的外观。
