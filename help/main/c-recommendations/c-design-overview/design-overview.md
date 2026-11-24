---
keywords: 推荐设计;模板;创建设计;交付;输出
description: 了解如何使用Adobe [!DNL Target]推荐中的设计来定义推荐在页面上的显示方式（1X4、1X6、2X2等）。
title: 设计入门
feature: Recommendations
exl-id: 348b1d77-49c9-4a6b-ba85-7ba051713d5b
TQID: 'https://experienceleague.adobe.com/08jboJLkp6MhgXiISjkVzh2kVze5DRrxO8BbQBFLeA4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: f9c9c7b2b78ec020fcabae420686b8955e350a0e
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%
---
# 设计入门 {#design-overview}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解设计如何定义[!DNL Adobe Target Recommendations]中推荐的布局和格式。

>[!ENDSHADEBOX]

[!DNL Adobe Target Recommendations]中的设计定义推荐在页面上的显示方式。 设计可定义推荐的布局和格式。

[!DNL Recommendations]附带几个默认（预建）设计，也可以创建自定义设计。 有关详细信息，请参阅[创建设计](/help/main/c-recommendations/c-design-overview/create-design.md)。

[!DNL Target]可以提供推荐的完整外观，如下图所示。 设计中可以包含 HTML、JavaScript 和 CSS。 此设计称为4 x 1设计：一行四个空格。

![标题为“其他有趣的活动”的4 x 1设计示例，其中四个项目分别显示照片、名称、价格、评分和距离](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

[!DNL Target]还可以将推荐作为JSON对象发送，这些对象可用于电子邮件、物联网(IoT)设备、控制台或语音用例（Amazon Alexa或Google Home）。

设计确定：

* 推荐中显示的项目数
* 项目的显示方式（在行、列、网格或表中）
* 访客是只能看到指定数量的项目，还是可以滚动浏览多个项目
