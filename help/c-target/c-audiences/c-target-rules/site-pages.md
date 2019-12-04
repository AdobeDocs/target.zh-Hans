---
keywords: site pages;target site pages;targeting;current page;target current page;previous page;target previous page;landing page;target landing page;mbox;target mbox
description: 您可以使用Adobe Target定位特定页面上或具有特定mbox参数的访客。
title: Adobe Target中的站点页面
topic: Standard
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: 3742c2a19aab55d65ee3f32c9202321ece860439

---


# 网页{#site-pages}

您可以定位特定页面上的访客或具有特定mbox参数的访客。

>[!NOTE]
>
>Audience site page types and comparison operators now match types and comparison operators as they were in [!DNL Target Classic]. 您也可以使用自己的“用户定义的查询参数”或“用户定义的标头”来创建网站页面受众。

1. 在 [!DNL Target] 界面中，单击&#x200B;**[!UICONTROL 受众]** &gt; **[!UICONTROL 创建受众]**。
1. 对受众进行命名。
1. 单击&#x200B;**[!UICONTROL 添加规则]** &gt; **[!UICONTROL 网站页面]**。

   ![“网站页面”受众](assets/target_site_pages.png)

1. 单击“ **[!UICONTROL 选择]** ”(Select)下拉列表，选择以下选项之一，然后根据需要配置规则。

   规则中后续下拉列表中的可用选项和计算器因您选择的选项而异。 下图显示了如果选择“当前页面”时可用 [!UICONTROL 的选项]:

   ![当前页面](/help/c-target/c-audiences/c-target-rules/assets/current-page.png)

   选择“选择”时，初始下拉列表中提供以下 [!UICONTROL 选项]。

   * **当前页面：**&#x200B;用户当前所在的页面，即包含活动中的 mbox 的页面。如果在活动级别进行定位，当前页面可以是包含用于定义活动参加条件的 mbox 的页面，或显示内容的页面。如果按体验确定目标，当前页即展示型 mbox 所在的页面。对于成功量度或转化定位，它是这些mbox所在的页面。

      如果选择此选项，则第二个下拉列表中提供以下选项：

      * URL
      * 域
      * 查询
      * 子域
      * 顶级域
      * 路径
      * 哈希 (#) 碎片
   * **上一页：**&#x200B;用户在点击到当前页面之前所在的页面。（必须是用户从前一页点击进入当前页的情况下才能跟踪此页。如果用户通过在浏览器输入新 URL 进入当前页，则上一页不会被跟踪。）该页的实际内容取决于网站设计。例如，如果当前页显示某特定产品的信息，上一页则可能是供访客选择此特定项目的产品类别页（比如展示同类型的几款相机的页面），也有可能是导向最终页面的主页。

      如果选择此选项，则第二个下拉列表中提供以下选项：

      * URL
      * 域
      * 查询
      * 子域
      * 顶级域
      * 路径
   * **登陆页面：**&#x200B;登陆页面指访客访问您的网站时看到的第一个页面。例如，如果访客点击了 Google 上的某个通往类别页面的链接，则该类别页面即登陆页面。如果链接通往主页，该主页为登录页。访客会话将记住登录页。您可以根据该会话中访客的登录页向网站的更深层次定位。

      如果选择此选项，则第二个下拉列表中提供以下选项：

      * URL
      * 域
      * 查询
      * 子域
      * 顶级域
      * 路径
      * 哈希 (#) 碎片
      >[!NOTE]
      >
      >`landing.url` 对象会在更改子域或直接替换 URL 时重置。

   * **** HTTP头：此选项评估访客访问站点时看到的第一页的HTTP头中的信息。 例如，如果HTTP头包含语言信息，则可以创建一个规则，其中包含用于定位访 `Accept-Language: es` 客的条件。

      如果选择此选项，则第二个下拉列表中提供以下选项：

      * Accept
      * Accept-Charset
      * 接受编码
      * Accept-Language
      * 授权
      * Cache-Control
      * 连接
      * 内容——长度
      * 内容MDS
      * Content-Type
      * 日期
      * 期望
      * 从
      * 主机
      * If-Match
      * If-Modified-Since
      * If-None-Match
      * If-Range
      * If-Uniquofied-Since
      * 最大转发
      * Pragma
      * 代理授权
      * 范围
      * Referer
      * TE
      * 升级
      * User-Agent
      * Via
      * 警告
   如果选择“当前页 [!UICONTROL 面]”、“上 [!UICONTROL 一页”或“登录页]”，则 [!UICONTROL DomainDomain]和Query Query选项  将可用。 选择这些选项时，请考虑以下事项：

   * **域：**&#x200B;页面的完整域。指定域时，最佳做法是使用“包含”。例如，“域等于 facebook.com”将不接受 `m.facebook.com` 或 `www.facebook.com`。而“域包含 facebook.com”则将接受 facebook.com 的任何变体。
   * **查询：** URL 中第一个问号 (?) 后面的内容。

      `foo.html?e0a72cb2a2c7`





1. （可选）单击&#x200B;**[!UICONTROL 添加规则]，然后为受众设置更多规则。**
1. 单击&#x200B;**[!UICONTROL 保存]**。

您还可以使用自己的“用户定义的查询参数”或“用户定义的标头”来创建网站页面受众。

使用：

* 查询参数，如果用户选择的规则是“当前页面”、“登陆页面”或“上一页”。
* 标头，如果用户选择的规则是 HTTP 标头。

如下图所示：

![](assets/site_pages.png)

## 疑难解答 {#ts}

* 要使登陆页面受众正常工作，请求必须设置at.js javaScript库使用属性从页面获取的参数 `mboxReferrer` (对于Delivery API, `context.address.referringUrl` 该参数为 `document.referrer` 参数)。 此 `HTMLDocument` 属性返回用户从中导航的页面的URI。 当用户直接导航到页面时（不是通过链接，而是通过书签），此属性的值是空字符串。

   如果此行为与您的要求不符，请考虑执行下列操作之一：

   * 传递 [mbox参数](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) , [!DNL Target] 以便用于定位目的。
   * 使用 [A/B测试活动](/help/c-activities/t-test-ab/test-ab.md) ，而不是登录页面活动。 A/B测试活动不会切换同一访客的体验。
   * 请改用访 [客资料](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) 。

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=chi_hans)
