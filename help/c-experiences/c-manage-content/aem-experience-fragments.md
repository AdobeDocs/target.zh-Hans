---
description: 有关在 Target 活动中使用在 Adobe Experience Manager (AEM) 中创建的体验片段以帮助优化或个性化的信息。
keywords: 体验;AEM;Adobe Experience Manager;导出到 Adobe Target;体验片段;片段;XF
seo-description: 有关在 Target 活动中使用在 Adobe Experience Manager (AEM) 中创建的体验片段以帮助优化或个性化的信息。
seo-title: AEM 体验片段
solution: Target
title: AEM 体验片段
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 16bbe7b628c6f72f63465d4dfd4ca0e9c63b57e7

---


# AEM 体验片段{#aem-experience-fragments}

有关在 Target 活动中使用在 Adobe Experience Manager (AEM) 中创建的体验片段以帮助优化或个性化的信息。

## AEM 体验片段 {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

有关在 Target 活动中使用在 Adobe Experience Manager (AEM) 中创建的体验片段以帮助优化或个性化的信息。

>[!NOTE]
>
>此功能要求您是 Adobe Experience Manager (AEM) 客户。有关更多信息，请参阅下面的[要求](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)。

## 概述 {#section_95A91830530F493B81C5C9CDB9B783EA}

通过在 Target 活动中使用 AEM 中创建的体验片段，您可以将 AEM 中这一简单易用的功能与 Target 中强大的自动化智能 (AI) 和机器学习 (ML) 功能结合使用，从而测试和个性化大量体验。

AEM 可将您的所有内容和资产汇集到一个中心位置，以帮助实施您的个性化策略。通过 AEM，您能够在一个位置轻松创建适用于桌面、平板电脑和移动设备的内容，而无需编写代码。您无需为每种设备分别创建页面，因为 AEM 可以使用您的内容自动调整每个体验。

Target 允许您根据一组基于规则且由 AI 驱动的机器学习方法（这些方法包含行为、上下文和离线变量），交付大量的个性化体验。通过 Target，您可以轻松地设置并运行 A/B 活动和多变量 (MVT) 活动，从而确定最佳的选件、内容和体验。

现在，有些从事优化和个性化工作的专业人士正在使用 Target 促进其业务发展，对这类人士而言，体验片段代表了在将内容/体验创建器与管理器关联方面迈出了巨大的一步。

## 要求 {#section_AE6F0971E1574B3AA324003599B96E5A}

您必须已在 Target 中配置体验片段功能。此外，您还必须使用 AEM 6.3 以及相应的 Service Pack，或者使用 AEM 6.4（或更高版本）。您的客服专员可以帮助您确保满足使用此功能的要求：

* Adobe Experience Manager 6.4（或更高版本）。
* Adobe Experience Manager 6.3 SP2（或更高版本）。
* Adobe Target Standard 或 Adobe Target Premium 帐户。
* 联系 Adobe Target 客户关怀团队以启用集成并为您提供身份验证详细信息。

## 在 AEM 中创建并配置体验片段 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要在 Target 中使用 AEM 体验片段，您必须执行以下步骤：

### 步骤 1：将 AEM 与 Target 集成

有关详细信息，请参阅：

* **AEM 6.3：** Adobe Experience Manager 6.3 [](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html)文档中的_选择使用 Adobe Analytics 和 Adobe Target_。
* **AEM 6.4：** Adobe Experience Manager 6.4 [](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html)文档中的_选择使用 Adobe Analytics 和 Adobe Target_。

### 步骤 2：创建体验片段

体验片段是在 AEM 中创建的。有关详细信息，请参阅：

* **AEM 6.3：** Adobe Experience Manager 6.3 [](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html)文档中的*体验片段*。
* **AEM 6.4：** Adobe Experience Manager 6.4 [](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html)文档中的*体验片段*。

### 步骤 3：配置 AEM 以与 Target 共享体验片段

