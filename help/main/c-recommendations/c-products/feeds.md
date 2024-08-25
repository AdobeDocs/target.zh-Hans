---
keywords: 推荐信息源；信息源；SAINT；ftp；csv；分类；analytics分类
description: 了解信息源如何使用CSV文件、Google Product Search信息源格式和 [!DNL Analytics] 产品分类将实体导入 [!DNL Adobe Target] [!DNL Recommendations]。
title: 如何在 [!DNL Target Recommendations]中使用[!UICONTROL Feeds]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: a0cf6d497fc5b9a04888d0c6597c98bbbb639cbe
workflow-type: tm+mt
source-wordcount: '2463'
ht-degree: 45%

---

# 信息源

使用信息源将实体导入到[!DNL Adobe Target] [!DNL Recommendations]中。 可以使用CSV文件、Google Product Search信息源格式和[!DNL Adobe Analytics]产品分类发送实体。

## 信息源概述 {#concept_D1E9C7347C5D4583AA69B02E79607890}

信息源允许您传递[实体](/help/main/c-recommendations/c-products/products.md)，或者使用页面上没有提供或不能直接从页面安全发送（如利润、COGS等）的信息来扩充您的mbox数据。

信息源允许您将详细的项目信息传递到[!DNL Recommendations]，例如产品ID、类别、名称、消息和其他属性。

您可以从[!DNL Target]产品分类文件或Google Product Search文件中选择要发送到[!DNL Recommendations]服务器的列。

然后，有关每个项目的这些数据段可用于：

* 显示设计中的值
* 定义标准包含规则
* 将项目排序为不同的收藏集
* 将排除项应用于推荐

可使用信息源或mbox将项目描述传递到[!DNL Target]。 如果同时通过实体源和 mbox 收集数据，则采用最新的数据。通常，最新的数据来自 mbox，因为 mbox 的查看频率更高。在极少数情况下，实体源数据和 mbox 数据的时间相同，这时使用 mbox 数据。

[!UICONTROL Feeds]列表(**[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]**)提供了有关您创建的任何馈送的信息。

![“信息源”页面](/help/main/c-recommendations/c-products/assets/feeds-page.png)

[!UICONTROL Feeds]页包含以下列：

* **名称**：创建过程中指定的信息源的名称。要编辑信息源的名称，您必须编辑信息源本身。使用新名称保存馈送时，将刷新馈送。
* **类型**：类型包括 [CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA)、[Google 产品信息源](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)和 [Analytics 分类](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A)。
* **状态**：信息源的当前[状态](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0)。
* **计划**：显示信息源的更新计划： [!UICONTROL Daily]、[!UICONTROL Weekly]、[!DNL Every 2 Weeks]或[!UICONTROL Never]。
* **项目**：显示信息源中的项目数。
* **上次更新**：显示上次更新信息源的日期和时间，以及更新信息源的人员姓名。如果[!UICONTROL Last Updated]信息源显示为“未定义”，则表示该信息源来自[!DNL Recommendations Classic]，不能在[!DNL Target Premium Recommendations]内进行更改。

单击信息图标可显示一个卡片，其中显示上次上传日期和馈送的URL。

单击省略号图标可访问以下操作： [!UICONTROL Deactivate]、[!DNL Edit]、[!UICONTROL Copy]和[!UICONTROL Delete]。

>[!IMPORTANT]
>
>上传的实体和实体属性会在61天后过期。 这意味着：
>
>* 您的信息源应至少每月运行一次，以确保您的目录内容不会过期。
>* 从信息源文件中删除项目时，不会从目录中删除该项目。 要从目录中删除该项，请通过[!DNL Target] UI或API手动删除该项。 或者，修改物料属性（如库存）以确保不考虑物料。

## Source类型

可以使用CSV文件、Google Product Search信息源格式和[!DNL Adobe Analytics]产品分类发送实体。

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

您可以使用[!DNL Adobe]专有的CSV上传格式创建.csv文件。 该文件包含有关产品的保留属性和自定义属性的显示信息。要上传特定于您的实施的属性，请将标头行中的 `CustomN` 替换为您要使用的属性的名称。在下面的示例中，`entity.Custom1` 被替换为 `entity.availability`。然后，您可以将文件批量上传到 [!DNL Recommendations] 服务器。

