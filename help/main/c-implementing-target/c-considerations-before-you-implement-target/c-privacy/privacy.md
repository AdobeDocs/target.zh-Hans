---
keywords: 隐私;ip 地址;地域划分;选择退出;选择禁用;数据隐私;政府法规;法规;gdpr;ccpa
description: 了解 Adobe [!DNL Target] 如何遵循适用的数据隐私法，包括 IP 地址的收集和处理，以及选择退出指令。
title: ' [!DNL Target] 如何处理隐私问题？'
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 98%

---

# 隐私

[!DNL Adobe Target] 启用了一些流程和设置，使您能够在遵守适用数据隐私法律的情况下使用 [!DNL Target]

## 功能使用数据集合

单独的功能使用情况数据会被收集用于内部 [!DNL Adobe] 用途，确定 [!DNL Target] 功能是否按意图执行或者确定利用率不足的功能。各个延迟测量值会被收集用于帮助解决性能问题。不收集个人数据。

您可在客户端初始化选项中，通过将 `telemetryEnabled` 设置为 false 来选择在 SDK 中禁用报表使用情况数据。有关更多信息，请参阅 [targetGlobalSettings 中的 telemetryEnabled](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)。

## IP 地址收集 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

网站访客的 IP 地址会传输到 Adobe 数据处理中心 (DPC)。根据访客的网络配置，IP 地址不一定能代表访客计算机的 IP 地址。例如，IP 地址可能为网络地址转换 (NAT) 防火墙、HTTP 代理或互联网网关的外部 IP 地址。Target 不会存储用户的任何 IP 地址或任何个人身份信息 (PII)。Target 仅在会话期间（内存中，绝不保留）使用 IP 地址。

## 替换 IP 地址的最后一个八位字节 {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe 制定了新的“从设计着手保护隐私”(privacy by design) 设置，Adobe ClientCare 可以为 Adobe Target 启用该设置。启用此设置后，当 Adobe 收集 IP 地址时，该 IP 地址的最后八位字节（最后一部分）会立即隐藏。此匿名化在 IP 地址的任意处理之前执行，包括在可选的 IP 地址地理位置查找之前。

当启用此功能时，会对 IP 地址进行充分地匿名化处理，以便它不能再被识别为个人信息。因此，Adobe Target 的使用符合国家/地区数据隐私法律，这些国家/地区不允许收集个人信息。获取城市级别信息很有可能会受到 IP 地址模糊处理的影响。获得地区和国家级别信息应该只会受到轻微影响。

以下设置可供使用：

* 不模糊处理：Target 不隐藏 IP 地址的任何部分。
* 最后八位字节：Target 隐藏 IP 地址的最后一个八位字节。
* 完整 IP：Target 隐藏完整 IP 地址。

Target 接收完整 IP 地址并根据指定对其进行模糊处理（设置为“最后八位字节”或“完整 IP”）时。然后，Target 在会话期间将进行了模糊处理的 IP 地址保存在内存中。

>[!NOTE]
>
>[联系 Adobe 客户关怀](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)以确定您当前使用的设置或者启用 IP 模糊处理功能。

## 地域划分 {#section_BB69F96559BD44BDA4177537C4A5345A}

如果您启用了“替换 IP 地址的最后八位字节”功能，则可以在 Adobe Target 中使用报表来分析 IP 地址中的剩余字节值。如果 IP 地址的最后八位字节没有进行模糊处理，则可以在 Adobe Target 中分析完整的 IP 地址。您可以使用地域划分功能来按地理区域在地图上标出访客位置。地域划分数据只精确到城市级别或邮政编码级别，而不能精确到个人级别。

如果对 IP 地址进行了完全模糊处理，则无法使用地域划分和地域定位。

## 选择退出链接 {#section_E7A62B7B99C94B3A806CB262D16E27FC}

您可以向网站添加选择退订链接，使访客可以选择退订所有计数和内容发送服务。

1. 请为您的网站添加以下链接：

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. （视情况而定）如果您在使用 CNAME，则链接应包含“client=`clientcode`”参数，例如：
https://my.cname.domain/optout?client=clientcode.

1. 使用您的客户端代码替换 `clientcode`，然后添加要链接到选择退出 URL 的文本或图像。

点击该链接的任何访客都不会包含在通过浏览会话调用的任何 mbox 请求中，直到他们删除 Cookie 或两年后（以时间在先者为准）为止。这通过在 `disableClient` 域中为访客设置称为 `clientcode.tt.omtrdc.net` 的 Cookie 实现。

即使您使用第一方 Cookie 实施，提供的选择退订也将通过第三方 Cookie 进行设置。如果客户端只使用第一方 Cookie，则 Target 将会检查是否设置了选择退订 Cookie。

## 隐私和数据保护法规

有关欧盟的通用数据保护条例 (GDPR)、加州消费者隐私法案 (CCPA) 和其他国际隐私要求的信息，以及这些法规对您的组织和 Adobe Target 的影响，请参阅[隐私和数据保护法规](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/)。
