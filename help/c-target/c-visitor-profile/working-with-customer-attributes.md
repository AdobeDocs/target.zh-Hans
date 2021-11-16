---
keywords: 客户关系管理；客户记录服务；crs;crm;mbox3rdpartyid；客户属性；定位；csv;crm;adobe experience cloud
description: 了解如何在 [!DNL Adobe Target].
title: 什么是客户属性？如何使用这些属性？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 19b012a0fcbf5195b12990f0a634a90597850899
workflow-type: tm+mt
source-wordcount: '1571'
ht-degree: 32%

---

# [未定义](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)

有关在中使用客户关系管理(CRM)数据库中的企业客户数据进行内容定位的信息 [!DNL Adobe Target] 在 [!DNL Adobe Enterprise Cloud People] 服务。

通过多个源收集并存储在CRM数据库内的企业客户数据可以在 [!DNL Target] 以向客户战略性地交付最相关的内容，特别是旧客户。 中的受众和客户属性 [!DNL People] 服务（以前称为“配置文件和受众”）将数据收集和分析与测试和优化结合在一起，使数据和分析具有可操作性。

## 客户属性概述 {#section_B4099971FA4B48598294C56EAE86B45A}

[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) 在 [!DNL People] 服务是 [!DNL Adobe Experience Cloud] 并为企业提供了一个将其客户数据推送到 [!DNL Experience Cloud] 平台。

载入到 [!DNL Experience Cloud] 的数据适用于所有 [!DNL Experience Cloud] 工作流。[!DNL Target] 使用此数据根据属性定位旧客户。 [!DNL Adobe Analytics] 也会使用这些属性，它们可用于分析和分段。

![crs示例](/help/c-target/c-visitor-profile/assets/crs.png)

在您使用客户属性和 [!DNL Target]:

* 在使用 [!UICONTROL 客户属性] 功能 [!DNL People] 服务。 有关更多信息，请参阅 [客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) 在 *Experience Cloud服务和管理文档*.
* 请注意有关文件上载的限制，如 [关于客户属性的数据文件和数据源](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en) 在 *Experience Cloud中心界面组件指南*. 作为最佳实践：

   * 上载单个大文件(在 [指定的限制](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=en))。 与多个较小文件相比，首选使用单个大文件。
   * 如果必须将上传拆分为多个文件，请确保在提交新文件之前已完全处理文件。 在提交下一批之前，请确保对批处理中的每个文件进行了完全处理。

