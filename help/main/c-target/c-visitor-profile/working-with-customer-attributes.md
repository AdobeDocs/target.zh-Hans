---
keywords: 客户关系管理；客户记录服务；crs；crm；mbox3rdpartyid；客户属性；定位；csv；crm；adobe experience cloud人员
description: 了解如何使用客户关系管理(CRM)数据库中的企业客户数据在中进行内容定位 [!DNL Adobe Target].
title: 什么是客户属性以及如何使用它们？
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 34%

---

# 客户属性

有关使用客户关系管理(CRM)数据库中的企业客户数据在中进行内容定位的信息 [!DNL Adobe Target] 通过使用 [!DNL Adobe Enterprise Cloud People] 服务。

通过多个源收集并存储在CRM数据库中的企业客户数据可用于 [!DNL Target] 战略性地向客户交付最相关的内容，特别是旧客户。 中的受众和客户属性 [!DNL People] 服务（以前称为“配置文件和受众”）将数据收集和分析与测试和优化结合在一起，使数据和分析具有可操作性。

## 客户属性概述 {#section_B4099971FA4B48598294C56EAE86B45A}

[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) 在 [!DNL People] 服务属于 [!DNL Adobe Experience Cloud] 并为企业提供了一个工具，用于将其客户数据推送到 [!DNL Experience Cloud] 平台。

载入到 [!DNL Experience Cloud] 的数据适用于所有 [!DNL Experience Cloud] 工作流。[!DNL Target] 使用此数据根据属性定位旧客户。 [!DNL Adobe Analytics] 也会使用这些属性，它们可用于分析和分段。

![crs示例](/help/main/c-target/c-visitor-profile/assets/crs.png)

在使用客户属性时请考虑以下信息 [!DNL Target]：

* 在使用之前，您必须满足一些先决条件要求 [!UICONTROL 客户属性] 中的功能 [!DNL People] 服务。 有关更多信息，请参阅中的“上传客户属性的先决条件”。 [客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) 在 *Experience Cloud服务和管理文档*.
* 了解有关文件上传的限制，如中所述 [关于客户属性的数据文件和数据源](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=cn) 在 *《Experience Cloud中央界面组件指南》*. 作为最佳实践：

   * 上传单个大文件(在 [指定的限制](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=cn))。 单个大文件优于多个较小文件。
   * 如果必须将上载拆分为多个文件，请确保在提交新文件之前已完全处理这些文件。 在批处理中提交下一个文件之前，请确保已完全处理批处理中的每个文件。

