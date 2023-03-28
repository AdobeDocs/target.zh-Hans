---
keywords: 体验；JSON;AEM;Adobe Experience Manager；导出到Adobe Target；体验片段；片段；XF
description: 了解如何使用 [!DNL Adobe Experience Manager] [!UICONTROL 体验片段] in [!DNL Adobe Target] 活动。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 体验片段]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 10%

---

# AEM [!UICONTROL 体验片段]

使用 [!UICONTROL 体验片段] (XF)在 [!DNL Adobe Experience Manager] (AEM)in [!DNL Target] 活动来帮助优化或个性化。

>[!NOTE]
>
>使用AEM时，请考虑以下事项 [!UICONTROL 体验片段] in [!DNL Target]:
> 
>* 此功能要求您是 [!DNL Adobe Experience Manager] (AEM)客户。 有关更多信息，请参阅 [要求](#section_AE6F0971E1574B3AA324003599B96E5A) 下。
>* 此功能适用于以下活动类型： [!UICONTROL A/B测试], [!UICONTROL 自动分配], [!UICONTROL 自动定位], [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 体验定位] (XT)。 此功能在 [!UICONTROL 多变量测试] (MVT)和 [!UICONTROL Recommendations] 活动。
>
>* 您可以使用 [!UICONTROL 体验片段] in [!DNL Target] 活动 [可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md).


详细了解AEM [!UICONTROL 体验片段] 和内容片段，请参阅 [AEM [!UICONTROL 体验片段] 和内容片段概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要求 {#requirements}

您必须配置 [!UICONTROL 体验片段] 功能 [!DNL Target]. 此外，您必须使用 [!DNL AEM] as a Cloud Service或 [!DNL AEM] 6.4（或更高版本）。 您的客服专员可以帮助您确保满足使用此功能的要求：

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帐户。

[!DNL Adobe Experience Manager] 6.3和6.4已结束生命周期，不再受支持（购买了扩展支持的客户除外）。

联系人 [Adobe Target客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ，以启用集成并向您提供身份验证详细信息。

## 创建和配置 [!UICONTROL 体验片段] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

为了使用 [!DNL AEM] [!UICONTROL 体验片段] in [!DNL Target]，则必须执行以下步骤：

### 步骤1:集成 [!DNL AEM] with [!DNL Target]

有关更多信息，请参阅：

* **AEMas a Cloud Service**: [与Adobe Target集成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} 在 *Experience Manageras a Cloud Service* 的双曲余切值。
* **Adobe I/O**: [使用Adobe Target I/0与Adobe集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank} 在 *Administering用户指南* 文档。
* **[!DNL AEM]6.5**: [选择加入Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [选择加入Adobe Analytics和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank} 在 *Adobe Experience Manager 6.4* 文档。

### 步骤2:创建体验片段

[!UICONTROL 体验片段] 创建于 [!DNL AEM]. 有关更多信息，请参阅：

* **AEMas a Cloud Service**: [[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} 在 *Experience Manageras a Cloud Service* 的双曲余切值。
* **[!DNL AEM]6.5**: [[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.4* 文档。

### 步骤3:配置 [!DNL AEM] 与共享体验片段 [!DNL Target]

1. 从内部 [!DNL AEM]，选择所需的体验片段或其包含文件夹，然后单击 **[!UICONTROL 属性]**.
2. 单击&#x200B;**[!UICONTROL 云服务]**&#x200B;选项卡，然后从&#x200B;**[!UICONTROL 云服务配置]**&#x200B;下拉列表中选择 **[!UICONTROL Adobe Target]**。

   上一步假定组织中的某人已创建 [!DNL Adobe Target] 配置。

3. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

### 步骤4:发布体验片段并将其导出到 [!DNL Target]

根据您的 [!DNL AEM] 版本中，请参阅以下链接以获取分步说明：

* **AEMas a Cloud Service**: [导出 [!UICONTROL 体验片段] 到Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} 在 *Experience Manageras a Cloud Service* 的双曲余切值。
* **[!DNL AEM]6.5**: [将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} 在 *Adobe Experience Manager 6.5* 文档。
* **[!DNL AEM]6.4**: [将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank} 在 *Adobe Experience Manager 6.4* 文档。

## 使用 [!UICONTROL 体验片段] in [!DNL Target] 活动 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，体验片段会显示在 [!UICONTROL 选件] 页面 [!DNL Target].

[!DNL Target] 当前正在查找 [!UICONTROL 体验片段] 每10分钟导入一次。 导入的体验片段应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。

体验片段将导入到 [!DNL Target] 作为HTML或JSON选件。 体验片段“主”版本保留在 [!DNL AEM]. 您无法在 [!DNL Target].

您可以按 [!UICONTROL HTML体验片段] 和 [!UICONTROL JSON XF] 以帮助您区分导出到的体验片段类型 [!DNL Target].

![按体验片段类型过滤：HTML或JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以将鼠标悬停在列表中的某个体验片段上，然后单击 [!UICONTROL 查看] 图标 ![“信息”图标](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 以查看有关体验片段(包括其 [!UICONTROL 名称], [!UICONTROL 类型], [!UICONTROL 选件ID], [!UICONTROL 选件路径]、和上次修改信息。 单击 [!UICONTROL 选件使用情况] 选项卡，以查看引用此选件的活动。

![体验片段信息弹出窗口](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

您可以使用 [!UICONTROL 体验片段] in [!DNL Target] 活动 [可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)或 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>将人工智能、机器学习和推荐与 [!UICONTROL 体验片段]:
>
>* 要充分利用 [!DNL Target] AI和ML功能，您可以选择 [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 创建A/B测试时。
>
>* [!UICONTROL 体验片段] 不支持 [!DNL Recommendations] 活动。 但是，要使用 [!UICONTROL 体验片段] 对于“推荐”，您可以创建 [!UICONTROL A/B测试] 活动(包括 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位])或 [!UICONTROL 体验定位] (XT)活动和 [将推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md).


**通过 VEC 使用体验片段：**

1. 在 [!DNL Target]，在中创建或编辑体验时 [可视化体验编辑器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)，单击要插入的页面位置 [!DNL AEM] 内容，然后选择所需的选项以显示 [!UICONTROL 选择体验片段] 列表。

   * [!UICONTROL 此项前插入]
   * [!UICONTROL 此项后插入]
   * [!UICONTROL 与体验片段交换]

   的 [!UICONTROL 体验片段] 列表显示在 [!DNL AEM] 现在可从内部本地访问 [!DNL Target].

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果您想要对图像使用此选项，请单击包含所需图像的容器元素。

   ![experience_fragment_list图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 选择所需的体验片段，然后单击 **[!UICONTROL 完成]**.
1. 完成活动配置。

   有关配置各种类型的活动的更多信息，请参阅以下主题：

   * **A/B 测试：**[创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自动分配：**[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自动定位：** [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **自动个性化 (AP)：**[创建自动个性化活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **体验定位 (XT)：**[创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Recommendations :** [Recommendations作为优惠](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL 体验片段] 在中导出为JSON [!DNL Target] 不能在使用VEC创建的活动中使用；仅HTML [!UICONTROL 体验片段] 在基于VEC的活动中受支持。 如果要使用JSON [!UICONTROL 体验片段]，请在使用 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md).

**通过基于表单的体验编辑器使用体验片段：**

1. 在 [!DNL Target]，在中创建或编辑体验时 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，选择要插入的页面位置 [!DNL AEM] 内容，然后选择 **[!UICONTROL 更改体验片段]** 以显示 [!UICONTROL 选择体验片段] 列表。

   ![experience_fragment_list图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   的 [!UICONTROL 体验片段] 列表显示在 [!DNL AEM] 现在可从内部本地访问 [!DNL Target].

1. 选择所需的体验片段，然后单击 **[!UICONTROL 保存]**.
1. 完成活动配置。

## 注意事项 {#considerations}

* [!DNL Target] 当前正在查找 [!UICONTROL 体验片段] 每10分钟导入一次。 导入的体验片段应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。
* 体验片段将导入到 [!DNL Target] 作为HTML或JSON选件。 体验片段的“主”版本保留在 [!DNL AEM]. 您无法在 [!DNL Target].
* 您无法创建 [!UICONTROL 体验片段] 使用 [!DNL Adobe I/O]. 创建 [!UICONTROL 体验片段] 使用AEM，如上所述。
* 如果您在AEM中更新体验片段，则必须将体验片段发布并导出到 [!DNL Target] 再次如此 [!DNL Target] 可以使用最新更改。

## 从中删除ClientLib和无关HTML [!UICONTROL 体验片段] 导出到 [!UICONTROL Target]

将体验片段选件与 [!DNL Target] 在由AEM交付的页面上，目标页面已包含所有必需的客户端库。 另请注意，选件中不重要的HTML元素也不是必需的。

有时，整个HTML页面会隐藏体验片段并导致问题。 确保体验片段是一段小的HTML，而不是包含HTML、HEAD、正文等的完整HTML页面。

有关更多信息，请参阅以下博客文章： [AEM 6.5:从中删除ClientLibs [!UICONTROL 体验片段] 导出到Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## 培训视频：使用AEM [!UICONTROL 体验片段] with [!DNL Adobe Target]

以下视频向您展示了如何设置和使用 [!UICONTROL 体验片段]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>的 [!DNL AEM] deeplink在4:54处讨论的功能已被删除。

有关更多详细信息，请参阅 [使用 [!UICONTROL 体验片段] 与Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) 在 *AEM Sites视频和Tutorials* 页面。