---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: 与Adobe Target服务器端API相关的发行说明。
title: 与Adobe TargetNode.js SDK相关的发行说明。
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---


# 发行说明-目标Node.js SDK

与Adobe TargetNode.js [SDK相关的发行说明](https://github.com/adobe/target-nodejs-sdk)。

目标Node.js SDK允许您在服 [!DNL Target] 务器端部署。

此Node.js SDK可帮助您轻松 [!DNL Target] 与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。

Node.js SDK在通过我们的投放API与集成时引入最佳实践并消除 [!DNL Target] 复杂性，以便您的工程团队能够专注于业务逻辑。

通过目标技术博客——打开来源补充新的Adobe Target节 [点。js SDK进一步了解AdobeNode.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。

## 版本1.0.0（2019年10月9日）

以下各节提供有关目标Node.js SDK版本1.0.0的更多信息：

### 为管理控制台帮助添加了

* 目标视图投放v1 API支持，包括页面加载和视图预取。
* 完全支持提供在Visual Experience Composer(VEC)中创作的所有类型优惠。
* 通过缓存预取的内容支持预取和通知以实现性能优化。
* 支持在服务器端和客 [!DNL Target] 户端 `serverState` 部署 [!DNL Target] 时，通过在混合集成中优化性能。

   我们引入了一个名为的 `serverState` 设置，该设置包含通过服务器端检索的体验，因此at.js v2.2+不会再进行服务器调用来检索体验。 此方法优化页面加载性能。

* 在GitHub上以 [目标Node.js SDK的形式开放](https://github.com/adobe/target-nodejs-sdk)。
* 新 [的sendNotifications()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) ，用于将显示／单击的通知发送 [!DNL Target] 到通过getOffers()预取 [的内容](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers)。
* 简化的视图投放API请求构建，内部字段自动完成，默认值 `request.id`为( `request.context`例如，等等)。
* 验证SDK API方法参数。
* 更新了自述文件、示例和单元测试。
* 使用GitHub Actions设置新的CI流。
* 增加了CoC、贡献指南、公关和期刊模板

### 已将

* 项目已重命名 `target-nodejs-sdk`为。
* 主要重构，用目标视图投放v1 API替换目标BatchMbox v2 API。
* [create()API方法参数已修改](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) ，删除了冗余嵌套(请参阅此处的旧方 [法声明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate))。
* [getOffers()API方法参数已](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) 修改(请参阅此处的旧方 [法声明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers))。
* API `getTargetCookieName()` 方法已替换为存 `TargetCookieName` 取器。 请参 [阅TargetClient实用程序访问器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。
* API `getTargetLocationHintCookieName()` 方法已替换为存 `TargetLocationHintCookieName` 取器。  请参 [阅TargetClient实用程序访问器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。

### 已删除

* 目标BatchMbox v2 API支持。
* 已 [删除getOffer()API方法](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) ，请改 [用getOffers()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) 。

