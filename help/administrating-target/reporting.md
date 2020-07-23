---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 通过指定Adobe Target可视体验书写器(VEC)的常规设置、移动视口配置和CSS选择器，配置该体验书写器。
title: 在Adobe Target中配置报告
topic: Standard
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 32%

---


# 在目标中配置报告

配置一般设置，以在 [!DNL Adobe Target] 报告中应用于整个 [!DNL Target] 帐户。

要访问报告 [!UICONTROL 配置] 页，请单击“ **[!UICONTROL 管理]** ” **[!UICONTROL >]报告。**

您可以在此页面上指定以下设置：

* 用于报告的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报告的货币
* 要从报告中排除的IP地址
* 是否显示报告收入的估计增长
* 是否启用细粒度优先级

>[!NOTE]
>
>请注意，排除设置的时区、货币和IP地址应用于使用活动的 [!DNL Target] 报告。 这些设置不适用于将活动( [A4T)用作Analytics源] (/help/c-integrating-target-with-mac/a4t/a4t.md)的目标。

![报告页](/help/administrating-target/assets/reporting.png)

## 报告云解决方案

设置相应选项，以确定用于结果和报表的数据。

Select the reporting source for your activities, either [!DNL Target] or [!DNL Adobe Analytics]. 您也可以选择为每个活动分别选择报表源。

选择报表源时，请考虑以下信息：

* 如果将此处的报表来源设置为“**[!DNL Target]**”，则将不允许激活使用“”作为报表源的活动。[!DNL Analytics]You must change the reporting source to [!DNL Target] in your activity or change the reporting source to **[!UICONTROL Select per activity]** in **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* If the reporting source is set to **[!DNL Analytics]** here, you are not allowed to activate an activity that uses [!DNL Target] as the reporting source (the reporting source is specified as **[!UICONTROL Target per activity])**. You must change the reporting source to[!DNL Analytics]in your activity or change the reporting engine to**[!UICONTROL Select per activity ]**in**[!UICONTROL Administration]>[!UICONTROL Reporting ]**.
* If the reporting source is set to **[!UICONTROL Select per activity]** here, you can create, activate, and deactivate activities that are supported by the selected reporting source. For a matrix of supported activities, see [Supported activity types](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics as the reporting source for Adobe Target (A4t)*.
* [!UICONTROL 无论选择的活动源] ，都允许自动个性化(AP)报告创建、激活和取消激活。 Automated Personalization activities are not supported when you choose [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Even if you specify [!DNL Analytics] as your reporting source, [!DNL Target] is used as the reporting source for Automated Personalization activities. For more information, see [Supported activity types](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics as the reporting source for Adobe Target (A4t)*.

## 报告时区

指定用于报告的时区。

## 报告货币

指定用于报告的货币。

## 要从目标报告数据中排除的IP

指定要从报告数据中排除的任何IP地址。 例如，排除内部公司地址是确保报告数据反映客户在网站上的互动的好方法。

在新行上输入每个IP地址。

## 显示预计收入提升

如果为目标输入货币值，则可以选择显示预计的收入提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

Only [!DNL Experience Cloud] Admin users can enable or disable this feature. 如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
