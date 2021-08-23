---
keywords: 体验；JSON;AEM;Adobe Experience Manager；导出到Adobe Target；体验片段；片段；XF
description: 了解如何在Adobe [!DNL Target] 活动中使用AEM体验片段。 将AEM的易用性和强大功能与 [!DNL Target]中强大的AI和ML功能结合使用。
title: 如何使用Adobe Experience Manager(AEM)体验片段？
feature: 体验和选件
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: c9c335c241727c4eff1d27f52853e32b8d18b6a5
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 21%

---

# AEM 体验片段

有关在[!DNL Target]活动中使用在[!DNL Adobe Experience Manager](AEM)中创建的体验片段以帮助优化或个性化的信息。

>[!NOTE]
>
>此功能要求您是[!DNL Adobe Experience Manager]([!DNL AEM])客户。 有关更多信息，请参阅下面的[要求](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 概述 {#section_95A91830530F493B81C5C9CDB9B783EA}

通过使用在[!DNL Target]活动的[!DNL AEM]中创建的体验片段，您可以将[!DNL AEM]的易用性和强大功能与[!DNL Target]中强大的自动智能(AI)和机器学习(ML)功能结合使用，以测试和个性化大量体验。

[!DNL AEM] 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。[!DNL AEM]通过 ，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。无需为每个设备创建页面。 [!DNL AEM] 可使用您的内容自动调整每个体验。

[!DNL Target] 允许您根据一组基于规则且由 AI 驱动的机器学习方法（这些方法包含行为、上下文和离线变量），交付大量的个性化体验。借助[!DNL Target]，您可以轻松设置并运行[A/B测试](/help/c-activities/t-test-ab/test-ab.md)和[多变量](/help/c-activities/c-multivariate-testing/multivariate-testing.md)(MVT)活动，以确定最佳选件、内容和体验。

体验片段代表了在将内容/体验创建器和管理器关联到优化和个性化专业人士方面迈出了巨大的一步，这些专业人士正在使用[!DNL Target]推动业务成果。

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必须在[!DNL Target]中使用体验片段功能进行配置。 此外，您还必须将[!DNL AEM] 6.3与相应的Service Pack一起使用，或者将[!DNL AEM] 6.4（或更高版本）使用。 您的客服专员可以帮助您确保满足使用此功能的要求：

* [!DNL Adobe Experience Manager] 6.4（或更高版本）。
* [!DNL Adobe Experience Manager] 6.3 SP2（或更高版本）。
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帐户。
* 请联系[Adobe Target客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并提供身份验证详细信息。

## 在[!DNL AEM]中创建并配置体验片段 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要在[!DNL Target]中使用[!DNL AEM]体验片段，必须执行以下步骤：

### 步骤1:将[!DNL AEM]与[!DNL Target]集成

有关详细信息，请参阅：

* **Adobe I/O**: [使用“管理用户指南”文档中的AdobeI/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html) 与Adobe Target _集_ 成。
* **[!DNL AEM]6.3**: [在Adobe Experience Manager 6.3文](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 档中选 _择加入Adobe Analytics和Adobe_ 定位。
* **[!DNL AEM]6.4**: [在Adobe Experience Manager 6.4 ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) 文档中 _选择加入Adobe Analytics和Adobe_ 定位。
* **[!DNL AEM]6.5**: [在Adobe Experience Manager 6.5 ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en) 文档中 *选择加入Adobe Analytics和Adobe* 定位。

### 步骤 2：创建体验片段

体验片段是在[!DNL AEM]中创建的。 有关详细信息，请参阅：

* **[!DNL AEM]6.3**: [](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) Adobe Experience Manager 6.3 *文档中的体* 验片段。
* **[!DNL AEM]6.4**: [](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) Adobe Experience Manager 6.4 *文档中的体* 验片段。
* **[!DNL AEM]6.5**: [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) Adobe Experience Manager 6.5 *文档中的体* 验片段。

### 步骤3:配置[!DNL AEM]以与[!DNL Target]共享体验片段

1. 在[!DNL AEM]中，选择所需的体验片段或其包含文件夹，然后单击&#x200B;**[!UICONTROL 属性]**。
2. 单击&#x200B;**[!UICONTROL 云服务]**&#x200B;选项卡，然后从&#x200B;**[!UICONTROL 云服务配置]**&#x200B;下拉列表中选择 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步假定组织中已有人创建了[!DNL Adobe Target]配置。

3. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

### 步骤 4：发布体验片段并将其导出到 [!DNL Target]

根据您的[!DNL AEM]版本，请参阅以下链接以了解分步说明：

* **[!DNL AEM]6.3**: [在Adobe Experience Manager 6.3](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) 文档中 *将体验片段导出* 到Target。
* **[!DNL AEM]6.4**: [在Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) 文档中 *将体验片段导出* 到Target。
* **[!DNL AEM]6.5**: [在Adobe Experience Manager 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) 文档中 *将体验片段导出* 到Target。

## 在[!DNL Target]活动中使用体验片段 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，体验片段会显示在[!DNL Target]的[!UICONTROL 选件]页面中。

>[!NOTE]
>
>[!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。导入的体验片段应在10分钟内在[!DNL Target]中可用，但此时间范围应会缩短。

>[!IMPORTANT]
>
>当前，体验片段是作为HTML选件导入到[!DNL Target]中的。 请注意，体验片段“主”版本仍保留在[!DNL AEM]中。 无法在[!DNL Target]中编辑体验片段。

您可以将鼠标悬停在列表中某个体验片段上，然后单击[!UICONTROL 查看]图标![查看图标](assets/icon_info.png) ，以查看有关该体验片段的其他信息，包括其公共选件交付URL及其[!DNL AEM]路径。

您可以在[!DNL Target]活动中使用[可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)或[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md)来使用体验片段。

>[!NOTE]
>
>要充分利用[!DNL Target] AI和ML功能，您可以在创建A/B测试时选择[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)。

**要使用VEC使用体验片段，请执行以下操作：**

1. 在[!DNL Target]中，在[可视化体验编辑器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中创建或编辑体验时，单击页面上要插入[!DNL AEM]内容的位置，然后选择所需的选项以显示[!UICONTROL 选择体验片段]列表。

   * [!UICONTROL 此项前插入]
   * [!UICONTROL 此项后插入]
   * [!UICONTROL 与体验片段交换]

   [!UICONTROL 体验片段]列表显示了在[!DNL AEM]中创建的所有内容，这些内容现在可从[!DNL Target]内本地使用。

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果您想要对图像使用此选项，请单击包含所需图像的容器元素。

   ![](assets/experience_fragment_list.png)

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 完成]**。
1. 完成活动配置。

   有关配置各种类型的活动的更多信息，请参阅以下主题：

   * **A/B 测试：**[创建 A/B 测试](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自动分配：**[自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自动定位：** [自动定位](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **自动个性化 (AP)：**[创建自动个性化活动](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **体验定位 (XT)：**[创建体验定位活动](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多变量测试 (MVT)：**[创建多变量测试](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **推荐：**[创建“推荐”活动](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**要使用基于表单的体验编辑器来使用体验片段，请执行以下操作：**

1. 在[!DNL Target]中，在[基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，请选择页面上要插入[!DNL AEM]内容的位置，然后选择&#x200B;**[!UICONTROL 更改体验片段]**&#x200B;以显示[!UICONTROL 选择体验片段]列表。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL 体验片段]列表显示了在[!DNL AEM]中创建的所有内容，这些内容现在可从[!DNL Target]内本地使用。

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 完成活动配置。

## 注意事项 {#considerations}

* [!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。导入的体验片段应在10分钟内在[!DNL Target]中可用，但此时间范围应会缩短。
* 当前，体验片段是作为HTML选件导入到[!DNL Target]中的。 请注意，体验片段“主”版本仍保留在[!DNL AEM]中。 无法在[!DNL Target]中编辑体验片段。
* 您可以将JSON选件作为体验片段导入[!DNL Target]。 但是，这些选件会导入为HTML选件。 [!DNL Target] UI当前不完全支持JSON选件（体验片段）。
* 您无法使用AdobeIO创建体验片段。 您必须使用AEM创建体验片段，如上所述。

## 培训视频：将AEM体验片段与Adobe Target ![教程徽章](/help/assets/overview.png)结合使用 {#section_C0EDC54063464F41A182492D2045BC64}

以下视频向您展示了如何设置和使用体验片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已删除4:54处讨论的[!DNL AEM]深层链接功能。

有关更多信息，请参阅&#x200B;*AEM Sites视频和Tutorials*&#x200B;页面上的[将体验片段与Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)一起使用。
