---
keywords: 推荐信息源；信息源；SAINT；ftp；sftp；csv；分类；analytics分类
description: 了解信息源如何使用CSV文件、[!DNL Google Product Search]信息源格式和[!DNL Analytics]产品分类将实体导入[!DNL Adobe Target] [!DNL Recommendations]。
title: 如何在[!DNL Target Recommendations]中使用[!UICONTROL 信息源]？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
TQID: 'https://experienceleague.adobe.com/lXXX8XEXGtt1DDMI63Ck4AbCGDjzkxs60oW2nEnc0Go'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ced3e207fe0a99485fa1fce2a29d2c2855bb2bd4
workflow-type: tm+mt
source-wordcount: '2785'
ht-degree: 31%
---
# 信息源

使用信息源将实体导入到[!DNL Adobe Target] [!DNL Recommendations]中。 可以使用CSV文件、[!DNL Google Product Search]信息源格式和[!DNL Adobe Analytics]产品分类来发送实体。

## 信息源概述 {#concept_D1E9C7347C5D4583AA69B02E79607890}

馈送允许您传递[实体](/help/main/c-recommendations/c-products/products.md)，或者使用页面上没有提供或不能直接从页面安全发送的信息来扩充您的mbox数据。 例如，利润、销货成本(COGS)等。

信息源还允许您将详细的项目信息传递到[!DNL Recommendations]，例如产品ID、类别、名称、消息和其他属性。

您可以从[!DNL Target]产品分类文件或[!DNL Google Product Search]文件中选择要发送到[!DNL Recommendations]服务器的列。

然后，有关每个项目的这些数据段可用于：

* 显示设计中的值
* 定义标准包含规则
* 将项目排序为不同的收藏集
* 将排除项应用于推荐

可使用信息源或mbox将项目描述传递到[!DNL Target]。 如果[!DNL Target]同时使用实体馈送和mbox收集数据，则最新数据将获胜。 通常，最新的数据来自 mbox，因为 mbox 的查看频率更高。 在极少数情况下，实体源数据和 mbox 数据的时间相同，这时使用 mbox 数据。

[!UICONTROL 馈送]列表（**[!UICONTROL 推荐]** > **[!UICONTROL 馈送]**）提供了有关您创建的任何馈送的信息。

[!UICONTROL 馈送]页面包含以下列：

