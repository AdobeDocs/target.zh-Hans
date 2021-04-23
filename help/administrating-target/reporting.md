---
keywords: 报告；报告；报告；体验云解决方案；时区；时区；货币；排除IP；预计收入增加；收入增加；细粒度优先级；细粒度
description: 使用 [!DNL Target] 或Adobe Analytics作为报告源，指定默认时区和货币格式，添加要从报告中排除的IP地址，等等。
title: 如何在目标中配置报告?
feature: 管理和配置
role: Administrator
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 30%

---

# 在目标中配置报告

配置要在[!DNL Adobe Target]报告中使用的常规设置，这些设置适用于您的整个[!DNL Target]帐户。

要访问[!UICONTROL 报告]配置页，请单击&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 报告]。**

您可以在此页面上指定以下设置：

* 用于报告的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报告的货币
* 要从报告中排除的IP地址
* 是否显示报告收入的估计增长
* 是否启用细粒度优先级

>[!NOTE]
>
>请注意，要排除设置的时区、货币和IP地址应用于使用[!DNL Target]报告的活动。 这些设置不适用于使用[Analytics for 目标(A4T)]作为报告源(/help/c-integrating-target-with-mac/a4t/a4t.md)的活动。

![报告页](/help/administrating-target/assets/reporting.png)

## 报告云解决方案

设置相应选项，以确定用于结果和报表的数据。

为活动选择报告源，[!DNL Target]或[!DNL Adobe Analytics]。 您也可以选择为每个活动分别选择报表源。

选择报表源时，请考虑以下信息：

* 如果将此处的报表来源设置为“**[!DNL Target]**”，则将不允许激活使用“”作为报表源的活动。[!DNL Analytics]您必须在活动中将报告源更改为[!DNL Target]，或将报告源更改为&#x200B;**[!UICONTROL 管理] > [!UICONTROL 报告]**&#x200B;中的&#x200B;**[!UICONTROL 按活动]**&#x200B;选择。
* 如果报告源在此处设置为&#x200B;**[!DNL Analytics]**，则不允许激活使用[!DNL Target]作为报告源的活动(报告源指定为每个活动]的目标)**。**[!UICONTROL &#x200B;您必须在活动中将报告源更改为[!DNL Analytics]，或将报告引擎更改为&#x200B;**[!UICONTROL 管理] > [!UICONTROL 报告]**&#x200B;中的&#x200B;**[!UICONTROL 选择每个活动]**。
* 如果报告源在此处设置为&#x200B;**[!UICONTROL 按活动]**&#x200B;选择，则可以创建、激活和取消激活所选报告源支持的活动。 有关支持的活动的矩阵，请参阅&#x200B;*Adobe Analytics中[支持的活动类型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作为Adobe Target(A4t)*&#x200B;的报告源。
* [!UICONTROL Automated Personalization] (AP)活动创建、激活和取消激活是允许的，而不管选择的报告源。如果选择[Adobe Analytics作为Adobe Target(A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)的报告源，则不支持Automated Personalization活动。 即使指定[!DNL Analytics]作为报告源，[!DNL Target]也用作Automated Personalization活动的报告源。 有关详细信息，请参阅&#x200B;*Adobe Analytics中[支持的活动类型](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作为Adobe Target(A4t)*&#x200B;的报告源。

## 报告时区

指定用于报告的时区。

## 报告货币

指定用于报告的货币。

## 要从[!DNL Target]报告数据中排除的IP

指定要从报告数据中排除的任何IP地址。 例如，排除内部公司地址是确保报告数据反映客户在网站上互动的好方法。

在新行上输入每个IP地址。

## 显示预计收入提升

如果为目标输入货币值，则您可以选择显示收入的估计提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

只有[!DNL Experience Cloud]管理员用户可以启用或禁用此功能。 如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI 和“优先级”选项会有所不同。您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
