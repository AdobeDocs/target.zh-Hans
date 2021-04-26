---
keywords: 实现；javascript库；js;atjs；设备上决策；设备上决策；at.js；设备上；设备上；疑难解答；故障排除
description: 了解如何通过at.js库对设备决策进行疑难解答。
title: 如何通过at.js JavaScript库对设备上决策进行疑难解答？
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: a73525a7c2096235d583f54865fcdcbc4b36e7c0
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# 对at.js的设备上决策进行疑难解答

完成以下步骤，以通过at.js JavaScript库解决Adobe Target中的设备上决策问题：

1. 为at.js启用控制台日志
1. 在浏览器的“网络”选项卡中验证规则对象下载
1. 使用at.js自定义事件验证规则对象下载

以下各节将更详细地描述每个步骤：

## 第1步：为at.js启用控制台日志

附加URL参数`mboxDebug=1`可启用at.js在浏览器控制台中打印消息。

所有邮件都包含前缀“AT：”，方便了概述。 要确保已成功加载对象，控制台日志中应包含类似以下消息：

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

下图在控制台日志中显示这些消息：

![包含对象消息的控制台日志](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 第2步：在浏览器的“网络”选项卡中验证规则对象下载

打开浏览器的“网络”选项卡。

例如，要在Google Chrome中打开DevTools:

1. 按Ctrl+Shift+J(Windows)或Command+Option+J(Mac)。
1. 导航到“网络”选项卡。
1. 按关键字“rules.json”过滤调用，以确保仅显示对象规则文件。

   此外，您还可以按“/投放|rules.json/”进行筛选，以显示所有[!DNL Target]调用和项目rules.json。

   ![Google Chrome中的“网络”选项卡](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 第3步：使用at.js自定义事件验证规则对象下载

at.js库调度两个新的自定义事件以支持设备决策。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

订阅后，您可以在应用程序中侦听这些自定义事件，以便在项目规则文件下载成功或失败时执行操作。

以下示例显示了侦听对象下载成功和失败事件的代码示例：

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
