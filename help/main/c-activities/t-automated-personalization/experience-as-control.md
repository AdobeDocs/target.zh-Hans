---
keywords: 体验;控制;自动个性化;自动锁定
description: 了解在[!DNL Adobe Target]中创建[!UICONTROL Automated Personalization] (AP)或[!UICONTROL 自动定位]活动时，如何选择要用作控制的体验。
title: 如何在[!UICONTROL Automated Personalization]活动中使用特定体验作为控制？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: 'https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 3%
---
# 选择控制体验 {#experience-as-control}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何选择&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;或&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动的控制，以及使用特定体验作为控制时要考虑的事项。

>[!ENDSHADEBOX]

在创建[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP)或[**[!UICONTROL 自动定位]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT)活动时，您可以选择随机提供的体验或特定体验作为控制。 控制流量会根据活动中配置的流量分配百分比路由到相关体验，以便您可以根据控制流量评估个性化流量的性能报表。

在手动&#x200B;**[!UICONTROL A/B测试]**&#x200B;中，您可以更改显示为控制的报表，并根据该体验计算提升度，因为无论控制是什么，都会随机向所有体验提供流量。 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;和&#x200B;**[!UICONTROL 自动定位]**&#x200B;活动中，控制确实会影响访客流量的提供方式，因此请仔细选择它。

控件有两个可用选项：

* **随机提供的体验：**&#x200B;流量的控制百分比随机提供给活动中的所有体验，而不考虑访客的配置文件。 它在您的活动中像&#x200B;**[!UICONTROL A/B测试]**&#x200B;一样工作，它显示每个体验或选件的非个性化转化率，这有助于您分析结果。

* **特定体验：**&#x200B;流量的控制百分比仅随机为该一个体验提供服务。 此选项允许您将[!DNL Target]个性化模型提供的流量与您定义的特定体验（例如，您的默认主页）进行比较。

## 注意事项 {#considerations}

在使用特定体验作为控制时，请记住以下几点：

* 不建议更改已处于实时状态的活动中的控制体验。 所选的最新控制体验会在报表中进行命名，即使较旧的报表基于其他体验也是如此。

* 不建议删除控制体验。

* 不建议向使用特定体验作为控制的实时活动中添加许多新选件或体验。

* 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中，不建议包含对控制体验的定位，这可能会进一步限制能够查看该体验的用户。

* 在&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;活动中，如果选择了特定体验，则提升度和置信度信息在选件级别报表中&#x200B;*不*&#x200B;可用。 这是因为将特定体验的转化率与选件的转化率进行比较由于单位不同，不合逻辑。 提升度和置信度信息可在活动的整体“目标”与“控制”流量级别使用，如果选择“随机”作为控制，则可在所有级别使用。 无论选择哪种类型的控制，**[!UICONTROL 自动定位]**&#x200B;活动中的可用信息都是相同的。

* 当您选择特定体验作为控制时，所有控制流量都会流向一个体验或一组选件。 对于随机控制，控制流量会根据活动中的体验或选件数进行拆分。 因此，对于具有特定体验的控制项，您通常不需要那么多的流量。 分配 10% 的流量即可。

* 如果您对使用特定体验作为控制的实时活动执行以下操作之一，则控制会自动重置为随机提供的体验（而不是之前选择的特定体验）：

  * 删除体验。
  * 删除位置或选件（仅限&#x200B;**[!UICONTROL Automated Personalization]**）。
  * 通过删除重复的选件或通过排除组（仅限&#x200B;**[!UICONTROL Automated Personalization]**）手动排除体验。


## 指定特定体验作为控制 {#specify-control}

将特定体验指定为控制可为个性化流量提供一个在活动报表中与之进行比较的已知体验，例如您当前的默认体验。

1. 创建或编辑[**[!UICONTROL Automated Personalization ]**活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)或[**[!UICONTROL 自动定位]**&#x200B;活动](/help/main/c-activities/auto-target/create-auto-target.md#create-auto-target-activity)时，根据需要配置体验。

1. 在&#x200B;**[!UICONTROL 定位]**&#x200B;页面（三步引导式工作流的步骤2）上，单击控制体验以在右侧窗格中显示&#x200B;**[!UICONTROL 控制]**&#x200B;选项。

   ![控制面板](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. 从&#x200B;**[!UICONTROL 控制]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL 随机体验]**&#x200B;或选择要用作控制的体验。

1. 单击&#x200B;**[!UICONTROL 流量分配]**&#x200B;控制，然后为控制体验和其他体验指定流量分配。

   ![流量分配边栏](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   对于特定体验控制，建议分配 10% 到 30% 的流量。

1. 继续使用&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面。

活动上线后，其报表会将个性化流量与您选择的控制体验进行比较。 在更改实时活动之前，请查看[注意事项](#considerations)，因为某些更改会自动将控制重置为随机提供的体验。
