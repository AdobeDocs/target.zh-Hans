---
keywords: 时间范围;开始日期;结束日期;开始/结束日期;定位时间计划;星期分开;日期分开;分开
description: 了解如何使用开始和结束日期及时间来定位在特定时间段内访问您网站的用户。
title: 我能否定位在特定时间访问我的网站的访客？
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 35%

---

# [!UICONTROL Time Frame]

您可以在[!DNL Adobe Target]中添加开始和结束日期及时间，以定位在特定时间范围内访问您网站的用户。 您也可以设置“将星期与日期分开”选项来为受众定位创建循环模式。

例如，使用[组合即席受众功能](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)，您可以定位黑色星期五之前的三天内特定内容的低消费人群，以及黑色星期五之后其他内容的低消费人群。

1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 命名受众并添加可选描述。
1. 将&#x200B;**[!UICONTROL Time Frame]**&#x200B;拖放到受众生成器窗格中。

   ![target_timeframe_dialog图像](assets/target_timeframe_dialog.png)

1. 指定受众的[!UICONTROL Start]和[!UICONTROL End]日期和时间。

   将开始日期留空，可根据活动的计划开始定位。将结束日期留空，可一直定位到活动的结束日期和时间。

   您也可以将开始日期和结束日期都留空。通过此功能，您可以在多个活动中使用相同的受众（不制作受众的副本），同时在活动级别控制开始和结束日期。

   >[!NOTE]
   >
   >请考虑以下事项：
   >
   >* 开始/结束日期的时区显示为 GMT +/- NN:NN，其中 NN:NN 是与 GMT 的时间差，它反映的是帐户级别的时区，而不是访客所在时区。例如，加利福尼亚的时区会显示为 GMT -08:00。
   >
   >* [!DNL Target]时间受众未考虑夏令时(DST)更改。 您必须手动重新保存受众以考虑DST更改。

1. （视情况而定）单击&#x200B;**[!UICONTROL Set frequency]**&#x200B;以设置循环模式，包括星期几和具体时间。

   ![将星期与日期分开](assets/week_and_day_parting.png)

   例如，您可以使用[!UICONTROL Frequency]选项，仅在呼叫中心人员配备的日期和时间向访客显示“立即聊天”选项。

   选择一周中的一天或多天，然后设置开始时间和结束时间。单击&#x200B;**[!UICONTROL Add frequency]**&#x200B;以根据需要指定其他模式。

   >[!NOTE]
   >
   >[!UICONTROL Week and Day Parting]的时区显示为GMT +/- NN：NN，其中NN：NN是与GMT的时间差，它反映的是帐户级别时区，而不是访客所在时区。 例如，加利福尼亚的太平洋夏令时时时区会显示为GMT -07:00。

1. （可选）为受众设置其他规则。

   如果需要，您可以对每个规则重复步骤5。

1. 单击 **[!UICONTROL Done]**。

## 培训视频：创建受众![概述徽章](/help/main/assets/overview.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
