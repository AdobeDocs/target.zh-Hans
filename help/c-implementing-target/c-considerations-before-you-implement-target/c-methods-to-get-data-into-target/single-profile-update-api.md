---
keywords: 实施；设置；设置；单个配置文件更新
description: 使用单个配置文件更新API将数据导入 [!DNL Target] 。
title: 如何使用单个配置文件更新API将数据导入 [!DNL Target] ?
feature: 实施
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 18b9a56b8aef2fdfb8a4431fec4ae3a65adcf067
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 42%

---

# 单个配置文件更新 API

与批量配置文件更新API几乎相同，只是一次更新一个访客配置文件，这与API调用中的一行相同，而不是与.csv文件相同。

## 格式

必须通过 Target mboxPC 值或 mboxThirdPartyId 值对访客进行标识。不支持 Experience Cloud ID (ECID)。

## 使用示例

您希望在访客执行某些离线操作时实时更新Target。 行动包括到达呼叫中心、提供贷款、使用店内会员卡、访问网亭等。

## 方法的好处

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

## 注意事项

每 24 小时限制 1,000,000（100 万）次 API 调用

仅限配置文件更新。无法为尚未使用 Target 的潜在用户创建配置文件。

## 代码示例

GET和POST。`https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)

