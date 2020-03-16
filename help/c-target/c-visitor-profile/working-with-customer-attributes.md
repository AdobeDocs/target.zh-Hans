---
keywords: customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm
description: 有关如何利用 Adobe Profiles & Audiences 核心服务中的客户属性将客户关系管理 (CRM) 数据库的企业客户数据用于 Adobe Target 中的内容定位的信息。
title: Adobe Target中的客户属性
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 7c8705e45b84fb7d49f93e1f3a25392a8d2758a6

---


# 客户属性 {#customer-attributes}

Information about using enterprise customer data from a customer relationship management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud] core service.

通过多个源收集并存储在 CRM 数据库中的企业客户数据可以在 [!DNL Target] 中使用，以便向客户战略性地交付最相关的内容，尤其是旧客户。[!DNL Audiences] 核心服务（以前称为“配置文件和受众”）将数据收集和分析与测试和优化结合在一起，使数据和分析具有可操作性。

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

The Audiences core service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. 载入到 [!DNL Experience Cloud] 的数据适用于所有 [!DNL Experience Cloud] 工作流。[!DNL Target] 使用此数据根据属性定位退回客户。 [!DNL Adobe Analytics] 也会使用这些属性，它们可用于分析和分段。

![](assets/crs.png)

Consider the following information as your work with customer attributes and [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL Audiences] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the *Experience Cloud Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] （任何版本）或 [!DNL mbox.js] 58或更高版本是必需的。

* Adobe does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. 在我们目前的设计中，可能有一小部分数据不会被载入。
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. 有关详细信息，请参阅访 [客资料生命周期](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)。
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will only come into play if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. 如果获取已经过身份验证的配置文件是必需的行为，则 `vst.myDataSource.authState` 必须具有值 1 (AUTHENTICATED)。

* 不能在 `mbox3rdPartyID` 中发送下列字符：加号 (+) 和正斜线 (/)。

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

完成以下步骤以在 [!DNL Target] 中使用 CRM 数据，如下所示：

![](assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Product Documentation*.

1. 创建数据文件。

   将客户数据从 CRM 导出为 CSV 格式以创建 .csv 文件。或者，也可以创建 zip 或 gzip 文件进行上传。确保CSV文件的第一行是标题，并且所有行（客户数据）的条目数相同。

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. 创建属性来源并上传数据文件。

   指定数据源的名称和描述以及别名 ID。The alias Id is a unique ID to be used in your Customer Attribute code in `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >数据源名称和属性名称不得包含句点。

   使用 HTTP 方式最多可以上传 100 MB 的数据文件。大于100 MB（最多4 GB）的文件可以通过FTP上传。

   * **HTTPS:** 您可以拖放。csv数据文件或单击“浏览” **** ，从文件系统上传。
   * **FTP:** 单击FTP链接以通 [过FTP上传文件](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html)。 第一步是为 Adobe 提供的 FTP 服务器提供密码。Specify the password, then click **[!UICONTROL Done]**.

      现在，将您的 CSV/ZIP/GZIP 文件传输到 FTP 服务器。在此文件传输成功后，创建一个名称相同且扩展名为。fin的新文件。 将此空文件传输到服务器。This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. 验证架构。

   验证过程允许您将显示名称和描述映射到已上传的属性（字符串、整数、数字等等）。将每个属性映射到其正确的数据类型、显示名称和描述。

   Click **[!UICONTROL Save]** after the schema validation is complete. 文件上传时间因其大小而异。

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. 配置订阅并激活属性来源。

   单击&#x200B;**[!UICONTROL 添加订阅]**，然后选择解决方案以订阅这些属性。[配置订阅](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) ，在和解决方案之间设置 [!DNL Experience Cloud] 数据流。 激活属性来源允许数据流动到订阅的解决方案。您上传的客户记录与您的网站或应用程序中的传入 ID 信号相匹配。

   ![](assets/solution.png)

   ![](assets/activate.PNG)

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

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### 使用 Experience Cloud ID 服务

如果您使用 Experience Cloud ID 服务，则需要设置客户 ID 和身份验证状态以在定位中使用客户属性。For more information, see [Customer IDs and Authentication State](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

有关在 [!DNL Target] 中使用客户属性的更多信息，请参阅以下资源：

* [创建客户属性来源并上传](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) Experience Cloud产品文 *档中的数据文件*
* 数字营销产品组的博客文章&#x200B;**[客户属性：了解的越多，关联的越好](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/)

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

搭配 [!DNL Target] 使用客户属性时，您可能会遇到以下问题：

| 问题 | 详细信息 |
|--- |--- |
| 客户属性因配置文件过大而被删除 | 用户配置文件中的特定字段没有字符限制，但如果配置文件大于 64 K，则会通过删除最早的属性来截断配置文件，直到其再次小于 64 K。 |
| 即使在几天之后，[!DNL Target] 的受众库中仍未列出属性 | 这通常是管道连接问题。您可以让您的客户属性团队重新发布该信息源来解决此问题。 |
| 不能根据属性进行交付 | 该配置文件尚未在 Edge 上更新。您可以让您的客户属性团队重新发布该信息源来解决此问题。 |
| 实施问题 | 请注意以下实施问题：<ul><li>未正确传递访客 ID。The ID was passed in `mboxMCGVID` instead of `setCustomerId`.</li><li>已正确传递访客 ID，但“AUTHENTICATION”状态未设置为“已验证”。</li><li>未正确传递 `mbox3rdPartyId`。</li> |
| 未正确执行 `mboxUpdate` | `mboxUpdate`未能通过 `mbox3rdPartyId` 正确执行  |
| 客户属性未导入到Target | If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default). |

与客户属性相关的问题中，大约 60% 是因上述第 1 行和第 2 行的问题所致。大约 30% 是因第 3 行中的问题所致。大约 5% 是因第 4 行中的问题所致。其余 5% 是由于其他问题所致。

## 培训视频：使用客户属性上传离线数据 {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8} 教 ![程徽章](/help/assets/tutorial.png)

此视频向您展示如何将离线CRM、服务台、销售点和其他营销数据导入Experience Cloud People服务中，并使用其已知ID将其与访客关联。

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
