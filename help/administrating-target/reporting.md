---
keywords: 报表；报表；Experience Cloud解决方案；时区；时区；货币；排除IP；预计收入提升；收入提升；细粒度优先级；细粒度
description: 使用 [!DNL Target] 或Adobe Analytics作为报表源，指定默认时区和货币格式，添加要从报表中排除的IP地址，等等。
title: 如何在Target中配置报表？
feature: 管理和配置
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 30%

---

# 在Target中配置报表

配置常规设置，以在[!DNL Adobe Target]报表中使用，这些设置将应用于您的整个[!DNL Target]帐户。

要访问[!UICONTROL Reporting]配置页面，请单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Reporting]。**

您可以在此页面上指定以下设置：

* 用于报表的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报告的货币
* 要从报表中排除的IP地址
* 是否在报表中显示预计收入提升
* 是否启用细粒度优先级

>[!NOTE]
>
>请注意，要排除设置的时区、货币和IP地址适用于使用[!DNL Target]报表的活动。 这些设置不适用于使用[Analytics for Target(A4T)]作为报表源(/help/c-integrating-target-with-mac/a4t/a4t.md)的活动。

![报表页面](/help/administrating-target/assets/reporting.png)

## Reporting Cloud解决方案

设置相应选项，以确定用于结果和报表的数据。

选择活动的报表源，即[!DNL Target]或[!DNL Adobe Analytics]。 您也可以选择为每个活动分别选择报表源。

选择报表源时，请考虑以下信息：

* 如果将此处的报表来源设置为“**[!DNL Target]**”，则将不允许激活使用“”作为报表源的活动。[!DNL Analytics]您必须在活动中将报表源更改为[!DNL Target]，或将报表源更改为&#x200B;**[!UICONTROL 在**[!UICONTROL  Administration] > [!UICONTROL Reporting ]**中为每个活动]**&#x200B;选择。
* 如果此处将报表源设置为&#x200B;**[!DNL Analytics]**，则不允许激活使用[!DNL Target]作为报表源的活动（将报表源指定为&#x200B;**[!UICONTROL 每个活动的目标]）**。 您必须在活动中将报表源更改为[!DNL Analytics]，或将报表引擎更改为&#x200B;**[!UICONTROL 在**[!UICONTROL  Administration] > [!UICONTROL Reporting ]**中为每个活动]**&#x200B;选择。
* 如果将此处的报表源设置为&#x200B;**[!UICONTROL 为每个活动选择]**，则可以创建、激活和停用选定报表源支持的活动。 有关受支持活动的矩阵，请参阅将Adobe Analytics作为Adobe Target报表源(A4t)*中的[受支持的活动类型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)。*
* [!UICONTROL 无论选择何种报表源，都允许创建、激活和停用Automated Personalization] (AP)活动。选择[Adobe Analytics作为Adobe Target(A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)的报表源时，不支持Automated Personalization活动。 即使指定[!DNL Analytics]作为报表源，也会使用[!DNL Target]作为Automated Personalization活动的报表源。 有关更多信息，请参阅&#x200B;*Adobe Analytics中的[支持的活动类型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作为Adobe Target报表源(A4t)*。

## 报表时区

指定用于报表的时区。

## 报告货币

指定用于报告的货币。

## 从[!DNL Target]报告数据中排除的IP

指定要从报表数据中排除的任何IP地址。 例如，排除内部公司地址是确保报表数据反映客户在您网站上的交互的一种好方法。

在新行上输入每个IP地址。

## 显示预计收入提升

如果您为目标输入货币值，则可以选择显示预计收入提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

只有[!DNL Experience Cloud]管理员用户可以启用或禁用此功能。 如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
