---
keywords: 网站页面；定位网站页面；定位；当前页面；定位当前页面；上一页；定位上一页；登陆页面；定位登陆页面；HTTP标头
description: 了解如何使用 [!DNL Adobe Target] 网站上特定页面的访客。
title: 我是否可以根据网站页面定位访客？
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 24%

---

# 网站页面

您可以使用 [!DNL Adobe Target] 访问您网站上特定页面的访客。

1. 在 [!DNL Target] 界面中，单击&#x200B;**[!UICONTROL 受众]** > **[!UICONTROL 创建受众]**。
1. 为受众命名并添加可选描述。
1. 拖放 **[!UICONTROL 网站页面]** 进入受众生成器窗格。

   ![“网站页面”受众](assets/target_site_pages.png)

1. 单击 **[!UICONTROL 选择]** 下拉列表中，选择以下选项之一，然后根据需要配置规则。

   规则中后续下拉列表中的可用选项和计算器因您选择的选项而异。 下图显示了在您选择 [!UICONTROL 当前页面]:

   ![当前页面](assets/current-page.png)

   当您选择 [!UICONTROL 选择].

   * **[!UICONTROL 当前页面]:** 用户正在查看的页面。

      如果选择此选项，则第二个下拉列表中提供了以下选项：

      * [!UICONTROL URL] (有关如何 [!DNL Target] 评估URL，请参阅 [定位和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 域名]
      * [!UICONTROL 查询]
      * [!UICONTROL 子域]
      * [!UICONTROL 顶级域]
      * [!UICONTROL 路径]
      * [!UICONTROL 哈希 (#) 碎片]
   * **[!UICONTROL 上一页]:** 用户在单击到当前页面之前查看的页面。 用户必须从上一页点击到当前页面才能跟踪页面。 如果用户在浏览器中键入新URL，则不会跟踪上一页。 该页的实际内容取决于网站设计。例如，如果当前页面显示有关特定产品的信息，则上一页可能是访客在其中选择特定项目的类别页面。 例如，显示某种类型的多个摄像机的页面，或者可能是指向最终页面的主页。

      如果选择此选项，则第二个下拉列表中提供了以下选项：

      * [!UICONTROL URL] (有关Target如何评估URL的更多信息，请参阅 [定位和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 域名]
      * [!UICONTROL 查询]
      * [!UICONTROL 子域]
      * [!UICONTROL 顶级域]
      * [!UICONTROL 路径]
   * **登陆页面：**&#x200B;登陆页面指访客访问您的网站时看到的第一个页面。例如，如果访客点击了 Google 上的某个通往类别页面的链接，则该类别页面即登陆页面。如果链接通往主页，该主页为登录页。访客会话将记住登录页。您可以根据该会话中访客的登录页向网站的更深层次定位。

      如果选择此选项，则第二个下拉列表中提供了以下选项：

      * [!UICONTROL URL] (有关Target如何评估URL的更多信息，请参阅 [定位和受众常见问题解答](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL 域名]
      * [!UICONTROL 查询]
      * [!UICONTROL 子域]
      * [!UICONTROL 顶级域]
      * [!UICONTROL 路径]
      * [!UICONTROL 哈希 (#) 碎片]

      >[!NOTE]
      >
      >`landing.url` 对象会在更改子域或直接替换 URL 时重置。

   * **[!UICONTROL HTTP标头]:** 此选项会评估 [!DNL Target] 请求。 例如，如果HTTP标头包含语言信息，则可以创建一个包含 `Accept-Language: es` 定位以西班牙语访问该页面的访客的条件。

      如果选择此选项，则第二个下拉列表中提供了以下选项：

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL 授权]
      * [!UICONTROL Cache-Control]
      * [!UICONTROL 连接]
      * [!UICONTROL Content-Length]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Content-Type]
      * [!UICONTROL 日期]
      * [!UICONTROL 预期]
      * [!UICONTROL 从]
      * [!UICONTROL 主机]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL If-None-Match]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Uniquified-Since]
      * [!UICONTROL 最大转发]
      * [!UICONTROL Pragma]
      * [!UICONTROL 代理授权]
      * [!UICONTROL 范围]
      * [!UICONTROL Referrer]
      * [!UICONTROL TE]
      * [!UICONTROL 升级]
      * [!UICONTROL User-Agent]
      * [!UICONTROL 通过]
      * [!UICONTROL 警告]

   如果您选择 [!UICONTROL 当前页面], [!UICONTROL 上一页]或 [!UICONTROL 登陆页面], [!UICONTROL 域] 和 [!UICONTROL 查询] 选项。 选择这些选项时，请考虑以下事项：

   * **域：**&#x200B;页面的完整域。指定域时，最佳做法是使用“包含”。例如，“域等于facebook.com”不接受 `m.facebook.com` 或 `www.facebook.com`. “域包含facebook.com”接受facebook.com的任何变体。
   * **查询：** URL 中第一个问号 (?) 后面的内容。

      `foo.html?e0a72cb2a2c7`





1. （可选）为受众设置其他规则。
1. 单击&#x200B;**[!UICONTROL 完成]**。

您还可以使用自己的“用户定义的查询参数”或“用户定义的标头”来创建网站页面受众。

使用：

* 查询参数(如果用户选择的规则为 [!UICONTROL 当前页面], [!UICONTROL 登陆页面]或 [!UICONTROL 上一页]
* 标头（如果用户选择的规则是HTTP标头）

## 故障排除 {#ts}

* 要使登陆页面受众正常运行，请求必须具有 `mboxReferrer` 参数集(对于交付API， `context.address.referringUrl` 参数),at.js JavaScript库会使用 `document.referrer` 属性。 此 `HTMLDocument` 属性会返回用户从中导航的页面的URI。 当用户直接导航到页面（不是通过链接，而是通过书签）时，此属性的值是一个空字符串。

   如果此行为与您的要求不匹配，请考虑执行以下操作之一：

   * 通过 [mbox参数](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/) to [!DNL Target] 用于定位。
   * 使用 [A/B测试活动](/help/main/c-activities/t-test-ab/test-ab.md) 而不是登陆页面活动。 A/B测试活动不会切换同一访客的体验。
   * 使用 [访客资料](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) 中。

* 在包含逗号的字符串上使用“开始/结束于”计算器时，这些字符串将作为值数组进行计算，其中每个以逗号分隔的值都将进行计算。 例如，如果标题的值为： `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` 它符合以下条件：
   * 从zh开始，
   * 从en开始，
   * 以0.7结尾，
   * 以0.8结束。

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
