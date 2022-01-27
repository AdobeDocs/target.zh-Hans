---
keywords: 体验；JSON;AEM;Adobe Experience Manager；导出到Adobe Target；体验片段；片段；XF
description: 了解如何使用 [!DNL Adobe Experience Manager] 体验片段 [!DNL Adobe Target] 活动。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM)体验片段？
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 3009b232c3f0208c7632ad6369bf5d96334fe377
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 20%

---

# AEM 体验片段

使用在中创建的体验片段 [!DNL Adobe Experience Manager] (AEM)in [!DNL Target] 活动来帮助优化或个性化。

>[!NOTE]
>
>此功能要求您是 [!DNL Adobe Experience Manager] (AEM)客户。 有关更多信息，请参阅 [要求](#section_AE6F0971E1574B3AA324003599B96E5A) 下。

使用在中创建的体验片段 [!DNL AEM] in [!DNL Target] 通过活动，您可以将 [!DNL AEM] 在 [!DNL Target] 以大规模测试和个性化体验。

[!DNL AEM] 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。[!DNL AEM]通过 ，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。无需为每个设备创建页面。 [!DNL AEM] 可使用您的内容自动调整每个体验。

[!DNL Target] 允许您根据一组基于规则且由 AI 驱动的机器学习方法（这些方法包含行为、上下文和离线变量），交付大量的个性化体验。使用 [!DNL Target]，则可以轻松设置和运行 [A/B测试](/help/c-activities/t-test-ab/test-ab.md) 和 [多变量](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT)活动来确定最佳选件、内容和体验。

体验片段是向将内容/体验创建器和管理器关联到优化和个性化专业人士(这些专业人士正在使用 [!DNL Target].

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必须在 [!DNL Target]. 此外，您必须使用 [!DNL AEM] as a Cloud Service或 [!DNL AEM] 6.4（或更高版本）。 您的客服专员可以帮助您确保满足使用此功能的要求：

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5。
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帐户。

>[!NOTE]
>
>[!DNL Adobe Experience Manager] 6.3和6.4已结束生命周期，不再受支持（购买了扩展支持的客户除外）。

联系人 [Adobe Target客户关怀](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ，以启用集成并向您提供身份验证详细信息。

## 在中创建和配置体验片段 [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

为了使用 [!DNL AEM] 体验片段 [!DNL Target]，则必须执行以下步骤：

### 步骤1:集成 [!DNL AEM] with [!DNL Target]

有关详细信息，请参阅：

* **AEMas a Cloud Service**: [与Adobe Target集成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} *Experience Manageras a Cloud Service* 的双曲余切值。
* **Adobe I/O**: [使用Adobe Target I/0与Adobe集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} *Administering用户指南* 文档。
* **[!DNL AEM]6.5**: [选择加入Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [选择加入Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} *Adobe Experience Manager 6.4* 文档。

### 步骤 2：创建体验片段

体验片段是在中创建的 [!DNL AEM]. 有关详细信息，请参阅：

* **AEMas a Cloud Service**: [体验片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} *Experience Manageras a Cloud Service* 的双曲余切值。
* **[!DNL AEM]6.5**: [体验片段](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [体验片段](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} *Adobe Experience Manager 6.4* 文档。

### 步骤3:配置 [!DNL AEM] 与共享体验片段 [!DNL Target]

1. 从内部 [!DNL AEM]，选择所需的体验片段或其包含文件夹，然后单击 **[!UICONTROL 属性]**.
2. 单击&#x200B;**[!UICONTROL 云服务]**&#x200B;选项卡，然后从&#x200B;**[!UICONTROL 云服务配置]**&#x200B;下拉列表中选择 **[!UICONTROL Adobe Target]**。

   >[!NOTE]
   >
   >上一步假定组织中的某人已创建 [!DNL Adobe Target] 配置。

3. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

### 步骤 4：发布体验片段并将其导出到 [!DNL Target]

根据您的 [!DNL AEM] 版本中，请参阅以下链接以获取分步说明：

* **AEMas a Cloud Service**: [将体验片段导出到Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank}
* **[!DNL AEM]6.5**: [将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} *Adobe Experience Manager 6.4* 文档。

## 在中使用体验片段 [!DNL Target] 活动 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，体验片段会显示在 [!UICONTROL 选件] 页面 [!DNL Target].

>[!NOTE]
>
>* [!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。导入的体验片段应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。
>
>* 体验片段将导入到 [!DNL Target] 作为HTML选件。 体验片段“主”版本保留在 [!DNL AEM]. 您无法在 [!DNL Target].


您可以将鼠标悬停在列表中的某个体验片段上，然后单击 [!UICONTROL 查看] 图标 ![“查看”图标](assets/icon_info.png) 查看有关体验片段的其他信息，包括其公共选件交付URL及其 [!DNL AEM] 路径。

您可以在 [!DNL Target] 活动 [可视化体验编辑器](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>要充分利用 [!DNL Target] AI和ML功能，您可以选择 [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自动分配](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) 创建A/B测试时。

**要使用VEC使用体验片段，请执行以下操作：**

1. 在 [!DNL Target]，在中创建或编辑体验时 [可视化体验编辑器](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)，单击要插入的页面位置 [!DNL AEM] 内容，然后选择所需的选项以显示 [!UICONTROL 选择体验片段] 列表。

   * [!UICONTROL 此项前插入]
   * [!UICONTROL 此项后插入]
   * [!UICONTROL 与体验片段交换]

   的 [!UICONTROL 体验片段] 列表显示在 [!DNL AEM] 现在可从内部本地访问 [!DNL Target].

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果您想要对图像使用此选项，请单击包含所需图像的容器元素。

   ![](assets/experience_fragment_list.png)

1. 选择所需的体验片段，然后单击 **[!UICONTROL 完成]**.
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

1. 在 [!DNL Target]，在中创建或编辑体验时 [基于表单的体验编辑器](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，选择要插入的页面位置 [!DNL AEM] 内容，然后选择 **[!UICONTROL 更改体验片段]** 以显示 [!UICONTROL 选择体验片段] 列表。

   ![](assets/experience_fragment_list.png)

   的 [!UICONTROL 体验片段] 列表显示在 [!DNL AEM] 现在可从内部本地访问 [!DNL Target].

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 完成活动配置。

## 注意事项 {#considerations}

* [!DNL Target]当前， 会每隔 10 分钟查找一次要导入的体验片段。导入的体验片段应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。
* 体验片段将导入到 [!DNL Target] 作为HTML选件。 体验片段的“主”版本保留在 [!DNL AEM]. 您无法在 [!DNL Target].
* 您不能使用 [!DNL Adobe I/O]. 如上所述，使用AEM创建体验片段。
* 如果您在AEM中更新体验片段，则必须将该体验片段发布并导出到 [!DNL Target] 再次如此 [!DNL Target] 可以使用最新更改。

## 培训视频：将AEM体验片段与 [!DNL Adobe Target]

以下视频向您展示了如何设置和使用体验片段：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>的 [!DNL AEM] deeplink在4:54处讨论的功能已被删除。

有关更多详细信息，请参阅 [在Adobe Target中使用体验片段](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) 在 *AEM Sites视频和Tutorials* 页面。
