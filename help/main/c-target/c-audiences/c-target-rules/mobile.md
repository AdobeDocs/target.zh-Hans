---
keywords: 定位;移动设备;Target 移动设备;DeviceAtlas;iPhone;iPhone 机型;Device Atlas;displaywidth;显示屏宽度;显示屏高度;设备类型;displayheight;手机;平板电脑;设备型号
description: 了解如何在 [!DNL Adobe Target] 中创建受众以定位移动设备。
title: 我是否可以根据移动设备选项定位访客？
feature: Audiences
exl-id: 73d5c80c-bfa2-4806-8c04-652781b70bf2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 34%

---

# 移动设备

在[!DNL Adobe Target]中创建受众以根据移动设备、设备类型、设备供应商、屏幕维度等参数定位移动设备。

例如，您可能希望向使用手机访问您页面的用户显示与使用计算机访问您页面时显示的内容不同的内容。 在这种情况下，您可以选择[!UICONTROL Mobile]受众，然后选择&#x200B;**[!UICONTROL Is Mobile Phone]**&#x200B;选项。 然后，您可以添加任何对您而言重要的特定详细信息，例如手机类型、屏幕大小（以像素为单位）等等。

移动设备定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 提供的，属于 DotMobi 的一个服务。DeviceAtlas 是一种综合的移动设备数据库，它基于从众多来源收集的数据构建，其中包括制造商和网络运营商。然后，系统对这些数据进行确认、交叉引用和验证，以构建准确的大型移动设备数据库。

可通过分析用户-代理字符串来实现设备检测。但是，有些设备制造商（例如 Apple）不会在用户-代理中提供足够的信息，从而无法使用此功能。

例如，Apple 设备不会在用户-代理中共享特定于设备型号的令牌。结果是无法使用基于关键字的简单方法检测iPhone模型(例如iPhone 12 Pro、iPhone 12、iPhone 11 Pro Max等)。

要解决此问题，[!DNL Target]会收集其他数据，以便使用以下参数准确检测iPhone和其他Apple设备：

| 参数 | 类型 | 描述 |
|--- |--- |--- |
| devicePixelRatio | 字符串 | 浏览器上物理像素和与设备无关的像素(dip)之间的比率。 例如，“1.5”或“2” |
| screenOrientation | 字符串 | 设备和浏览器的 JavaScript 引擎支持“设备方向”。可以是“横向”或“纵向”。 |
| webGLRenderer | 字符串 | 图形驱动程序的浏览器渲染器。 |

>[!NOTE]
>
>使用Mobile SDK的客户无需执行任何操作即可应用此功能。 使用at.js的客户必须[升级到at.js版本1.5.0](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=zh-Hans){target=_blank}（或更高版本）。

您可以选择多个移动设备属性。使用OR运算符连接多个选择。

使用自定义集成（不使用 at.js 或 Mobile SDK）的客户可以自己收集这些参数并将其作为 mbox 参数传递。

1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
1. 命名受众并添加可选描述。
1. 将&#x200B;**[!UICONTROL Mobile]**&#x200B;拖放到受众生成器窗格中。
1. 单击&#x200B;**[!UICONTROL Select]**，然后选择以下选项之一：

   * 设备营销名称
   * 设备型号
   * 设备供应商
   * 是移动设备
   * 是移动电话
   * 是平板电脑
   * 操作系统
   * 屏幕高度（像素）
   * 屏幕宽度（像素）

   >[!NOTE]
   >
   >您可以使用[地域设置](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)通过移动设备运营商进行定位。

1. （可选）为受众设置其他规则。
1. 单击 **[!UICONTROL Done]**。

下图展示了一个受众，它定位的是使用Google制造的移动设备的访客。

![定位移动设备](assets/target_mobile.png)

## 注意事项

定位移动设备时，请考虑以下信息：

### 定位运行iOS 12.2或更高版本的设备

由于iOS 12.2中引入了新更改，使用由[!UICONTROL Device Marketing Name]和[!UICONTROL Device Model]定义并指定iPhone模型的规则创建受众受到了影响。 [!DNL Target]无法再定位安装了iOS 12.2（或更高版本）的iPhone的用户。 但是，如果这些用户没有iOS 12.2（或更高版本），则iPhone模型定位将继续正常工作。

iOS 12.2（或更高版本）更新不会影响以下模型的识别，因为这些模型不支持升级到iOS 12.2：iPhone、iPhone 3G、iPhone 3GS、iPhone 4、iPhone 4s、iPhone 5、iPhone 5c、iPad、iPad 2、iPad / Retina显示屏、iPad Retina（第4代）、iPod Touch 4和iPod Touch 5。

### 定位运行Safari 14.0.2（或更高版本）的设备

使用移动规则来定位在macOS上运行Safari版本14.0.2（或更高版本）的设备时，由于Apple的用户代理和DeviceAtlas存在已知问题，[!DNL Target]在Mac和iPad设备上错误地识别了Safari。 此问题将在将来得到解决。

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
