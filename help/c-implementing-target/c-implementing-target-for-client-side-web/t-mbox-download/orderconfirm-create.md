---
keywords: order confirmation;orderConfirmPage
description: 订单确认 mbox 将记录您网站上订单的详细信息，并能够基于收入和订单生成报表。订单确认 mbox 还可驱动推荐算法，例如“购买了产品 x，也购买了产品 y 的人”。
title: 创建订单确认 mbox - mbox.js
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 69%

---


# 创建订单确认 mbox - mbox.js

订单确认 mbox 将记录您网站上订单的详细信息，并能够基于收入和订单生成报表。订单确认 mbox 还可驱动推荐算法，例如“购买了产品 x，也购买了产品 y 的人”。

>[!IMPORTANT]
>
>**mbox.js终止使用**:2021年3月31日 [!DNL Adobe Target] 将不再支持mbox.js库。2021年3月31日之后，mbox.js发出的所有调用将正常失败，并会通过提供默认内容影响[!DNL Target]活动运行的页面。
>
>我们建议所有客户在此日期之前迁移到新[!DNL Adobe Experience Platform Web SDK]或at.js JavaScript库的最新版本，以避免您的站点出现任何潜在问题。 有关详细信息，请参阅[概述：实现客户端web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)的目标。

>[!NOTE]
>
>* 如果用户在您的网站上进行购买，那么即使您使用了 Analytics for Target (A4T) 进行报告，我们也仍然建议您实施订单确认 mbox。
   >
   >
* 您还可以为at.js 1创建订单确认mbox。*使* 用同一方法；但是， [!DNL at.js] 方法是首选。有关更多信息，请参阅[跟踪转化](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)。
   >
   >
* 如果您使用at.js 2。*x*, `mboxCreate` 不再受支持。使用at.js 2进行订单确认。*x*，使用以下跟踪相关API: [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 和 [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)。


1. 在订单详细信息页面，按照以下模式插入 mbox 脚本。
1. 使用您目录中的动态或静态值替换大写的文字。

   >[!NOTE]
   >
   >使用逗号分隔多个产品 ID。

   **提示：**&#x200B;您也可以在任意 mbox（必须命名为 `orderConfirmPage`）中传递订单信息。还可以在同一营销活动之内的多个 mbox 中传递订单信息。

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

订单确认 mbox 使用以下参数：

| 参数 | 描述 |
|--- |--- |
| `orderId` | 针对转化计数标识订单的唯一值。<br>`orderId` 必须唯一。报表中会忽略重复订单。 |
| `orderTotal` | 所购产品的币值。<br>不要传递货币符号。使用小数点（而非逗号）表示小数值。 |
| `productPurchasedId`（可选） | 订单中所购产品的产品 ID（逗号分隔）列表。<br>这些产品 ID 显示在审计报表中，以支持其他报表分析。 |