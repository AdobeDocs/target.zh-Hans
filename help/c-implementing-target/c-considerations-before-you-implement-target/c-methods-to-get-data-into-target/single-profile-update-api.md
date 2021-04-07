---
keywords: 实现；实现；设置；设置；单个用户档案更新
description: 使用单个用户档案更新API将数据导入目标。
title: 如何使用单个用户档案更新API将数据导入目标?
feature: 实施
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 41%

---

# 单个配置文件更新 API

几乎与批量用户档案更新API相同，但每次更新一个访客用户档案，在API调用中排行，而不是.csv文件。

## 格式

必须通过 Target mboxPC 值或 mboxThirdPartyId 值对访客进行标识。不支持 Experience Cloud ID (ECID)。

## 使用示例

您希望在目标执行某些脱机操作时实时更新访客。 行动包括到达呼叫中心、为贷款提供资金、使用店内忠诚卡、访问自助终端等。

## 方法的优势

配置文件属性的数量没有限制。

通过该站点发送的配置文件属性可以通过 API 进行更新，反之亦然。

## 注意事项

每 24 小时限制 1,000,000（100 万）次 API 调用

仅限配置文件更新。无法为尚未使用 Target 的潜在用户创建配置文件。

## 代码示例

GET和POST。`https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

## 相关信息的链接

[更新配置文件](https://developers.adobetarget.com/api/#updating-profiles)
