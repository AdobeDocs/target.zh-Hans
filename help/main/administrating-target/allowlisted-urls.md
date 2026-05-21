---
keywords: 允许列表；远程选件；管理；URL模式；验证；活动；选件；通配符；正则表达式
description: 了解如何在Adobe Target管理部分查看、搜索、添加和删除远程选件的列入允许列表URL，包括验证行为和整个帐户范围。
title: 管理列入允许列表的远程选件URL
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# 列入允许列表的URL

受信任的URL定义了受信任的URL模式，贵组织可以在其中创建和运行[!DNL Adobe Target]体验，包括当您使用远程或重定向选件时。 该列表与[主机管理](/help/main/administrating-target/hosts.md)和[环境](/help/main/administrating-target/environments.md)配合使用，但特别适用于允许的远程选件URL模式和相关验证。

若要管理列入允许列表的URL，请单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Allowlisted URLs]**。

显示URL列表、搜索字段和添加URL控件的![已列入允许列表URL页](../administrating-target/assets/allowlist-1.png)

## 管理列入允许列表的URL {#add-url}

主表在单个列中列出了每个阵列。 支持的条目可以包含精确的URL、通配符路径或您的组织接受的远程体验模式格式。

1. 单击 **[!UICONTROL Add URL]**。

   ![](../administrating-target/assets/allowlist-2.png)

1. 在对话框中，输入组织必须允许的URL或模式。

   ![](../administrating-target/assets/allowlist-3.png)

1. 保存更改。

   在模式列入允许列表后，用户可以创建或运行依赖于该URL的活动和选件，但受您其他[!DNL Target]规则的限制。

1. 使用&#x200B;**[!UICONTROL Search URLs]**&#x200B;字段筛选表。

1. 要删除URL，请找到不再需要该模式的行，然后单击![删除](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg)图标。

   ![](../administrating-target/assets/allowlist-4.png)


