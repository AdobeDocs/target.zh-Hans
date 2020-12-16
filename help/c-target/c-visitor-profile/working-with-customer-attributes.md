---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: 有关通过在Adobe Target人员服务中使用客户属性从客户关系管理(CRM)数据库中使用企业客户数据进行内容定位的信息。
title: Adobe Target客户属性
feature: visitor profiles
translation-type: tm+mt
source-git-commit: e347266dffd00e2a47e0f29f396e9340e581b1be
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 37%

---


# 客户属性

在[!DNL Adobe Enterprise Cloud People]服务中使用客户属性，在[!DNL Adobe Target]中使用客户关系管理(CRM)数据库中的企业客户数据进行内容定位。

通过多个来源收集并存储在CRM数据库中的企业客户数据可用于[!DNL Target]，以战略性方式向客户提供最相关的内容，特别是侧重于回头客。 [!DNL People]服务(以前称为受众和受众)中的用户档案和客户属性将数据收集和分析与测试和优化结合在一起，使数据和洞察具有可操作性。

## 客户属性概述{#section_B4099971FA4B48598294C56EAE86B45A}

[服务](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) 中的客 [!DNL People] 户属性是服务的一部分， [!DNL Adobe Experience Cloud] 它为企业提供了将客户数据推送到平台的 [!DNL Experience Cloud] 工具。

载入到 [!DNL Experience Cloud] 的数据适用于所有 [!DNL Experience Cloud] 工作流。[!DNL Target] 使用此数据根据属性定位退回客户。[!DNL Adobe Analytics] 也会使用这些属性，它们可用于分析和分段。

![crs示例](/help/c-target/c-visitor-profile/assets/crs.png)

在处理客户属性和[!DNL Target]时，请考虑以下信息：

* 在使用[!DNL People]服务中的[!UICONTROL 客户属性]功能之前，您必须满足一些先决条件要求。 有关详细信息，请参阅&#x200B;*Experience Cloud服务和管理文档*&#x200B;中[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0)中的“上传客户属性的先决条件”。

   >[!NOTE]
   >
   >[!DNL at.js] （任何版本）或 [!DNL mbox.js] 58或更高版本是必需的。

