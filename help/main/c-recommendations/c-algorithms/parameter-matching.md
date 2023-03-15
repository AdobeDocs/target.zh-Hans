---
keywords: 包含规则；包含标准；推荐；促销活动；动态筛选；动态；参数匹配
description: 了解如何在Adobe中动态筛选 [!DNL Target] Recommendations(通过比较项目（实体）与请求中的值（API或mbox）。
title: 如何在Recommendations活动中按参数匹配进行过滤？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---

# 参数匹配

通过比较项目（实体）与请求中的值（API或mbox）来进行动态筛选。

例如，只推荐与“行业”页面参数或其他参数（如设备维度或地理位置）匹配的内容，如以下示例中所示。

* 屏幕宽度和高度的mbox参数可用于定位移动访客，并且仅推荐移动设备和附件。
* 创建一个推荐规则，以仅返回与访客使用页面查看的移动设备的屏幕高度匹配或超过该设备屏幕高度的畅销手机。
* 区域地理位置参数可用于在冬季返回工具的建议。 在下雪的地区，可以向游客推荐吹雪机和其他减雪工具，但在没有下雪的地区，则不推荐游客。

>[!NOTE]
>
>如果活动是在2016年10月31日之前创建的，则如果活动使用“参数匹配”筛选器，则交付会失败。 要解决此问题，请执行以下操作：
>
>* 创建一个新的活动并在其中添加您的标准。
>* 使用不包含“参数匹配”筛选器的标准。
>* 从您的标准中删除“参数匹配”筛选器。


## 参数匹配示例

[!UICONTROL 参数匹配] 允许您推荐与页面参数或访客参数匹配的内容，例如设备维度或地理位置，如以下示例中所示：

[!DNL Recommendations] 可以匹配 [!DNL Target] 呼叫。 在本例中， [!DNL Target] 根据 [!DNL Target] 调用，并将仅推荐属于移动设备的项目。

请考虑以下示例Target调用：

![Target调用](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

访客在查看的页面上，将看到移动设备产品。

![移动设备产品](/help/main/c-recommendations/c-algorithms/assets/phones.png)
