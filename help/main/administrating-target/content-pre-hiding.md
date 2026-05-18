---
keywords: 闪烁，预隐藏，预隐藏，个性化，实施，防闪烁， VEC，可视化体验编辑器
description: 了解内容预隐藏如何通过使用帐户级别设置、轻量级页面库和按活动控件，通过仅隐藏活动Adobe Target个性化将更改的区域来减少闪烁。
title: 用于个性化体验的内容预隐藏
feature: Administration & Configuration
role: Admin
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#beta newtab=true" tooltip=" [!DNL Adobe Target] 中有哪些 Beta 功能。"
hide: true
source-git-commit: 77741253fdfb007d0eda0c57fe293df2f9c638a2
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 3%

---

# 用于个性化体验的内容预隐藏

>[!AVAILABILITY]
>
>个性化内容的内容预隐藏可用作&#x200B;**测试版**&#x200B;功能。

当访客加载页面时，默认内容可能会短暂出现，然后由[!DNL Adobe Target]中的个性化内容替换。 该可见开关通常称为&#x200B;**闪烁**，这是个性化项目常见的体验问题。

通过内容预隐藏，您可以通过仅隐藏活动在页面加载期间个性化的页面部分来管理闪烁，这样客户看到的闪烁和屏幕空置时间就会减少。

下面是内容预隐藏的工作方式，通过页面实施和每个活动的选择，从帐户默认值开始进行。

1. 为帐户启用内容预隐藏以设置全局默认值。 默认情况下处于关闭状态。 [了解详情](#content-pre-hiding-enable-account)

1. 将内容预隐藏库添加到您运行个性化活动的所有页面的`<head>`。

1. [!DNL Target]从实时[!UICONTROL Visual Experience Composer]和[!UICONTROL Enhanced Experience Composer]活动中生成规则集。 规则集列出了投放可能更改的选择器和区域。

   请注意，不支持[!UICONTROL Form-Based Composer]活动。

1. 库将从Adobe CDN中提取该规则集，并仅在个性化内容仍在加载时预隐藏匹配元素。

1. 在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;中，您可以为各个活动禁用&#x200B;**[!UICONTROL Content pre-hiding]**，但前提是在帐户级别启用。 [了解详情](#content-pre-hiding-activity)

## 为实例启用内容预隐藏 {#content-pre-hiding-enable-account}

>[!IMPORTANT]
>
>要为实例启用内容预隐藏，您必须是&#x200B;**管理员**。

在启用内容预隐藏之前，它将对实例处于关闭状态。 使用&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;启用该功能，设置默认值，并访问实施团队的下载内容。

1. 在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**。

1. 从&#x200B;**[!UICONTROL Content pre-hiding]**&#x200B;菜单中，启用内容预隐藏选项。

   ![](assets/content-pre-hiding-1.png)

1. 如果需要，可在秒内更新&#x200B;**[!UICONTROL Pre-hiding timeout]**。

1. 单击 **[!UICONTROL Save]**。 这会将闪烁管理设置应用于您的实例。

1. 启用后，单击&#x200B;**[!UICONTROL Download]**，然后将文件添加到页面`<head>`，使其在[!DNL at.js]或[!DNL Web SDK]之前加载。 有关完整的实施说明，请参阅[内容预隐藏SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/prehide-sdk)。

   ![](assets/content-pre-hiding-2.png)

现在，您的实例使用保存的内容预隐藏和超时设置作为选择加入的活动的默认设置。

## 为活动启用内容预隐藏 {#content-pre-hiding-activity}

在为实例启用预隐藏的情况下，选择每个活动是否在&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;中使用它。 为其启用预隐藏的活动在活动时包括在目标行为中。

然后，[!DNL Target]根据在[!UICONTROL Visual Experience Composer] (VEC)和[!UICONTROL Form-Based Composer]中创作的实时活动构建轻量级规则集，其中描述了选择器和投放可更改的区域。

创建或编辑活动时：

1. 访问要启用预隐藏选项的活动。

1. 访问&#x200B;**[!UICONTROL Edit activity]**&#x200B;下拉列表并选择&#x200B;**[!UICONTROL Edit Goals & Settings]**。

   ![](assets/content-pre-hiding-3.png)

1. 从&#x200B;**[!UICONTROL Content pre-hiding]**&#x200B;菜单中，打开&#x200B;**[!UICONTROL Enable content pre-hiding]**&#x200B;选项以选择加入或退出此活动的预隐藏。

   ![](assets/content-pre-hiding-4.png)

1. 完成后，单击&#x200B;**[!UICONTROL Save & Close]**。

在保存并在活动上线或被停用后，会更新规则集，以便预隐藏与实际交付的内容保持一致，而无需编辑每个启动项的页面代码。

在访客端，库会在每次页面加载时从Adobe CDN中检索该规则集，并仅在需要时预隐藏匹配元素，直到个性化内容准备就绪为止。
