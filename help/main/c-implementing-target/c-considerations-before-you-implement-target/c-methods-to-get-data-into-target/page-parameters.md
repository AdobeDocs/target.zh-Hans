---
keywords: 实施；设置；设置；页面参数
description: 将数据导入 [!DNL Target] 使用页面参数。
title: 如何将数据导入 [!DNL Target] 使用页面参数？
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 44%

---

# 页面参数

页面参数（也称为“mbox参数”）是直接通过页面代码传入的名称/值对，不会存储在访客的配置文件中以供将来使用。

页面参数可用于将页面数据发送到Target，而无需与访客的配置文件一起存储以供将来定位使用。 而是用来描述页面或用户在特定页面上执行的操作。

## 格式

页面参数通过服务器调用作为字符串名称/值对传递给 Target。参数名称和值是可自定义的（但存在一些用于特定用途的“保留名称”）。

### 示例

* `page=productPage`

* `categoryId=homeLoans`

## 用例示例

* **产品页面**:发送有关已查看的特定产品的信息(此方法就是Recommendations的工作方式)
* **订单详细信息**:发送订单ID、orderTotal等以进行订单收集
* **类别亲和度**：将已查看的类别信息发送到 Target，以了解用户对特定站点类别的亲和度
* **第三方数据**：发送来自第三方数据源的信息，例如天气定位提供程序、帐户数据（例如 DemandBase）、人口统计数据（例如 Experian）等。

## 方法的好处

数据会实时发送到Target，并且可以在同一服务器调用数据传入时使用该数据。

## 注意事项

* 需要更新页面代码（直接或通过标记管理系统）。
* 如果数据必须用于在后续的页面/服务器调用中进行定位，则必须将其转换为配置文件脚本。
* 查询字符串只能包含符合 [Internet 工程任务组 (IETF) 标准](https://www.ietf.org/rfc/rfc3986.txt)的字符。

   除了IETF站点上提到的那些字符之外，Target还允许在查询字符串中使用以下字符：

   ```< > # % " { } | \ ^ [ ] ` ```

   其他所有字符都必须采用 URL 编码。该标准指定以下格式( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) )，如下图所示：

   ![](assets/ietf1.png)

   或者，简单显示完整列表：

   ![](assets/ietf2.png)

## 代码示例

targetPageParamsAll（将参数附加到页面上的所有 mbox 调用）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（将参数附加到页面上的全局 mbox）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

## 相关信息的链接

推荐：[按照页面类型实施](https://developer.adobe.com/target/implement/recommendations/)

订单确认：[跟踪转化](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

类别亲和度：[类别亲和度](/help/main/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
