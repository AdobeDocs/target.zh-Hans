---
keywords: 实现；实现；设置；设置；页面参数
description: 使用页面参数将数据导入目标。
title: 如何使用页面参数将数据导入目标?
feature: 实施
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: 8a12ef3581d3f99f21c0d6d50af0ac09e6aebd4c
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 45%

---

# 页面参数

页面参数（也称为“mbox参数”）是直接通过页面代码传递的名称/值对，不会存储在访客用户档案中以供将来使用。

页面参数对于将页面数据发送到目标很有用，因为该访客无需与用户档案一起存储，以便将来进行定位。 而是用来描述页面或用户在特定页面上执行的操作。

## 格式

页面参数通过服务器调用作为字符串名称/值对传递给 Target。参数名称和值是可自定义的（但存在一些用于特定用途的“保留名称”）。

### 示例

* `page=productPage`

* `categoryId=homeLoans`

## 示例用例

* **产品页面**:发送有关查看特定产品的信息(此方法是Recommendations的工作方式)
* **订单详细信息**:发送订单ID、orderTotal等，用于订单收集
* **类别亲和度**：将已查看的类别信息发送到 Target，以了解用户对特定站点类别的亲和度
* **第三方数据**：发送来自第三方数据源的信息，例如天气定位提供程序、帐户数据（例如 DemandBase）、人口统计数据（例如 Experian）等。

## 方法的优势

数据会实时发送到目标，并且可以在同一服务器上使用，调用数据所传入的数据。

## 注意事项

* 需要更新页面代码（直接或通过标记管理系统）。
* 如果数据必须用于后续页面/服务器调用的定位，则必须将其转换为用户档案脚本。
* 查询字符串只能包含符合 [Internet 工程任务组 (IETF) 标准](https://www.ietf.org/rfc/rfc3986.txt)的字符。

   除了IETF站点上提到的字符之外，目标还允许在查询字符串中使用以下字符：

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   其他所有字符都必须采用 URL 编码。该标准指定以下格式([https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt))，如下所示：

   ![](assets/ietf1.png)

   或者，简单显示完整列表：

   ![](assets/ietf2.png)

## 代码示例

targetPageParamsAll（将参数附加到页面上的所有 mbox 调用）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（将参数附加到页面上的全局 mbox）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

mboxCreate 代码中的参数：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## 相关信息的链接

推荐：[按照页面类型实施](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

订单确认：[跟踪转化](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

类别亲和度：[类别亲和度](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
