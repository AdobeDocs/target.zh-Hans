---
keywords: 定位；analytics；跟踪服务器；analytics for target；a4t
description: 了解如何在[!DNL Adobe Target]中将活动配置为使用[!DNL Adobe Analytics]作为报表源(A4T)。
title: 如何在[!DNL Target]中使用[!DNL Analytics]数据？
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# 使用[!DNL Adobe Analytics]数据 {#create-a4t}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何配置活动以使用[!DNL Adobe Analytics]作为报表源(A4T)，开始之前要准备什么，以及如何选择活动的目标。

>[!ENDSHADEBOX]

Analytics for Target (A4T)使用数据和量度[!DNL Adobe Analytics]测量[!DNL Adobe Target]活动的结果。 要使用A4T，请配置该活动，以使[!DNL Analytics]作为其报表源。 有关将[!DNL Analytics]设置为[!DNL Target]的数据源的详细信息，请参阅[Adobe Analytics作为Adobe Target的报表Source](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

## 开始之前 {#before-you-begin}

>[!NOTE]
>
>当您的[!DNL Adobe Experience Cloud]帐户同时链接到[!DNL Analytics]和[!DNL Target]时，**[!UICONTROL Adobe Analytics]**&#x200B;选项可用，即使尚未为您的帐户设置[!DNL Target]和[!DNL Analytics]之间的集成。

在创建活动之前，确立其目标，例如提高每位访客带来的收入(RPV)或增加购物车的点击次数。 然后选择用于衡量此目标的最终成功量度。 可随时在[!DNL Analytics]中选择其他量度，但您仍必须指定该测试预计会影响的一个量度。

## 选择Analytics作为报表源 {#select-reporting-source}

>[!NOTE]
>
>如果您使用at.js版本0.9.1或更高版本，则在创建使用[!DNL Adobe Analytics]作为报表源的活动时，无需指定跟踪服务器。 at.js库自动将跟踪服务器值发送到[!DNL Target]。 **[!UICONTROL 目标和设置]**&#x200B;页面上的&#x200B;**[!UICONTROL 跟踪服务器]**&#x200B;字段可以保留为空。

已在活动的&#x200B;**[!UICONTROL 目标和设置]**&#x200B;页面上选择报表源。 在此页面上，您选择了一个[!DNL Analytics]公司和接收[!DNL Target]活动数据的报表包，并验证跟踪服务器。

➡️有关步骤、报表包要求和跟踪服务器的详细信息，请参阅[报告Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source)。

当[!DNL Analytics]为报表源时，该活动不提供用于设置报表受众的选项。 [!DNL Analytics]区段在[!DNL Target] **[!UICONTROL 活动]**&#x200B;报表中可用。

## 设置活动的目标 {#set-goal}

每个活动都需要成功量度作为目标。 目标是表示活动成功的转化活动。 可以使用[!DNL Analytics]量度选择器中可用的任何量度。 最佳实践是，绝不要在没有以特定方式改进的目标的情况下运行测试。

设置目标不会阻止您使用其他量度来评估测试结果。 但是，目标指明了您希望通过测试改进的方面。

访客完成目标后，该访客将不再包含在活动中。 如果该访客在完成活动后重新进入该活动，则将被计为新访客。
