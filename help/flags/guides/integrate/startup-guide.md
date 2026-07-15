---
title: 启动指南
description: 按照以下步骤将您的应用程序与标志集成：从请求访问权限到创建第一个功能标志。
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 1%

---

# 启动指南 {#startup-guide}

请按照以下步骤将标记集成到您的应用程序中。

## 步骤1：请求访问 {#step-1-access}

请求访问标记控制台并加入您的团队。 有关分步说明，请参阅[请求访问权限](../console/request-access.md)。

## 步骤2：载入应用程序 {#step-2-onboard}

获得访问权限后，登录到Flags控制台并验证您的应用程序是否列在您的团队下。 如果不是，请让您的团队管理员添加它。 请参阅[将应用程序载入](../applications/onboard-your-application.md)。

在上线之前，请准备以下内容：

| 要求 | 详细信息 |
|---|---|
| **应用程序ID** | 调用标志API时使用的唯一客户端标识符。 在可用的情况下，使用应用程序的现有客户端ID。 |
| **服务器端客户端** | 如果与服务器端SDK集成，则需要具有适当权限的管理客户端ID。 |
| **桌面客户端** | 可以使用产品代码和产品版本代替客户端ID。 |

## 步骤3：获取您的凭据 {#step-3-credentials}

所需的凭据取决于您的集成路径：

* **Web和移动设备（基于标记）：**&#x200B;使用已发布标记属性中的&#x200B;**环境文件ID**。 有关如何获取此信息，请参阅步骤4a 。
* **服务器端SDK：**&#x200B;请求一个&#x200B;**服务令牌客户端ID**&#x200B;并让标志支持在从SDK进行API调用之前列入允许列表它。
* **桌面：**&#x200B;可以使用产品代码和产品版本代替客户端ID。

## 步骤4：使用SDK集成 {#step-4-integrate}

对您的应用程序类型执行[集成步骤](integration-steps.md)。 选择适合您的栈栈的路径：

* **Web服务** → Java SDK或Node.js SDK
* AEP Mobile SDK→的&#x200B;**Web和移动应用程序** — 请参阅[Android](../sdk-releases/android/android-extension-integration-guide.md)和[iOS](../sdk-releases/ios/ios-extension-integration-guide.md)指南
* **桌面应用程序** → SDK（即将推出）

## 步骤4a：设置数据收集并发布您的配置 {#step-4a-data-collection}

如果通过基于标记的方法（Web或移动设备）进行集成，请在初始化SDK之前配置标记属性：

1. 在[Adobe Experience Platform数据收集](https://experience.adobe.com/#/data-collection)中，打开您的移动或Web属性。
1. 依次安装&#x200B;**Edge Network**&#x200B;扩展和&#x200B;**Experience Rollout**&#x200B;扩展（按顺序）。
1. 选择您的&#x200B;**数据流**（必须包括Customer Journey Analytics数据集）和边缘域。
1. 通过&#x200B;**Dev → Staging → Production**&#x200B;发布配置。
1. 从&#x200B;**环境**&#x200B;选项卡复制&#x200B;**环境文件ID** — 您将使用此项初始化SDK。

>[!IMPORTANT]
>
>在&#x200B;**暂存**&#x200B;环境中，为环境文件ID添加前缀`staging/` — 即，使用`staging/<environmentId>`。 在&#x200B;**生产**&#x200B;中，直接使用环境文件ID。

## 步骤5：创建和测试您的第一个功能标记 {#step-5-feature-flag}

集成完成后，在控制台中创建第一个功能标记并进行测试：

* [创建您的第一个功能标记](../feature-flags/create-your-first-feature-flag.md)

## 另请参阅 {#see-also}

* [在应用程序中集成标志](integrating-in-your-app.md)
* [集成步骤](integration-steps.md)
* [SDK](sdks.md)

<!-- -->
