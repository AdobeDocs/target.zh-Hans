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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

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

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![管理内容](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   此时将打开“管理内容”对话框。

1. 单击“选件”选项卡。

   ![选件页面](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. 选择所需的选件，然后选择您想要查看该优惠的受众。

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击&#x200B;**[!UICONTROL 完成]**。

>[!NOTE]
>
>您最多可以设置 50 个位置，每个位置最多可以设置 250 个选件。
