---
keywords: 基于表单的体验编辑器;基于表单的编辑器;细化
description: 了解如何使用基于Adobe [!DNL Target] 表单的体验编辑器创建非可视化体验。 当VEC不可用或不实用时，使用此编辑器。
title: 如何使用基于表单的体验编辑器？
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 33%

---

# 基于表单的体验编辑器

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]是非可视化体验和选件创建界面，当[!UICONTROL Visual Experience Composer] (VEC)不可用或不实用时，它有助于创建在[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活动中使用的体验。 例如，您可以使用基于表单的体验编辑器创建在电子邮件、网亭和语音助手中交付的体验和选件。

如果您正在创建[!UICONTROL Recommendations]活动，则没有体验。 需选择您的标准和设计。如果选择多个标准或设计，[!UICONTROL Target]将自动生成体验。

1. 单击&#x200B;**[!UICONTROL Create Activity]**，然后选择要创建的活动类型。

   [!UICONTROL Form-Based Experience Composer]可用于[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting]、[!UICONTROL Automated Personalization]和[!UICONTROL Recommendations]活动。

1. 从[!UICONTROL Create Activity]对话框中选择&#x200B;**[!UICONTROL Form]**。

1. （视情况而定）如果您是[Target Premium客户](/help/main/c-intro/intro.md#premium)，请从&#x200B;**[!UICONTROL Choose Workspace]**&#x200B;下拉列表中选择一个[工作区](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)选项是[Target Premium](/help/main/c-intro/intro.md)功能，如果您的组织具有[!UICONTROL Target Standard]许可证，则可能无法显示。

1. 选择属性。

1. 单击 **[!UICONTROL Create]**。

   将打开[!UICONTROL Form-Based Experience Composer]。

   如果您正在创建[!UICONTROL Recommendations]活动，则此屏幕不同。 [!UICONTROL Recommendations]活动不包含体验。

1. &#x200B;
   1. 单击&#x200B;**[!UICONTROL Rename]**&#x200B;图标（![重命名图标](/help/main/assets/icons/MoreSmallListVert.svg)），单击&#x200B;**[!UICONTROL Rename]**，指定活动的名称，然后单击&#x200B;**[!UICONTROL Save]**。

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

1. 选择位置。

   单击[!UICONTROL Select Location]框时，将显示可用位置列表。 选择其中一个位置。

   您还可以输入一个未在此处列出的位置。如果尚未在页面上创建或查看 mbox，则可以使用此方法。键入位置的名称。输入尚不存在的位置时务必要仔细。如果位置拼写或大小写与调用 mbox 时使用的拼写和大小写不匹配，则活动将无法交付。手动输入的位置将保存到可用位置列表中。 下次尝试选择手动输入的位置时，该活动的[!UICONTROL Select Location]下拉列表中会显示该位置。

   >[!NOTE]
   >
   >在活动创建期间创建手动输入的位置不会自动创建新位置。 位置名称仅保存在活动的上下文中。 当存在内容投放调用时会创建位置。 在创建位置之后，还可用于其他活动、创建受众等。 从可用位置的下拉列表中。

1. 单击&#x200B;**[!UICONTROL Add Audience Refinements]**，为此活动选择一个或多个[受众](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)，然后单击&#x200B;**[!UICONTROL Done]**。

   在[!UICONTROL Form-based Experience Composer]中，细化已替换为完整的受众功能。 现有活动的细化已迁移到[仅限活动的受众](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)。

1. 选择要在该位置中显示的内容类型。

1. 为选定的内容类型指定内容。

   **更改 HTML 产品建议：**&#x200B;选择一个 HTML 产品建议。

   **更改图像产品建议：**&#x200B;选择 Target 内容库中保存的某个图像。

   您还可以添加指向图像的链接（点进链接、目标链接、登陆链接，等等）。

   1. 单击 [!UICONTROL Change Image Offer]。
   1. 选择所需的图像，然后单击[!UICONTROL Edit Links]。
   1. 在您的网站上指定所需的URL或页面，然后单击[!UICONTROL Update]。

   **更改 JSON 产品建议：**&#x200B;选择一个 JSON 产品建议。

   **更改体验片段：**&#x200B;选择一个体验片段。 有关详细信息，请参阅[体验片段](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)。

   **更改重定向选件：**&#x200B;选择一个重定向选件。 有关详细信息，请参阅[创建重定向选件](/help/main/c-experiences/c-manage-content/offer-redirect.md)。

   **更改远程选件：**&#x200B;选择一个远程选件。 有关详细信息，请参阅[创建远程选件](/help/main/c-experiences/c-manage-content/about-remote-offers.md)。

   **创建 HTML 产品建议:**

   1. 单击[!UICONTROL Offers]，然后选择[!UICONTROL Code Offers]选项卡。
   1. 单击[!UICONTROL Create] > [!UICONTROL HTML Offer]。
   1. 键入产品建议名称。
   1. 在代码框中键入或粘贴您的 HTML 代码。
   1. 单击 [!UICONTROL Save]。

   **创建 JSON 产品建议：**

   1. 单击[!UICONTROL Offers]，然后选择[!UICONTROL Code Offers]选项卡。
   1. 单击[!UICONTROL Create] > [!UICONTROL JSON Offer]。
   1. 键入产品建议名称。
   1. 在代码框中键入或粘贴您的 JSON 代码。
   1. 单击 [!UICONTROL Save]。

   **添加推荐：**

   对于Recommendations活动，“内容”下拉列表提供了[!UICONTROL Add Recommendation]选项。 单击&#x200B;**[!UICONTROL Add Recommendation]**，然后选择页面类型。 接下来，按照界面中定义的常规步骤[创建“推荐”活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)。

   在基于表单的体验编辑器中选择推荐标准时，现在有一个指向所选标准卡片的直接链接，以便您快速方便地对标准进行编辑。

   从[!DNL Target]三步引导式工作流的[!UICONTROL Targeting]页面：

   **添加优惠决策：**

   将在[!DNL Adobe Journey Optimizer] (AJO)中创建的优惠添加到[!DNL Adobe Target]活动，以使用offer decisioning向网站或移动网站上的访客展示最佳的动态优惠和体验。 此选项仅适用于手动[!UICONTROL A/B Test]和[!UICONTROL Experience Targeting] (XT)活动。

   有关详细信息，请参阅[使用优惠决策](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)。

1. （可选，适用于[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization]和[!UICONTROL Experience Targeting]活动）要对其他位置重复执行此流程，请单击&#x200B;**[!UICONTROL Add Location]**&#x200B;并配置位置和内容。
1. 单击&#x200B;**[!UICONTROL Next]**，然后为您选择的活动类型完成常规的活动创建步骤。

* [创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [创建“推荐”活动](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## 培训视频：基于表单的编辑器![教程徽章](/help/main/assets/tutorial.png)

以下视频演示了基于表单的编辑器。

* 使用基于表单的体验编辑器创建活动
* 了解何时使用基于表单的体验编辑器，何时使用可视化体验编辑器
* 使用细化来定位位置

>[!VIDEO](https://video.tv.adobe.com/v/17390)
