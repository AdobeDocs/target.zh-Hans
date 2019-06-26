---
description: 使用可视化体验编辑器，可在启用了 Target 的页面上创建体验定位活动，并在 Target 中修改页面的各个部分。
seo-description: 使用视觉体验书写器在启用Target的页面上创建体验定位(XT)活动并修改Adobe Target中页面的部分。
seo-title: 创建体验定位活动
solution: Target
subtopic: 多变量测试
title: 创建体验定位活动
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 创建体验定位活动{#create-an-experience-targeting-activity}

Use the [!UICONTROL Visual Experience Composer] (VEC) to create an [!UICONTROL Experience Targeting] (XT) activity on a Target-enabled page and to modify portions of the page within [!DNL Adobe Target].

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

Experience Targeting, including [geo-targeting](/help/c-target/c-audiences/c-target-rules/geo.md), is valuable for defining rules that target a specific experience or content to a particular audience. 可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。

For more information about Experience Targeting, a use-case scenario, and training videos, see [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**要创建XT活动，请执行以下操作：**

1. 在[!UICONTROL 活动]**列表中，单击[!UICONTROL 创建活动]&gt;****[!UICONTROL 体验定位]**。

   ![创建活动&gt;体验定位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 Target 帐户。有些活动类型可能不会显示在列表中。For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![“创建体验定位活动”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您希望使用基于表单的体验编辑器，请选择[!UICONTROL 表单]。See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >除了CMS和基于表单的Experience Composer之外，Target还提供单页应用程序CMS和CMS for Mobile Apps。For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. 如果您看不到此选项，则您的组织有Target Standard许可证。]

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   If your account is [configured with a default URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), that URL appears by default. 如有必要，您可以从默认位置更改为其他URL。

   此时将打开CMS，显示URL中指定的页面。

   ![CMS中的体验定位活动](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 在提供的空白处键入该活动的名称。

   ![名称字段](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   活动名称中不允许使用以下字符：

   | 字符 | 描述 |
   |--- |--- |
   | `/` | 正斜线 |
   | `?` | 问号 |
   | `#` | 数字符号 |
   | `:` | 冒号 |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

1. 创建旨在不同受众的新体验。

   For step-by-step instructions, see [Add experience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. 指定活动的[目标和设置](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。