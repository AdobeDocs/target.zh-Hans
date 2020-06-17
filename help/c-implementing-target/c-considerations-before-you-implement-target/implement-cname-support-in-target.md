---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b4b51eabee1b3cac9933ecfc6c94e0de02abb633
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 2%

---


# CNAME 和 Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 为了最好地处理广告阻止问题或与ITP相关的cookie策略，会使用CNAME，以便对客户所拥有的域而不是Adobe所拥有的域进行调用。

## 请求CNAME支持

Perform the following steps to request CNAME support in [!DNL Target]:

1. 确定SSL证书所需的主机名列表（请参阅常见问题解答）。

1. 对于每个主机名，在DNS中创建一个指向常规主机名的CNAME [!DNL Target] 记录 `clientcode.tt.omtrdc.net`。

   例如，如果您的客户端代码是“客户”，而您建议的主机名 `target.example.com`是，则您的DNS CNAME记录应类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >* Adobe的证书颁发机构DigiCert在此步骤完成之前无法颁发证书。 因此，在此步骤完成之前，Adobe无法满足您对CNAME实施的请求。


1. 在打开请求CNAME支持的Adobe客户 [关怀票证时填写以下表单](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target] client code:
   * SSL证书主机名(示例： `target.example.com target.example.org`):
   * SSL证书购买者（强烈建议使用Adobe，请参阅常见问题解答）: Adobe/客户
   * 如果客户正在购买证书（又称BYOC），请填写以下附加详细信息：
      * 证书组织(示例： 示例公司公司):
      * 证书组织单位(可选，示例： 营销):
      * 证书国家／地区(示例： 美国):
      * 证书状态／区域(示例： 加利福尼亚):
      * 证书城市(示例： 圣何塞):

1. 如果Adobe购买证书，Adobe将与DigiCert合作，在Adobe的生产服务器上购买并部署您的证书。

   如果客户购买证书(BYOC),Adobe客户关怀部门将向您发送证书签名请求(CSR)，当您通过您选择的证书颁发机构购买证书时，您需要使用该请求。 颁发证书后，您必须将证书和任何中间证书的副本发送回Adobe客户关怀部门进行部署。

   Adobe客户关怀部门将在您的实施准备就绪后通知您。

1. 完成上述任务后，Adobe客户关怀团队已通知您实施已准备就绪，您必须将 `serverDomain` 其更新到at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在中请求和实施CNAME支持的常见问题 [!DNL Target]:

### 我是否可以提供自己的证书（又称自带证书或BYOC）?

是的，您可以提供自己的证书； 但是，不建议这样做。 对于Adobe和您来说，在购买和控制证书时，SSL证书生命周期的管理都会非常简单。 SSL证书必须每年续订，这意味着Adobe客户关怀部门必须每年与您联系，以便及时向Adobe发送新证书。 某些客户可能每年都难以及时生成续订的证书，这会危及他们的实施，因为当证书过期 [!DNL Target] 时，浏览器将拒绝连接。

>[!IMPORTANT]
>
>请注意，如果您请求 [!DNL Target] 自带证书CNAME实施，您有责任每年为Adobe Client Care提供续订的证书。 如果允许您的CNAME证书在Adobe部署续订的证书之前过期，将导致您的特定实施中 [!DNL Target] 断。

### 新SSL证书到期的时间为多长？

2020年9月1日之前颁发的证书为两年。 2020年9月1日或之后颁发的证书为一年期证书。 您可以在此处阅读有关迁移到一年证书的更多 [信息](https://www.digicert.com/position-on-1-year-certificates)。

### 我应选择哪些主机名？ 我应选择每个域的主机名数？

[!DNL Target] CNAME实现在SSL证书和客户的DNS中每个域只需要一个主机名，因此我们建议这样做。 某些客户可能需要每个域额外的主机名用于自己的用途（例如，在暂存中进行测试），这是受支持的。

大多数客户都选择像这样 `target.example.com`的主机名，因此我们建议这样选择，但最终选择是您的。 请务必不要请求现有DNS记录的主机名，因为这会导致冲突和延迟时间，从而解决您的CNAME [!DNL Target] 请求。

### 我已经有CNAME实现，我 [!DNL Adobe Analytics]们是否可以使用相同的证书或主机名？

否，需 [!DNL Target] 要单独的主机名和证书。

### 我当前的Target实施是否受ITP 2.x影响？

在Safari浏览器中，导航到您具有TargetJavaScript库的网站。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

ITP问题可以针对仅使用AnalyticsCNAME的Target进行解决。 您仅在广告阻止情况下需要单独的TargetCNAME,Target被阻止。

有关ITP的详细信息，请 [参阅Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME实施时，我预计会发生何种服务中断？

部署证书（包括证书续订）时不会中断服务。 但是，当您将实施代码(在at.js [!DNL Target] 中)中的主机名更改为新的CNAME主机名(`serverDomain` )时，Web浏览器会将返回的访客视为新访客，并且其用户档案数据将丢失，因为由于浏览器安全模型，以前的Cookie将无法在旧主机名(`target.example.com``clientcode.tt.omtrdc.net`)下访问。 这只是一次性中断，只针对新CNAME的初始切换。 证书续订没有相同的效果，因为主机名没有更改。

### 我的CNAME实现将使用哪种密钥类型和证书签名算法？

默认情况下，所有证书都是RSA SHA-256和密钥是RSA 2048位。 当前不支持大于2048位的密钥大小。

### 如何验证CNAME实施是否已准备好进行流量？

使用以下命令集（在MacOs或Linux命令行终端中，使用bash和curl 7.49+）:

1. 首先将此bash功能粘贴到终端中：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 下一步粘贴此命令( `target.example.com` 替换为主机名):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果实现就绪，您应看到如下输出。 重要的部分是所有行都显示， `CN=target.example.com`这些行与我们所需的主机名匹配。 如果其中任何一个 `CN=*.tt.omtrdc.net`显示，则实 **现尚未** 就绪。

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

1. 使用另一个curl请求验证新DNS CNAME，该请求还应显示 `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失败， `validateEdgeFpsslSni` 但上述命令成功，则可能需要等待DNS更新完全传播。 DNS记录具有关 [联的TTL（生存时间）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) ，它规定这些记录的DNS回复的缓存到期时间，因此您至少需要等待TTL。 您可以使用命 `dig target.example.com` 令或 [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) ，查找您的特定TTL。

## 已知限制

* QA模式在您有CNAME和at.js 1.x时不会粘滞，因为它基于第三方cookie。 解决方法是将预览参数添加到您导航到的每个URL。 QA模式在您有CNAME和at.js 2.x时是粘滞的。
* 当前 `overrideMboxEdgeServer` 此设置在CNAME中无法正常使用。 应将此设置为 `false` 以避免请求失败。
