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
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# ![PREMIUM](/help/assets/premium.png) Target 自动个性化选件{#target-automated-personalization-offers}

在自动个性化活动中，您可以将选件定位到特定的受众。

使用此功能可减少特定访客有资格查看的选件数量。例如，以含有三个选件的自动个性化 (AP) 活动为例。选件 1 有一个定位规则，该规则限制仅向受众 A 显示该选件。有两位访客看到了此 AP 活动。

|  | 访客 1 | 访客 2 |
|--- |--- |--- |
| 受众资格 | 受众 A | 受众 B |
| 选件 1 的 Target 个性化模型得分 | 90 | 90 |
| 选件 2 的 Target 个性化模型得分 | 50 | 70 |
| 选件 3 的 Target 个性化模型得分 | 80 | 60 |

在此情景中，访客 1 将看到选件 1（因为他/她符合成为受众 A 的条件），这是该访客获得的最高分数。但是，访客 2 将看到选件 2，即便他/她的最高分数符合选件 1，这是因为访客 2 不是受众 A 的一员。此示例演示了为何应该谨慎地使用定位规则来满足业务需求。添加这些规则可能会降低 Target 个性化模型的有效性。

## 设置定位规则

1. 创建包含要定位的选件的自动个性化活动。
1. 在可视化体验编辑器中设置活动的选件后，单击**[!UICONTROL 内容]**。

   此时将打开“管理内容”对话框。

   ![](assets/ap_content.png)

   >[!NOTE]
   >
   >您最多可以设置 50 个位置，每个位置最多可以设置 250 个选件。

1. 在**[!UICONTROL 内容]**列中，选择选件，单击**[!UICONTROL 定位]**，然后选择有资格查看该选件的受众。

   仅会向选定的受众显示该选件。

   >[!NOTE]
   >
   >除了选择现有受众之外，您还可以合并多个受众来创建临时组合受众，而不是创建新受众。有关更多信息，请参阅[合并多个受众](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击**[!UICONTROL 完成]**。
