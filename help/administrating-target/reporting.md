---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 通过指定Adobe目标可视体验书写器(VEC)的常规设置、移动视口配置和CSS选择器，配置Adobe Visual Experience Composer(VEC)。
title: 在Adobe报告中配置目标
topic: Standard
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 69%

---


# 在目标中配置报告

配置一般设置，以在目标报告中使用，这些设置应用于您的整个 [!DNL Target] 帐户。

要访问报告 [!UICONTROL 配置] 页，请单击“ **[!UICONTROL 管理]** ” **[!UICONTROL >]报告。**

您可以在此页面上指定以下设置：

* 用于报告的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报告的货币
* 要从报告中排除的IP地址
* 是否显示报告收入的估计增长
* 是否启用细粒度优先级

![报告页](/help/administrating-target/assets/reporting.png)

## 报告云解决方案

设置相应选项，以确定用于结果和报表的数据。

选择活动的报表源（[!DNL Target] 或 Adobe Analytics）。您也可以选择为每个活动分别选择报表源。

选择报表源时，请考虑以下信息：

* 无论选择何种报表源，都允许执行以下操作：[!UICONTROL 自动分配]、[!UICONTROL 自动定位]和[!UICONTROL 自动个性化] (AP) 活动创建、激活和停用。当您选择[将 Adobe Analytics 作为 Adobe Target (A4T) 的报表源](/help/c-integrating-target-with-mac/a4t/a4t.md)时，这些活动类型不受支持。即使您将 Analytics 指定为报表源，[!DNL Target] 也会用作这些活动类型的报表源。
* 如果将此处的报表源设置为“Analytics”，则将不允许激活使用 [!DNL Target] 作为报表源的活动（将每个活动的报表源指定为 Target）。您必须在活动中将报表源更改为“Analytics”，或在“设置”>“首选项”中将报表引擎更改为“为每个活动选择”。
* 如果将此处的报表来源设置为“[!DNL Target]”，则将不允许激活使用“Analytics”作为报表源的活动。您必须在活动中将报表源更改为“[!DNL Target]”，或在“设置”>“首选项”中将报表源更改为“为每个活动选择”。
* 如果将此处的报表源设置为“为每个活动选择”，则可以创建、激活和停用所选报表源支持的活动。有关受支持活动的矩阵，请参阅[](/help/c-integrating-target-with-mac/a4t/a4t.md)将 Adobe Analytic 作为 Adobe Target (A4T) 的报表源。
* 当您从 A/B 手动切换到[!UICONTROL 自动分配]或[!UICONTROL 自动定位]时，如果[!UICONTROL 自动分配]或[!UICONTROL 自动定位]活动中不支持 A/B 手动活动的报表源，则所有量度和报表受众都将会丢失。

## 报告时区

指定用于报告的时区。

## 报告货币

指定用于报告的货币。

## 要从目标报告数据中排除的IP

指定要从报告数据中排除的任何IP地址。 例如，排除内部公司地址是确保报告数据反映客户在网站上的互动的好方法。

在新行上输入每个IP地址。

## 显示预计收入提升

如果为目标输入货币值，则可以选择显示预计的收入提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

只有 Experience Cloud 管理员用户可以启用或禁用此功能。如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
