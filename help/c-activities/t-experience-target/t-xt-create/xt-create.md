---
description: 使用可视化体验编辑器，可在启用了 Target 的页面上创建体验定位活动，并在 Target 中修改页面的各个部分。
seo-description: 使用视觉体验书写器在启用Target的页面上创建体验定位活动，并在Adobe Target中修改页面部分。
seo-title: 创建体验定位活动
solution: Target
subtopic: 多变量测试
title: 创建体验定位活动
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# 创建体验定位活动{#create-an-experience-targeting-activity}

使用 [!UICONTROL 视觉体验书写器] (CMS)在启用Target的页面上创建 [!UICONTROL 体验定位] (XT)活动并修改其中 [!DNL Adobe Target]页面的部分。

1. 在[!UICONTROL 活动]**列表中，单击[!UICONTROL 创建活动]&gt;****[!UICONTROL 体验定位]**。

   ![创建活动&gt;体验定位](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 Target 帐户。有些活动类型可能不会显示在列表中。例如，自动个性化是 [Target Premium功能](/help/c-intro/intro.md#premium)。

   有关活动类型的信息，请参阅 [活动](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) 和 [目标活动类型](/help/c-activities/target-activities-guide.md)。

1. 如有必要，请选择 **[!UICONTROL 视觉(默认)]**。

   ![“创建体验定位活动”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您希望使用基于表单的体验编辑器，请选择相应的选项。请参阅[基于表单的体验编辑器](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html)。

   >[!NOTE]
   >
   >除了CMS和基于表单的Experience Composer之外，Target还提供单页应用程序CMS和CMS for Mobile Apps。有关各种书写器的更多信息，请参阅 [体验和选件](/help/c-experiences/experiences.md)。

   如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)。

1. 指定 [活动URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然后单击 **[!UICONTROL “下一步]**”。

   如果您的帐户配置了默认 URL，则默认情况下将显示该 URL。您可以将默认 URL 更改为其他 URL。

   此时会打开可视化体验编辑器，其中显示了在 URL 中指定的页面。

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

1. 创建任何新体验（通过更改页面上的元素）。

   有关分步说明，请参阅 [添加体验](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

   默认情况下，可视化体验编辑器不允许更改包含 JavaScript 的元素，如旋转横幅。如果您希望能够使用可视化体验编辑器更改这些元素，则可以选择禁用 JavaScript。

   将鼠标悬停在页面中的元素上时，这些元素会高亮显示。可以使用CMS更改任何高亮显示的元素。有关可对元素执行的操作以更改体验的列表，请参阅 [视觉体验合成器选项](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)。

   如果您曾使用 Target Classic（以前为 Test&amp;Target）在页面上创建了 mbox，则该 mbox 将显示为一个元素，该元素会显示 mbox 名称，且可以像其他任何元素一样进行修改。

1. 指定活动的[目标和设置](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。
