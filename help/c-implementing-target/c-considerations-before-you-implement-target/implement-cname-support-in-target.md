---
keywords: 客户关怀；CNAME；证书程序；规范名称；Cookie；证书；AMC;Adobe托管证书；Digicert；域控制验证；DCV
description: 与Adobe客户关怀团队合作，在Adobe [!DNL Target] 中实施CNAME（规范名称）支持，以处理广告阻止问题或与ITP相关的Cookie策略。
title: 如何在Target中使用CNAME?
feature: 隐私和安全
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 1f27ebfb7fb4203558f4d10e5e98cced04a82f2b
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 1%

---

# CNAME和Target

有关与[!DNL Adobe]客户关怀团队一起在[!DNL Adobe Target]中实施CNAME（规范名称）支持的说明。 使用CNAME处理广告拦截问题或与ITP相关（智能防跟踪）Cookie策略。 使用CNAME，将对客户拥有的域进行调用，而不是对[!DNL Adobe]拥有的域进行调用。

## 在Target中请求CNAME支持

1. 确定您的SSL证书所需的主机名列表（请参阅下面的常见问题解答）。

1. 对于每个主机名，在DNS中创建一个CNAME记录，指向常规[!DNL Target]主机名`clientcode.tt.omtrdc.net`。

   例如，如果您的客户端代码为“cnamecustomer”，并且您建议的主机名为`target.example.com`，则您的DNS CNAME记录类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobe的证书颁发机构DigiCert在此步骤完成之前无法颁发证书。 因此，在此步骤完成之前， [!DNL Adobe]无法完成您对CNAME实施的请求。

