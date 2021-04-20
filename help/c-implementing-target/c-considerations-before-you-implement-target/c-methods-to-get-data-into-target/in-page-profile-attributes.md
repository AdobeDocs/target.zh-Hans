---
keywords: 实现；实现；设置；设置；页面参数
description: 使用页面内目标属性将数据导入用户档案。
title: 如何使用页面内目标属性将数据导入用户档案?
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 56%

---

# 页面内用户档案属性

[!DNL Adobe Target]中的页内用户档案属性(也称为“in-mbox用户档案属性”)是直接通过页面代码传递的名称/值对，这些代码存储在访客用户档案中以供将来使用。

页面内配置文件属性允许将特定于用户的数据存储在 Target 的配置文件中，供以后进行定位和分段。

## 格式

页面内配置文件属性作为成对的字符串名称/值，通过服务器调用进行传递，且在属性名称前带有前缀“profile.”。

属性名称和值是可自定义的（但存在一些用于特定用途的“保留名称”）。

### 示例

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## 示例用例

* **登录信息**：根据用户的登录信息，将非 PII（个人身份信息）数据共享到 Target。此数据可以是会员资格状态、订单历史记录等。
* **存储信息**：跟踪哪个商店是该用户最喜欢的位置。
* **以前的互动**：跟踪用户以前在该网站上的操作，以便为其将来的个性化提供参考依据。

## 方法的优势

数据将实时发送到目标，并可用于数据传入的同一服务器调用。

## 注意事项

需要更新页面代码（直接或通过标记管理系统）。

属性和值在服务器调用中可见，因此访客可以查看这些值。如果共享信用范围等信息或其他可能的私人信息，则此方法可能不是最佳方法。

## 代码示例

targetPageParamsAll（将属性附加到页面上的所有 mbox 调用）：

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams（将属性附加到页面上的全局 mbox）：

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate 代码中的属性：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## 相关信息的链接

[配置文件属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[访客资料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
