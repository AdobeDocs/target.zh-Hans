---
title: 复杂的受众规则
description: 了解如何在Flags中使用大型或复杂的受众规则集，包括批量值限制以及如何跨多个条件拆分规则。
badge: label="Beta" type="Informative"
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 3%

---

# 复杂的受众规则 {#complex-rules}

## 对复杂规则使用嵌套逻辑 {#nested-logic}

通过嵌套逻辑，您可以将多个受众条件与精确的AND/OR控制结合使用。 要启用该功能，请执行以下操作：

1. 添加所需的受众条件。
2. 在受众规则部分中启用&#x200B;**嵌套逻辑**。
3. 每个条件都分配有一个编号。 输入引用这些数字的逻辑表达式，例如：
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## 另请参阅 {#see-also}

* [功能标志和功能组中的受众](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