* [!DNL Adobe] 不保证CRM数据库中100%的客户属性（访客配置文件）数据将载入到 [!DNL Experience Cloud] 因此，可用于在中定位 [!DNL Target]. 在当前设计中，有可能不载入一小部分数据（最多占大批量生产的0.1%）。
* 从导入的客户属性数据的生命周期 [!DNL Experience Cloud] 到 [!DNL Target] 取决于访客个人资料的生命周期，默认为14天。 有关更多信息，请参阅 [访客配置文件生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* 如果 `vst.*` 参数是对访客进行标识的唯一参数，只要满足以下条件，就不会获取现有的“已验证”配置文件 `authState` 是UNAUTHENTICATED (0)。 仅当满足以下条件时，配置文件才会起作用 `authState` 更改为AUTHENTICATED (1)。

   例如，如果 `vst.myDataSource.id` 参数用于标识访客(其中 `myDataSource` 数据源别名)，并且没有使用参数的MCID或第三方ID `vst.myDataSource.authState=0` 不会获取可能已通过“客户属性”导入创建的配置文件。 如果获取经过身份验证的配置文件是必需的行为， `vst.myDataSource.authState` 必须具有值1 (AUTHENTICATED)。

* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 访问People服务中的客户属性

1. 在 [!DNL Adobe Experience Cloud]，单击菜单图标( ![菜单图标](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) )，然后单击 **[!UICONTROL 人员]**.

   ![人员](/help/main/c-target/c-visitor-profile/assets/people.png)

1. 单击 **[!UICONTROL 客户属性]** 选项卡。

   ![“客户属性”选项卡](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## 的客户属性工作流 [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成以下步骤以在 [!DNL Target] 中使用 CRM 数据，如下所示：

![crm工作流](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

有关完成以下每项任务的详细说明，请参阅 [创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服务和管理文档*.

1. 创建数据文件。

   将客户数据从 CRM 导出为 CSV 格式以创建 .csv 文件。或者，也可以创建 zip 或 gzip 文件进行上传。确保CSV文件的第一行是标题，并且所有行（客户数据）的条目数相同。

   下图显示了一个示例企业客户数据文件：

   ![crs示例](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   下图显示了一个示例企业客户.csv文件：

   ![csv示例](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 创建属性来源并上传数据文件。

   指定数据源的名称和描述以及别名 ID。别名ID是用于客户属性代码的唯一ID，位于 `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >数据源名称和属性名称不得包含句点。

   您的数据文件必须符合文件上传要求，并且不得超过100 MB。 如果文件过大，或者您必须定期上传数据，则可以改用FTP传输文件。

   * **HTTPS：** 您可以拖放.csv数据文件或单击 **[!UICONTROL 浏览]** 以从您的文件系统上传。
   * **FTP：** 单击FTP链接以访问 [通过FTP上传文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). 第一步是为 Adobe 提供的 FTP 服务器提供密码。指定密码，然后单击 **[!UICONTROL 完成]**.

   现在，将您的 CSV/ZIP/GZIP 文件传输到 FTP 服务器。此文件传输成功后，请创建一个具有相同名称和 `.fin` 扩展。 将此空文件传输到服务器。这表示传输结束，并且 [!DNL Experience Cloud] 开始处理数据文件。

1. 验证架构。

   验证过程允许您将显示名称和描述映射到已上传的属性（字符串、整数、数字等等）。将每个属性映射到其正确的数据类型、显示名称和描述。

   单击 **[!UICONTROL 保存]** 架构验证完成后。 文件上传时间因其大小而异。

   ![验证架构](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上载架构](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. 配置订阅并激活属性来源。

   单击&#x200B;**[!UICONTROL 添加订阅]**，然后选择解决方案以订阅这些属性。[配置订阅](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 设置数据流 [!DNL Experience Cloud] 和解决方案。 激活属性来源允许数据流动到订阅的解决方案。您上传的客户记录与您的网站或应用程序中的传入 ID 信号相匹配。

   ![配置解决方案](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![激活](/help/main/c-target/c-visitor-profile/assets/activate.png)

   在执行此步骤时，请注意以下限制：

   * 使用 HTTP 方法每次上传的最大文件大小为 100 MB。
   * 使用 HTTP 方法每次上传的最大文件大小为 4 GB。
   * 允许订阅的属性数量：[!DNL Target Standard] 为 5，[!DNL Target Premium] 为 200。

## 在中使用客户属性 [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以通过以下方式在 [!DNL Target] 中使用客户属性：

### 创建定位受众

在 [!DNL Target] 中，您可以在创建受众时从“访客配置文件”区域选择一个客户属性。列表中的所有客户属性都有前缀 &lt; data_source_name >。可根据需要，将这些属性与其他数据属性结合使用以构建受众。

![Target 受众](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用令牌创建配置文件脚本

可以在配置文件脚本中使用格式 `crs.get('<Datasource Name>.<Attribute name>')` 引用客户属性。

此配置文件脚本可直接在选件中使用以交付属于当前访客的属性。

### 在您的网站中使用 mbox3rdPartyID 以便成功实施和使用

通过 `mbox3rdPartyId` 作为参数访问内的全局mbox `targetPageParams()` 方法。 的值 `mbox3rdPartyId` 应设置为CSV数据文件中存在的客户ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服务

如果您使用的是Experience CloudID服务，则必须设置客户ID和身份验证状态，以便在定位中使用客户属性。 有关更多信息，请参阅 [客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 在 *Experience CloudID服务帮助*.

有关在 [!DNL Target] 中使用客户属性的更多信息，请参阅以下资源：

* [创建客户属性来源并上传数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 在 *Experience Cloud服务和管理文档*

## 客户经常遇到的问题 {#section_BE0F70E563F64294B17087DE2BC1E74C}

使用客户属性和时，您可能会遇到以下问题 [!DNL Target].

>[!NOTE]
>
>问题1和2导致该领域约60%的问题。 问题3导致大约30%的问题。 问题4导致大约5%的问题。 其余 5% 是由于其他问题所致。

### 问题1：客户属性被删除，因为用户档案太大

用户配置文件中的特定字段没有字符限制，但如果配置文件大于 64 K，则会通过删除最早的属性来截断配置文件，直到其再次小于 64 K。

### 问题2：中的受众库中未列出属性 [!DNL Target]，即使在几天之后

这通常是管道连接问题。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题3：投放基于属性不起作用

该配置文件尚未在 Edge 上更新。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题4：实施问题

请注意以下实施问题：

* 未正确传递访客 ID。已传入ID `mboxMCGVID` 而不是 `setCustomerId`.
* 已正确传递访客 ID，但“AUTHENTICATION”状态未设置为“已验证”。
* 未正确传递 `mbox3rdPartyId`。

### 第五期： `mboxUpdate` 未正确执行

`mboxUpdate`未能通过 `mbox3rdPartyId` 正确执行 

### 问题6：客户属性未导入到 [!DNL Target]

如果您在Target中找不到客户属性数据，请确保导入发生在过去 *x* 天数，其中 *x* 是目标 [访客配置文件生命周期](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) 值（默认为14天）。

## 培训视频：使用客户属性上传离线数据 ![教程徽章](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

本视频说明如何将离线CRM、技术支持、销售点和其他营销数据导入 [!DNL Experience Cloud People] ，并使用访客的已知ID将其与访客相关联。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
