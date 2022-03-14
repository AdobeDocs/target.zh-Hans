---
keywords: 实施；javascript库；js;atjs；设备上决策；设备上决策；at.js；设备上；设备上；故障诊断
description: 了解如何使用at.js库对设备决策进行故障诊断。
title: 如何使用at.js JavaScript库对设备上决策进行故障诊断？
feature: at.js
role: Developer
exl-id: 76bb9393-1560-455b-9d95-91576faee1f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# 对 at.js 的设备上决策疑难解答

完成以下步骤以对中的设备决策进行故障诊断 [!DNL Adobe Target] 与at.js JavaScript库一起使用时：

## 步骤1:为at.js启用控制台日志

附加URL参数 `mboxDebug=1` 可在浏览器控制台中打印消息。

所有消息都包含前缀“AT：”，以方便概述。 要确保成功加载对象，控制台日志应包含类似以下消息：

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

下图在控制台日志中显示了这些消息：

![包含对象消息的控制台日志](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 步骤2:验证在浏览器的“网络”选项卡中下载的规则对象

打开浏览器的“网络”选项卡。

例如，要在Google Chrome中打开DevTools，请执行以下操作：

1. 按Ctrl+Shift+J(Windows)或Command+Option+J(Mac)。
1. 导航到“网络”选项卡。
1. 按关键字“rules.json”过滤调用，以确保仅显示对象规则文件。

   此外，您还可以按“/delivery|rules.json/”进行过滤，以显示所有 [!DNL Target] 调用和对象rules.json。

   ![Google Chrome中的“网络”选项卡](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 步骤3:使用at.js自定义事件验证下载的规则对象

at.js库会调度两个新的自定义事件以支持设备决策。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

您可以订阅，以在应用程序中监听这些自定义事件，以便在项目规则文件下载成功或失败时执行操作。

以下示例显示了监听对象下载成功和失败事件的代码示例：

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