与 Google 信息源格式相比，使用 .csv 格式具有以下优势：

* .csv格式不需要字段映射。
* .csv格式支持多值属性（请参阅下面的示例）。
* .csv格式支持最多100个自定义属性。 如果您需要 100 个以上的自定义属性，则可以使用指定的一组不同的自定义属性创建第二个信息源文件。

如果您的页面上没有mbox，或者希望使用网站上不可用的项目来补充显示信息，请使用批量上传方法来发送显示信息。 例如，您可能想要发送不会在您的网站上发布的库存信息。

使用.csv文件、Google产品信息源或[!DNL Analytics]产品分类信息源上传的任何数据都会覆盖数据库中的现有实体属性值。 如果您通过 mbox 请求发送价格信息，然后使用文件发送不同的价格值，则文件中的值将覆盖使用 mbox 请求设置的值。一个例外是 `categoryId` 实体属性，该属性会附加类别值，而不是被覆盖以符合 250 个字符限制。

>[!IMPORTANT]
>
>在 .csv 文件中，不要用双引号 (&quot;) 引住值，除非是有意为之。如果用双引号引住值，则必须使用另一组双引号将其引住来进行转义。 未转义的双引号会导致推荐信息源无法正确加载。

例如，以下语法不正确：

```
"Apples "Bananas" Grapes"",
```

以下语法正确：

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>无法使用空白值覆盖现有值。在其位置传递另一个值以覆盖它。 对于售价，一种常见解决方案是传入实际的“NULL”或某种其他消息。 然后，可以写入一个模板规则，以排除具有该值的项目。

成功上传产品实体约两个小时后，产品将显示在管理界面中。

以下是 .csv 文件的代码示例：

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### Google {#section_8EFA98B5BC064140B3F74534AA93AFFF}

Google Product Search 信息源类型使用 Google 格式。这与[!DNL Adobe]专有的CSV上传格式不同。

如果您已有 Google 产品信息源，则可以将其用作导入文件。

>[!NOTE]
>
>无需使用 Google 数据。[!DNL Recommendations]使用与Google相同的格式。 您可以使用此方法上传您的任何数据，并且还可以使用可用的计划功能。但是，您必须在设置文件时保留 Google 的预定义属性名称。

