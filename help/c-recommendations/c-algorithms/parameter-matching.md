---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: 在Adobe TargetRecommendations，通过比较项（实体）与请求（API或mbox）中的值来动态筛选。
title: Adobe TargetRecommendations动态包含规则中参数匹配的过滤
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![PREMIUM参数](/help/assets/premium.png) 匹配

通过比较项（实体）与请求（API或mbox）中的值来动态筛选。

例如，只推荐与“行业”页面参数或其他参数（如设备尺寸或地理位置）匹配的内容，如以下示例所示。

* 屏幕宽度和高度的Mbox参数可用于目标移动访客，仅推荐移动设备和附件。
* 区域地理位置参数可用于在冬季返回工具的建议。 在下雪的地区，可以推荐访客使用吹雪机和其他降雪工具，但在没有下雪的地区，不推荐访客使用。

>[!NOTE]
>
>如果活动是在2016年10月31日之前创建的，则如果投放使用“参数匹配”过滤器，则该数据将失败。 要解决此问题，请执行以下操作：
>
>* 创建一个新的活动并在其中添加您的标准。
>* 使用不包含“参数匹配”筛选器的标准。
>* 从您的标准中删除“参数匹配”筛选器。


可用的运算符：

* 等于
* 不等于
* 包含
* 不包含
* 始于
* 止于
* 大于或等于
* 小于或等于
* 介于