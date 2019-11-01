---
description: 与Adobe Target的Node.js SDK相关的发行说明
keywords: at.js;sdk;node.js;release;updates;sdks；服务器端；服务器端；服务器端；nodejs
seo-description: 与Adobe Target的服务器端API相关的发行说明。
seo-title: 与Adobe Target的Node.js SDK相关的发行说明。
solution: Target
title: 发行说明——目标Node.js SDK
topic: Standard
translation-type: tm+mt
source-git-commit: 5f05f218e5fdea26827b86cb7fbea05ac6349014

---


# 发行说明——目标Node.js SDK

与 [Adobe Target的Node.js SDK相关的发行说明](https://github.com/adobe/target-nodejs-sdk)。

Target Node.js SDK可让您部署 [!DNL Target] 服务器端。

此Node.js SDK可帮助您轻松 [!DNL Target] 与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。

Node.js SDK在通过我们的交付API与集成时引入了最佳实践并消除了 [!DNL Target] 复杂性，这样您的工程团队就可以专注于业务逻辑。

通过Adobe Tech Blog —— 开放式搜索新的Adobe Target Node.js SDK，进一步了 [解Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。

## 版本1.0.0（2019年10月9日）

以下各节提供有关Target Node.js SDK版本1.0.0的更多信息：

### 为管理控制台帮助添加了

* 目标视图交付v1 API支持，包括页面加载和视图预取。
* 完全支持提供在Visual Experience Composer(VEC)中创作的所有类型的选件。
* 通过缓存预取的内容支持预取和通知以优化性能。
* 支持在服务器端和客 [!DNL Target] 户端部 `serverState` 署时 [!DNL Target] 通过混合集成优化性能。

   我们引入了一个名为的设置 `serverState` ，该设置包含通过服务器端检索的体验，因此at.js v2.2+不会再进行服务器调用以检索体验。 此方法可优化页面加载性能。

* 在GitHub上以 [Target Node.js SDK的形式开放](https://github.com/adobe/target-nodejs-sdk)。
* 新 [的sendNotifications()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) ，用于将显示／单击的通知发送到通过 [!DNL Target] getOffers()预取的内 [容的API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers)。
* 简化的查看交付API请求构建，内部字段自动完成，默 `request.id`认值 `request.context`为（例如，等等）。
* 验证SDK API方法参数。
* 更新了自述文件、示例和单元测试。
* 使用GitHub Actions设置新的CI流。
* 添加了CoC、贡献指南、公关和期刊模板

### 已将

* 项目已重命名为 `target-nodejs-sdk`。
* 主要重构，用Target View Delivery v1 API替换Target BatchMbox v2 API。
* [create()API方法参数已修改](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) ，删除了冗余嵌套(请参阅此处的旧方 [法声明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate))。
* [getOffers()API方法参数已修改](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) (请参阅此处的旧方 [法声明](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers))。
* API方 `getTargetCookieName()` 法已替换为存取 `TargetCookieName` 器。 请参 [阅TargetClient实用程序访问器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。
* API方 `getTargetLocationHintCookieName()` 法已替换为存取 `TargetLocationHintCookieName` 器。  请参 [阅TargetClient实用程序访问器](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)。

### 已删除

* 目标BatchMbox v2 API支持。
* 已 [删除getOffer()API方法](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) ，请改 [用getOffers()API方法](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) 。

