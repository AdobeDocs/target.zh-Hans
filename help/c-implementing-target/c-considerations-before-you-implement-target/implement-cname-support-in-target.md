---
keywords: 客户关怀；cname；证书程序；规范名；cookie；证书；amc;adobe受管证书；digicert；域控制验证
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
title: CNAME 和 Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 872e2329e7954453b5c8bd4f4885b94f1b02fd1f

---


# CNAME 和 Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. 为了最好地处理广告阻止问题或与ITP相关的Cookie策略，会使用CNAME，以便对客户所拥有的域而不是Adobe所拥有的域进行调用。

## 请求CNAME支持

Perform the following steps to request CNAME support in [!DNL Target]:

1. Adobe的证书颁发机构(DigiCert)需要验证Adobe是否获得在您的域下生成证书的授权。

   DigiCert调用此过 [程域控制验证](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) (DCV)，在此过程完成之前，Adobe将不允许在您的域下生成证书。

   DCV使用一些方法，在打开Adobe客户关怀票证（步骤3）之前，您可以执行一些操作来帮助加快DCV流程：

   * DigiCert将首先尝试使用电子邮件方法，在该方法中，他们将电子邮件发送到域的WHOIS信息中找到的地址以及预先确定的电子邮件地址(admin、administrator、webmaster、hostmaster和postmaster `@[domain_name]`)。 有关详细 [信息，请参阅DCV方法文档](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) 。

      为加快DCV电子邮件流程，DigiCert提供了以下建议：

      “请确认您的注册/WHOIS提供商未蒙版或删除相关 [电子邮件地址]。 如果是，请查明它们是否提供了一种方式（例如匿名电子邮件地址、Web表单），让证 [书颁发机构访问您域的WHOIS数据] 。”

   * 如果DCV电子邮件方法不适合您，则下一种方法是DNS TXT方法，在该方法中，您可以使用哈希值向域添加DNS TXT记录。 此TXT记录向DigiCert指示Adobe已获得生成证书的授权。 如果需要使用此方法，请在打开票证时通知Adobe客户关怀团队（步骤3）。 这将有助于加快DCV流程。

1. 在域的DNS上创建指向常规主机名的CNAME记录 `clientcode.tt.omtrdc.net`。 例如，如果您的客户端代码是客户，而您建议的主机名是 `target.example.com`，则您的DNS CNAME记录应类似于：

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. 打开 [Adobe客户关怀票证，请求呼叫的CNAME](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) 支 [!DNL Target] 持。

   Adobe将与DigiCert合作，在Adobe的生产服务器上购买和部署您的证书。 DigiCert将启动DCV进程，Adobe Client Care将在实施准备就绪后通知您。

1. 完成上述任务后，Adobe客户关怀团队已通知您实施已准备就绪，您必须将 `serverDomain` 其更新至at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在中请求和实施CNAM支持的常见问题解答 [!DNL Target]:

### 我是否可以提供自己的证书？ 如果是，过程是什么？

是的，您可以提供自己的证书，以便：

1. 跳过上面的步骤1，但完成步骤2和3。 打开Adobe客户关怀票证（步骤3）时，请告知他们您将提供您自己的证书。

   Adobe将生成并向您发送证书签名请求(CSR)。

1. 使用CSR通过您选择的证书颁发机构(CA)购买证书。

1. 将新公共证书发送到Adobe。 Adobe代表将在其生产服务器上部署公共证书。

1. 在Adobe客户关怀通知您实施已准备就绪后完成步骤4。

### 我已经有了CNAME实现，我 [!DNL Adobe Analytics]们是否可以使用相同的证书或主机名？

否，需 [!DNL Target] 要单独的主机名和证书。

### 如何验证CNAME实施已准备好进行流量？

使用以下命令集（在MacOs或Linux命令行终端中，使用bash和curl 7.49+）:

1. 首先将此bash函数粘贴到您的终端中：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. 使用另一个curl请求验证新的DNS CNAME，该请求还应显示 `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >如果此命令失败，但上 `validateEdgeFpsslSni` 述命令成功，则可能需要等待DNS更新完全传播。
