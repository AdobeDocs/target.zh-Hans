---
keywords: 推荐;设置;首选项;垂直行业;筛选不兼容的标准;默认主机组;缩览图基本 URL;推荐 API 令牌
description: '了解如何在Adobe Target中实施Recommendations活动。 '
title: 如何实施Recommendations活动？
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 2910fd1130030df79b96160b64e6bd1bdf295814
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 30%

---

# ![PREMIUM](/help/assets/premium.png) 计划和实施 [!DNL Recommendations]

在设置您的首个 [!DNL Recommendations] 活动 [!DNL Adobe Target]，请完成以下步骤：

1. [实施 [!DNL Target]](#implement-target) 和移动设备应用程序界面（用于捕获用户行为和提供推荐）。
1. [设置 [!DNL Recommendations] 目录](#rec-catalog) 产品或内容的受众。
1. [传递行为信息和上下文](#pass-behavioral) to [!DNL Target Recommendations] 以便提供个性化的推荐。
1. [配置全局排除](#exclusions).
1. [配置 [!DNL Recommendations] 设置](#concept_C1E1E2351413468692D6C21145EF0B84).

## 实施 [!DNL Target] {#implement-target}

[!DNL Target Recommendations] 需要您实施 [!DNL Adobe Experience Platform Web SDK] 或at.js 0.9.2（或更高版本）。 请参阅 [实施 [!DNL Target]](/help/c-implementing-target/implementing-target.md) 以了解更多信息。

## 设置Recommendations目录 {#rec-catalog}

要提供高质量的推荐， [!DNL Target] 必须知道要推荐的产品或内容。 您的目录通常应包含三种类型的有关要推荐项目的信息。 假定您推荐电影。 包括以下内容：

1. 要向收到推荐的用户显示的数据。例如，您可以显示电影的名称和电影海报缩略图的URL。
1. 用于应用营销和销售控制的数据。例如，您可以显示影片的评级，以便不推荐NC-17影片。
1. 用于确定项目与其他项目的相似度的数据。 例如，您可以显示电影的流派和电影的导演。

[!DNL Target] 提供了多个用于填充目录的集成选项。 这些选项可以组合使用来更新目录中的不同项目，或更新不同频率上的不同项目属性。

| 方法 | 是什么 | 何时使用 | 其他信息 |
| --- | --- | --- | --- |
| 目录馈送 | 计划信息源(CSV、Google产品XML或 [!DNL Analytics Product Classifications])，以便每天上传和摄取。 | 用于一次发送有关多个项目的信息。 用于发送不常更改的信息。 | 请参阅 [信息源](/help/c-recommendations/c-products/feeds.md). |
| 实体API | 调用API以发送单个项目的即时更新。 | 用于在每次发生大约一个项目时发送更新。 用于发送频繁更改的信息（例如，价格、库存/库存水平）。 | 请参阅 [实体API开发人员文档](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| 在页面上传递更新 | 使用页面上的JavaScript或使用交付API，发送单个项目的即时更新。 | 用于在每次发生大约一个项目时发送更新。 用于发送频繁更改的信息（例如，价格、库存/库存水平）。 | 请参阅 [项目查看/产品页面](#items-product-pages) 下。 |

大多数客户应至少实施一个信息源。 然后，您可以选择使用实体API或页面内方法，通过经常更改的属性或项目的更新来补充您的信息源。

## 传递行为信息和上下文 {#pass-behavioral}

您应该传递到的行为信息和上下文 [!DNL Target] 取决于访客正在执行的操作，该操作通常与访客正在交互的页面类型相关联。

### 项目查看/产品页面 {#items-product-pages}

在访客正在查看单个项目的页面（如产品详细信息页面）上，您应传递访客正在查看的项目的标识。 您还应传递访客正在查看的项目的最精细类别，以允许将推荐过滤到当前类别。

您还可以在产品页面本身上传递某些快速更改的属性。 例如，您可以将`value`)和库存/库存水平。

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### 类别查看/类别页面

在类别页面上，您可能希望将推荐限制为该类别中的产品或内容。 为此，请确保传递当前已查看类别的标识。

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### 购物车加货/购物车查看/结帐页面 {#cart}

在购物车页面上，您可以根据访客当前购物车的内容推荐项目。 为此，请使用特殊参数传递访客当前购物车中所有项目的ID `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

基于购物车的推荐逻辑与“[!UICONTROL 推荐给您]“基于用户的算法”和“[!UICONTROL 查看了这些项目，购买了这些项目的人]&quot;和&quot;[!UICONTROL 购买了这些，也购买了那些的人]“基于项目的算法。

[!DNL Target] 使用协作筛选技术确定访客购物车中每个项目的相似性，然后将每个项目中的这些行为相似性合并在一起，以获得合并列表。

[!DNL Target] 此外，营销人员还可以选择在单个会话或多个会话中查看访客行为：

* **在单个会话中**:基于其他访客在单个会话中的操作。

   当有一种感觉，即产品会根据使用情况、时机或事件强烈地“一起使用”时，在单个会话中查看行为可能会很有意义。 例如，访客正在购买打印机，并且可能还需要墨水和纸张。 或者，游客正在购买花生酱，可能还需要面包和果冻。

* **跨多个会话**:基于其他访客在多个会话中执行的操作。

   当有一种感觉，即产品会根据访客偏好或品味强烈地彼此“一起使用”时，跨多个会话查看行为可能会很有意义。 例如，访客喜欢《星球大战》，也可能喜欢《印第安纳·琼斯》，即使该访客不一定想在同一座位上观看两个电影。 或者，访客喜欢棋盘游戏“代号”，也可能喜欢棋盘游戏“Avalon”，即使访客不能同时玩两个游戏。 

无论您是查看单个会话中的访客行为还是查看多个会话中的访客行为， [!DNL Target] 根据每位访客当前购物车中的项目，为其提供推荐。

### 排除访客购物车中已有的项目

在您网站的整个页面上，您可以从推荐中排除某些项目。 例如，您可能不希望推荐访客当前购物车中已有的项目。 为此，请使用特殊参数传递要排除的所有项目的ID `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### 购买/订单确认页面

发生购买事件时，传递已购买项目或项目的标识。 请参阅 [跟踪转化](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) in *实施 [!DNL Target] 没有标签管理器*.

## 配置全局排除 {#exclusions}

排除您从不希望向访客推荐的全局级别的任何项目。 请参阅[排除项](/help/c-recommendations/c-products/exclusions.md)。

## 配置 [!DNL Recommendations] 设置 {#concept_C1E1E2351413468692D6C21145EF0B84}

可使用一些设置来管理 [!DNL Recommendations] 实施。

访问 [!UICONTROL Recommendations设置] 选项，打开 [!DNL Target] 在 [!DNL Adobe Experience Cloud]，然后单击 **[!UICONTROL Recommendations]** > **[!UICONTROL 设置]**.

![](assets/recs_settings.png)

以下选项可供选择：

| 设置 | 描述 |
|--- |--- |
| 自定义全局 Mbox | （可选）指定要用于提供 [!DNL Target] 活动的自定义全局 mbox。默认情况下，使用的全局mbox [!DNL Target] 用于 [!DNL Recommendations].<br>注意：此选项在 [!DNL Target] [!UICONTROL 管理] 页面。 打开 [!DNL Target]，然后单击 [!UICONTROL 管理] > [!UICONTROL 可视化体验编辑器]. |
| 垂直行业 | 垂直行业用来帮助对您的推荐标准进行分类。此信息可帮助您的团队成员找到适用于特定页面的标准，例如最适用于购物车页面或媒体页面的标准。 |
| 筛选不兼容的标准 | 启用此选项，可仅显示要求选定页面传递所需数据的标准。并非每个标准都能在每个页面上正确运行。 页面或mbox必须传入 `entity.id` 或 `entity.categoryId` 以兼容当前项目/当前类别推荐。 一般来说，最好只显示兼容的标准。但是，如果您希望将不兼容的标准用于活动，请取消选中此选项。<br>如果使用标签管理解决方案，建议您禁用此选项。<br>有关此选项的更多信息，请参阅[推荐常见问题解答](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md)。 |
| 默认主机组 | 选择您的默认主机组。<br>主机组可用于为不同用途而分隔目录中的可用项。例如，您可以将主机组用于“开发和生产”环境、不同的品牌或不同的地理位置。默认情况下，“目录搜索”、“收藏集”和“排除项”中的预览结果均基于默认的主机组。（也可以使用“环境”筛选器来选择要预览结果的不同主机组。）默认情况下，新添加的项目在所有主机组中都可用，除非在创建或更新项目时指定了环境 ID。交付的“推荐”取决于请求中指定的主机组。<br>如果您看不到产品，请确保您使用的是正确的主机组。例如，如果您将推荐设置为使用测试环境并将您的主机组设置为“测试”，则您可能需要在测试环境中重新创建收藏集，之后才会显示产品。要查看每个环境中提供了哪些产品，请在每个环境中使用“目录搜索”。您还可以预览选定环境（主机组）的“推荐”收藏集和排除项内容。<br>**注意：**&#x200B;更改选定的环境后，必须单击搜索以更新返回的结果。<br>[!UICONTROL 环境]筛选器可从 [!DNL Target] UI 中的以下位置访问：<ul><li>目录搜索（推荐 > 目录搜索）</li><li>“创建收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 新建]）</li><li>“更新收藏集”对话框（[!UICONTROL 推荐 > 收藏集 > 编辑]）</li><li>“创建排除项”对话框（[!UICONTROL 推荐 > 排除项 > 新建]）</li><li>“更新排除项”对话框（[!UICONTROL 推荐 > 排除项 > 编辑]）</li></ul>有关更多信息，请参阅[主机](/help/administrating-target/hosts.md)。 |
| 缩览图基本 URL | 为您的产品目录设置基本 URL 后，可以在指定产品缩览图以及传递缩览图 URL 时使用相对 URL。<br>例如：<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>设置的便是相对于缩览图基本 URL 的 URL。 |
| 推荐 API 令牌 | 在推荐 API 调用（例如下载 API）中使用此令牌。 |
