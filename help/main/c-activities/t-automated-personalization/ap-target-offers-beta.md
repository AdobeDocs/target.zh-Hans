---
keywords: 自动个性化；选件；定位；受众；定位规则；定位
description: 了解如何使用[!UICONTROL Automated Personalization] (AP)活动将各个选件定位到特定受众。
title: 如何定位[!UICONTROL Automated Personalization]优惠？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
hide: true
hidefromtoc: true
exl-id: 2897c4d1-116d-483c-8fc0-64857b9cbdaf
source-git-commit: 2c10ec521ceed1901ef8c3f95eb11654a7182590
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 19%

---

# 目标[!UICONTROL Automated Personalization]优惠

在[!DNL Adobe Target] [!DNL Automated Personalization] (AP)活动中，您可以将选件定位到特定受众。

使用此功能可减少特定访客有资格查看的产品建议数量。例如，假定一个[!UICONTROL Automated Personalization]活动有三个选件。 选件1有一个定位规则，该规则限制仅向受众A显示该选件。有两个访客看到了此活动。

| | 访客 1 | 访客 2 |
|--- |--- |--- |
| 受众资格 | 受众 A | 受众 B |
| 选件 1 的 Target 个性化模型得分 | 90 | 90 |
| 选件 2 的 Target 个性化模型得分 | 50 | 70 |
| 选件 3 的 Target 个性化模型得分 | 80 | 60 |

在这种情况下，访客1会看到选件1（因为该访客符合受众A的条件），这是该访客的最高得分。 但是，访客2会看到选件2，尽管得分最高的是选件1，因为访客2不是受众A的一部分。此示例演示了为何应谨慎使用定位规则以满足业务需求。 添加这些规则可能会降低[!DNL Target]个性化模型的有效性。

## 设置定位规则

1. 创建或编辑包含要定位的选件的[Automated Personalization活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在[!UICONTROL Visual Experience Composer]中设置活动的选件后，单击&#x200B;**[!UICONTROL Manage Content]**&#x200B;图标（ ![管理内容图标](/help/main/assets/icons/Experience.svg)）。

   此时将显示[!UICONTROL Manage Content]对话框。

1. 单击&#x200B;**[!UICONTROL Offers]**&#x200B;选项卡。

1. 选择所需的选件，然后选择有资格查看该选件的受众。

   要为单个选件设置定位，请单击所需选件旁边的更多信息（![更多信息图标](/help/main/assets/icons/MoreSmallList.svg) ）图标，然后单击&#x200B;**[!UICONTROL Target Audience]**&#x200B;以显示[!UICONTROL Add Audiences]对话框。

   要为多个选件设置定位，请选中所需选件的复选框，然后单击列表底部显示的&#x200B;**[!UICONTROL Target Audience]**&#x200B;链接。

1. 在[!UICONTROL Add Audiences]对话框中，为选件选择所需的受众，然后单击&#x200B;**[!UICONTROL Assign Audience]**&#x200B;以返回到[!UICONTROL Manage Content]对话框。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众以创建按需合并受众，而不是创建新受众。 有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击 **[!UICONTROL Done]**。

>[!NOTE]
>
>您最多可以设置 50 个位置，每个位置最多可以设置 250 个产品建议。