大多数零售商会将产品上传到Google，这样当访客使用Google产品搜索时，将会显示其产品。 [!DNL Recommendations] 完全遵循 Google 对实体源的规范要求。实体源可以通过.xml、.txt或.tsv发送到[!DNL Recommendations]，并且可以使用Google](https://support.google.com/merchants/answer/188494?hl=en&amp;topic=2473824&amp;ctx=topic#US)定义的[属性。 可以在 [Google 购物页面](https://www.google.com/prdhp)上搜索结果。

>[!NOTE]
>
>托管 Google 信息源内容的服务器上必须可以使用 POST 方法。

由于[!DNL Recommendations]用户已将.xml或.txt源配置为通过URL或FTP发送到Google，因此实体源将接受该产品数据并使用这些数据构建Recommendations目录。 指定此信息源存在的位置后，推荐服务器随即会检索数据。

如果您使用Google Product Search来上传实体信息源，并且想要在其中显示推荐或根据查看次数跟踪算法交付的产品查看次数，则仍必须在页面上具有产品页面mbox。

Google 信息源不支持自定义属性具有多个值。

馈送会在您保存并激活它时运行。 它在您保存馈送时运行，然后在一小时后每天运行。

以下是 Google Product Search 信息源 .xml 文件的代码示例：

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

以下是 Google Product Search 信息源 .tsv 文件的代码示例：

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### [!DNL Analytics]产品分类 {#section_79E430D2C75443BEBC9AA0916A337E0A}

[!DNL Analytics]产品分类是唯一可用于推荐的分类。 有关此分类文件的详细信息，请参阅&#x200B;*Analytics组件*&#x200B;指南中的[关于分类](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html)。 推荐需要的所有信息并非都可在当前实施中使用，因此，如果要添加到分类文件，请遵循此用户指南。

>[!IMPORTANT]
>
>在使用[!DNL Analytics]产品分类将实体数据导入[!DNL Recommendations]之前，请注意，这不是首选方法。
>
> 请注意以下事项：
>
>* 更新实体属性会导致长达 24 小时的额外延迟。
>* [!DNL Target]仅支持[!UICONTROL Product Classifications]。 [!DNL Analytics]产品SKU必须映射到与[!DNL Recommendations] `entity.id`相同的级别。 可以使用[!UICONTROL Adobe Consulting Services]设计自定义[!DNL Analytics]分类。 如有疑问，请联系您的客户经理。

## 创建信息源 {#steps}

可创建一个信息源，以将有关产品或服务的信息插入到 [!DNL Recommendations] 中。

1. 在Target界面中，单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**。

   ![“创建信息源”对话框](assets/CreateFeed.png)

1. 为您的信息源指定一个描述性名称。
1. 选择&#x200B;**[!UICONTROL Source Type]**。

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   有关[!UICONTROL CSV]和[!UICONTROL Google Product Feed]信息源类型的信息，请参阅[信息源概述](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890)。 您还可以[下载模型CSV指南](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv)，以帮助您正确设置信息源的格式。

1. （视情况而定）如果您选择&#x200B;**[!UICONTROL CSV]**&#x200B;或&#x200B;**[!UICONTROL Google Product Feed]**，请指定可以访问馈送的位置。

   * **FTP**：如果您选择 FTP，请提供 FTP 服务器信息、登录凭据、文件名和 FTP 目录。您可以使用带有SSL的FTP (FTPS)实现更安全的上传。

     支持的 FTP 服务器设置：

      * 必须将 FTP 和 FTPS 设置为使用被动 FTP。
      * 对于FTPS，请将服务器配置为接受显式FTPS连接。
      * 不支持 SFTP。
      * 您可以手动指定启动连接的端口（例如，`ftp://ftp.yoursite.com:2121`）。 如果未指定端口，则将使用默认的 FTP 或 FTPS 端口。

   * **URL**：如果选择[!UICONTROL URL]，请指定URL。

1. （视情况而定）如果您选择&#x200B;**[!UICONTROL Analytics Classifications]**，请从下拉列表中选择报表包。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;箭头以显示[!UICONTROL Schedule]选项。

   ![步骤结果](assets/CreateFeedSchedule.png)

1. 选择一个更新选项：

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never]：不计划更新。 如果您不希望运行此信息源，请选择此选项。

1. 指定要运行信息源的时间。

   此选项基于浏览器中使用的时区。如果您想要使用不同时区的时间，则必须根据您所在的时区计算该时间。

1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;箭头以显示[!UICONTROL Mapping]选项，然后指定您希望如何将数据映射到[!DNL Target]定义。

   ![步骤结果](assets/CreatFeedMapping.png)

