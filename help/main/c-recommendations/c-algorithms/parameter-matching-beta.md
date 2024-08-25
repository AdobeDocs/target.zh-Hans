---
keywords: 包含规则；包含标准；推荐；促销活动；促销活动；动态筛选；动态；参数匹配
description: 了解如何通过比较项目（实体）与Adobe [!DNL Target] Recommendations中的值（API或mbox）来动态筛选。
title: 如何在Recommendations活动中按参数匹配进行筛选？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: f77c321b-57b0-4610-b58f-3765ace2d6ad
source-git-commit: 22b0ba18efb736b291f9b7951acd9f706beedbe1
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 10%

---

# [!UICONTROL Parameter Matching]

通过比较项目（实体）与请求中的值（API或mbox）来进行动态筛选。

例如，只推荐与“行业”页面参数或其他参数（如设备尺寸或地理位置）匹配的内容，如以下示例所示。

* 屏幕宽度和高度的Mbox参数可用于定位移动访客，并仅推荐移动设备和附件。
* 创建一个推荐规则，该规则仅返回与访客正在查看页面的移动设备的屏幕高度匹配或超过其屏幕高度的畅销移动电话。
* 区域地理位置参数可用于在冬季返回对工具的推荐。 在下雪地区可以推荐使用吹雪机和其他降雪工具，但不在不下雪地区推荐使用这些工具。

>[!NOTE]
>
>如果活动是在2016年10月31日之前创建，则当它使用“参数匹配”过滤器时，交付会失败。 要解决此问题，请执行以下操作：
>
>* 创建一个新的活动并在其中添加您的标准。
>* 使用不包含“参数匹配”筛选器的标准。
>* 从您的标准中删除“参数匹配”筛选器。

## 参数匹配示例

[!UICONTROL Parameter Matching]允许您推荐与页面参数或访客参数（如设备维度或地理位置）匹配的内容，如以下示例所示：

[!DNL Recommendations]可以匹配[!DNL Target]调用中发送的参数值。 在此实例中，[!DNL Target]根据[!DNL Target]调用中发送的屏幕高度和宽度参数检测访客正在使用移动设备，并仅推荐属于移动设备的项目。

请考虑以下示例Target调用：

![目标调用](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

在访客正在查看的页面上，他或她将看到移动设备产品。

![移动设备产品](/help/main/c-recommendations/c-algorithms/assets/phones.png)
