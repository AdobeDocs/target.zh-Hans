---
keywords: Target;报表;报表设置;超常订单;极端值
description: 了解如何在Adobe [!DNL Target] 中排除影响报表的极端值，以便少数异常订单不会影响您的活动结果。
title: 如何在报表中排除极端值？
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
TQID: https://experienceleague.adobe.com/yQtG4u-sLVJ66PezWW9ZgmY8ZuK177m-hLdQq-zlmfI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 62%

---

# 排除极端值

您可以排除影响[!DNL Adobe Target]中报表的极端值，以便少数异常订单不会影响您的活动结果。 例如，与个人购买者购买个人制服相比，一位教练为整个团队购买统一制服可能会产生一个超常订单。

>[!NOTE]
>
>[!UICONTROL 排除极端值]标记仅适用于具有[!UICONTROL 收入]和[!UICONTROL 参与]度量类型的活动。

极端值会根据下面所述的规则自动标记。 您可以在查看报表中的极端值和排除报表中的极端值之间进行切换。 在活动运行一小时，或订单量达到 15 个后（以先到者为准），活动将排除其极端值。

如果某个值与根据上个月（从当前时间往回算起）的数据计算出来的平均订单值之间的标准偏差超过 +/- 3，则该值会被视为极端值。

例如，使用 RPV 时，极端值筛选器往往很有用。 RPV 结合了转化率和平均订单值，并且通常会暴露这些量度的不稳定性。 如果您使用 RPV 并确定这些订单显现出未被正常分配的状态，则在应用超常订单筛选器时可能会看到更正常的结果。

如果某个值被标记为极端值，则其订单值会被替换为上个月体验的平均订单值（排除极端值后计算出来的平均值）。 在[!UICONTROL 订单详细信息]报表和CSV下载中（用于每日结果），该订单也被标记为极端。

**要从报表中排除极端值，请执行以下操作：**

1. 打开包含[!UICONTROL 收入]或[!UICONTROL 参与]度量类型的活动，然后单击&#x200B;**[!UICONTROL 报表]**&#x200B;选项卡。
1. 单击“报表设置”（![报表设置图标](/help/main/assets/icons/Setting.svg)）图标以显示&#x200B;**[!UICONTROL 设置]**&#x200B;对话框。

1. 根据需要将&#x200B;**[!UICONTROL 排除极端值]**&#x200B;切换开关滑动到“开”或“关”位置。
1. 单击&#x200B;**[!UICONTROL 保存]**。
