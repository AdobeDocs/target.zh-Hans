---
keywords: 概述和参考
description: Adobe Target 启用了一些流程和设置，使您能够在遵守适用数据隐私法律的情况下使用 Target。
title: 隐私
subtopic: 入门指南
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 隐私{#privacy}

Adobe Target 启用了一些流程和设置，使您能够在遵守适用数据隐私法律的情况下使用 Target。

## IP 地址收集 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

网站访客的 IP 地址会传输到 Adobe 数据处理中心 (DPC)。根据访客的网络配置，IP 地址不一定能代表访客计算机的 IP 地址。例如，IP 地址可能为网络地址转换 (NAT) 防火墙、HTTP 代理或互联网网关的外部 IP 地址。Target 不会存储用户的任何 IP 地址或任何个人身份信息 (PII)。IP 地址仅在会话持续期间由 Target 使用（位于内存中，永不保留）。

## 替换 IP 地址的最后八位字节 {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe 制定了新的“从设计着手保护隐私”(privacy by design) 设置，Adobe ClientCare 可以为 Adobe Target 启用该设置。启用此设置后，当 Adobe 收集 IP 地址时，该 IP 地址的最后八位字节（最后一部分）会立即隐藏。此匿名化发生在 IP 地址的任何处理之前，包括在 IP 地址可选地理位置查询之前。

当启用此功能时，会对 IP 地址进行充分地匿名化处理，以便它不能再被识别为个人信息。因此，Adobe Target 的使用符合国家/地区数据隐私法律，这些国家/地区不允许收集个人信息。获取城市级别信息很有可能会受到 IP 地址模糊处理的影响。获得地区和国家级别信息应该只会受到轻微影响。

还有一个可用于对整个 IP 地址进行模糊处理的设置。

请联系 Adobe ClientCare 以启用 IP 模糊处理功能。

## 地域划分 {#section_BB69F96559BD44BDA4177537C4A5345A}

如果您启用了“替换 IP 地址的最后八位字节”功能，则可以在 Adobe Target 中使用报表来分析 IP 地址中的剩余字节值。如果 IP 地址的最后八位字节没有进行模糊处理，则可以在 Adobe Target 中分析完整的 IP 地址。您可以使用地域划分功能来按地理区域在地图上标出访客位置。地域划分数据只精确到城市级别或邮政编码级别，而不能精确到个人级别。

如果对 IP 地址进行了完全模糊处理，则无法使用地域划分和地域定位。

## 退订链接 {#section_E7A62B7B99C94B3A806CB262D16E27FC}

您可以向网站添加选择退订链接，使访客可以选择退订所有计数和内容发送服务。

1. 请为您的网站添加以下链接：

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. 将 `clientcode` 一词替换成您的客户端代码，并将要链接的文字或图像添加到选择退订 URL。

点击该链接的任何访客都不会包含在通过浏览会话调用的任何 mbox 请求中，直到他们删除 Cookie 或两年后（以时间在先者为准）为止。这通过在 `disableClient` 域中为访客设置称为 `clientcode.tt.omtrdc.net` 的 Cookie 实现。

即使您使用第一方 Cookie 实施，提供的选择退订也将通过第三方 Cookie 进行设置。如果客户端只使用第一方 Cookie，则 Target 将会检查是否设置了选择退订 Cookie。
