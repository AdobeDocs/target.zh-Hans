---
keywords: 实施;mbox.js 非 javascript;重定向器;每次点击成本;每次点击收入
description: 了解如何在电子邮件实施中使用重定向器，其方式与在Adobe中使用mbox的方式类似 [!DNL Target] 活动。
title: 如何使用重定向器？
feature: Implement Email
role: Developer
exl-id: 1e7b99e4-857b-4d0f-afbd-2c5ce6bf0557
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 71%

---

# 使用重定向程序

使用重定向器的方法和您在测试中使用 mbox 的方法类似。

重定向器是使用一种特定的重定向器 URL 创建的，该重定向器 URL 将重定向器 mbox（重定向器）加载到您的帐户中。使用此重定向器的方法和您在测试中使用 mbox 的方法类似。将重定向器 URL 以广告目标链接的形式提交到您的广告网络。

使用重定向器可以执行以下操作：

* 跟踪从您的展示广告链接到您网站的点击量
* 创建单个集中化报表，跟踪多广告网络中对展示广告的点击量
* 多样化展示广告目标。

   例如，在您的主页、类别页面和产品页面上放置相同的横幅。

* 找出哪个登陆页能引起更多的转化

有关确定正确设置的帮助信息，请参阅 [不基于 JavaScript 的实施](/help/main/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)。

## 创建重定向器 {#redirector}

必须先创建重定向器才能使用重定向功能。

1. 决定广告的目标变量，包括默认的目标。
1. 创建重定向器 URL。

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * 其中，`yourclientcode` 是您公司的客户端代码。您公司的客户端代码全部为小写字母，且不含任何特殊字符。

      您的客户端代码位于 [!UICONTROL 管理>实施] 页面 [!DNL Target] 界面。

   * `redirectorlink_456` 是出现在您帐户中并在营销活动和测试中使用的重定向器 mbox 的名称。

      重定向器与其他 mbox 的运行方式不同，但是与其他任何 mbox 一样，都会显示在您的帐户中。为重定向器命名，以便能够轻松地将它与您帐户中其他标准类型的 mbox 区分开来。作为最佳实践，重定向器 mbox 的名称应该以“redirectorlink”开头。

   * 其中，`http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` 是默认目标。

      这必须是进行了编码的 URL，且必须是绝对引用。您可以使用 [HTMLURL编码引用](https://www.w3schools.com/tags/ref_urlencode.asp) 以快速对您的URL进行编码。

      >[!IMPORTANT]
      >
      >请注意，使用重定向器，您可能会面临打开重定向漏洞的风险。 为避免第三方未经授权使用重定向器链接，我们建议您使用“已授权的主机”来允许列表默认的重定向URL域。 Target 使用主机将您要允许重定向到的域列入允许列表。有关详细信息，请在“主机”**&#x200B;中参阅[创建允许列表，其中指定有权将 mbox 调用发送到 Target 的主机](/help/main/administrating-target/hosts.md#allowlist)。

1. 验证重定向器。
   1. *安全最佳实践*:如上所示，确保重定向器列入允许列表中使用的域。 如果您使用的域未，则列入允许列表Adobe将阻止对该域的任何调用，以阻止恶意行为者使用重定向器重定向到可能恶意的域。
   1. 将重定向器 URL 插入到浏览器中并刷新。
   1. 登录到您的帐户，刷新 mbox 列表，然后验证以 mbox 形式列出的新的重定向器。
1. 如果您要为一个广告测试不同目标，则请为每个版本创建[重定向选件](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)。
1. 创建营销活动。

   请参阅[不基于 JavaScript 的实施](/help/main/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)，以了解如何正确设置来实现您的目标。
1. 完成营销活动质量保证工作。

   使用包含重定向器 URL 的 `<a href>` 创建一个虚拟页面。示例：

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. 验证所有体验、默认内容和报表，确保它们在所有环境下能通过所有类型的浏览器按照预期工作。

   >[!NOTE]
   >
   >* “选件预览”或“浏览 mbox”功能不支持重定向器。请在浏览器中直接预览体验。
   >* `mboxDebug` 不适用于重定向器。


1. 将整个重定向 URL 作为广告的目标链接提交给您的展示广告网络。

## 使用重定向器传递“每次点击成本”和“每次点击收入” {#concept_3078EF48E9C44B34992D62AAB9628853}

有关使用重定向器传递每次点击成本和每次点击收入的信息。

### 传递每次点击成本 {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

使用重定向器传递每次点击成本。

>[!NOTE]
>
>最佳做法是使用 **每次访问得分** 参与量度。

将 `&mboxPageValue=-value` 添加到 URL。请注意负值。

例如，每次点击成本为 .10 美分时，如下所示：

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### 传递每次点击收入 {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

使用重定向器传递每次点击收入。

>[!NOTE]
>
>最佳做法是使用 **每次访问得分** 参与量度。

将 `&mboxPageValue=value` 添加到 URL。

例如，每次点击收入为 .10 美分时，如下所示：

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```