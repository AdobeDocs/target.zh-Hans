---
keywords: MVT；多变量测试；选件；组合
description: 了解如何使用Adobe [!DNL Target]中的[!UICONTROL 可视化体验编辑器] (VEC)创建要包含在[!UICONTROL 多变量测试] (MVT)中的选件。
title: 如何在[!UICONTROL 多变量测试] (MVT)中创建组合？
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# 创建组合 {#create-combinations}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何创建构成&#x200B;**[!UICONTROL 多变量测试]**&#x200B;组合的图像和HTML选件。

>[!ENDSHADEBOX]

在&#x200B;**[!UICONTROL 多变量测试]** (MVT)中，每个位置都包含多个选件，并且各个位置上的每个选件组合都是一个体验。 在[!DNL Adobe Target]中使用&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)创建要包含在测试中的选件。

有关使用 VEC 创建和编辑产品建议的更多信息，请参阅[可视化体验编辑器选项](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)。

>[!NOTE]
>
>选择页面上的对象时，除了最初选定的元素之外，您还可以单击&#x200B;**[!UICONTROL 展开选定内容]**&#x200B;以选择父元素。 选择任意父元素时，该元素的所有子元素均会自动选定。 您可以多次展开选定内容。
>
>您还可以使用 [DOM 路径](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)导览元素。

## 图像产品建议 {#image-offers}

可在某个位置测试多个图像选件，以确定哪个图像最为成功。

1. 单击页面上的图像，然后选择&#x200B;**[!UICONTROL 更改图像选件]**。

   ![更改图像选件菜单](../assets/multivariate-1.png)

1. 从&#x200B;**[!UICONTROL 图像选件]**&#x200B;对话框中，选择要包含在测试中的所有图像，然后单击&#x200B;**[!UICONTROL 添加]**。

   ![更改图像选件菜单](../assets/multivariate-3.png)

每个图像会成为该位置的独立体验。

## HTML优惠 {#html-offers}

可在某个位置测试多个 HTML 选件，以确定哪个选件最为成功。

1. 单击页面上的HTML选件，然后单击&#x200B;**[!UICONTROL 更改HTML选件]**。

   ![更改HTML选件菜单](../assets/multivariate-2.png)

1. 选择您的HTML选件，然后单击&#x200B;**[!UICONTROL 创建选件]**，然后单击&#x200B;**[!UICONTROL HTML选件]**。

   ![更改HTML选件菜单](../assets/multivariate-4.png)

1. 命名选件，键入或粘贴HTML选件的代码，然后单击&#x200B;**[!UICONTROL 创建]**。

   重复执行上述步骤以添加任何其他要包含的HTML选件。

1. 单击&#x200B;**[!UICONTROL 保存]**。

每个 HTML 选件会成为该位置的独立体验。

有关在启动测试之前要包含多少组合以及如何审查这些组合的建议，请参阅[多变量测试最佳实践](/help/main/c-activities/c-multivariate-testing/best-practices.md#create)。