1. [在您打开](/help/assets/FPC_Request_Form.xlsx) Adobe客户关怀票证请 [求CNAME支持时，填写此表单并将其包含在内](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe[!DNL Target]客户端代码：
   * SSL证书主机名(示例：`target.example.com target.example.org`):
   * SSL证书购买者(强烈建议购买Adobe，请参阅常见问题解答):Adobe/客户
   * 如果客户购买的证书也称为“自带证书”(BYOC)，请填写以下附加详细信息：
      * 证书组织(示例：Example Company Inc):
      * 证书组织单位(可选，示例：营销):
      * 证书国家/地区(示例：美国):
      * 证书状态/区域(示例：加州):
      * 证书城市(示例：圣何塞):

1. 如果[!DNL Adobe]正在购买证书，则[!DNL Adobe]将与DigiCert合作，在Adobe的生产服务器上购买并部署您的证书。

   如果客户购买证书(BYOC),[!DNL Adobe]客户关怀团队会向您发送证书签名请求(CSR)。 通过您选择的证书颁发机构购买证书时，请使用CSR。 颁发证书后，将证书和任何中间证书的副本发送到[!DNL Adobe]客户关怀团队进行部署。

   [!DNL Adobe] 客户关怀会在您的实施准备就绪后通知您。

1. 将`serverDomain`更新为at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在[!DNL Target]中请求和实施CNAME支持的常见问题：

### 我能否提供我自己的证书（自带您自己的证书或BYOC）？

您可以提供自己的证书。 但是，[!DNL Adobe]不建议使用此做法。 对于[!DNL Adobe]和[!DNL Adobe]购买并控制证书时，SSL证书生命周期的管理会更轻松。 必须每年续订SSL证书。 因此，[!DNL Adobe]客户关怀团队必须每年联系您以及时获取新证书。 某些客户可能难以及时生成续订的证书。 由于浏览器拒绝连接，证书过期后，您的[!DNL Target]实施就会受到威胁。

>[!IMPORTANT]
>
>如果您请求[!DNL Target]自带证书CNAME实施，则您负责每年向[!DNL Adobe]客户关怀团队提供续订的证书。 如果允许CNAME证书在[!DNL Adobe]可以部署续订的证书之前过期，则会导致您的特定[!DNL Target]实施中断。

### 新SSL证书过期多长时间？

2020年9月1日以前签发的证书为两年。 2020年9月1日或之后签发的证书为一年期证书。 您可以在此处](https://www.digicert.com/position-on-1-year-certificates)阅读有关迁移到一年证书的更多信息。[

### 我应选择哪些主机名？ 我应选择每个域的主机名数量？

[!DNL Target] CNAME实施在SSL证书和客户DNS中每个域只需要一个主机名。Adobe建议使用一个主机名。 某些客户出于自身目的而要求每个域的主机名更多（例如，在暂存环境中进行测试），这是受支持的。

大多数客户都选择诸如`target.example.com`之类的主机名。 Adobe建议遵循此做法，但最终由您选择。 请求现有DNS记录的主机名。 这样做会导致冲突并延迟[!DNL Target] CNAME请求的解决时间。

### 我已经为[!DNL Adobe Analytics]实施了CNAME，我们能否使用相同的证书或主机名？

否， [!DNL Target]需要单独的主机名和证书。

### 我当前的[!DNL Target]实施是否受ITP 2.x的影响？

在 Safari 浏览器中，导航到您拥有 [!DNL Target] JavaScript 库的网站。如果您在CNAME的上下文中看到已设置[!DNL Target] Cookie（如`analytics.company.com`），则不受ITP 2.x的影响。

仅使用[!DNL Analytics] CNAME即可解决[!DNL Target]的ITP问题。 只有在广告拦截场景中，如果[!DNL Target]被阻止，您才需要单独的[!DNL Target] CNAME。

有关ITP的更多信息，请参阅[Apple智能防跟踪(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME实施后，我可以期待哪种服务中断？

部署证书时（包括证书续订）不会中断服务。

但是，在您将[!DNL Target]实施代码中的主机名（at.js中的`serverDomain`）更改为新的CNAME主机名(`target.example.com`)后，Web浏览器会将旧访客视为新访客。 旧访客的配置文件数据丢失，因为旧主机名(`clientcode.tt.omtrdc.net`)下无法访问上一个Cookie。 由于浏览器安全模型，无法访问之前的Cookie。 此中断仅在初始切换到新CNAME时发生。 证书续订没有相同的效果，因为主机名不会更改。

### 我的CNAME实施使用哪种密钥类型和证书签名算法？

默认情况下，所有证书都是RSA SHA-256和密钥是RSA 2048位。 当前不支持大于2048位的键大小。

### 如何验证我的CNAME实施是否已准备好进行流量测试？

使用以下命令集（在macOS或Linux命令行终端中，使用bash和curl 7.49+）：

1. 将此bash函数粘贴到终端中：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 粘贴此命令（将`target.example.com`替换为主机名）：

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果实施已准备就绪，您将看到如下输出。 重要部分是所有行都包含`CN=target.example.com`，与所需的主机名匹配。 如果有任何行包含`CN=*.tt.omtrdc.net`，则实现为&#x200B;**未**&#x200B;就绪。

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一个curl请求验证新的DNS CNAME，该请求还应显示`CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失败但上述`validateEdgeFpsslSni`命令成功，请等待DNS更新完全传播。 DNS记录具有关联的[TTL（生存时间）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，该TTL指示这些记录的DNS回复的缓存过期时间。 因此，您可能需要至少等待TTL的长时间。 您可以使用`dig target.example.com`命令或[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)查找特定TTL。

### 如何结合使用包含CNAME的选择退出链接

如果您使用的是CNAME，则选择退出链接应包含“client=`clientcode`参数，例如：
`https://my.cname.domain/optout?client=clientcode`。

将`clientcode`替换为您的客户端代码，然后将要链接的文本或图像添加到[选择退出URL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC)。

## 已知限制

* 当您拥有CNAME和at.js 1.x时，QA模式不会粘滞，因为它基于第三方Cookie。 解决方法是，将预览参数添加到您导航到的每个URL中。 当您拥有CNAME和at.js 2.x时，QA模式会很粘滞。
* 当前，在使用at.js 1.8.2和at.js 2.3.1之前的at.js版本时，`overrideMboxEdgeServer`设置无法正常用于CNAME。如果您使用的是较低版本的at.js，则应将此设置设置为`false`，以避免请求失败。 或者，您还应当考虑将[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新到支持的较新版本。
* 使用CNAME时，[!DNL Target]调用的Cookie标头大小更有可能增加。 [!DNL Adobe] 建议将Cookie大小保持在8 KB以下。