* [!DNL Adobe] 不保证来自CRM访客库的100%的客户属性(用户档案)数据 [!DNL Experience Cloud] 都已载入，因此可用于在中定位 [!DNL Target]。在我们当前的设计中，可能不会载入少量数据（大型生产批次中高达0.1%）。
* 从[!DNL Experience Cloud]导入到[!DNL Target]的访客属性数据的生命周期取决于用户档案的生命周期，默认为14天。 有关详细信息，请参阅[访客用户档案生命周期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* 如果`vst.*`参数是标识访客的唯一内容，则只要`authState`为UNAUTHENTICATED(0)，就不会获取现有的“authenticated”用户档案。 仅当`authState`更改为AUTHENTICATED(1)时，用户档案才会生效。

   例如，如果`vst.myDataSource.id`参数用于标识访客（其中`myDataSource`是数据源别名），且没有MCID或第三方ID，则使用参数`vst.myDataSource.authState=0`将不会获取可能通过“客户属性”导入创建的用户档案。 如果所需的行为是获取已验证的用户档案，则`vst.myDataSource.authState`的值必须为1(AUTHENTICATED)。

* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## 在人员服务中访问客户属性

1. 在[!DNL Adobe Experience Cloud]中，单击菜单图标（![菜单图标](/help/c-target/c-visitor-profile/assets/menu-icon.png)），然后单击&#x200B;**[!UICONTROL 人员]**。

   ![人员](/help/c-target/c-visitor-profile/assets/people.png)

1. 单击&#x200B;**[!UICONTROL 客户属性]**&#x200B;选项卡。

   ![“客户属性”选项卡](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## 目标{#section_00DAE94DA9BA41398B6FD170BC7D38A3}的客户属性工作流

完成以下步骤以在 [!DNL Target] 中使用 CRM 数据，如下所示：

![crm工作流](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

有关完成以下每个任务的详细说明，请参阅[创建客户属性源并上传&#x200B;*Experience Cloud服务和管理文档*&#x200B;中的数据文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)。

1. 创建数据文件。

   将客户数据从 CRM 导出为 CSV 格式以创建 .csv 文件。或者，也可以创建 zip 或 gzip 文件进行上传。确保CSV文件的第一行是标题，并且所有行（客户数据）的条目数相同。

   下图显示了一个企业客户数据文件示例：

   ![crs示例](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   下图显示了一个企业客户。csv文件示例：

   ![csv范例](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. 创建属性来源并上传数据文件。

   指定数据源的名称和描述以及别名 ID。别名ID是用于`VisitorAPI.js`中客户属性代码的唯一ID。

   >[!IMPORTANT]
   >
   >数据源名称和属性名称不得包含句点。

   您的数据文件必须符合文件上传要求，且不得超过100MB。 如果您的文件太大，或者您有需要重复上传的数据，您可以通过FTP传送您的文件。

   * **HTTPS:** 您可以拖放。csv数据文件或单击浏览以 **** 从文件系统上传。
   * **FTP：单** 击FTP链接， [通过FTP上传文件](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。第一步是为 Adobe 提供的 FTP 服务器提供密码。指定密码，然后单击&#x200B;**[!UICONTROL 完成]**。

   现在，将您的 CSV/ZIP/GZIP 文件传输到 FTP 服务器。此文件传输成功后，请创建一个名称相同且扩展名为。fin的新文件。 将此空文件传输到服务器。这表示传输结束和[!DNL Experience Cloud]开始处理数据文件。

1. 验证架构。

   验证过程允许您将显示名称和描述映射到已上传的属性（字符串、整数、数字等等）。将每个属性映射到其正确的数据类型、显示名称和描述。

   完成模式验证后，单击&#x200B;**[!UICONTROL 保存]**。 文件上传时间因其大小而异。

   ![验证模式](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![上传模式](/help/c-target/c-visitor-profile/assets/upload1.png)

1. 配置订阅并激活属性来源。

   单击&#x200B;**[!UICONTROL 添加订阅]**，然后选择解决方案以订阅这些属性。[配](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) 置订阅设置和解决方案之 [!DNL Experience Cloud] 间的数据流。激活属性来源允许数据流动到订阅的解决方案。您上传的客户记录与您的网站或应用程序中的传入 ID 信号相匹配。

   ![配置解决方案](/help/c-target/c-visitor-profile/assets/solution.png)

   ![激活](/help/c-target/c-visitor-profile/assets/activate.png)

   在执行此步骤时，请注意以下限制：

   * 使用 HTTP 方法每次上传的最大文件大小为 100 MB。
   * 使用 HTTP 方法每次上传的最大文件大小为 4 GB。
   * 允许订阅的属性数量：[!DNL Target Standard] 为 5，[!DNL Target Premium] 为 200。

## 在 Target 中使用客户属性 {#section_107E3A0F0EC7478E82E6DBD17B30B756}

您可以通过以下方式在 [!DNL Target] 中使用客户属性：

### 创建定位受众

在 [!DNL Target] 中，您可以在创建受众时从“访客配置文件”区域选择一个客户属性。列表中的所有客户属性都有前缀 &lt; data_source_name >。可根据需要，将这些属性与其他数据属性结合使用以构建受众。

![Target 受众](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### 使用令牌创建配置文件脚本

可以在配置文件脚本中使用格式 `crs.get('<Datasource Name>.<Attribute name>')` 引用客户属性。

此配置文件脚本可直接在选件中使用以交付属于当前访客的属性。

### 在您的网站中使用 mbox3rdPartyID 以便成功实施和使用

将`mbox3rdPartyId`作为参数传递到`targetPageParams()`方法内的全局mbox。 应将`mbox3rdPartyId`的值设置为CSV数据文件中存在的客户ID。

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服务

如果您使用 Experience Cloud ID 服务，则需要设置客户 ID 和身份验证状态以在定位中使用客户属性。有关详细信息，请参阅&#x200B;*Experience CloudID服务帮助*&#x200B;中的[客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。

有关在 [!DNL Target] 中使用客户属性的更多信息，请参阅以下资源：

* [创建客户属性源并上传Experience Cloud服](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) 务和管 *理文档中的数据文件*
* 数字营销产品组的博客文章&#x200B;**[客户属性：了解的越多，关联的越好](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## 客户{#section_BE0F70E563F64294B17087DE2BC1E74C}经常遇到的问题

使用客户属性和[!DNL Target]时，您可能会遇到以下问题。

>[!NOTE]
>
>问题1和问题2在这一领域造成大约60%的问题。 问题3造成大约30%的问题。 问题4造成大约5%的问题。 其余 5% 是由于其他问题所致。

### 问题1:由于用户档案太大，客户属性被删除

用户配置文件中的特定字段没有字符限制，但如果配置文件大于 64 K，则会通过删除最早的属性来截断配置文件，直到其再次小于 64 K。

### 问题2:[!DNL Target]的受众库中未列出的属性，即使在数天后也是如此

这通常是管道连接问题。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题3:投放无法基于属性工作

该配置文件尚未在 Edge 上更新。您可以让您的客户属性团队重新发布该信息源来解决此问题。

### 问题4:实施问题

请注意以下实施问题：

* 未正确传递访客 ID。ID在`mboxMCGVID`中传递，而不是`setCustomerId`。
* 已正确传递访客 ID，但“AUTHENTICATION”状态未设置为“已验证”。
* 未正确传递 `mbox3rdPartyId`。

### 问题五：`mboxUpdate`未正确执行

`mboxUpdate`未能通过 `mbox3rdPartyId` 正确执行 

### 问题6:未将客户属性导入[!DNL Target]

如果在目标中找不到“客户属性”数据，请确保在过去&#x200B;*x*&#x200B;天内进行导入，其中&#x200B;*x*&#x200B;是目标[访客用户档案生命周期](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md)值（默认为14天）。

## 培训视频：使用客户属性![Tutorial徽章](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}上载脱机数据

此视频向您展示如何将脱机CRM、服务台、销售点和其他营销数据导入[!DNL Experience Cloud People]服务，并使用其已知ID将其与访客关联。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
