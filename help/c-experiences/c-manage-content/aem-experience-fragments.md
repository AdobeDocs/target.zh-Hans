---
description: 有关在 Target 活动中使用在 Adobe Experience Manager (AEM) 中创建的体验片段以帮助优化或个性化的信息。
keywords: 体验；json；aem；adobe experience manager；导出到adobe目标；体验片段；片段；XF
seo-description: 有关使用Adobe Target活动中在Adobe Experience Manager(AEM)中创建的体验片段以帮助优化或个性化的信息。
seo-title: Adobe Target中的Adobe Experience Manager(AEM)体验片段
solution: Target
title: AEM 体验片段
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# AEM 体验片段{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. 有关更多信息，请参阅下面的[要求](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 概述 {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in [!DNL Target] activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

AEM 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。通过 AEM，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。无需为每台设备创建页面。AEM会使用内容自动调整每个体验。

[!DNL Target] 允许您根据一组基于规则且由 AI 驱动的机器学习方法（这些方法包含行为、上下文和离线变量），交付大量的个性化体验。With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using [!DNL Target].

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNl Target]. 此外，您还必须使用 AEM 6.3 以及相应的 Service Pack，或者使用 AEM 6.4（或更高版本）。您的客服专员可以帮助您确保满足使用此功能的要求：

* Adobe Experience Manager 6.4（或更高版本）。
* Adobe Experience Manager 6.3 SP2（或更高版本）。
* Adobe Target Standard 或 Adobe Target Premium 帐户。
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## 在 AEM 中创建并配置体验片段 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in [!DNL Target], you must perform the following steps:

### 步骤 1：将 AEM 与 Target 集成

有关详细信息，请参阅：

* **AEM6.3**： [在Adobe Experience](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) _Manager6.3_ 文档中选择加入Adobe Analytics和Adobe Target。
* **AEM6.4**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) _Manager6.4_ 文档中选择加入Adobe Analytics和Adobe Target。
* **AEM6.5**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) *Manager6.5* 文档中选择加入Adobe Analytics和Adobe Target。

### 步骤 2：创建体验片段

体验片段是在 AEM 中创建的。有关详细信息，请参阅：

* **AEM6.3**： [Adobe Experience](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) *Manager6.3* 文档中的体验片段。
* **AEM6.4**： [Adobe Experience](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) *Manager6.4* 文档中的体验片段。
* **AEM6.5**： [Adobe Experience](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) *Manager6.5* 文档中的体验片段。

### 步骤 3：配置 AEM 以与 Target 共享体验片段

1. From within AEM, select the desired experience fragment or its containing folder, then click **[!UICONTROL Properties]**.
2. Click the **[!UICONTROL Cloud Services]** tab, then from the **[!UICONTROL Cloud Service Configuration]** drop-down list, select **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

### 步骤 4：发布体验片段并将其导出到 Target

根据您的AEM版本，请参阅以下链接以获得分步说明：

* **AEM6.3**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) *Manager6.3* 文档中将体验片段导出到Target。
* **AEM6.4**： [在Adobe Experience](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) *Manager6.4* 文档中将体验片段导出到Target。
* **AEM6.5**： [在Adobe Experience](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) *Manager6.5* 文档中将体验片段导出到Target。

## 在 Target 活动中使用体验片段 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，体验片段会显示在 Target 的“[!UICONTROL 选件]”页面中。

>[!NOTE]
>
>[!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. 请注意，体验片段的“母”版仍保留在 AEM 中。因此，您无法在 Target 中编辑体验片段。

You can hover over an experience fragment in the list, then click the View icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**通过 VEC 使用体验片段：**

1. 在 [!DNL Target][“可视体验书写器](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)”中创建或编辑体验时，单击要插入AEM内容的页面上的位置，然后选择所需选项以显示“ [!UICONTROL 选择体验片段] ”列表。

   * [!UICONTROL 此项前插入]
   * [!UICONTROL 此项后插入]
   * [!UICONTROL 使用体验片段交换]
   [!UICONTROL Experience Fragments] 列表显示在AEM中创建的所有内容(现在可从内部获取) [!DNL Target]。

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果您想要对图像使用此选项，请单击包含所需图像的容器元素。

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. 完成活动配置。

   有关配置各种类型的活动的更多信息，请参阅以下主题：

   * **A/B 测试：**[创建 A/B 测试](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **自动分配：**[自动分配](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自动定位：**[自动定位以提供个性化体验](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **自动个性化 (AP)：**[创建自动个性化活动](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **体验定位 (XT)：**[创建体验定位活动](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多变量测试 (MVT)：**[创建多变量测试](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **推荐：**[创建“推荐”活动](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**通过基于表单的体验编辑器使用体验片段：**

1. 在 [!DNl Target]中，在基于 [表单的Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，选择要插入AEM内容的页面上的位置，然后选择 **[!UICONTROL 更改体验片段]** 以显示 [!UICONTROL 选择体验片段] 列表。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL Experience Fragments] 列表显示在AEM中创建的所有内容(现在可从内部获取) [!DNL Target]。

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 完成活动配置。

## 注意事项 {#considerations}

* [!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. 请注意，体验片段的“母”版仍保留在 AEM 中。You cannot edit the experience fragment in [!DNL Target].
* 您可以将JSON选件作为体验片段导入 [!DNL Target]。但是，这些选件将作为HTML选件导入。JSON选件(体验片段)当前在 [!DNL Target] UI中不完全受支持。

## 培训视频：在 Adobe Target 中使用 AEM 体验片段{#section_C0EDC54063464F41A182492D2045BC64}

以下视频演示了如何设置和使用体验片段：[在 Adobe Target 中使用 AEM 体验片段](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html)。
