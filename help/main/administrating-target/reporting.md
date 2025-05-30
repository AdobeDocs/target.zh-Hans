---
keywords: 报表；报表；报表；Experience Cloud解决方案；时区；时区；货币；排除IP；预计收入提升；收入；收入提升；细粒度优先级；细粒度
description: 使用 [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] 作为报表源，指定默认时区和货币格式，添加要从报表中排除的IP地址等。
title: 如何在 [!DNL Target]中配置报表？
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 3e2682acdf8c7be86285c901ddcdae0f43b647f2
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# 在[!DNL Target]中配置报表

配置要在[!DNL Adobe Target]报告中使用的常规设置，这些设置适用于您的整个[!DNL Target]帐户。

{{permissions-update}}

要访问[!UICONTROL Reporting]配置页面，请单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Reporting]。**

您可以在此页上指定以下设置：

* 用于报表的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报表的货币
* 要从报表中排除的IP地址
* 是否在报表中显示预计收入提升
* 是否启用细粒度优先级

>[!NOTE]
>
>请注意，要排除设置的时区、货币和IP地址适用于使用[!DNL Target]报表的活动。 这些设置不适用于使用[Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)或[!DNL Customer Journey Analytics]作为报表源的活动。

![报告页面](/help/main/administrating-target/assets/reporting.png)

## 报表云解决方案 {#solution}

设置相应选项，以确定用于结果和报表的数据。

选择活动的报表源： [!DNL Target]、[!DNL Adobe Analytics]或[!DNL Adobe Customer Journey Analytics]。 在创建活动时，您还可以选择作为三步引导式工作流的一部分，为每个活动选择报表源。

选择报表源时，请考虑以下信息：

* **[!DNL Adobe Target]**：如果将此处的报表源设置为&#x200B;**[!DNL Target]**，则将不允许创建或激活使用[!DNL Analytics]或[!DNL Customer Journey Analytics]作为报表源的活动。 必须将报表源更改为&#x200B;**[!UICONTROL Select per activity]**。
* **[!DNL Adobe Analytics]**：如果将此处的报表源设置为&#x200B;**[!DNL Analytics]**，则将不允许创建或激活使用[!DNL Target]或[!DNL Customer Journey Analytics]作为报表源的活动。 必须将报表源更改为&#x200B;**[!UICONTROL Select per activity]**。
* **[!DNL Adobe Customer Journey Analytics]**：如果将此处的报表源设置为&#x200B;**[!DNL Customer Journey Analytics]**，则将不允许创建或激活使用[!DNL Target]或[!DNL Analytics]作为报表源的活动。 必须将报表源更改为&#x200B;**[!UICONTROL Select per activity]**。
* **为每个活动选择**：如果将此处的报表源设置为&#x200B;**[!UICONTROL Select per activity]**，则可以创建和激活所选报表源支持的活动。

在确定报表源时，请考虑以下信息：

* **[!DNL Analytics]**：有关使用[!DNL Analytics]作为报表源(A4T)的支持活动的矩阵，请参阅&#x200B;*Adobe Analytics中的[支持的活动类型](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)作为Adobe Target (A4T)*&#x200B;的报表源。

  无论选择何种报表源，都允许创建和激活[!UICONTROL Automated Personalization] (AP)活动。 当您选择[Adobe Analytics作为Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md)的报表源时，[!UICONTROL Automated Personalization]活动不受支持。

  即使您指定[!DNL Analytics]作为报表源，[!DNL Target]也用作[!DNL Automated Personalization]活动的报表源。

* **[!DNL Customer Journey Analytics]**：有关在[!DNL Customer Journey Analytics]中使用[!DNL Target]报表的受支持活动的矩阵，请参阅&#x200B;[!DNL Adobe Customer Journey Analytics]*中的*[!DNL Target]&#x200B;报表中的[受支持的活动类型](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities)。

  无论选择什么报表源，[!UICONTROL Automated Personalization] (AP)、[!UICONTROL Auto-Allocate]和[!UICONTROL Auto-Target]活动都允许创建和激活。 选择[Adobe Customer Journey Analytics作为报表源](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)时，不支持这些活动。

  即使您指定[!DNL Customer Journey Analytics]作为报表源，[!DNL Target]也用作[!DNL Automated Personalization]活动的报表源。

  如果将[!DNL Customer Journey Analytics]指定为[!UICONTROL Auto-Allocate]或[!UICONTROL Auto-Target]活动的报表源，则可以将[!DNL Target]或[!DNL Analytics]用作报表源。

## 用于报表的时区

指定用于报表的时区。

## 用于报表的货币

指定用于报表的货币。

## 要从[!DNL Target]报表数据中排除的IP

指定要从报表数据中排除的任何IP地址。 例如，排除内部公司地址是一种很好的方法，可确保您的报表数据反映客户在您网站上的交互。

在新行中输入每个IP地址。

## 显示预计收入提升

如果您为目标输入货币值，则可以选择显示预计收入提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

只有[!DNL Experience Cloud]管理员用户可以启用或禁用此功能。 如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI和“优先级”选项会有所不同。 您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
