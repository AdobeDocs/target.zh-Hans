---
keywords: 优先级;体验创建;优先级;体验;受众;切换体验;可视化体验编辑器
description: 了解访客如何在 [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT)活动中的体验之间随着其个人资料的发展而切换。
title: 访客能否在[!UICONTROL Experience Targeting]活动中切换体验？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 43%

---

# 在[!UICONTROL Experience Targeting]中切换体验

通过[!UICONTROL Experience Targeting]，您可以控制访客在其配置文件演变时看到的体验。

以下列表介绍了一些访客配置文件可以演变的情况，您可能希望根据这些更改呈现不同的内容：

| 场景 | 详细信息 |
|--- |--- |
| 地理位置 | 访客出差或外出旅游时，可能会从不同的地理位置访问您的网站或移动设备应用程序。 |
| 客户状态 | 访客尚未创建帐户或购买产品时，可能会将其视为潜在客户。 |
| 类别亲和力 | [中的](/help/main/c-target/c-visitor-profile/category-affinity.md)类别亲和度[!DNL Target]功能会自动捕获访客查看的类别，然后计算访客对该类别的喜爱程度，以便进行定位。 例如，查看了您网站上有关特定主题的多篇文章的访客，将会看到与该主题相关的内容。 |
| 每周时间 | 随着周末临近，您可能想要向访客显示与电影、美食或其他类型的娱乐活动有关的内容。 |

要在[!DNL Target]中使用这些功能，在使用[!UICONTROL Experience Targeting]活动时请务必了解以下信息：

* **优先级是由体验的顺序（从上到下）来控制的。**&#x200B;如果访客符合两个以上受众的条件，则该访客会从更高优先级的体验中接收内容。
* **如果访客开始符合具有较高优先级的体验的受众资格，则访客将在[!UICONTROL Experience Targeting]活动中的体验之间切换。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客切换到了体验 B（德国访客）。

  ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **如果访客停止符合当前受众的资格条件，但开始符合较低优先级的体验，则访客也会在体验之间切换。**
* **如果访客不再符合其当前体验的资格条件，并且没有资格获得其他体验，则会看到默认内容。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了法国并在法国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在法国访问您的网站后，该访客将停留在原始体验中。

  ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **定位到“所有访客”的体验可以用作[!UICONTROL Experience Targeting]活动中的最后一个体验，以“捕获”所有不符合任何其他体验条件的访客。 如果定位到“所有访客”的体验不是顺序中的最后一个体验，则仍会评估列出低于此体验的其他目标体验。**

  例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客将停留在体验A（美国访客）中。

  ![优先级：美国 > 所有访客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  如果这不是您所期望的结果，您可以创建一个新受众，并将其明确定义为与目标受众相反的受众，如以下示例所示：

  ![优先级：美国 > 非美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **如果只有一个体验[!UICONTROL Experience Targeting]活动，则即使访客不再符合体验的受众条件，访客仍会保留在该体验中。**

  如果这不是您所期望的结果，您可以再创建一个体验，并将其定位到相反的受众（例如，与“美国”相反的“非美国”）。

  作为另一个选项，您可以创建一个[!UICONTROL A/B Test]活动，并将其定位到分配了100%流量的所需受众，如下所示：

  ![优先级：一个体验](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **体验的优先级是由体验在[!DNL Target] UI中的显示顺序（从上到下）定义的。**

  访客可能会符合多个受众的条件，在这种情况下，记住这一点十分重要。例如，如果您有两个体验：一个针对“美国”，一个针对“纽约”，则位于纽约的访客将同时符合这两个受众的资格。 因此，您必须确保先定义“New York”体验，然后再定义[!DNL Target] UI中的“United States”体验。 这种做法可确保更具针对性的“纽约”体验具有更高的优先级，如以下示例所示：

  ![优先级：纽约 > 美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
