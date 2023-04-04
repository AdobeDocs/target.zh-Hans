---
keywords: 体验;json;AEM;Adobe Experience Manager;导出到 Adobe Target;体验片段;片段;XF
description: 了解如何在 [!DNL Adobe Target] 活动中使用 [!DNL Adobe Experience Manager] [!UICONTROL 体验片段]。
title: 如何使用 [!DNL Adobe Experience Manager]  (AEM) [!UICONTROL 体验片段]？
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: ht
source-wordcount: '1346'
ht-degree: 100%

---

# AEM [!UICONTROL 体验片段]

在 [!DNL Target] 活动中使用在 [!DNL Adobe Experience Manager] (AEM) 中创建的[!UICONTROL 体验片段] (XF) 帮助进行优化或个性化。

>[!NOTE]
>
>在 [!DNL Target] 中使用 AEM [!UICONTROL 体验片段]时，请考虑以下内容：
> 
>* 此功能要求您是 [!DNL Adobe Experience Manager] (AEM) 客户。有关更多信息，请参阅下面的[要求](#section_AE6F0971E1574B3AA324003599B96E5A)。
>* 以下活动类型有此功能可用：[!UICONTROL A/B 测试]、[!UICONTROL 自动分配]、[!UICONTROL 自动定位]、[!UICONTROL 自动个性化] (AP) 和[!UICONTROL 体验定位] (XT)。在[!UICONTROL 多变量测试] (MVT) 和[!UICONTROL 推荐]活动中无此功能可用。
>
>* 可通过[可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在 [!DNL Target] 活动中使用[!UICONTROL 体验片段]。


要详细了解 AEM [!UICONTROL 体验片段]和内容片段，请参阅 [AEM [!UICONTROL 体验片段]和内容片段概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)。

## 要求 {#requirements}

必须在 [!DNL Target] 中为您配置[!UICONTROL 体验片段]功能。此外，还必须使用 [!DNL AEM] as a Cloud Service 或 [!DNL AEM] 6.4（或更高版本）。您的客户代表可帮助确保您满足使用此功能的要求：

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] 或 [!DNL Adobe Target Premium] 帐户。

[!DNL Adobe Experience Manager] 6.3 和 6.4 的生命周期已结束，因此不再支持这些版本（已购买延期支持的客户除外）。

请联系 [Adobe Target 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以启用集成并为您提供身份验证详细信息。

## 在 [!DNL AEM] 中创建并配置[!UICONTROL 体验片段] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要在 [!DNL Target] 中使用 [!DNL AEM] [!UICONTROL 体验片段]，必须执行以下步骤：

### 第 1 步：将 [!DNL AEM] 与 [!DNL Target] 集成

有关更多信息，请参阅：

* **AEM as a Cloud Service**：*Experience Manager as a Cloud Service* 指南中的[与 Adobe Target 集成](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank}
* **Adobe I/O**：*应用使用指南*&#x200B;文档中的[使用 Adobe I/0 与 Adobe Target 集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html){target=_blank}。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* 文档中的[选择使用 Adobe Analytics 和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* 文档中的[选择使用 Adobe Analytics 和 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html){target=_blank}。

### 第 2 步：创建体验片段

在 [!DNL AEM] 中创建[!UICONTROL 体验片段]。有关更多信息，请参阅：

* **AEM as a Cloud Service**：*Experience Manager as a Cloud Service* 指南中的[[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* 文档中的[[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* 文档中的[[!UICONTROL 体验片段]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=zh-Hans){target=_blank}。

### 第 3 步：配置 [!DNL AEM] 以与 [!DNL Target] 共享体验片段

1. 在 [!DNL AEM] 中，选择所需的体验片段或其所属的文件夹，然后单击&#x200B;**[!UICONTROL 属性]**。
2. 单击&#x200B;**[!UICONTROL 云服务]**&#x200B;选项卡，然后从&#x200B;**[!UICONTROL 云服务配置]**&#x200B;下拉列表中选择 **[!UICONTROL Adobe Target]**。

   上一步假设您的组织中已有人创建了 [!DNL Adobe Target] 配置。

3. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

### 第 4 步：发布体验片段并将它导出到 [!DNL Target] 中

根据您的 [!DNL AEM]版本，请参阅以下链接以获取分步说明：

* **AEM as a Cloud Service**：*Experience Manager as a Cloud Service* 指南中的[将 [!UICONTROL 体验片段]导出到 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* 文档中的[将体验片段导出到 Target](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=zh-Hans){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* 文档中的[将体验片段导出到 Target](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html){target=_blank}。

## 在 [!DNL Target] 活动中使用[!UICONTROL 体验片段] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，将在 [!DNL Target] 中的[!UICONTROL 选件]页面上显示体验片段。

[!DNL Target] 当前每 10 分钟查找一次要导入的[!UICONTROL 体验片段]。应在十分钟内可在 [!DNL Target] 中找到导入的体验片段，但此时长以后应可缩短。

体验片段作为 HTML 或 JSON 选件导入到 [!DNL Target] 中。该体验片段“主要”版本保留在 [!DNL AEM] 中。您无法在 [!DNL Target] 中编辑体验片段。

您可以按 [!UICONTROL HTML XF] 和 [!UICONTROL JSON XF] 进行过滤和搜索，以帮助您区分导出到 [!DNL Target] 的体验片段类型。

![按体验片段类型过滤：Target UI 中的 HTML 或 JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

可将光标悬停在列表中的某个体验片段上，然后单击[!UICONTROL 查看]图标 ![信息图标](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 以查看关于该体验片段的其他信息，包括其[!UICONTROL 名称]、[!UICONTROL 类型]、[!UICONTROL 选件 ID]、[!UICONTROL 选件路径]以及上次修改的相关信息。单击[!UICONTROL 选件使用情况]选项卡以查看引用此选件的活动。

![体验片段信息弹出窗口](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

可通过[可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) 或[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)在 [!DNL Target] 活动中使用[!UICONTROL 体验片段]。


>[!TIP]
>
>将人工智能、机器学习和推荐与[!UICONTROL 体验片段]结合使用：
>
>* 要充分利用 [!DNL Target] AI 和 ML 功能，您可以在创建 A/B 测试时选择[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)。
>
>* [!DNL Recommendations] 活动中不支持[!UICONTROL 体验片段]。但是，要使用[!UICONTROL 体验片段]进行推荐，您可以创建[!UICONTROL  A/B 测试]活动（包括[!UICONTROL 自动分配]和[!UICONTROL 自动定位]）或[!UICONTROL 体验定位] (XT) 活动，并[包括推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)。


**通过 VEC 使用[!UICONTROL 体验片段]：**

1. 在 [!DNL Target] 的[视觉体验编辑器](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中创建或编辑体验时，单击要在页面上插入 [!DNL AEM] 内容的位置，然后选择所需的选项以显示[!UICONTROL 选择体验片段]列表。

   * [!UICONTROL 此项前插入]
   * [!UICONTROL 此项后插入]
   * [!UICONTROL 与体验片段交换]

   [!UICONTROL 体验片段]列表显示在现在从 [!DNL Target] 中原生提供的 [!DNL AEM] 中创建的内容。

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果要将此选项用于图像，请单击包含所需图像的容器元素。

   ![体验片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 完成]**。
1. 配置完活动。

   有关配置各种类型的活动的更多信息，请参阅以下主题：

   * **A/B 测试：**[创建 A/B 测试](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自动分配：**[自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自动定位：**[自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **自动个性化 (AP)：**[创建自动个性化活动](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **体验定位 (XT)：**[创建体验定位活动](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B 测试或 XT 活动中的推荐：**[推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md)

   无法在使用 VEC 创建的活动中使用在 [!DNL Target] 中导出为 JSON 的[!UICONTROL 体验片段]；仅在基于 VEC 的活动中支持 HTML [!UICONTROL 体验片段]。如果要使用 JSON [!UICONTROL 体验片段]，请在使用[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md)创建的活动中使用它们。

**通过基于表单的体验编辑器使用[!UICONTROL 体验片段]：**

1. 在 [!DNL Target] 的[基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，选择要在页面上插入 [!DNL AEM] 内容的位置，然后选择&#x200B;**[!UICONTROL 更改体验片段]**&#x200B;以显示[!UICONTROL 选择体验片段]列表。

   ![体验片段列表图像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL 体验片段]列表显示在现在从 [!DNL AEM] 中原生提供的 [!DNL Target] 中创建的内容。

1. 选择所需的体验片段，然后单击&#x200B;**[!UICONTROL 保存]**。
1. 配置完活动。

## 注意事项 {#considerations}

* [!DNL Target] 当前每 10 分钟查找一次要导入的[!UICONTROL 体验片段]。应在十分钟内可在 [!DNL Target] 中找到导入的体验片段，但此时长以后应可缩短。
* 体验片段作为 HTML 或 JSON 选件导入到 [!DNL Target] 中。该体验片段的“主要”版本保留在 [!DNL AEM] 中。您无法在 [!DNL Target] 中编辑体验片段。
* 因此，您无法使用 [!DNL Adobe I/O] 创建[!UICONTROL 体验片段]。请使用 AEM 创建[!UICONTROL 体验片段]，如上所述。
* 如果在 AEM 中更新体验片段，则必须再次发布该体验片段并将其导出到 [!DNL Target]，以使 [!DNL Target] 可使用最新更改。

## 从导出到 [!UICONTROL Target] 的[!UICONTROL 体验片段]中删除 ClientLib 和无关的 HTML

在 AEM 投放的页面上使用体验片段选件配合 [!DNL Target] 时，目标页面已包含所有必要的客户端库。另请注意，选件中的无关 HTML 元素也不是必需的。

有时整个 HTML 页面包裹住体验片段，并因此导致问题。确保体验片段是一小段 HTML，而不是包含 HTML、HEAD、BODY 等的完整 HTML 页面。

有关更多信息，请参阅以下博客帖子：[AEM 6.5：从导出到 Target 的[!UICONTROL 体验片段]中删除客户端库](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}。

## 培训视频：使用 AEM [!UICONTROL 体验片段]配合 [!DNL Adobe Target]

以下视频展示如何设置和使用[!UICONTROL 体验片段]：

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>已删除在 4:54 讨论的 [!DNL AEM] 深度链接功能。

有关更多详细信息，请参阅 *AEM Sites 视频和教程*&#x200B;页面上的[使用[!UICONTROL 体验片段]配合 Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)。