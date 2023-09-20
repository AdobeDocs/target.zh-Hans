---
keywords: 优先级;体验创建;优先级;体验;受众;切换体验;可视化体验编辑器
description: 了解访客如何在中切换体验 [!DNL Adobe Target] [!UICONTROL 体验定位] (XT)活动随着其用户档案的发展而发展。
title: 访客能否在 [!UICONTROL 体验定位] 活动？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 44%

---

# 在中切换体验 [!UICONTROL 体验定位]

替换为 [!UICONTROL 体验定位]，您可以控制访客在其配置文件演变时看到的体验。

以下列表介绍了一些访客配置文件可以演变的情况，您可能希望根据这些更改呈现不同的内容：

| 场景 | 详细信息 |
|--- |--- |
| 地理位置 | 访客出差或外出旅游时，可能会从不同的地理位置访问您的网站或移动设备应用程序。 |
| 客户状态 | 访客尚未创建帐户或购买产品时，可能会将其视为潜在客户。 |
| 类别亲和力 | 此 [类别亲和力](/help/main/c-target/c-visitor-profile/category-affinity.md) 中的功能 [!DNL Target] 自动捕获访客查看的类别，然后计算访客对该类别的喜爱程度，以便进行定位。 例如，查看了您网站上有关特定主题的多篇文章的访客，将会看到与该主题相关的内容。 |
| 每周时间 | 随着周末临近，您可能想要向访客显示与电影、美食或其他类型的娱乐活动有关的内容。 |

要在中使用这些功能 [!DNL Target]，在使用时请务必了解以下信息 [!UICONTROL 体验定位] 活动：

* **优先级是由体验的顺序（从上到下）来控制的。** 如果访客符合两个以上受众的条件，则该访客会从更高优先级的体验中接收内容。
* **访客可在中的体验之间切换 [!UICONTROL 体验定位] 活动（如果他们开始符合具有较高优先级的体验的受众的条件）。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客切换到了体验 B（德国访客）。

  ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **如果访客不再符合当前受众的资格条件，但开始符合较低优先级的体验，则访客还会在体验之间切换。**
* **如果访客不再符合其当前体验的资格条件，并且没有资格获得其他体验，他们将看到默认内容。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了法国并在法国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在法国访问您的网站后，该访客将停留在原始体验中。

  ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **定位到“所有访客”的体验可以用作中的最后一个体验 [!UICONTROL 体验定位] 活动，用于“捕获”任何不符合任何其他体验条件的访客。 如果定位到“所有访客”的体验不是顺序中的最后一个，则仍会评估列出低于此体验的其他定位体验。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客将停留在体验A（美国访客）中。

  ![优先级：美国 > 所有访客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  如果这不是您所期望的结果，您可以创建一个新受众，并将其明确定义为与目标受众相反的受众，如以下示例所示：

  ![优先级：美国 > 非美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **具有单一体验 [!UICONTROL 体验定位] 活动，即使用户不再符合体验的受众条件，访客仍会保留在该体验中。**

  如果这不是您所期望的结果，您可以再创建一个体验，并将其定位到相反的受众（例如，与“美国”相反的“非美国”）。

  作为另一个选项，您可以创建 [!UICONTROL A/B测试] 活动以100%流量分配定位到所需的受众，如下所示：

  ![优先级：一个体验](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **[!DNL Target]体验的优先级是由体验在 UI 中的显示顺序（从上到下）来定义的。**

  访客可能会符合多个受众的条件，在这种情况下，记住这一点十分重要。例如，如果您有两个体验：一个针对“美国”，一个针对“纽约”，则位于纽约的访客将同时符合这两个受众的资格。 因此，您必须确保先定义“纽约”体验，然后再定义“美国”体验。 [!DNL Target] UI。 这种做法可确保更具针对性的“纽约”体验具有更高的优先级，如以下示例所示：

  ![优先级：纽约 > 美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