1. 在 AEM 中，选择所需的体验片段或其包含文件夹，然后单击[!UICONTROL 属性]。
2. 单击[!UICONTROL 云服务]选项卡，然后从[!UICONTROL 云服务配置]下拉列表中选择 [!UICONTROL Adobe Target]。

   >[!NOTE]
   >
   >上一步骤假设贵组织中已有人创建了 Adobe Target 配置。

3. 单击[!UICONTROL 保存并关闭]。

### 步骤 4：发布体验片段并将其导出到 Target

**AEM 6.3：**

1. 在 AEM 中，选择所需的体验片段，单击[!UICONTROL 发布]选项卡，然后单击[!UICONTROL 发布]按钮。
2. 在 AEM 中，选择所需的体验片段，单击[!UICONTROL 导出到 Adobe Target]，然后单击[!UICONTROL 确定]。

   ![](assets/experience_fragment_export_to_target.png)

**AEM 6.4：**

1. 在 AEM 中，选择所需的体验片段，然后单击[!UICONTROL 导出到 Adobe Target]。

   ![](assets/experience_fragment_export_to_target.png)

2. 在显示的对话框中，选择[!UICONTROL 发布]以将体验片段中的所有资产发布到 [!DNL Target]。

## 在Target活动中使用体验片段 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后，体验片段会显示在 Target 的“[!UICONTROL 选件]”页面中。

>[!NOTE]
>
>当前，Target 会每隔 10 分钟查找一次要导入的体验片段。导入的体验片段应在十分钟内可在 Target 中使用，但是以后，此时间应会缩短。

>[!IMPORTANT]
>
>当前，体验片段是作为 HTML 选件导入到 Target 中的。请注意，体验片段的“母”版仍保留在 AEM 中。因此，您无法在 Target 中编辑体验片段。

您可以将鼠标悬停在列表中某个体验片段的上方，然后单击“查看”图标 (![](assets/icon_info.png)

) 以查看有关体验片段的其他信息，其中包括其公共选件交付 URL、其 AEM 路径以及用于打开 AEM 内部体验片段的深层链接。

您可以在 Target 活动中通过可视化体验编辑器 (VEC) 或基于表单的体验编辑器来使用体验片段。

>[!NOTE]
>
>要充分利用 Target 的 AI 和 ML 功能，您可以在创建 A/B 测试时选择[自动分配](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)或[自动个性化](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)。

**通过 VEC 使用体验片段：**

1. 在 Target 中，在[可视化体验编辑器](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)中创建或编辑体验时，单击要将 AEM 内容插入到的页面位置，然后选择 **[!UICONTROL 与体验片段交换]**，以显示“[!UICONTROL 选择体验片段]”列表。

   >[!NOTE]
   >
   >[!UICONTROL 与体验片段交换]选项不适用于图像。如果您想要对图像使用此选项，请单击包含所需图像的容器元素。

   “[!UICONTROL 体验片段]”列表显示了在 AEM 中创建的所有内容，这些内容现在可从 Target 中以本地方式使用。

   ![](assets/experience_fragment_list.png)

1. 选择所需的体验片段，然后单击 **[!UICONTROL 保存]**。
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

1. 在 Target 中，在[基于表单的体验编辑器](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)中创建或编辑体验时，选择要将 AEM 内容插入到的页面位置，然后选择 **[!UICONTROL 更改体验片段]**，以显示“[!UICONTROL 选择体验片段]”列表。

   ![](assets/experience_fragment_list.png)

   “[!UICONTROL 体验片段]”列表显示了在 AEM 中创建的所有内容，这些内容现在可从 Target 中以本地方式使用。

1. 选择所需的体验片段，然后单击 **[!UICONTROL 保存]**。
1. 完成活动配置。

## 培训视频：在 Adobe Target 中使用 AEM 体验片段{#section_C0EDC54063464F41A182492D2045BC64}

以下视频演示了如何设置和使用体验片段：[在 Adobe Target 中使用 AEM 体验片段](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html)。
