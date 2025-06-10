---
keywords: 体验;json;AEM;Adobe Experience Manager;导出到 Adobe Target;体验片段;片段;XF
description: 了解如何在 [!DNL Adobe Target] 活动中使用 [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments]。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Experience Fragments]？
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: b29614680b27c9c33f11eed85d8ab4feebc28b0d
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 27%

---

# AEM [!UICONTROL Experience Fragments]

在[!DNL Target]活动中使用在[!DNL Adobe Experience Manager] (AEM)中创建的[!UICONTROL Experience Fragments] (XF)帮助优化和个性化。

## 注意事项

在[!DNL Target]中使用AEM [!UICONTROL Experience Fragments]时，请考虑以下事项：

* 此功能要求您是 [!DNL Adobe Experience Manager] (AEM) 客户。有关更多信息，请见以下[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]可用于以下活动类型：

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]不适用于以下活动类型：

   * [[!UICONTROL Multivariate Test] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* 您可以使用[可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)和[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在[!DNL Target]活动中使用[!UICONTROL Experience Fragments]。

要了解有关AEM [!UICONTROL Experience Fragments]和[!UICONTROL Content Fragments]的更多信息，请参阅[AEM [!UICONTROL Experience Fragments]和内容片段概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

必须在[!DNL Target]内为您设置[!UICONTROL Experience Fragments]功能。 此外，还必须使用 [!DNL AEM] as a Cloud Service 或 [!DNL AEM] 6.4（或更高版本）。您的客户代表可帮助确保您满足使用此功能的要求：

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帐户

[!DNL Adobe Experience Manager] 6.3 和 6.4 的生命周期已结束，因此不再支持这些版本（已购买延期支持的客户除外）。

请联系 [Adobe Target 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并为您提供身份验证详细信息。

## 在[!DNL AEM]中创建和配置[!UICONTROL Experience Fragments] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要在[!DNL Target]中使用[!DNL AEM] [!UICONTROL Experience Fragments]，必须执行以下步骤：

### 第 1 步：将 [!DNL AEM] 与 [!DNL Target] 集成

有关更多信息，请参阅：

* **AEM as a Cloud Service**： *Adobe Targetas a Cloud Service*&#x200B;指南中的[与Experience Manager集成](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank}。
* **Adobe Developer**： *管理用户指南*&#x200B;文档中的[使用Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank}与Adobe Target集成。
* **[!DNL AEM]6.5**： *Adobe Analytics 6.5*&#x200B;文档中的[选择使用Adobe Experience Manager和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.4**： *Adobe Analytics 6.4*&#x200B;文档中的[选择使用Adobe Experience Manager和Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank}。

### 第 2 步：创建体验片段

[!UICONTROL Experience Fragments]在[!DNL AEM]中创建。 有关更多信息，请参阅：

* **AEM as a Cloud Service**： *Experience Manager as a Cloud Service*&#x200B;指南中的[[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=zh-Hans){target=_blank}。
* *Adobe Experience Manager 6.5*&#x200B;文档中的&#x200B;**[!DNL AEM]6.5**： [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=zh-Hans){target=_blank}。
* *Adobe Experience Manager 6.4*&#x200B;文档中的&#x200B;**[!DNL AEM]6.4**： [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=zh-Hans){target=_blank}。

### 步骤3：将[!DNL AEM]配置为与[!DNL Target]共享[!UICONTROL Experience Fragment]

1. 从[!DNL AEM]中，选择所需的[!UICONTROL Experience Fragment]或其包含文件夹，然后单击&#x200B;**[!UICONTROL Properties]**。
2. 单击&#x200B;**[!UICONTROL Cloud Services]**&#x200B;选项卡，然后从&#x200B;**[!UICONTROL Cloud Service Configuration]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Adobe Target]**。

   上一步假设您的组织中已有人创建了 [!DNL Adobe Target] 配置。

3. 单击 **[!UICONTROL Save & Close]**。

### 步骤4：发布[!UICONTROL Experience Fragment]并将其导出到[!DNL Target]

根据您的 [!DNL AEM]版本，请参阅以下链接以获取分步说明：

* **AEM as a Cloud Service**： [正在将[!UICONTROL Experience Fragments]导出到&#x200B;*Adobe Target as a Cloud Service*&#x200B;指南中的Experience Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank}。
* **[!DNL AEM]6.5**： *Adobe Experience Manager 6.5*&#x200B;文档中的[将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.4**： *Adobe Experience Manager 6.4*&#x200B;文档中的[将体验片段导出到Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank}。

## 在[!DNL Target]活动中使用[!UICONTROL Experience Fragments] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，[!UICONTROL Experience Fragment]将显示在[!DNL Target]的[!UICONTROL Offers]页面上。

[!DNL Target]当前查找[!UICONTROL Experience Fragments]以每十分钟导入一次。 导入的[!UICONTROL Experience Fragment]应在10分钟内在[!DNL Target]内可用，但以后，此时间应会缩短。

[!UICONTROL Experience Fragment]作为HTML或JSON选件导入到[!DNL Target]中。 [!UICONTROL Experience Fragment]“主要”版本保留在[!DNL AEM]中。 您无法在[!DNL Target]中编辑[!UICONTROL Experience Fragment]。

您可以按[!UICONTROL HTML XFs]和[!UICONTROL JSON XFs]筛选和搜索，以帮助您区分导出到[!DNL Target]的[!UICONTROL Experience Fragment]类型。

![按体验片段类型筛选：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以将鼠标悬停在列表中的[!UICONTROL Experience Fragment]上，然后单击[!UICONTROL View]图标![信息图标](/help/main/assets/icons/InfoOutline.svg)以查看有关[!UICONTROL Experience Fragment]的其他信息，包括其[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]以及上次修改信息。 单击[!UICONTROL [!UICONTROL View Full Details]]可查看引用此选件的活动。

![体验片段信息弹出窗口](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

您可以使用[可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)和[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在[!DNL Target]活动中使用[!UICONTROL Experience Fragments]。

>[!TIP]
>
>将人工智能、机器学习和推荐与[!UICONTROL Experience Fragments]结合使用：
>
>* 要充分利用 [!DNL Target] AI 和 ML 功能，您可以在创建活动时选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!DNL Recommendations]活动中不支持[!UICONTROL Experience Fragments]。 但是，要将[!UICONTROL Experience Fragments]用于推荐，您可以创建[!UICONTROL A/B Test]活动（包括[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]）或[!UICONTROL Experience Targeting] (XT)活动以及[将推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。

**使用VEC使用[!UICONTROL Experience Fragments]：**

1. 在[!DNL Target]中，在[可视化体验编辑器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中创建或编辑体验时，单击页面上要插入[!DNL AEM]内容的位置，然后单击&#x200B;**[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]**&#x200B;以显示[!UICONTROL Experience Fragment]对话框。

   [!UICONTROL Experience Fragment]对话框显示在[!DNL AEM]中创建的内容，该内容现在可从[!DNL Target]中以本地方式使用。

   >[!NOTE]
   >
   >[!UICONTROL Replace Content]选项不适用于图像。 如果要将此选项用于图像，请单击包含所需图像的容器元素。

   ![体验片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 选择所需的[!UICONTROL Experience Fragment]，然后单击&#x200B;**[!UICONTROL Add]**。
1. 配置完活动。

   有关配置各种类型的活动的更多信息，请参阅以下主题：

   * **A/B 测试：**[创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自动分配：**[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自动锁定：**[自动锁定](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **自动个性化 (AP)：**[创建自动个性化活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **体验定位 (XT)：**[创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B 测试或 XT 活动中的推荐：**[推荐作为产品建议](/help/main/c-recommendations/recommendations-as-an-offer.md)

   在[!DNL Target]中导出为JSON的[!UICONTROL Experience Fragments]无法在使用VEC创建的活动中使用；在基于VEC的活动中仅支持HTML [!UICONTROL Experience Fragments]。 如果要使用JSON [!UICONTROL Experience Fragments]，请在使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)创建的活动中使用它们。

**使用[!UICONTROL Form-based Experience Composer]使用[!UICONTROL Experience Fragments]：**

1. 在[!DNL Target]中，在[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，在页面上选择要插入[!DNL AEM]内容的位置，单击&#x200B;**[!UICONTROL More Details]**&#x200B;图标（![更多详细信息图标](/help/main/assets/icons/MoreSmall.svg)），然后选择&#x200B;**[!UICONTROL Change Experience Fragment]**&#x200B;以显示[!UICONTROL Change Experience Fragment]对话框。

   ![体验片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL Experience Fragment]对话框显示在[!DNL AEM]中创建的内容，该内容现在可从[!DNL Target]中以本地方式使用。

1. 选择所需的[!UICONTROL Experience Fragment]，然后单击&#x200B;**[!UICONTROL Add]**。
1. 配置完活动。

## 其他信息

* [!DNL Target]当前查找[!UICONTROL Experience Fragments]以每十分钟导入一次。 导入的[!UICONTROL Experience Fragment]应在10分钟内在[!DNL Target]内可用，但以后，此时间应会缩短。
* [!UICONTROL Experience Fragment]作为HTML或JSON选件导入到[!DNL Target]中。 [!UICONTROL Experience Fragment]“主要”版本保留在[!DNL AEM]中。 您无法在[!DNL Target]中编辑[!UICONTROL Experience Fragment]。
* 无法使用[!DNL Adobe Developer]创建[!UICONTROL Experience Fragments]。 使用AEM创建[!UICONTROL Experience Fragments]，如上所述。
* 如果您在AEM中更新[!UICONTROL Experience Fragment]，则必须再次发布[!UICONTROL Experience Fragment]并将其导出到[!DNL Target]，以便[!DNL Target]可以使用最新更改。

## 正在从[!UICONTROL Experience Fragments]中删除导出到[!UICONTROL Target]的clientlibs和无关HTML

在AEM交付的页面上结合使用[!UICONTROL Experience Fragment]选件和[!DNL Target]时，目标页面已包含必要的客户端库。 另请注意，产品建议中的无关 HTML 元素也不是必需的。

有时整个HTML页面会包装[!UICONTROL Experience Fragment]并导致问题。 确保[!UICONTROL Experience Fragment]是HTML的一小部分，而不是包含HTML、HEAD、BODY等的完整HTML页面。

有关详细信息，请参阅以下博客文章： [AEM 6.5：从[!UICONTROL Experience Fragments]中删除导出到Target](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}的clientlibs。

## 培训视频：将AEM [!UICONTROL Experience Fragments]与[!DNL Adobe Target]结合使用

以下视频向您说明如何设置和使用[!UICONTROL Experience Fragments]：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已删除在 4:54 讨论的 [!DNL AEM] 深度链接功能。

有关更多详细信息，请参阅&#x200B;*Adobe Target视频和教程*&#x200B;页面上的[将[!UICONTROL Experience Fragments]与AEM Sites结合使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)。
