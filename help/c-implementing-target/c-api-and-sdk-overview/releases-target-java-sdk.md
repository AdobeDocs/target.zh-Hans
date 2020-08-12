---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: 与Adobe Target的Java SDK相关的发行说明。
title: 与Adobe Target的Java SDK相关的发行说明。
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# 发行说明-目标Java SDK

与目标Java SDK相 [关的发行说明](https://github.com/adobe/target-java-sdk)。

Java [!DNL Target] SDK允许您在服 [!DNL Target] 务器端部署。 此Java SDK可帮助您轻松 [!DNL Target] 与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。

Java SDK在通过我们的投放API进行集成时引入了最佳实践 [!DNL Target] 并消除了复杂性，使您的工程团队能够专注于业务逻辑。

通过新的目标Java SDK在Adobe技术博客——服 [务器端优化中进一步了解目标Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。

## 版本1.1.0（2019年12月16日）

以下部分提供有关目标Java SDK版本1.1.0的更多信息：

### 为管理控制台帮助添加了

* 由于@hisham-hassan提供的开放源码贡献，增加了对代理配置的支持。

## 版本1.0.1（2019年11月11日）

以下部分提供有关目标Java SDK版本1.0.1的更多信息：

### 固定

* 在目标请求中发送补充数据ID，即使不存在访客API cookie。

## 版本1.0.0（2019年10月31日）

以下各节提供有关目标Java SDK版本1.0.0的更多信息：

### 为管理控制台帮助添加了

* [目标视图投放v1 API支持](https://developers.adobetarget.com/api/delivery-api/) ，包括页面加载和视图预取。
   * 完全支持提供在Visual Experience Composer(VEC)中创作的所有类型优惠。
* 支持预取和通知，可通过缓存预取的内容实现性能优化。
* 支持通过在服务 [!DNL Target] 器端和 `serverState`客户端 [!DNL Target] 部署时在混合集成中优化性能。
   * 我们引入了一个名为的 `serverState` 设置，该设置包含通过服务器端检索的体验，因此at.js v2.2+不会再进行服务器调用来检索体验。 此方法优化页面加载性能。
* 在GitHub上以目标 [Java SDK的形式开放](https://github.com/adobe/target-java-sdk)。
* 验证SDK API方法参数。
* 添加了自述文件、示例和单元测试。
* 添加了CoC、贡献指南、公关和期刊模板。

