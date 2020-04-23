---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 8267de6c27566ec397651d3bfc88aad0818ed8d2

---


# CNAME 和 Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 为了最好地处理广告阻止问题或与ITP相关的Cookie策略，会使用CNAME，以便对客户所拥有的域而不是Adobe所拥有的域进行调用。

## 请求CNAME支持

Perform the following steps to request CNAME support in [!DNL Target]:

1. Adobe的证书颁发机构(DigiCert)需要验证Adobe是否获得在您的域下生成证书的授权。

   DigiCert调用此过程域控制验 [证(DCV)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)，并且在以下DCV方法中的至少一种方法完成此过程之前，Adobe将不允许在您的域下生成证书：

   * 最快的DCV方法是 __DNS CNAME方法__，在该方法中，您向指向DigiCert的DCV主机名(dcv.digicert.com)的域添加DNS CNAME记录（包含令牌）。 此CNAME记录向DigiCert指示Adobe已获得生成证书的授权。 Adobe客户关怀团队将向您发送包含必要DNS记录的说明。 示例：

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >这些DCV令牌将在30天后过期，此时Adobe Client Care会与您联系以获取更新的令牌。 为了使CNAME请求的解决速度最快，请准备好在提交请求之前对所有请求的域进行这些DNS更改。

      >[!NOTE]
      >
      >如果您的域有 [DNS CAA记录](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)，则需要添加 `digicert.com` （如果尚未添加）。 此DNS记录指示哪些证书颁发机构已获得授权为域颁发证书。 生成的DNS记录如下所示： `example.com. IN CAA 0 issue "digicert.com"`. 您可以使 [用G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CAA) ，确定根域是否有现有CAA记录。 您可以在此处阅读更多关于DigiCert如何处理CAA记 [录的信息](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check)。

   * DigiCert还将尝试使用电子邮 __件方法__，在该方法中，他们将电子邮件发送到域的WHOIS信息中找到的地址以及预先确定的电子邮件地址(admin、administrator、webmaster、hostmaster和postmaster `@[domain_name]`)。 有关详细 [信息，请参阅DCV方法文档](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) 。

      为加快DCV电子邮件流程，DigiCert提供了以下建议：

      “请确认您的注册/WHOIS提供商未蒙版或删除相关 [电子邮件地址]。 如果是，请查明他们是否提供了一种方式（例如匿名电子邮件地址、Web表单），让证 [书颁发机构访问您域的WHOIS数据] 。”

1. 在域的DNS上创建指向常规主机名的CNAME记录 `clientcode.tt.omtrdc.net`。 例如，如果您的客户端代码是客户，而您建议的主机名是 `target.example.com`，则您的DNS CNAME记录应类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 打开 [Adobe客户关怀票证，请求呼叫的CNAME](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 支 [!DNL Target] 持。

   Adobe将与DigiCert合作，在Adobe的生产服务器上购买和部署您的证书。 DigiCert将启动DCV进程，Adobe Client Care将在实施准备就绪后通知您。

1. 完成上述任务后，Adobe客户关怀团队已通知您实施已准备就绪，您必须将其更新 `serverDomain` 到at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在中请求和实施CNAME支持的常见问题解答 [!DNL Target]:

### 我是否可以提供自己的证书(aka ling-your-own-certificate aka BYOC)? 如果是，过程是什么？

是的，您可以提供自己的证书，但 __不建议这样做__。 在Adobe购买和控制证书时，对于Adobe和客户来说，SSL证书生命周期的管理都会非常容易。 SSL证书需要每年续订，这意味着Adobe客户关怀部门需要每年与您联系，以便及时向Adobe发送新证书。 某些客户可能难以每年及时生成续订的证书，这会危及他们的实施，因为当证书过期时，浏览器将拒绝连接。 [!DNL Target]

>[!NOTE]
>
>请注意，如果您请求自带证 [!DNL Target] 书CNAME实施，您将负责每年向Adobe Client Care提供续订的证书。 如果允许您的CNAME证书在Adobe部署续订的证书之前过期，将导致您的特定实施中 [!DNL Target] 断。

1. 跳过上面的步骤1，但完成步骤2和3。 打开Adobe客户关怀票证（步骤3）时，请告知他们您将提供您自己的证书。

   Adobe将生成并向您发送证书签名请求(CSR)。

1. 使用CSR通过您选择的证书颁发机构(CA)购买证书。

1. 将新公共证书发送到Adobe。 Adobe代表将在其生产服务器上部署公共证书。

1. 在Adobe客户关怀通知您实施已准备就绪后完成步骤4。

### 新的SSL证书到期多久？

2020年9月1日前颁发的证书为2年期证书。 2020年9月1日及之后颁发的证书为1年证书。 您可以在此处阅读有关迁移到1年证书的更多 [信息](https://www.digicert.com/position-on-1-year-certificates)。

### 我应选择哪些主机名？ 我应选择每个域的主机名数？

[!DNL Target] CNAME实现在SSL证书上和客户的DNS中，每个域只需要一个主机名，因此我们建议这样做。 某些客户可能出于自己的目的（例如，在暂存中进行测试）需要每个域的额外主机名，这是受支持的。

大多数客户都选择类似 `target.example.com`的主机名，因此我们建议这样做，但最终选择归您所有。 请务必不要请求现有DNS记录的主机名，因为这会导致CNAME请求的解决出现冲突和延 [!DNL Target] 迟时间。

### 我已经有了CNAME实现，我 [!DNL Adobe Analytics]们是否可以使用相同的证书或主机名？

否，需 [!DNL Target] 要单独的主机名和证书。

### 我目前实施的目标是否受到ITP 2.1或2.2的影响？

在Safari浏览器中，导航到您拥有目标JavaScript库的网站。 If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

ITP问题可以解决，以便仅与Analytics CNAME目标。 您仅在广告阻止场景中目标被阻止时需要单独的目标CNAME。

有关ITP的详细信息，请参 [阅Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### Adobe/DigiCert是否可以将DCV电子邮件发送到其他电子邮件地址 `<someone>@example.com`?

否，DigiCert（或任何证书颁发机构）将不允许域下具有电子邮件地址的任何人对同一域下的SSL证书授权，除非该电子邮件地址也包含在域的WHOIS信息或预定的地址列表中（见上文）。 这确保只有经过授权的个人才能批准特定域的DCV。 如果这对您不可行，我们建议使用DNS CNAME DCV方法（请参阅上文）。

### 如何验证CNAME实施已准备好进行流量？

使用以下命令集（在MacOs或Linux命令行终端中，使用bash和curl 7.49+）:

1. 首先将此bash函数粘贴到您的终端中：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 下一步粘贴此命令(替 `target.example.com` 换为您的主机名):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果实现就绪，您应看到如下输出。 重要的部分是所有行都显示， `CN=target.example.com`这与我们所需的主机名匹配。 如果其中任何一 `CN=*.tt.omtrdc.net`个显示，则实施 **尚未** 就绪。

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一个curl请求验证新的DNS CNAME，该请求还应显示 `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失败，但上 `validateEdgeFpsslSni` 述命令成功，则可能需要等待DNS更新完全传播。 DNS记录具有关联的 [TTL（生存时间）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) ，它规定了这些记录的DNS回复的缓存到期时间，因此您至少需要等待TTL。 可以使用命 `dig target.example.com` 令或G [Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) ，查找您的特定TTL。
