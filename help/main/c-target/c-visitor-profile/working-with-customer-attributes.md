---
keywords: 客户关系管理；客户记录服务；crs；crm；mbox3rdpartyid；客户属性；定位；csv；crm；adobe experience cloud人员
description: 了解如何使用客户关系管理(CRM)数据库中的企业客户数据在 [!DNL Adobe Target]中进行内容定位。
title: 什么是客户属性以及如何使用它们？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 0b17b61bb60162af6bc35246219355077ab6bf44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 29%

---

# 客户属性

有关使用[!DNL Adobe Target]服务中的客户属性将客户关系管理(CRM)数据库中的企业客户数据用于[!DNL Adobe Experience Cloud People]中的内容定位的信息。

通过多个源收集并存储在CRM数据库中的企业客户数据可以在[!DNL Target]中使用，以便向客户战略性地交付最相关的内容，特别是旧客户。 [!DNL People]服务（以前为“配置文件和受众”）中的受众和客户属性将数据收集和分析与测试和优化结合在一起，使数据和分析具有可操作性。

## 客户属性概述 {#section_B4099971FA4B48598294C56EAE86B45A}

[服务中的](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=zh-Hans)客户属性[!DNL People]是[!DNL Adobe Experience Cloud]的一部分，它为企业提供了一个将其客户数据推送到[!DNL Experience Cloud]平台的工具。

载入到 [!DNL Experience Cloud] 的数据适用于所有 [!DNL Experience Cloud] 工作流。[!DNL Target]使用此数据根据属性定位旧客户。 [!DNL Adobe Analytics] 也会使用这些属性，它们可用于分析和分段。

![crs示例](/help/main/c-target/c-visitor-profile/assets/crs.png)

在处理客户属性和[!DNL Target]时请考虑以下信息：