1. （可选）如果您希望信息源属于某个环境（主机组），请选择该主机组。

   默认情况下，信息源属于所有主机组。这可确保此信息源中的项目可在任何环境中使用。有关更多信息，请参阅[主机](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

1. 单击 **[!UICONTROL Save]**。

创建或编辑信息源后，该信息源将立即运行。 然后，馈送会根据您设置的参数进行更新。 需要一些时间才能提供这些信息。 首先，信息源必须同步，接着必须对其进行处理并将其编入索引，然后才能对其发布并使其可供使用。当前状态显示在“信息源”列表中的[信息源状态](/help/main/c-recommendations/c-products/feeds.md#status)下。 在该过程完成之前，您可以关闭 [!DNL Target]，该过程会继续执行。

编入索引期间，在将各个值编入索引之前，将会显示产品和信息源标头。这样，您就可以搜索并查看产品，从而在完成索引之前创建收藏集、排除项、设计和活动。

如果状态显示为“成功”，则表示文件已找到且已正确解析。在将该文件编入索引之前，无法在 [!DNL Recommendations] 中使用相应的信息，编入索引可能需要一些时间，具体取决于文件的大小。如果进程失败，则表示找不到文件。 例如，您使用了不正确的URL，或者FTP信息不正确，或者存在解析错误。

## 信息源状态和指示器 {#concept_E475986720D1400999868B3DFD14A7A0}

有关可能的信息源状态及其指示器的信息。

### 信息源状态 {#status}

以下是信息源可能具有的几种状态：

| 状态 | 描述 |
|--- |--- |
| [!UICONTROL Syncing] | 正在将信息源设置详细信息保存到[!DNL Target]。 |
| [!UICONTROL Sync Failed] | 无法将信息源设置详细信息保存到[!DNL Target]。 请重试。 |
| [!UICONTROL No Feed Run] | 您已创建信息源，但尚未安排该信息源（频率设置为“从不”）。 |
| 已计划在 &lt;日期和时间>** 运行 | 信息源尚未运行，但已计划在指定的日期和时间运行。 |
| [!UICONTROL Waiting for Download] | [!DNL Target]正在准备下载信息源文件。 |
| [!UICONTROL Downloading Feed File] | [!DNL Target]正在下载信息源文件。 |
| [!UICONTROL Importing Items] | [!DNL Target]正在从信息源文件导入项目。 |
| 已在&#x200B;*指定时间*&#x200B;成功导入信息源 | [!DNL Target]已将信息源文件导入其内容交付系统。 已在内容交付系统中对项目属性进行了更改，这些更改将很快地反映在交付的推荐中。 如果没有看到预期的更改，请重试并刷新包含推荐的页面。<br>注释：<ul><li>如果对项目属性所做的更改导致项目被排除在推荐之外，则会立即反映该排除项。 如果项目是新添加的，或者对属性的更改导致该项目不再&#x200B;*从推荐中*，则在下一次算法更新之前不会反映此项目，此过程将在24小时内发生。</li><li>显示此状态时，更新可能尚未反映在[!UICONTROL Catalog Search] UI中。 [!UICONTROL Catalog Search]中列出了单独的状态，指示上次更新可搜索目录的时间。</li></ul> |
| [!UICONTROL Failed to Index] | 索引操作失败。请重试。 |
| [!UICONTROL Server Not Found] | FTP 或 URL 位置无效或无法访问。 |

要更新信息源（例如，更改信息源配置或信息源文件），请打开该信息源，进行任何所需更改，然后单击&#x200B;**[!UICONTROL Save]**。

>[!IMPORTANT]
>
>上传的实体会在 61 天后过期。这意味着您应该至少每 60 天上传一次信息源文件，以避免对您的推荐活动造成干扰。如果某个项至少每60天未包含在信息源文件（或其他实体更新方法）中一次，则[!DNL Target]推断该项不再相关，并将其从目录中删除。

### 信息源状态指示器 {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

以下信息源状态指示器显示在[!UICONTROL Status]列中：

| 状态指示器 | 描述 |
|--- |--- |
| 绿色状态指示器 | 当成功将信息源编入索引时，会显示绿色状态圆点，以指示该信息源处于成功状态。 |
| 黄色状态指示器 | 当信息源或信息源索引延迟的时间为信息源频率的 25% 时，会显示黄色状态圆点。例如，对于设置为每日运行的信息源，如果在计划时间后的六小时内未完成索引，则会显示黄色圆点。 注意：一旦信息源状态为“正在等待索引队列”，新更新的值即可用于交付和标准处理。 |
| 白色状态指示器 | 当未设置信息源运行计划时，会显示白色状态圆点，以指示信息源尚未运行。 |
| 红色状态指示器 | 如果馈送无法将数据上传到服务器，则会显示红色状态指示器。 |

请仔细研究下面的示例：

**示例 1:**

* 第一天：上午9:00（太平洋标准时间）的每日馈送流程。
* 第二天：现在是下午 3:30，信息源从昨天上午 9 点之后就没有运行。

状态应为黄色，因为索引原本应在大约 6.5 小时之前运行。6.5 小时 + 24 等于信息源运行期限的 127%。

**示例 2:**

* 1月1日：每月馈送流程在太平洋标准时间上午9:00进行。
* 2月3日：上午10点，馈送已分别有一个月、一天和一小时前未运行。

状态应为黄色，因为索引原本应在大约一天零一小时之前运行。虽然这只是频率设置的 (31+(1/25))/30 = 1.03%，但它超过了延迟一天的最大值。

## 培训视频

以下视频包含有关本文中所讨论概念的详细信息。

### 了解Recommendations中的信息源(3:01) ![概述徽章](/help/main/assets/overview.png)

本视频包含以下信息：

* 了解信息源的用途
* 了解信息源的值

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### 创建信息源(6:44) ![教程徽章](/help/main/assets/tutorial.png)

本视频包含以下信息：

* 设置信息源
* 了解要使用哪种类型的信息源

>[!VIDEO](https://video.tv.adobe.com/v/27696)
