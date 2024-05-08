---
keywords: 报表；报表；报表；Experience Cloud解决方案；时区；时区；货币；排除IP；预计收入提升；收入；收入提升；细粒度优先级；细粒度
description: 使用 [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] 作为报表源，指定默认时区和货币格式，添加要从报表中排除的IP地址等。
title: 如何在中配置报表 [!DNL Target]？
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: ea9513c4310d13e1e7899aa7e228b4d7ecdf0748
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# 在中配置报表 [!DNL Target]

配置要在中使用的常规设置 [!DNL Adobe Target] 适用于您的整个报表的报表 [!DNL Target] 帐户。

要访问 [!UICONTROL Reporting] 配置页面，单击 **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

您可以在此页上指定以下设置：

* 用于报表的Adobe Experience Cloud解决方案
* 用于报告的时区
* 用于报表的货币
* 要从报表中排除的IP地址
* 是否在报表中显示预计收入提升
* 是否启用细粒度优先级

>[!NOTE]
>
>请注意，要排除设置的时区、货币和IP地址适用于使用的活动 [!DNL Target] 报表。 这些设置不适用于使用 [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) 或 [!DNL Customer Journey Analytics] 作为报表源。

![报告页面](/help/main/administrating-target/assets/reporting.png)

## 报表云解决方案 {#solution}

设置相应选项，以确定用于结果和报表的数据。

选择活动的报表源，方法是 [!DNL Target]， [!DNL Adobe Analytics]，或 [!DNL Adobe Customer Journey Analytics]. 在创建活动时，您还可以选择作为三步引导式工作流的一部分，为每个活动选择报表源。

选择报表源时，请考虑以下信息：

* **[!DNL Adobe Target]**：如果将报表源设置为 **[!DNL Target]** 在此，不允许创建或激活使用 [!DNL Analytics] 或 [!DNL Customer Journey Analytics] 作为报表源。 必须将报表源更改为 **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**：如果将报表源设置为 **[!DNL Analytics]** 在此，不允许创建或激活使用 [!DNL Target] 或 [!DNL Customer Journey Analytics] 作为报表源。 必须将报表源更改为 **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**：如果将报表源设置为 **[!DNL Customer Journey Analytics]** 在此，不允许创建或激活使用 [!DNL Target] 或 [!DNL Analytics] 作为报表源。 必须将报表源更改为 **[!UICONTROL Select per activity]**.
* **为每个活动选择**：如果将报表源设置为 **[!UICONTROL Select per activity]** 在这里，您可以创建和激活所选报表源支持的活动。

在确定报表源时，请考虑以下信息：

* **[!DNL Analytics]**：有关支持的活动的矩阵，使用 [!DNL Analytics] 作为报表源(A4T)，请参阅 [支持的活动类型](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 在 *将Adobe Analytics作为Adobe Target报表源(A4t)*.

  [!UICONTROL Automated Personalization] (AP)无论选择什么报表源，都允许创建和激活活动。 [!UICONTROL Automated Personalization] 选择时不支持活动 [将Adobe Analytics作为Adobe Target报表源(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  即使您指定 [!DNL Analytics] 作为您的报表源， [!DNL Target] 用作的报表源 [!DNL Automated Personalization] 活动。

* **[!DNL Customer Journey Analytics]**：有关支持的活动的矩阵，使用 [!DNL Target] 报告 [!DNL Customer Journey Analytics]，请参见 [支持的活动类型](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) 在 *[!DNL Target]报告[!DNL Adobe Customer Journey Analytics]*.

  [!UICONTROL Automated Personalization] （美联社）， [!UICONTROL Auto-Allocate]、和 [!UICONTROL Auto-Target] 无论选择何种报表源，均允许创建和激活活动。 当您选择时，这些活动不受支持 [将Adobe Customer Journey Analytics作为报表源](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  即使您指定 [!DNL Customer Journey Analytics] 作为您的报表源， [!DNL Target] 用作的报表源 [!DNL Automated Personalization] 活动。

  如果您指定 [!DNL Customer Journey Analytics] 作为的报表源 [!UICONTROL Auto-Allocate] 或 [!UICONTROL Auto-Target] 活动， [!DNL Target] 或 [!DNL Analytics] 可用作报表源。

## 用于报表的时区

指定用于报表的时区。

## 用于报表的货币

指定用于报表的货币。

## 要从中排除的IP [!DNL Target] 报表数据

指定要从报表数据中排除的任何IP地址。 例如，排除内部公司地址是一种很好的方法，可确保您的报表数据反映客户在您网站上的交互。

在新行中输入每个IP地址。

## 显示预计收入提升

如果您为目标输入货币值，则可以选择显示预计收入提升。 [!DNL Target] 可以估计在所有用户都查看成功体验时将获得的收入提升。默认情况下，预计提升功能处于禁用状态。

仅 [!DNL Experience Cloud] 管理员用户可以启用或禁用此功能。 如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

有关详细信息，请参阅[预计收入提升](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)。

## 启用细粒度优先级

允许使用 0 至 999 之间的优先级数字条目。

根据您的设置，UI和“优先级”选项会有所不同。 您可以使用“低”、“中”或“高”的传统优先级设置，也可以启用 0 至 999 的细粒度优先级设置。

如果将具有相同受众的多个活动分配到同一个位置，则需使用优先级。如果将两个或更多活动分配到同一个位置，则会显示具有最高优先级的活动。
