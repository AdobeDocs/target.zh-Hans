---
keywords: 包含规则；包含条件；推荐；促销；动态过滤；动态；参数匹配
description: 了解如何通过比较项（实体）与请求（API或mbox）中的值，在Adobe [!DNL Target] Recommendations中动态筛选。
title: 如何在Recommendations活动中按参数匹配过滤？
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 10%

---

# ![PREMIUMParameter](/help/assets/premium.png) 匹配

通过比较项（实体）与请求（API或mbox）中的值来动态筛选。

例如，只推荐与“行业”页面参数或其他参数（如设备尺寸或地理位置）匹配的内容，如以下示例中所示。

* 屏幕宽度和高度的Mbox参数可用于目标移动访客，仅推荐移动设备和附件。
* 创建一个推荐规则，该规则仅返回与访客使用页面视图的移动设备的屏幕高度匹配或超过的畅销手机。
* 区域地理位置参数可用于在冬季返回工具建议。 在下雪的地区，可以推荐访客使用吹雪机和其他降雪工具，但不推荐在没有下雪的地区的访客使用。

>[!NOTE]
>
>如果活动是在2016年10月31日之前创建的，则如果投放使用“参数匹配”过滤器，则该过滤器将失败。 要解决此问题，请执行以下操作：
>
>* 创建一个新的活动并在其中添加您的标准。
>* 使用不包含“参数匹配”筛选器的标准。
>* 从您的标准中删除“参数匹配”筛选器。


## 参数匹配示例

[!UICONTROL 参] 数匹配允许您推荐与页面参数或访客参数（如设备尺寸或地理位置）匹配的内容，如下例所示：

[!DNL Recommendations] 可以匹配在调用中发送的参 [!DNL Target] 数值。在此实例中，[!DNL Target]会根据在[!DNL Target]调用中发送的屏幕高度和宽度参数检测访客是否使用移动设备，并将仅推荐移动设备项。

请考虑以下示例目标调用：

![目标呼叫](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

在访客查看的页面上，他/她将看到移动设备产品。

![移动设备产品](/help/c-recommendations/c-algorithms/assets/phones.png)
