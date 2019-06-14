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
source-git-commit: dcddbf8c1a4f406fdbfb00b9deaa75113aa7b624

---


# 创建体验定位活动{#create-an-experience-targeting-activity}

使用 [!UICONTROL 视觉体验书写器] (CMS)在启用Target的页面上创建 [!UICONTROL 体验定位] (XT)活动并修改其中 [!DNL Adobe Target]页面的部分。

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

体验定位(包括 [地理定位](/help/c-target/c-audiences/c-target-rules/geo.md))对于定义将特定体验或内容定向到特定受众的规则很有价值。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。

有关体验定位、使用案例方案和培训视频的更多信息，请参阅 [体验定位](/help/c-activities/t-experience-target/experience-target.md)。

**要创建XT活动，请执行以下操作：**

1. 在[!UICONTROL 活动]**列表中，单击[!UICONTROL 创建活动]&gt;****[!UICONTROL 体验定位]**。

   ![创建活动&gt;体验定位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 Target 帐户。有些活动类型可能不会显示在列表中。例如 [!UICONTROL ，自动个性化] 是 [Target Premium功能](/help/c-intro/intro.md#premium)。
   >
   >有关可用的各种活动类型 [!DNL Target] 及其差异的更多信息，请参阅 [活动](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [目标活动类型](/help/c-activities/target-activities-guide.md) 以帮助您确定哪种活动类型最适合您的需求。

1. 如有必要，请选择 **[!UICONTROL 视觉(默认)]**。

   ![“创建体验定位活动”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您希望使用基于表单的体验编辑器，请选择相应的选项。请参阅[基于表单的体验编辑器](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html)。

   >[!NOTE]
   >
   >除了CMS和基于表单的Experience Composer之外，Target还提供单页应用程序CMS和CMS for Mobile Apps。有关各种书写器的更多信息，请参阅 [体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)。

1. 指定 [活动URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然后单击 **[!UICONTROL “下一步]**”。

   如果您的帐户 [配置了默认URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)，默认情况下会显示该URL。如有必要，您可以从默认位置更改为其他URL。

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

   有关分步说明，请参阅 [添加体验](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活动的[目标和设置](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。