* **名称**：创建过程中指定的信息源的名称。 要编辑信息源的名称，您必须编辑信息源本身。 使用新名称保存馈送时，将刷新馈送。
* **状态**：信息源的当前[状态](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0)。
* **类型**：类型包括[CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA)、[[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)和[Analytics分类](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A)。
* **项目**：显示信息源中的项目数。
* **计划**：显示馈送的更新计划： [!UICONTROL 每日]、[!UICONTROL 每周]、[!DNL Every 2 Weeks]或[!UICONTROL 从不]。
* **上次更新**：显示上次更新信息源的日期和时间，以及更新信息源的人员姓名。

单击[!UICONTROL 自定义表]图标（![自定义表图标](/help/main/assets/icons/ColumnSetting.svg)）以选择或取消选择要显示的列。

单击[!UICONTROL 信息]图标（![信息图标](/help/main/assets/icons/InfoOutline.svg)）可显示显示上次上传日期和馈送URL的卡片。

单击[!UICONTROL 更多操作]图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）可访问以下操作： [!UICONTROL 停用]、[!DNL Edit]、[!UICONTROL 复制]和[!UICONTROL 删除]。

>[!IMPORTANT]
>
>上传的实体和实体属性会在61天后过期。 这意味着：
>
>* 您的信息源应至少每月运行一次，以确保您的目录内容不会过期。
>* 从信息源文件中删除项目时，不会从目录中删除该项目。 要从目录中删除该项，请通过[!DNL Target] UI或API手动删除该项。 或者，修改物料属性（如库存）以确保不考虑物料。

## Source类型

可以使用CSV文件、[!DNL Google Product Search]信息源格式和[!DNL Adobe Analytics]产品分类来发送实体。

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

您可以使用[!DNL Adobe]专有的CSV上传格式创建.csv文件。 该文件包含有关产品的保留属性和自定义属性的显示信息。 要上传特定于您的实施的属性，请将标头行中的 `CustomN` 替换为您要使用的属性的名称。 在下面的示例中，`entity.Custom1` 被替换为 `entity.availability`。 然后，您可以将文件批量上传到 [!DNL Recommendations] 服务器。

与[!DNL Google]信息源格式相比，使用.csv格式具有以下优势：

* .csv格式不需要字段映射。
* .csv格式支持多值属性（请参阅下面的示例）。
* .csv格式支持最多100个自定义属性。 如果您需要 100 个以上的自定义属性，则可以使用指定的一组不同的自定义属性创建第二个信息源文件。

如果您的页面上没有mbox，或者希望使用网站上不可用的项目来补充显示信息，请使用批量上传方法来发送显示信息。 例如，您可能想要发送不会在您的网站上发布的库存信息。

使用.csv文件、Google产品信息源或[!DNL Analytics]产品分类信息源上传的任何数据都会覆盖数据库中的现有实体属性值。 如果您通过 mbox 请求发送价格信息，然后使用文件发送不同的价格值，则文件中的值将覆盖使用 mbox 请求设置的值。 一个例外是 `categoryId` 实体属性，该属性会附加类别值，而不是被覆盖以符合 250 个字符限制。

>[!IMPORTANT]
>
>在 .csv 文件中，不要用双引号 (&quot;) 引住值，除非是有意为之。 如果用双引号引住值，则必须使用另一组双引号将其引住来进行转义。 未转义的双引号会导致推荐信息源无法正确加载。

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
>无法使用空白值覆盖现有值。 在其位置传递另一个值以覆盖现有值。 对于售价，一种常见解决方案是传入实际的“NULL”或某种其他消息。 然后，可以写入一个模板规则，以排除具有该值的项目。

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

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

[!DNL Google Product Search]信息源类型使用[!DNL Google]格式，而不是[!DNL Adobe]专有的CSV格式。 您可以重用现有的[!DNL Google Product Feed]将产品数据导入[!DNL Recommendations]。

>[!NOTE]
>
>您不需要向[!DNL Google]提交数据。 您可以导入自己的数据和计划更新，前提是文件使用预定义的[!DNL Google]属性名称。

[!DNL Recommendations]接受遵循[!DNL Google]信息源规范并使用由Google[&#128279;](https://support.google.com/merchants/answer/188494?hl=en&topic=2473824&ctx=topic#US)定义的属性的.xml、.txt和.tsv文件。 指定信息源的URL或FTP位置，以便[!DNL Recommendations]服务器可以检索文件并生成您的目录。

>[!NOTE]
>
>承载[!DNL Google]馈送的服务器必须允许POST方法。

请牢记以下要求和限制：

* 仍需要产品页面mbox才能在该页面上显示推荐或跟踪基于查看数的算法的产品查看。
* [!DNL Google]信息源不支持自定义属性的多个值。

在保存并激活馈送时，馈送会运行，并且其每日运行时间比初始运行时间晚一个小时。

以下示例显示了.xml格式的[!DNL Google Product Search]馈送：

```xml
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

以下是[!DNL Google Product Search]源.tsv文件的示例代码：

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### [!DNL Analytics]产品分类 {#section_79E430D2C75443BEBC9AA0916A337E0A}

[!DNL Adobe Analytics]产品分类是唯一可用于推荐的分类。 有关此分类文件的详细信息，请参阅&#x200B;*Analytics组件*&#x200B;指南中的[关于分类](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html)。 推荐需要的所有信息并非都可在当前实施中使用，因此，如果要添加到分类文件，请遵循此用户指南。

>[!IMPORTANT]
>
>在使用[!DNL Analytics]产品分类将实体数据导入[!DNL Recommendations]之前，请注意，这不是首选方法。
>
> 请注意以下事项：
>
>* 更新实体属性会导致长达 24 小时的额外延迟。
>* [!DNL Target]仅支持[!UICONTROL 产品分类]。 [!DNL Analytics]产品SKU必须映射到与[!DNL Recommendations] `entity.id`相同的级别。 可以使用[!UICONTROL Adobe Consulting服务]来设计自定义[!DNL Analytics]分类。 如有疑问，请联系您的客户经理。

## 创建信息源 {#steps}

可创建一个信息源，以将有关产品或服务的信息插入到 [!DNL Recommendations] 中。

1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 信息源]** > **[!UICONTROL 创建信息源]**。

1. 为您的信息源指定一个描述性名称。
1. 选择&#x200B;**[!UICONTROL Source类型]**。

   * [!UICONTROL CSV]
   * [!UICONTROL Google产品信息源]
   * [!UICONTROL Analytics分类]

   有关[!UICONTROL CSV]和[!UICONTROL Google产品信息源]信息源类型的信息，请参阅[信息源概述](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890)。 您还可以[下载模型CSV指南](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv)，以帮助您正确设置信息源的格式。

1. （视情况而定）如果您选择了&#x200B;**[!UICONTROL CSV]**&#x200B;或&#x200B;**[!UICONTROL Google产品信息源]**，请指定可以访问信息源的位置。

   * **FTP**：如果您选择 FTP，请提供 FTP 服务器信息、登录凭据、文件名和 FTP 目录。 您可以使用带有SSL的FTP (FTPS)实现更安全的上传。

     +++ 支持的FTP服务器设置

     * 必须将 FTP 和 FTPS 设置为使用被动 FTP。
     * 对于FTPS，请将服务器配置为接受显式FTPS连接。
     * 您可以手动指定启动连接的端口（例如，`ftp://ftp.yoursite.com:2121`）。 如果未指定端口，则将使用默认的 FTP 或 FTPS 端口。

   +++

   * **SFTP**：输入SFTP服务器的主机名或IP地址、端口（默认值： 22）、用户名、目录和文件名。 对于身份验证，请提供密码、SSH私钥或两者。

     +++ 支持的SFTP服务器设置和限制

     * 身份验证使用密码、SSH私钥或两者。 至少需要一个。
     * 客户生成并拥有密钥对。 在SFTP用户的`authorized_keys`文件中安装公钥，然后将私钥作为PEM文本粘贴到Target中。 接受的密钥类型为RSA、Ed25519和ECDSA，格式为PEM (`-----BEGIN RSA PRIVATE KEY-----`)、PKCS#8 (`-----BEGIN PRIVATE KEY-----`)或OpenSSH (`-----BEGIN OPENSSH PRIVATE KEY-----`)。
     * 不支持受密码保护的私钥，无法保存信息源。
     * Target会存储已加密的私钥，并且不再显示。 要旋转馈送，请编辑馈送并输入新键。
     * 输入没有`sftp://`前缀、端口或路径的裸主机名或IP地址。 将“端口”字段用于非默认端口。
     * 首次连接时接受服务器主机密钥，无需与Adobe交换指纹。
     * SFTP在Target界面和Recommendations API中可用，但在旧版Recommendations Classic管理界面中不可用。 Adobe不托管SFTP端点，请使用客户托管的服务器。
     * SFTP服务器必须可从Internet访问，并允许来自Adobe Target下载地址的入站连接。 发布此更新之前，生产IP列表必须由工程部门确认。

   +++

   * **URL**：如果选择[!UICONTROL URL]，请指定URL。

1. （视情况而定）如果您选择&#x200B;**[!UICONTROL Analytics分类]**，请从下拉列表中选择报表包。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;箭头以显示[!UICONTROL 计划]选项。

1. 选择一个更新选项：

   * [!UICONTROL 每天]
   * [!UICONTROL 每周]
   * [!UICONTROL 每2周]
   * [!UICONTROL 从不]：不计划更新。 如果您不希望运行此信息源，请选择此选项。

1. 指定要运行信息源的时间。

   此选项基于浏览器中使用的时区。 如果您想要使用不同时区的时间，则必须根据您所在的时区计算该时间。

1. 单击&#x200B;**[!UICONTROL 下一步]**&#x200B;箭头以显示[!UICONTROL 映射]选项，然后指定您希望如何将数据映射到[!DNL Target]定义。

1. （可选）如果您希望信息源属于某个环境（主机组），请选择该主机组。

   默认情况下，信息源属于所有主机组。 这可确保此信息源中的项目可在任何环境中使用。 有关更多信息，请参阅[主机](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)。

1. 单击&#x200B;**[!UICONTROL 保存]**。

创建或编辑馈送后，馈送会立即运行，然后根据您的设置进行更新。 馈送在数据可用之前必须同步、处理和索引。 检查[!UICONTROL 信息源]列表中的[信息源状态](/help/main/c-recommendations/c-products/feeds.md#status)以了解进度。 即使您关闭[!DNL Target]，处理过程仍会继续。

在索引过程中，产品和信息源标题显示在单个值之前，因此您可以在索引完成之前搜索产品并创建收藏集、排除项、设计和活动。

“成功”状态表示已找到文件并已正确解析该文件。 其数据仅在索引后才会在[!DNL Recommendations]中可用，这需要一些时间，具体取决于文件大小。 失败可能是由于URL或FTP信息不正确、文件缺失或解析错误所致。

## 信息源状态和指示器 {#concept_E475986720D1400999868B3DFD14A7A0}

有关可能的信息源状态及其指示器的信息。

### 信息源状态 {#status}

以下是信息源可能具有的几种状态：

| 状态 | 描述 |
|--- |--- |
| [!UICONTROL 正在同步] | 正在将信息源设置详细信息保存到[!DNL Target]。 |
| [!UICONTROL 同步失败] | 无法将信息源设置详细信息保存到[!DNL Target]。 请重试。 |
| [!UICONTROL 没有运行的信息源] | 您已创建信息源，但尚未安排该信息源（频率设置为“从不”）。 |
| 已计划在 &lt;日期和时间>** 运行 | 信息源尚未运行，但已计划在指定的日期和时间运行。 |
| [!UICONTROL 正在等待下载] | [!DNL Target]正在准备下载信息源文件。 |
| [!UICONTROL 正在下载信息源文件] | [!DNL Target]正在下载信息源文件。 |
| [!UICONTROL 正在导入项目] | [!DNL Target]正在从信息源文件导入项目。 |
| 已在&#x200B;*指定时间*&#x200B;成功导入信息源 | [!DNL Target]已将信息源文件导入其内容交付系统。 已在内容交付系统中对项目属性进行了更改，这些更改将很快地反映在交付的推荐中。 如果没有看到预期的更改，请重试并刷新包含推荐的页面。<br>注意：<ul><li>如果对项目属性所做的更改导致项目被排除在推荐之外，则会立即反映该排除项。 如果项目是新添加的，或者对属性的更改导致该项目不再&#x200B;*从推荐中*，则在下一次算法更新之前不会反映此项目，此过程将在24小时内发生。</li><li>显示此状态时，更新可能尚未反映在[!UICONTROL 目录搜索] UI中。 [!UICONTROL 目录搜索]中列出了单独的状态，指示上次更新可搜索目录的时间。</li></ul> |
| 部分导入失败 | 以前，当所有行均未上传时，馈送仍会被标记为成功。 因此，会错误地认为所有行都已上载为信息源，这表明上载成功。<P>以下是您可能会遇到部分信息源导入的情景：<ul><li>您为生产环境上传了一个信息源文件，例如100行。</li><li>馈送运行并上传了这些行中的80行，由于格式不正确、字段超出字符数等原因，删除了20行。</li><li>馈送在UI中标记为成功，这让您感觉已上传所有100行。</li><li>您预计这20种产品中会有一部分在交付活动中出现，但实际上并未出现。</li><li> 您现在很困惑，因为您上传了包含相关产品的产品详细信息的信息源。 当您通过实体API进行查询时，您不会在后端看到它，这告知您它不在后端。</li></ul>为了消除这种混淆，改进了消息以确切告知馈送发生了什么情况。 它现在不会标记为成功，而是标记为部分导入失败。 |
| [!UICONTROL 未能编入索引] | 索引操作失败。 请重试。 |
| 找不到[!UICONTROL 服务器] | FTP、SFTP或URL位置无效或无法访问。 |

要更新信息源（例如，更改信息源配置或信息源文件），请打开该信息源，进行任何所需更改，然后单击&#x200B;**[!UICONTROL 保存]**。

>[!IMPORTANT]
>
>上传的实体会在 61 天后过期。 这意味着您应该至少每 60 天上传一次信息源文件，以避免对您的推荐活动造成干扰。 如果某个项至少每60天未包含在信息源文件（或其他实体更新方法）中一次，则[!DNL Target]推断该项不再相关，并将其从目录中删除。

### 信息源状态指示器 {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

以下信息源状态指示器将显示在“[!UICONTROL 状态]”列中：

| 状态指示器 | 描述 |
|--- |--- |
| 绿色状态指示器 | 当成功将信息源编入索引时，会显示绿色状态圆点，以指示该信息源处于成功状态。 |
| 黄色状态指示器 | 当信息源或信息源索引延迟的时间为信息源频率的 25% 时，会显示黄色状态圆点。 例如，对于设置为每日运行的信息源，如果在计划时间后的六小时内没有完成索引，则会显示黄色圆点。 注意：一旦信息源状态为“正在等待索引队列”，新更新的值即可用于交付和标准处理。 |
| 白色状态指示器 | 当未设置信息源运行计划时，会显示白色状态圆点，以指示信息源尚未运行。 |
| 红色状态指示器 | 如果馈送无法将数据上传到服务器，则会显示红色状态指示器。 |

请仔细研究下面的示例：

**示例 1:**

* 第一天：上午9:00（太平洋标准时间）的每日馈送流程。
* 第二天：现在是下午 3:30，信息源从昨天上午 9 点之后就没有运行。

状态应为黄色，因为索引原本应在大约 6.5 小时之前运行。 6.5 小时 + 24 等于信息源运行期限的 127%。

**示例 2:**

* 1月1日：每月馈送流程在太平洋标准时间上午9:00进行。
* 2月3日：上午10点，馈送已分别有一个月、一天和一小时前未运行。

状态应为黄色，因为索引原本应在大约一天零一小时之前运行。 虽然这只是频率设置的 (31+(1/25))/30 = 1.03%，但它超过了延迟一天的最大值。

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
