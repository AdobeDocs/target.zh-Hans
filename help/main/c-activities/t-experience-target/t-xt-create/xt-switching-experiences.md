---
keywords: 优先级;体验创建;优先级;体验;受众;切换体验;可视化体验编辑器
description: 了解访客如何在Adobe中的体验之间切换 [!DNL Target] 体验定位(XT)活动，因为其用户档案会发生变化。
title: 访客能否在体验定位活动中切换体验？
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 94%

---

# 在体验定位中切换体验

此信息介绍了随着访客配置文件发生更改，访客如何在体验定位 (XT) 活动中切换体验。

>[!NOTE]
>
>**2017 年 9 月 21 日**
>
>随着 2017 年 9 月 21 日版的发布，Target 将更改在体验定位 (XT) 活动（Target Classic 中的登陆页面营销活动）中将用户置入体验的方式。对于所有新活动和现有活动，用户必须在每次展示时满足体验定位规则，才能继续查看体验内容并计入报表。以前，如果用户不再符合任何体验的参加条件，用户将继续能够看到他们之前符合参加条件的最后一个体验的内容，并被计入该体验的报表中。
>
>在此版本中，所有现有活动都会自动进行这项更改，在此版本之后创建的任何新活动也会自动进行这项更改。如果需要使用以前的方法（9 月 21 日之前），则可以使用配置文件脚本创建受众，这样，用户只需满足条件一次，以后便会一直符合该受众条件。之后，可以在活动的各个体验中使用这些受众。

使用体验定位，您可以控制访客配置文件发生更改时访客所看到的体验。在少数方案中，访客配置文件可能会发生更改，此时您可能希望向访客显示不同的内容，下表列出了这些方案：

| 方案 | 详细信息 |
|--- |--- |
| 地理位置 | 访客出差或外出旅游时，可能会从不同的地理位置访问您的网站或移动设备应用程序。 |
| 客户状态 | 访客尚未创建帐户或购买产品时，可能会将其视为潜在客户。 |
| 类别亲和力 | 的 [类别亲和度](/help/main/c-target/c-visitor-profile/category-affinity.md) 功能可自动捕捉用户访问的类别，然后计算用户对该类别的喜爱程度，从而进行定位。 例如，如果访客在您的网站上查看了关于某个特定主题的多篇文章，则可以向其显示与该主题有关的内容。 |
| 每周时间 | 随着周末临近，您可能想要向访客显示与电影、美食或其他类型的娱乐活动有关的内容。 |

使用 XT 活动时，要利用 [!DNL Target] 中提供的上述功能，请务必了解以下信息：

* **优先级是由体验的顺序（从上到下）来控制的。**&#x200B;如果一位访客符合两个以上受众的条件，则该访客会收到具有较高优先级的体验的内容。
* **如果访客开始符合具有较高优先级的体验的受众条件，则访客将会在 XT 活动中切换体验。**

   例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客切换到了体验 B（德国访客）。

   ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **如果访客不再符合当前受众的条件，但却开始符合具有较低优先级的体验的条件，则访客也将会切换体验。**
* **如果访客不再符合当前体验的条件，而且也不符合其他体验的条件，则访客将会看到默认内容。**

   例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了法国并在法国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在法国访问您的网站后，该访客将停留在原始体验中。

   ![优先级：美国 > 德国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **定位到“所有访客”的体验可以用作体验定位活动中的最后一个体验，以“捕获”所有还未进入任何其他体验的访客。如果定位到“所有访客”的体验不是排在最后，则仍会对列在该体验下方的其他已定位体验进行评估。**

   例如，在以下活动设置中，一位访客先在美国访问了您的网站，然后又来到了德国并在德国再次访问您的网站。在首次访问期间，该访客符合体验 A（美国访客）的条件。在德国访问您的网站后，该访客将停留在体验 A（美国访客）中。

   ![优先级：美国 > 所有访客](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   如果这不是您所期望的结果，您可以创建一个新受众，并将其明确定义为与目标受众相反的受众，如以下示例所示：

   ![优先级：美国 > 非美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **如果 XT 活动中只有一个体验，则即使访客不再符合体验的受众条件，访客仍会保留在该体验中。**

   如果这不是您所期望的结果，您可以再创建一个体验，并将其定位到相反的受众（例如，与“美国”相反的“非美国”）。

   或者，您可以创建一个 A/B 活动，并将其定位到分配了 100% 流量的所需受众，如下所示：

   ![优先级：一个体验](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **体验的优先级是由体验在 Target UI 中的显示顺序（从上到下）来定义的。**

   访客可能会符合多个受众的条件，在这种情况下，记住这一点十分重要。例如，如果您有两个体验：一个体验定位到“美国”，而另一个体验则定位到“纽约”，则位于纽约的访客将同时满足这两个受众的条件。因此，您必须确保在 Target UI 中先定义“纽约”体验，然后再定义“美国”体验。这样做可以确保定位更为精确的“纽约”体验具有较高优先级，如以下示例所示：

   ![优先级：纽约 > 美国](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)