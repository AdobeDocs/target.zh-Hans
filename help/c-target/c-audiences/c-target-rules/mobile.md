---
description: 可根据移动设备、设备类型、设备供应商、屏幕大小（按像素）等参数定位移动设备。
keywords: 定位;移动设备;Target 移动设备;DeviceAtlas;iPhone;iPhone 机型;Device Atlas;displaywidth;显示屏宽度;显示屏高度;设备类型;displayheight;手机;平板电脑;设备型号
seo-description: 可根据移动设备、设备类型、设备供应商、屏幕大小（按像素）等参数定位移动设备。
seo-title: 移动设备
solution: Target
title: 移动设备
topic: Standard
uuid: a731e8c0-e9c1-4971-95b7-882cefcabfc7
translation-type: tm+mt
source-git-commit: 95e7a8240db8bf7c09d5cf003748c6cb544a8c05

---


# 移动设备{#mobile}

可根据移动设备、设备类型、设备供应商、屏幕大小（按像素）等参数定位移动设备。

例如，您可能希望向从手机访问您页面和从计算机访问您页面的用户显示不同的内容。在这种情况下，您可以选择“移动设备”受众，再选择 **[!UICONTROL 是移动电话]选项，然后添加任何对您而言重要的特定信息，例如手机类型、屏幕大小（以像素为单位）等等。**

移动设备定位是由 [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester) 提供的，属于 DotMobi 的一个服务。DeviceAtlas 是一种综合的移动设备数据库，它基于从众多来源收集的数据构建，其中包括制造商和网络运营商。然后，系统对这些数据进行确认、交叉引用和验证，以构建准确的大型移动设备数据库。

可通过分析用户-代理字符串来实现设备检测。但是，有些设备制造商（例如 Apple）不会在用户-代理中提供足够的信息，从而无法使用此功能。

例如，Apple 设备不会在用户-代理中共享特定于设备型号的令牌。因此，无法使用基于关键字的简单方法来检测 iPhone 机型（例如 iPhone 5S、iPhone SE、iPhone 6，等等）。

为解决此问题，Target 使用以下参数收集其他数据来准确检测 iPhone 和其他 Apple 设备：

| 参数 | 类型 | 描述 |
|--- |--- |--- |
| devicePixelRatio | 字符串 | 浏览器中物理像素和与设备无关的像素 (dip) 之间的比率。例如“1.5”或“2” |
| screenOrientation | 字符串 | 设备和浏览器的 JavaScript 引擎支持“设备方向”。可以是“横向”或“纵向”。 |
| webGLRenderer | 字符串 | 图形驱动程序的浏览器渲染器。 |

>[!NOTE]
>
>使用 Mobile SDK 的客户无需执行任何操作即可使用此功能。使用 at.js 的客户必须[升级至 at.js 版本 1.5.0](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)（或更高版本）。

您可以选择多个移动设备属性。选择的多个属性将使用 OR 来连接。

使用自定义集成（不使用 at.js 或 Mobile SDK）的客户可以自己收集这些参数并将其作为 mbox 参数传递。

1. 在 [!DNL Target] 界面中，单击 **[!UICONTROL 受众]** &gt; **[!UICONTROL 创建受众]**。
1. 对受众进行命名。
1. 单击 **[!UICONTROL 添加规则]** &gt; **[!UICONTROL 移动设备]**。

   ![](assets/target_mobile.png)

1. 单击 **[!UICONTROL 选择]**，然后选择以下选项之一：

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
   >由于iOS12.2中引入的新更改，使用指定iPhone型号的设备营销名称和设备模型定义的受众会受到影响。我们不再将装有iOS12.2的iPhone定位到它们。但是，如果这些用户没有iOS12.2，则iPhone型号定位继续正常工作。
   >
   >iOS12.2更新不会影响下列型号的识别，因为这些模型不支持升级到iOS12.2：iPhone、iPhone3 G、iPhone3 GS、iPhone4、iPhone4 s、iPhone5、iPhone5 c、iPad、iPad、iPad/Retina显示屏、iPad Retina(4th Generation)、iPod Touch和iPod Touch5。

   >[!NOTE]
   >
   >您可以使用[地域设置](../../../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)通过移动设备运营商进行定位。

1. （可选）单击 **[!UICONTROL 添加规则]，然后为受众设置更多规则。**
1. 单击 **[!UICONTROL 保存]**。

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=chi_hans)
