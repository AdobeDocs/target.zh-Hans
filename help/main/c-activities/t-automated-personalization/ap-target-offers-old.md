---
keywords: 自动个性化；选件；定位；受众；定位规则；定位
description: 了解如何通过在 [!DNL Adobe Target]中使用[!UICONTROL Automated Personalization] (AP)活动将单个选件定位到特定受众。
title: 如何定位[!UICONTROL Automated Personalization]选件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 26%

---

# 定位[!UICONTROL Automated Personalization]选件

在[!DNL Adobe Target] [!DNL Automated Personalization] (AP)活动中，您可以将选件定位到特定受众。

使用此功能可减少特定访客有资格查看的产品建议数量。 例如，考虑具有三个选件的[!UICONTROL Automated Personalization]活动。 选件1有一个定位规则，该规则限制仅向受众A显示该选件。有两个访客看到了此活动。

| | 访客 1 | 访客 2 |
|--- |--- |--- |
| 受众资格筛选 | 受众 A | 受众 B |
| 选件 1 的 Target 个性化模型得分 | 90 | 90 |
| 选件 2 的 Target 个性化模型得分 | 50 | 70 |
| 选件 3 的 Target 个性化模型得分 | 80 | 60 |

在这种情况下，访客1会看到选件1（因为该访客符合受众A的条件），这是该访客的最高得分。 但是，访客2会看到选件2，尽管得分最高的是选件1，因为访客2不是受众A的一部分。此示例演示了为何应谨慎使用定位规则以满足业务需求。 添加这些规则可能会降低[!DNL Target]个性化模型的有效性。

## 设置定位规则

1. 创建包含要定位的选件的[Automated Personalization活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在[!UICONTROL 可视化体验编辑器]中设置活动的选件后，单击&#x200B;**[!UICONTROL 管理内容]**。

   ![管理内容](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   此时将显示[!UICONTROL 管理内容]对话框。

1. 单击&#x200B;**[!UICONTROL 选件]**&#x200B;选项卡。

   ![“产品建议”页面](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 选择所需的选件，然后选择有资格查看该选件的受众。

   要为单个选件设置定位，请将鼠标悬停在所需选件上，然后单击&#x200B;**[!UICONTROL 定位]**&#x200B;图标。

   要为多个选件设置定位，请选中所需选件的复选框，然后单击列表右上角显示的&#x200B;**[!UICONTROL 定位]**&#x200B;图标。

1. 在[!UICONTROL 选择受众]对话框中，为选件选择所需的受众，然后单击&#x200B;**[!UICONTROL 完成]**&#x200B;以返回[!UICONTROL 管理内容]对话框。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。 有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击&#x200B;**[!UICONTROL 完成]**。

>[!NOTE]
>
>您最多可以设置 50 个位置，每个位置最多可以设置 250 个产品建议。
