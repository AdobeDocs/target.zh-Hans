---
description: 在自动个性化活动中，您可以将选件定位到特定的受众。
seo-description: 在自动个性化活动中，您可以将选件定位到特定的受众。
seo-title: Target 自动个性化选件
solution: Target,Analytics
title: Target 自动个性化选件
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
translation-type: tm+mt
source-git-commit: 7b7f61efde2c72e6054dd8f08fbde2a395b6447c

---


# ![PREMIUM](/help/assets/premium.png) Target 自动个性化选件{#target-automated-personalization-offers}

在自动个性化(AP)活动中，您可以将选件定向到特定受众。

使用此功能可减少特定访客有资格查看的选件数量。例如，假定具有三个选件的AP活动。优惠酬宾的目标规则限制了对受众A的披露。两个访客看到此AP活动。

|  | 访客 1 | 访客 2 |
|--- |--- |--- |
| 受众资格 | 受众 A | 受众 B |
| 选件 1 的 Target 个性化模型得分 | 90 | 90 |
| 选件 2 的 Target 个性化模型得分 | 50 | 70 |
| 选件 3 的 Target 个性化模型得分 | 80 | 60 |

在此情景中，访客 1 将看到选件 1（因为他/她符合成为受众 A 的条件），这是该访客获得的最高分数。但是，访客 2 将看到选件 2，即便他/她的最高分数符合选件 1，这是因为访客 2 不是受众 A 的一员。此示例演示了为何应该谨慎地使用定位规则来满足业务需求。添加这些规则可能会降低 Target 个性化模型的有效性。

## 设置定位规则

1. 创建包含您想要定位的选件的 [自动个性化活动](/help/c-activities/t-automated-personalization/create-ap-activity.md) 。
1. 在Visual Experience Composer中设置活动的选件后，单击 **[!UICONTROL “管理内容]**”。

   ![管理内容](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   此时将打开“管理内容”对话框。

1. 单击“选件”选项卡。

   ![选件页面](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 选择所需的选件，然后选择您想要查看该优惠的受众。

   要为单个选件设置定位，请将鼠标悬停在所需选件上方，然后单击 **[!UICONTORL 定位]** 图标。

   要为多个选件设置定位，请选择所需选件的复选框，然后单击列表右上角显示[!UICONTROL 的**定位] 图标。

1. 在 [!UICONTROL “选择受众] ”对话框中，为选件选择所需的受众，然后单击 **[!UICONTROL 完成]** 以返回 [!UICONTROL 到“管理内容] ”对话框。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击 **[!UICONTROL 完成]**。

>[!NOTE]
>
>您最多可以设置 50 个位置，每个位置最多可以设置 250 个选件。
