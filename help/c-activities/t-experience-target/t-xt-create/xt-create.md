---
description: 使用可视化体验编辑器，可在启用了 Target 的页面上创建体验定位 (XT) 活动，并在 Adobe Target 中修改页面的各个部分。
title: 创建体验定位活动
feature: xt
subtopic: Multivariate Test
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# 创建体验定位活动{#create-an-experience-targeting-activity}

使用[!UICONTROL 可视化体验编辑器] (VEC)，可在启用了 Target 的页面上创建[!UICONTROL 体验定位] (XT) 活动，并在 [!DNL Adobe Target] 中修改页面的各个部分。

体验定位 (XT) 可根据营销人员定义的一组规则和标准，将内容交付给指定的受众。

体验定位（包括[地理定位](/help/c-target/c-audiences/c-target-rules/geo.md)）对于定义规则以将特定体验或内容定位到特定受众非常有用。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。

有关体验定位、用例情景和培训视频的更多信息，请参阅[体验定位](/help/c-activities/t-experience-target/experience-target.md)。

**创建 XT 活动：**

1. 在“[!UICONTROL 活动]”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 体验定位]**。

   ![“创建活动”>“体验定位”](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 Target 帐户。有些活动类型可能不会显示在列表中。例如，“[!UICONTROL 自动个性化]”是一项 [Target Premium 功能](/help/c-intro/intro.md#premium)。
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [Target 活动类型](/help/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   ![“创建体验定位活动”对话框](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   如果您希望使用基于表单的体验编辑器，请选择“[!UICONTROL 表单]”。请参阅[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)，以了解更多信息。

   >[!NOTE]
   >
   >除了 VEC 和基于表单的体验编辑器之外，Target 还提供单页应用程序 VEC 和适用于移动设备应用程序的 VEC。有关各种编辑器的更多信息，请参阅[体验和选件](/help/c-experiences/experiences.md)。
   >
   >如需 VEC 的故障诊断信息，或者当您遇到问题时，请参阅[可视化体验编辑器故障诊断](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。
   >
   >上图中的“[!UICONTROL 选择工作区]”选项是一项 [Target Premium](/help/c-intro/intro.md) 功能。如果您看不到此选项，则表明贵组织具有 Target Standard 许可证。

1. （视情况而定）如果您是一位 Target Premium 客户，请[选择一个工作区](/help/administrating-target/c-user-management/property-channel/property-channel.md)。

1. 指定[活动 URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然后单击&#x200B;**[!UICONTROL 下一步]**。

   如果您的帐户[配置了默认 URL](/help/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认 URL 更改为其他 URL。

   此时会打开 VEC，其中显示了在 URL 中指定的页面。

   ![VEC 中的体验定位活动](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

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

1. 创建定位到不同受众的新体验。

   有关分步说明，请参阅[添加体验](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活动的[目标和设置](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。