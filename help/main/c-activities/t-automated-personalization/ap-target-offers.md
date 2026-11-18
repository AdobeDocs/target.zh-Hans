---
keywords: 自动个性化；选件；定位；受众；定位规则；定位
description: 了解如何使用[!UICONTROL Automated Personalization] (AP)活动将单个选件定位到特定受众。
title: 如何定位[!UICONTROL Automated Personalization]选件？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 8%
---
# 定位[!UICONTROL Automated Personalization]选件 {#target-ap-offers}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中将单个选件定位到特定受众。

>[!ENDSHADEBOX]

在[!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP)活动中，定位规则允许您将选件限制为特定受众，以便只有属于这些受众的访客才能看到该选件。 请谨慎使用定位规则，并且仅在业务需求需要时使用，因为它们会减少访客有资格查看的选件数量，可能会降低[!DNL Target]个性化模型的有效性。

例如，以具有三个选件的AP活动为例。 选件1有一个定位规则，该规则限制仅向受众A显示该选件。两个访客看到此活动。

| | 访客 1 | 访客 2 |
|--- |--- |--- |
| 受众资格筛选 | 受众 A | 受众 B |
| 选件1 [!DNL Target]个性化模型分数 | 90 | 90 |
| 选件2 [!DNL Target]个性化模型分数 | 50 | 70 |
| 选件3 [!DNL Target]个性化模型分数 | 80 | 60 |

访客1有资格成为受众A的一部分，因此该访客会看到得分最高的选件1。 访客2不是受众A的一部分，因此该访客会看到选件2，即使最高分是选件1。

## 设置定位规则 {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

受众定位规则控制哪些访客可以查看每个选件，这让您能够满足特定的业务需求，例如为客户区段保留选件。 每个规则都会缩小个性化模型的选择范围，因此规则仅适用于需要它们的选件。

1. 创建或编辑包含要定位的选件的[Automated Personalization活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)。

   您最多可以设置 50 个位置，每个位置最多可以设置 250 个产品建议。

1. 在&#x200B;**[!UICONTROL 可视化体验编辑器]**&#x200B;中设置活动的选件后，单击&#x200B;**[!UICONTROL 管理内容]**&#x200B;图标（![管理内容图标](/help/main/assets/icons/Experience.svg)）。 此时将显示&#x200B;**[!UICONTROL 管理内容]**&#x200B;对话框。

   ![管理内容图标](../assets/ap-offers-1.png)

1. 单击&#x200B;**[!UICONTROL 选件]**&#x200B;选项卡。

1. 选择要定位的选件，然后选择有资格查看这些选件的受众。

   * 要为单个选件设置定位，请单击选件旁边的更多信息（![更多信息图标](/help/main/assets/icons/MoreSmallList.svg) ）图标，然后单击&#x200B;**[!UICONTROL 目标受众]**&#x200B;以显示&#x200B;**[!UICONTROL 添加受众]**&#x200B;对话框。
   * 要为多个选件设置定位，请选中选件对应的复选框，然后单击列表底部显示的&#x200B;**[!UICONTROL 定位受众]**&#x200B;链接。

   ![管理内容图标](../assets/ap-offers-2.png)

1. 在&#x200B;**[!UICONTROL 添加受众]**&#x200B;对话框中，选择选件的受众，然后单击&#x200B;**[!UICONTROL 分配受众]**&#x200B;以返回&#x200B;**[!UICONTROL 管理内容]**&#x200B;对话框。

   >[!NOTE]
   >
   >您可以将多个受众与现有受众相结合，以创建按需组合受众，而不是创建新受众。 有关更多信息，请参阅[合并多个受众](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)。

1. 单击&#x200B;**[!UICONTROL 完成]**。

现在，定位规则适用于选定选件，因此只有属于已分配受众的访客才能看到这些选件。
