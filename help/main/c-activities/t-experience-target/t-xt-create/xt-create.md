---
keywords: 体验定位；XT；创建
description: 了解如何在 [!DNL Adobe Target] 中使用[!UICONTROL Visual Experience Composer] (VEC)来创建[!UICONTROL Experience Targeting] (XT)活动。
title: 如何创建[!UICONTROL Experience Targeting]活动？
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 9cc1eb4c5c95ea51bc0a1fc9e89b245a18c9914b
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 33%

---

# 创建[!UICONTROL Experience Targeting] (XT)活动

使用[!UICONTROL Visual Experience Composer] (VEC)在启用了[!DNL Target]的页面上创建[!UICONTROL Experience Targeting] (XT)活动，并在[!DNL Adobe Target]内修改页面的各个部分。

[!UICONTROL Experience Targeting] (XT)根据一组营销人员定义的规则和条件向特定受众提供内容。

[!UICONTROL Experience Targeting]（包括[地理定位](/help/main/c-target/c-audiences/c-target-rules/geo.md)）对于定义规则以将特定体验或内容定位到特定受众非常有用。 可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。

有关[!UICONTROL Experience Targeting]、用例情景和培训视频的更多信息，请参阅[体验定位](/help/main/c-activities/t-experience-target/experience-target.md)。

**要创建[!UICONTROL Experience Targeting]活动：**

1. 从[!UICONTROL Activities]列表中，单击&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**。

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，[!UICONTROL Automated Personalization]是[Target Premium功能](/help/main/c-intro/intro.md#premium)。
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [Target 活动类型](/help/main/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. 根据需要选择&#x200B;**[!UICONTROL Visual]**。

   如果您希望使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，请选择[!UICONTROL Form]。

   >[!NOTE]
   >
   >除了VEC和[!UICONTROL Form-Based Experience Composer]之外，[!DNL Target]还提供单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和产品建议](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅[可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)。

1. （视情况而定）如果您是[!DNL Target Premium]客户，请[选择一个工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [!UICONTROL Choose Workplace]选项是[Target Premium](/help/main/c-intro/intro.md)功能。 如果您看不到此选项，则表明贵组织具有[!DNL Target Standard]许可证。

1. 指定您的[活动URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然后单击&#x200B;**[!UICONTROL Create]**。

   如果您的帐户[配置了默认 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认 URL 更改为其他 URL。

   此时会打开 VEC，其中显示了在 URL 中指定的页面。

1. 要命名活动，请单击“[!UICONTROL Untitled Activity]”旁边的&#x200B;**[!UICONTROL Edit]**&#x200B;图标（![编辑图标](/help/main/assets/icons/Edit.svg)），为活动指定描述性名称，然后单击&#x200B;**[!UICONTROL Save]**。

   活动名称不能以下列任何字符开头：

   | 字符 | 描述 |
   |--- |--- |
   | `=` | 等号 |
   | `+` | 加号 |
   | `-` | 减号 |
   | `@` | @ 符号 |

   活动名称不能包含以下任何字符序列：

   | 字符序列 | 描述 |
   |--- |--- |
   | ；= | 分号，等于 |
   | ；+ | 分号，加号 |
   | ；- | 分号，减号 |
   | ；@ | 分号， At sign |
   | ，= | 逗号，等于 |
   | ，+ | 逗号，加号 |
   | ，- | 逗号，减 |
   | ，@ | 逗号， At sign |
   | `[`” | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 创建定位到不同受众的新体验。

   有关分步说明，请参阅[添加体验](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活动的[目标和设置](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。
