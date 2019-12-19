---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: 与Adobe Target的Java SDK相关的发行说明。
title: 与Adobe Target的Java SDK相关的发行说明。
topic: Standard
translation-type: tm+mt
source-git-commit: 6b49e4fb6c92da023678c1f27823458229d21711

---


# 发行说明——目标Java SDK

与 [Target Java SDK相关的发行说明](https://github.com/adobe/target-java-sdk)。

Java [!DNL Target] SDK允许您部署 [!DNL Target] 服务器端。 此Java SDK可帮助您轻松 [!DNL Target] 地与其 [!DNL Adobe Experience Cloud] 他解决方案(如 [!DNL Adobe Experience Cloud Identity Service]、 [!DNL Adobe Analytics]和)集成 [!DNL Adobe Audience Manager]。

Java SDK在通过我们的交付API与集成时引入了最佳实践并消除了 [!DNL Target] 复杂性，这样您的工程团队就可以专注于业务逻辑。

通过Adobe Tech Blog了解有关Target Java SDK的更多信息- [使用新的Target Java SDK进行服务器端优化](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。

## 版本1.1.0（2019年12月16日）

以下部分提供有关Target Java SDK版本1.1.0的更多信息：

### 为管理控制台帮助添加了

* 由于@hisham-hassan提供了开放源代码贡献，因此增加了对代理配置的支持。

## 版本1.0.1（2019年11月11日）

以下部分提供有关Target Java SDK版本1.0.1的更多信息：

### 固定

* 在Target请求中发送补充数据ID，即使不存在访客API Cookie。

## 版本1.0.0（2019年10月31日）

以下各节提供有关Target Java SDK版本1.0.0的更多信息：

### 为管理控制台帮助添加了

* [目标视图交付v1 API支持](https://developers.adobetarget.com/api/delivery-api/) ，包括页面加载和视图预取。
   * 完全支持提供在Visual Experience Composer(VEC)中创作的所有类型的选件。
* 支持预取和通知，通过缓存预取的内容可实现性能优化。
* 支持在服务器端和客 [!DNL Target] 户端部 `serverState`署时，通 [!DNL Target] 过混合集成优化性能。
   * 我们引入了一个名为的设置 `serverState` ，该设置包含通过服务器端检索的体验，因此at.js v2.2+不会再进行服务器调用以检索体验。 此方法可优化页面加载性能。
* 以 [Target Java SDK形式在GitHub上开放](https://github.com/adobe/target-java-sdk)。
* 验证SDK API方法参数。
* 添加了自述文件、示例和单元测试。
* 添加了CoC、贡献准则、公关和期刊模板。