* [!DNL Adobe] 不保证100%的来自CRM数据库的客户属性（访客配置文件）数据会载入到 [!DNL Experience Cloud] 因此，可用于在 [!DNL Target]. 在当前设计中，可能未载入少量数据（大型生产批次的0.1%）。
* 从 [!DNL Experience Cloud] to [!DNL Target] 取决于访客配置文件的生命周期，默认为14天。 有关更多信息，请参阅 [访客配置文件生命周期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* 如果 `vst.*` 参数是标识访客的唯一参数，只要不获取现有的“已验证”配置文件， `authState` 为未验证(0)。 只有在 `authState` 已更改为AUTHENTICATED(1)。

   例如，如果 `vst.myDataSource.id` 参数用于识别访客(其中 `myDataSource` 是数据源别名)，并且没有MCID或第三方ID，使用参数 `vst.myDataSource.authState=0` 不会获取可能已通过“客户属性”导入而创建的配置文件。 如果获取已验证的配置文件是必需的行为，则 `vst.myDataSource.authState` 必须具有值1(AUTHENTICATED)。

* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 在人员服务中访问客户属性

1. 在 [!DNL Adobe Experience Cloud]，单击菜单图标( ![菜单图标](/help/c-target/c-visitor-profile/assets/menu-icon.png) )，然后单击 **[!UICONTROL 人员]**.

   ![人员](/help/c-target/c-visitor-profile/assets/people.png)

1. 单击 **[!UICONTROL 客户属性]** 选项卡。

   ![“客户属性”选项卡](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## 客户属性工作流 [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成以下步骤以在 [!DNL Target] 中使用 CRM 数据，如下所示：

![crm工作流程](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

有关完成以下每项任务的详细说明，请参阅 [创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服务和管理文档*.

1. 创建数据文件。

   将客户数据从 CRM 导出为 CSV 格式以创建 .csv 文件。或者，也可以创建 zip 或 gzip 文件进行上传。确保CSV文件的第一行是标题，并且所有行（客户数据）的条目数都相同。

   下图显示了一个示例企业客户数据文件：

   ![crs示例](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   下图显示了一个示例企业客户.csv文件：

   ![csv示例](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 创建属性来源并上传数据文件。

   指定数据源的名称和描述以及别名 ID。别名ID是要在 `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >数据源名称和属性名称不得包含句点。

   您的数据文件必须符合文件上传要求，且不得超过100 MB。 如果您的文件过大，或者您拥有必须定期上传的数据，则可以通过FTP传送您的文件。

   * **HTTPS:** 您可以拖放.csv数据文件或单击 **[!UICONTROL 浏览]** 从文件系统上传。
   * **FTP:** 单击FTP链接可 [通过FTP上传文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). 第一步是为 Adobe 提供的 FTP 服务器提供密码。指定密码，然后单击 **[!UICONTROL 完成]**.

   现在，将您的 CSV/ZIP/GZIP 文件传输到 FTP 服务器。此文件传输成功后，请创建一个同名文件，并 `.fin` 扩展。 将此空文件传输到服务器。这表示传输结束，并且 [!DNL Experience Cloud] 开始处理数据文件。

1. 验证架构。

   验证过程允许您将显示名称和描述映射到已上传的属性（字符串、整数、数字等等）。将每个属性映射到其正确的数据类型、显示名称和描述。

   单击 **[!UICONTROL 保存]** 架构验证完成后。 文件上传时间因其大小而异。

   ![验证架构](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上传架构](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 配置订阅并激活属性来源。

   单击&#x200B;**[!UICONTROL 添加订阅]**，然后选择解决方案以订阅这些属性。[配置订阅](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 在 [!DNL Experience Cloud] 和解决方案。 激活属性来源允许数据流动到订阅的解决方案。您上传的客户记录与您的网站或应用程序中的传入 ID 信号相匹配。

   ![配置解决方案](/help/c-target/c-visitor-profile/assets/solution.png)

   ![激活](/help/c-target/c-visitor-profile/assets/activate.png)

   在执行此步骤时，请注意以下限制：

   * 使用 HTTP 方法每次上传的最大文件大小为 100 MB。
   * 使用 HTTP 方法每次上传的最大文件大小为 4 GB。
   * 允许订阅的属性数量：[!DNL Target Standard] 为 5，[!DNL Target Premium] 为 200。

## 在中使用客户属性 [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以通过以下方式在 [!DNL Target] 中使用客户属性：

### 创建定位受众

在 [!DNL Target] 中，您可以在创建受众时从“访客配置文件”区域选择一个客户属性。列表中的所有客户属性都有前缀 &lt; data_source_name >。可根据需要，将这些属性与其他数据属性结合使用以构建受众。

![Target 受众](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用令牌创建配置文件脚本

可以在配置文件脚本中使用格式 `crs.get('<Datasource Name>.<Attribute name>')` 引用客户属性。

此配置文件脚本可直接在选件中使用以交付属于当前访客的属性。

### 在您的网站中使用 mbox3rdPartyID 以便成功实施和使用

通过 `mbox3rdPartyId` 作为 `targetPageParams()` 方法。 的值 `mbox3rdPartyId` 应设置为CSV数据文件中存在的客户ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服务

如果您使用的是Experience CloudID服务，则必须设置客户ID和身份验证状态，才能在定位中使用客户属性。 有关更多信息，请参阅 [客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 在 *Experience CloudID服务帮助*.

有关在 [!DNL Target] 中使用客户属性的更多信息，请参阅以下资源：

* [创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服务和管理文档*

## 客户经常遇到的问题 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客户属性时，您可能会遇到以下问题，以及 [!DNL Target].

>[!NOTE]
>
>问题1和问题2造成该领域大约60%的问题。 问题3造成大约30%的问题。 问题4造成大约5%的问题。 其余 5% 是由于其他问题所致。

### 第1期：由于配置文件过大，客户属性会被删除

用户配置文件中的特定字段没有字符限制，但如果配置文件大于 64 K，则会通过删除最早的属性来截断配置文件，直到其再次小于 64 K。

### 第二期：未在的受众库中列出的属性 [!DNL Target]即使在几天后

这通常是管道连接问题。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 第三期：投放无法基于属性运行

该配置文件尚未在 Edge 上更新。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 第4期：实施问题

请注意以下实施问题：

* 未正确传递访客 ID。ID已传入 `mboxMCGVID` 而不是 `setCustomerId`.
* 已正确传递访客 ID，但“AUTHENTICATION”状态未设置为“已验证”。
* 未正确传递 `mbox3rdPartyId`。

### 第5期： `mboxUpdate` 未正确执行

`mboxUpdate`未能通过 `mbox3rdPartyId` 正确执行 

### 第六期：未将客户属性导入 [!DNL Target]

如果您在Target中找不到客户属性数据，请确保导入发生在最后一个 *x* 天数 *x* 是目标 [访客配置文件生命周期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) 值（默认为14天）。

## 培训视频：使用客户属性上传离线数据 ![教程徽章](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

此视频向您展示如何将离线CRM、支持台、销售点和其他营销数据导入 [!DNL Experience Cloud People] 服务，并使用其已知ID将其与访客关联。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
