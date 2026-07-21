---
title: 在受众规则中使用上下文
description: 了解如何在受众规则中将上下文属性用于标记中的功能标记和功能组。
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# 在受众规则中使用上下文 {#context-in-audience-rules}

上下文属性是客户端应用程序在运行时提供的值。 利用这些功能，可根据动态的会话级别信息（如用户的活动语言、设备类型或应用程序状态）定位用户。

上下文属性与Web客户端和移动客户端相关。

## 上下文属性的工作方式 {#how-context-attributes-work}

在评估功能标志时，应用程序会将上下文属性传递给“标志”。 您可以在控制台中定义检查这些值的规则，平台在评估时使用它们来确定用户是否符合条件。

## 添加上下文属性 {#adding-context-attribute}

要将上下文属性添加到受众规则，请执行以下操作：

1. 在控制台中打开功能标志或功能组。
2. 转到&#x200B;**受众**&#x200B;选项卡。
3. 在&#x200B;**上下文**&#x200B;下，添加新条件。
4. 选择上下文属性、运算符和值。

如果所需的上下文属性未出现在列表中，则可以创建一个新属性 — 请参阅[创建上下文属性](creating-your-context-attributes.md)。

## 另请参阅 {#see-also}

* [功能标志和功能组中的受众](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
