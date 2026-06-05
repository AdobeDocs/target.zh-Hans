---
keywords: 自动个性化；选件；定位；受众；定位规则；定位
description: 了解如何使用[!UICONTROL Automated Personalization] (AP)活动将单个选件定位到特定受众。
title: 如何定位[!UICONTROL Automated Personalization]选件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 18%

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

1. 创建或编辑包含要定位的选件的[Automated Personalization活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)。
1. 在[!UICONTROL 可视化体验编辑器]中设置活动的选件后，单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）。

   此时将显示[!UICONTROL 管理内容]对话框。

1. 单击&#x200B;**[!UICONTROL 选件]**&#x200B;选项卡。

1. 选择所需的选件，然后选择有资格查看该选件的受众。

   要为单个选件设置定位，请单击所需选件旁边的更多信息(![更多信息(](/help/main/assets/icons/MoreSmallList.svg) )图标，然后单击&#x200B;**[!UICONTROL 目标受众]**&#x200B;以显示[!UICONTROL 添加受众]对话框。

   要为多个选件设置定位，请选中所需选件的复选框，然后单击列表底部显示的&#x200B;**[!UICONTROL 定位受众]**&#x200B;链接。

1. 在[!UICONTROL 添加受众]对话框中，为选件选择所需的受众，然后单击&#x200B;**[!UICONTROL 分配受众]**&#x200B;以返回[!UICONTROL 管理内容]对话框。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众以创建按需合并受众，而不是创建新受众。 有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击&#x200B;**[!UICONTROL 完成]**。

>[!NOTE]
>
>您最多可以设置 50 个位置，每个位置最多可以设置 250 个产品建议。