* 在使用[!UICONTROL Customer Attributes]服务中的[!DNL People]功能之前，必须满足一些先决条件要求。 有关详细信息，请参阅[Experience Cloud界面和管理](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans#section_BD38693AFBF34926BA28E964963B4EA0)指南中的&#x200B;*客户属性*&#x200B;中的“上传客户属性的先决条件”。
* 请注意，如[Experience Cloud界面和管理](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=cn)指南中的&#x200B;*客户属性数据文件和源*&#x200B;中所述，有关文件上传的限制。 作为最佳实践：

   * 上载单个大型文件（在指定的[限制内](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=cn)）。 单个大文件优先于多个较小文件。
   * 如果必须将上载拆分为多个文件，请确保在提交新文件之前已完全处理这些文件。 在提交批次中的下一个文件之前，请确保批次中的每个文件均已完全处理。

* [!DNL Adobe]不保证CRM数据库中100%的客户属性（访客配置文件）数据将加载到[!DNL Experience Cloud]，因此可用于在[!DNL Target]中定位。 在当前设计中，有可能不加载一小部分数据（最多占大批量生产的0.1%）。
* 从[!DNL Experience Cloud]导入到[!DNL Target]的客户属性数据的生命周期取决于访客配置文件的生命周期，默认情况下为14天。 有关详细信息，请参阅[访客配置文件生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* 如果`vst.*`参数是对访客进行标识的唯一参数，则只要`authState`是UNAUTHENTICATED (0)，就不会获取现有的“已经过身份验证”的配置文件。 只有在`authState`更改为AUTHENTICATED (1)时，配置文件才会起作用。

  例如，如果使用`vst.myDataSource.id`参数识别访客（其中`myDataSource`是数据源别名），并且没有MCID或第三方ID，则使用参数`vst.myDataSource.authState=0`不会获取可能已通过“客户属性”导入而创建的配置文件。 如果获取经过身份验证的配置文件是必需的行为，则`vst.myDataSource.authState`的值必须为1 (AUTHENTICATED)。

* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 访问People服务中的客户属性

1. 在[!DNL Experience Cloud]中，单击菜单图标（![菜单图标](/help/main/c-target/c-visitor-profile/assets/menu-icon.png)），然后单击&#x200B;**[!UICONTROL People]**。

   ![人员](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 单击 **[!UICONTROL Customer Attributes]**。

   ![客户属性选项卡](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## [!DNL Target]的客户属性工作流 {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成以下步骤以在 [!DNL Target] 中使用 CRM 数据，如下所示：

![crm工作流](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

有关完成以下每项任务的详细说明，请参阅[Experience Cloud界面和管理](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=zh-Hans)指南中的&#x200B;*创建客户属性来源并上传数据文件*。

1. 创建数据文件。

   将客户数据从CRM导出为CSV格式以创建.csv文件。 或者，也可以创建 zip 或 gzip 文件进行上传。确保CSV文件的第一行是标题，并且所有行（客户数据）的条目数量相同。

   下图显示了一个示例企业客户数据文件：

   ![crs示例](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   下图显示了一个示例企业客户.csv文件：

   ![csv示例](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 创建属性来源并上传数据文件。

   指定数据源的名称和描述以及别名 ID。别名ID是用于在`VisitorAPI.js`中的客户属性代码中的唯一ID。

   >[!IMPORTANT]
   >
   >数据源名称和属性名称不得包含句点。

   您的数据文件必须符合文件上传要求，并且不得超过100 MB。 如果文件过大，或者您必须定期上传数据，则可以改用FTP传输文件。

   * **HTTPS：**&#x200B;您可以拖放.csv数据文件或单击&#x200B;**[!UICONTROL Browse]**&#x200B;以从您的文件系统上传。
   * **FTP：**&#x200B;单击FTP链接以[通过FTP上传文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html?lang=zh-Hans)。 第一步是为 Adobe 提供的 FTP 服务器提供密码。指定密码，然后单击&#x200B;**[!UICONTROL Done]**。

   现在，将您的 CSV/ZIP/GZIP 文件传输到 FTP 服务器。此文件传输成功后，请创建一个具有相同名称和`.fin`扩展名的文件。 将此空文件传输到服务器。这表示传输结束，[!DNL Experience Cloud]开始处理数据文件。

1. 验证架构。

   验证过程允许您将显示名称和描述映射到已上传的属性（字符串、整数、数字等等）。将每个属性映射到其正确的数据类型、显示名称和描述。

   架构验证完成后，单击&#x200B;**[!UICONTROL Save]**。 文件上传时间因其大小而异。

   ![验证架构](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上载架构](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 配置订阅并激活属性来源。

   单击&#x200B;**[!UICONTROL Add Subscription]**，然后选择解决方案以订阅这些属性。 [配置订阅](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html?lang=zh-Hans)设置[!DNL Experience Cloud]和解决方案之间的数据流。 激活属性来源允许数据流动到订阅的解决方案。您上传的客户记录与您的网站或应用程序中的传入 ID 信号相匹配。

   ![配置解决方案](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![激活](/help/main/c-target/c-visitor-profile/assets/activate.png)

   在执行此步骤时，请注意以下限制：

   * 使用 HTTP 方法每次上传的最大文件大小为 100 MB。
   * 使用 HTTP 方法每次上传的最大文件大小为 4 GB。
   * 允许订阅的属性数量：[!DNL Target Standard] 为 5，[!DNL Target Premium] 为 200。

## 在[!DNL Target]中使用客户属性 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以通过以下方式在 [!DNL Target] 中使用客户属性：

### 创建定位受众

在[!DNL Target]中，您可以在创建受众时从[!UICONTROL Visitor Profile]部分中选择客户属性。 列表中的所有客户属性都有前缀 &lt; data_source_name >。可根据需要，将这些属性与其他数据属性结合使用以构建受众。

![Target 受众](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用令牌创建配置文件脚本

可以在轮廓脚本中使用格式 `crs.get('<Datasource Name>.<Attribute name>')` 引用客户属性。

此轮廓脚本可直接在产品建议中使用以交付属于当前访客的属性。

### 在您的网站中使用mbox3rdPartyID以便成功实施和使用

将`mbox3rdPartyId`作为参数传递给`targetPageParams()`方法内的全局mbox。 `mbox3rdPartyId`的值应设置为CSV数据文件中存在的客户ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用Experience Cloud ID服务

如果您使用的是Experience Cloud ID服务，则必须设置客户ID和身份验证状态，以便在定位中使用客户属性。 有关详细信息，请参阅[Experience Cloud ID服务](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hans)指南中的&#x200B;*客户ID和身份验证状态*。

有关在[!DNL Target]中使用客户属性的更多信息，请参阅以下资源：

* 在[Experience Cloud界面和管理](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html?lang=zh-Hans)指南中&#x200B;*创建和上传客户属性数据*

## 客户经常遇到的问题 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客户属性和[!DNL Target]时，您可能会遇到以下问题。

>[!NOTE]
>
>问题1和2导致此领域约60%的问题。 问题3导致大约30%的问题。 问题4导致大约5%的问题。 其余 5% 是由于其他问题所致。

### 问题1：因用户档案过大，删除了客户属性

用户配置文件中的特定字段没有字符限制，但如果配置文件大于 64 K，则会通过删除最早的属性来截断配置文件，直到其再次小于 64 K。

### 问题2：即使在几天之后，[!DNL Target]的受众库中仍未列出属性

这通常是管道连接问题。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题3：投放基于属性不起作用

该配置文件尚未在 Edge 上更新。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题4：实施问题

请注意以下实施问题：

* 未正确传递访客 ID。该ID是在`mboxMCGVID`而不是`setCustomerId`中传递的。
* 已正确传递访客 ID，但“AUTHENTICATION”状态未设置为“已验证”。
* 未正确传递 `mbox3rdPartyId`。

### 问题5：`mboxUpdate`未正确执行

未正确使用`mboxUpdate`执行`mbox3rdPartyId`。

### 问题6：客户属性未导入到[!DNL Target]中

如果在Target中找不到客户属性数据，请确保导入过程在最近&#x200B;*x*&#x200B;天内完成，其中的&#x200B;*x*&#x200B;是Target [访客配置文件生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)值（默认为14天）。

## 培训视频：使用客户属性![教程徽章](/help/main/assets/tutorial.png)上传离线数据 {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

此视频介绍如何将离线CRM、技术支持、销售点和其他营销数据导入[!DNL Experience Cloud People]服务，并使用访客已知ID将其与访客关联。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
