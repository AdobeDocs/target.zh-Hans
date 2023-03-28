---
keywords: 体验；JSON;AEM;Adobe Experience Manager；导出到Adobe Target；内容片段；片段；CF;CF
description: 了解如何使用 [!DNL Adobe Experience Manager] [!UICONTROL 内容片段] in [!DNL Adobe Target] 活动。
title: 如何使用 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL 内容片段]?
feature: Integrations
source-git-commit: cdb0e3f3e1ebb2f9076d3994aed533bd7c296fad
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---

# AEM [!UICONTROL 内容片段]

使用 [!UICONTROL 内容片段] (CF)在中创建 [!DNL Adobe Experience Manager] (AEM)in [!DNL Target] 活动来帮助优化或个性化。

>[!NOTE]
>
>使用AEM时，请考虑以下事项 [!UICONTROL 内容片段] in [!DNL Target]:
> 
>* 此功能要求您是 [!DNL Adobe Experience Manager] (AEM)客户。 有关更多信息，请参阅 [要求](#section_AE6F0971E1574B3AA324003599B96E5A) 下。
>
>* 此功能适用于以下活动类型： [!UICONTROL A/B测试], [!UICONTROL 自动分配], [!UICONTROL 自动定位], [!UICONTROL Automated Personalization] （美联社）和 [!UICONTROL 体验定位] (XT)。 此功能在 [!UICONTROL 多变量测试] (MVT)和 [!UICONTROL Recommendations] 活动。
>
>* 您可以使用 [!UICONTROL 内容片段] in [!DNL Target] 活动 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 仅。 您不能使用 [!UICONTROL 内容片段] 使用 [!UICONTROL 可视化体验编辑器] (VEC)。


详细了解AEM [!UICONTROL 内容片段] 和 [!UICONTROL 体验片段]，请参阅 [AEM [!UICONTROL 体验片段] 和 [!UICONTROL 内容片段] 概述](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要求 {#requirements}

您必须配置 [!UICONTROL 内容片段] 功能 [!DNL Target]. 此外，您必须使用 [!DNL AEM] as a Cloud Service。 您的客服专员可以帮助您确保满足使用此功能的要求：

联系人 [Adobe Target客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ，以启用集成并向您提供身份验证详细信息。

## 配置和使用 [!UICONTROL 内容片段] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

要导出，请执行以下操作 [!UICONTROL 内容片段] 使用 [!DNL Target] 活动时，您必须在AEM中执行一些初步步骤。 有关更多信息，请参阅 [将内容片段导出到Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

有关设计、创建、策划和发布的信息 [!UICONTROL 内容片段]，请参阅 [[!UICONTROL 内容片段]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## 使用 [!UICONTROL 内容片段] in [!DNL Target] 活动 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

执行上述任务后， [!UICONTROL 内容片段] 显示在 [!UICONTROL 选件] 页面 [!DNL Target].

[!DNL Target] 当前正在查找 [!UICONTROL 内容片段] 每10分钟导入一次。 导入的 [!UICONTROL 内容片段] 应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。

的 [!UICONTROL 内容片段] 导入到 [!DNL Target] 作为JSON选件。 那个 [!UICONTROL 内容片段] “primary”版本仍保留在 [!DNL AEM]. 您无法编辑 [!UICONTROL 内容片段] in [!DNL Target].

您可以按 [!UICONTROL HTML体验片段], [!UICONTROL JSON XF]和 [!UICONTROL 内容片段] 以帮助您区分导出到的不同选件类型 [!DNL Target].

![按内容片段类型过滤：HTML或JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

您可以将鼠标悬停在 [!UICONTROL 内容片段] ，然后单击 [!UICONTROL 查看] 图标 ![“信息”图标](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 查看有关 [!UICONTROL 内容片段]，包括 [!UICONTROL AEM路径] 和 [!UICONTROL AEM深层链接]. 单击 [!UICONTROL 选件使用情况] 选项卡，以查看引用此选件的活动。

![内容片段信息弹出窗口](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

您可以使用 [!UICONTROL 内容片段] in [!DNL Target] 活动 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md) 仅。 您 *无法* 消费 [!UICONTROL 内容片段] in [!DNL Target] 活动 [可视化体验编辑器](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)。 [!UICONTROL 内容片段] 在中导出为JSON [!DNL Target] 和不能用在使用VEC创建的活动中。

>[!TIP]
>
>将人工智能、机器学习和推荐与 [!UICONTROL 内容片段]:
>
>* 要充分利用 [!DNL Target] AI和ML功能，您可以选择 [自动分配](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) 或 [自动定位](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 创建A/B测试时。
>
>* [!UICONTROL 内容片段] 不支持 [!DNL Recommendations] 活动。 但是，要使用 [!UICONTROL 内容片段] 对于“推荐”，您可以创建 [!UICONTROL A/B测试] 活动(包括 [!UICONTROL 自动分配] 和 [!UICONTROL 自动定位])或 [!UICONTROL 体验定位] (XT)活动和 [将推荐作为选件](/help/main/c-recommendations/recommendations-as-an-offer.md).


**消费 [!UICONTROL 内容片段] 使用 [!UICONTROL 基于表单的体验编辑器]:**

1. 在 [!DNL Target]，在中创建或编辑体验时 [基于表单的体验编辑器](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)，选择要插入的页面位置 [!DNL AEM] 内容，然后选择 **[!UICONTROL 更改内容片段]** 以显示 [!UICONTROL 选择内容片段] 列表。

   ![content_fragment_list图像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   的 [!UICONTROL 内容片段] 列表显示在 [!DNL AEM] 现在可从内部本地访问 [!DNL Target].

1. 选择所需的 [!UICONTROL 内容片段]，然后单击 **[!UICONTROL 保存]**.
1. 完成活动配置。

## 注意事项 {#considerations}

* [!DNL Target] 当前正在查找 [!UICONTROL 内容片段] 每10分钟导入一次。 导入的 [!UICONTROL 内容片段] 应在 [!DNL Target] 10分钟内，但此时间范围应会缩短。
* 的 [!UICONTROL 内容片段] 导入到 [!DNL Target] 作为JSON选件。 的 [!UICONTROL 内容片段] “primary”版本仍保留在 [!DNL AEM]. 您无法编辑 [!UICONTROL 内容片段] in [!DNL Target].
* 您无法创建 [!UICONTROL 内容片段] 使用 [!DNL Adobe I/O]. 创建 [!UICONTROL 内容片段] 使用AEM，如上所述。
* 如果您更新了 [!UICONTROL 内容片段] 在AEM中， [!UICONTROL 内容片段] 必须发布并导出到 [!DNL Target] 再次如此 [!DNL Target] 可以使用最新更改。