---
keywords: 实施；设置；设置；批量配置文件更新
description: 将数据导入 [!DNL Target] 使用批量配置文件更新API。
title: 如何将数据导入 [!DNL Target] 是否使用批量配置文件更新API?
feature: Implementation
role: Developer
exl-id: 068658fc-7082-425a-87c1-dd0de03cdc71
source-git-commit: 95566b428d7404b0f336221881849c13707bb314
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 76%

---

# 批量配置文件更新 API

通过API，将.csv文件发送到 [!DNL Adobe Target] 通过为许多访客更新访客配置文件。 每个访客配置文件均可以在一次调用中通过多个页面内配置文件属性进行更新。

此选项与“客户属性”类似，但有一些差异：

* 客户属性使用 FTP 上传，而 Target 批量配置文件更新 API 则使用 HTTP POST API。
* 客户属性数据可以与 Analytics 共享。批量配置文件更新只能在 Target 中使用。
* 客户属性支持为尚未使用 Target 的用户创建配置文件。批量配置文件更新 API 仅更新现有的 Target 配置文件。
* 客户属性要求使用Experience CloudID(ECID)和源ID，如CRM ID或忠诚度ID。
* 批量配置文件更新 API 需要 TNT ID 或 `mbox3rdPartyId`。
* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 格式

.csv 文件必须通过访客的 Target PCID 或 mboxThirdPartyId 对每个访客进行引用。不支持 Experience Cloud ID (ECID)。所有配置文件属性/值都可通过 API 创建和更新。格式详细信息可在 API 文档中找到。

## 用例示例

您在 CRM 或其他内部系统中存储那些要持续更新到 Target 的有关访客的宝贵数据，从而无需在您的页面实施中暴露配置文件数据。

## 方法的好处

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

## 注意事项

批处理文件必须小于 50 MB。另外，每次上传的总行数不应超过 500,000 行。

在后续的批处理中，您在 24 小时内上传的数量或行数不受限制。但是，为了确保其他进程能够高效运行，这些数据的吸收过程在工作时间可能会受到节流限制。

对于相同 thirdPartyId，如果连续的 [V2 批量更新调用](https://developers.adobetarget.com/api/#updating-profiles)之间没有 mbox 调用，则会覆盖在第一次批量更新调用中更新的属性。

## 代码示例

请参阅[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)。

### 相关信息的链接

[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)
