---
keywords: 体验定位；XT；创建
description: 了解如何使用 [!UICONTROL 可视化体验编辑器] (VEC)位于 [!DNL Adobe Target] 创建 [!UICONTROL 体验定位] (XT)活动。
title: 如何创建 [!UICONTROL 体验定位] 活动？
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 51%

---

# 创建 [!UICONTROL 体验定位] (XT)活动

使用 [!UICONTROL 可视化体验编辑器] (VEC)以创建 [!UICONTROL 体验定位] (XT)上的活动 [!DNL Target]启用页面，并在中修改页面的各个部分 [!DNL Adobe Target].

[!UICONTROL 体验定位] (XT) 根据一组营销人员定义的规则和标准向特定受众提供内容。

体验定位（包括[地理定位](/help/main/c-target/c-audiences/c-target-rules/geo.md)）对于定义规则以将特定体验或内容定位到特定受众非常有用。可以在活动中定义多个规则，以将不同的内容变体交付到不同的受众。

有关详情 [!UICONTROL 体验定位]，用例情景和培训视频，请参阅 [体验定位](/help/main/c-activities/t-experience-target/experience-target.md).

**创建 [!UICONTROL 体验定位] 活动：**

1. 在“[!UICONTROL 活动]”列表中，单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 体验定位]**。

   ![“创建活动”>“体验定位”](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >可用的活动类型取决于您的 [!DNL Target] 帐户。有些活动类型可能不会显示在列表中。例如，“[!UICONTROL 自动个性化]”是一项 [Target Premium 功能](/help/main/c-intro/intro.md#premium)。
   >
   >有关 [!DNL Target] 中可用的各种活动类型及其差异的更多信息，请参阅[活动](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。请参阅 [Target 活动类型](/help/main/c-activities/target-activities-guide.md)，以帮助您确定最符合自己需求的活动类型。

1. 如有必要，选择&#x200B;**[!UICONTROL 可视（默认）]**。

   如果您希望使用 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)，选择 [!UICONTROL 表单].

   >[!NOTE]
   >
   >除了VEC和 [!UICONTROL 基于表单的体验编辑器]， [!DNL Target] 提供单页应用程序VEC。 有关各种编辑器的更多信息，请参阅[体验和选件](/help/main/c-experiences/experiences.md)。
   >
   >有关VEC的故障诊断信息，请参阅 [可视化体验编辑器故障诊断](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （视情况而定）如果您是 [!DNL Target Premium] 客户， [选择工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   此 [!UICONTROL 选择工作区] 选项是 [Target Premium](/help/main/c-intro/intro.md) 功能。 如果贵组织拥有 [!DNL Target Standard] 许可证（如果未看到此选项）。

1. 指定[活动 URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)，然后单击&#x200B;**[!UICONTROL 创建]**。

   如果您的帐户[配置了默认 URL](/help/main/administrating-target/visual-experience-composer-set-up.md)，则默认情况下将显示该 URL。您可以根据需要将默认 URL 更改为其他 URL。

   此时会打开 VEC，其中显示了在 URL 中指定的页面。

   ![VEC 中的体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 在提供的空白处键入该活动的名称。

   ![名称字段](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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
   | ;+ | 分号，加号 |
   | ;- | 分号，减号 |
   | ;@ | 分号， At sign |
   | ,= | 逗号，等于 |
   | ,+ | 逗号，加号 |
   | ,- | 逗号，减 |
   | ,@ | 逗号， At sign |
   | `[`&quot; | 左方括号，双引号 |
   | &quot;`]` | 双引号，右方括号 |

1. 创建定位到不同受众的新体验。

   有关分步说明，请参阅[添加体验](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)。

1. 指定活动的[目标和设置](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)。
