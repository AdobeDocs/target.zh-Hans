---
keywords: 客户关怀；cname；证书项目；规范名；cookie；证书；amc;adobe托管证书；digicert；域控制验证；dcv
description: 与Adobe Client Care合作，在Adobe [!DNL Target] 中实施CNAME（规范名称）支持，以处理广告阻塞问题或与ITP相关的Cookie策略。
title: 如何在目标中使用CNAME?
feature: 隐私和安全
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
translation-type: tm+mt
source-git-commit: 85a17944c7d5924edb1bbabb7531274249ceaaa8
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 2%

---

# CNAME 和 Adobe Target

有关使用[!DNL Adobe] Client Care在[!DNL Adobe Target]中实现CNAME（规范名称）支持的说明。 使用CNAME处理广告阻止问题或与ITP相关（智能跟踪预防）Cookie策略。 使用CNAME，将调用客户拥有的域，而不是[!DNL Adobe]拥有的域。

## 请求目标中的CNAME支持

1. 确定您的SSL证书所需主机名的列表（请参阅下面的常见问题解答）。

1. 对于每个主机名，在DNS中创建一个指向常规[!DNL Target]主机名`clientcode.tt.omtrdc.net`的CNAME记录。

   例如，如果您的客户端代码是“cnamecustomer”，而您建议的主机名是`target.example.com`，则您的DNS CNAME记录看起来类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobe的证书颁发机构DigiCert在此步骤完成之前无法颁发证书。 因此，在此步骤完成之前， [!DNL Adobe]无法满足您对CNAME实现的请求。

1. [填写此表](/help/assets/FPC_Request_Form.xlsx) 单并在打开请求CNAME [支持的Adobe Client Care票证时包含它](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe[!DNL Target]客户端代码：
   * SSL证书主机名(示例：`target.example.com target.example.org`):
   * SSL证书购买者(强烈建议使用Adobe，请参阅常见问题解答):Adobe/客户
   * 如果客户正在购买该证书，也称为“Bring Your Own Certificate”(BYOC)，请填写以下附加详细信息：
      * 证书组织(示例：示例公司公司):
      * 证书组织单位(可选，示例：营销):
      * 证书国家/地区(示例：美国):
      * 证书状态/区域(示例：加利福尼亚):
      * 证书城市(示例：圣何塞):

1. 如果[!DNL Adobe]正在购买证书，[!DNL Adobe]将与DigiCert一起购买您的证书并将其部署到Adobe的生产服务器上。

   如果客户正在购买证书(BYOC),[!DNL Adobe]客户关怀会向您发送证书签名请求(CSR)。 在通过您选择的证书颁发机构购买证书时使用CSR。 颁发证书后，将证书和任何中间证书的副本发送到[!DNL Adobe]客户关怀部署。

   [!DNL Adobe] 当您的实施准备就绪时，客户关怀将通知您。

1. 将`serverDomain`更新到at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在[!DNL Target]中请求和实施CNAME支持的常见问题：

### 我是否可以提供我自己的证书（带来您自己的证书或BYOC）？

您可以提供您自己的证书。 但是，[!DNL Adobe]不建议使用此方法。 [!DNL Adobe]和[!DNL Adobe]购买并控制证书时，SSL证书生命周期的管理更简单。 必须每年续订SSL证书。 因此，[!DNL Adobe]客户服务部门必须每年与您联系，以及时获得新证书。 某些客户可能难以及时生成续订的证书。 当证书过期时，您的[!DNL Target]实现会因浏览器拒绝连接而受损。

>[!IMPORTANT]
>
>如果您请求[!DNL Target]自带证书CNAME实施，则您有责任每年为[!DNL Adobe]客户服务部门提供续订证书。 允许您的CNAME证书在[!DNL Adobe]可以部署续订的证书之前过期，将导致特定[!DNL Target]实施的中断。

### 我的新SSL证书到期多久？

2020年9月1日之前颁发的证书为两年。 2020年9月1日或之后颁发的证书为一年期证书。 您可以阅读有关移动到一年证书[此处](https://www.digicert.com/position-on-1-year-certificates)的更多信息。

### 我应选择哪些主机名？ 我应选择每个域的主机名数？

[!DNL Target] CNAME实现在SSL证书和客户的DNS中，每个域只需要一个主机名。Adobe建议使用一个主机名。 某些客户出于其自身目的（例如，在暂存中进行测试）而要求每个域的更多主机名，这是受支持的。

大多数客户选择像`target.example.com`这样的主机名。 Adobe建议遵循这一做法，但最终由您选择。 请求现有DNS记录的主机名。 这样做会导致冲突并延迟解决[!DNL Target] CNAME请求的时间。

### 我已经有[!DNL Adobe Analytics]的CNAME实现，我们是否可以使用相同的证书或主机名？

否，[!DNL Target]需要单独的主机名和证书。

### 我当前的[!DNL Target]实现是否受ITP 2.x影响？

在 Safari 浏览器中，导航到您拥有 [!DNL Target] JavaScript 库的网站。如果您在CNAME的上下文中看到[!DNL Target] cookie集，如`analytics.company.com`，则ITP 2.x不会影响您。

对于[!DNL Target]，只有[!DNL Analytics] CNAME时，可以解决ITP问题。 您只需在[!DNL Target]被阻止的广告阻止场景中使用单独的[!DNL Target] CNAME。

有关ITP的详细信息，请参阅[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME实施时，我可以预计会出现何种服务中断？

部署证书（包括证书续订）时不会中断服务。

但是，在将[!DNL Target]实现代码（at.js中的`serverDomain`）中的主机名更改为新的CNAME主机名(`target.example.com`)后，Web浏览器将返回的访客视为新访客。 返回访客的用户档案数据丢失，因为以前的Cookie在旧主机名(`clientcode.tt.omtrdc.net`)下无法访问。 由于浏览器安全模型，以前的Cookie无法访问。 此中断仅在初始切换到新CNAME时发生。 证书续订没有相同的效果，因为主机名没有更改。

### 我的CNAME实现使用哪种密钥类型和证书签名算法？

默认情况下，所有证书都是RSA SHA-256和密钥是RSA 2048位。 当前不支持大于2048位的密钥大小。

### 如何验证我的CNAME实施是否已准备好用于流量？

使用以下命令集（在macOS或Linux命令行终端中，使用bash和curl 7.49+）：

1. 将此bash功能粘贴到终端中：

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. 粘贴此命令（用您的主机名替换`target.example.com`）：

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果实施就绪，您将看到如下输出。 重要部分是所有行都包含`CN=target.example.com` ，它们与所需的主机名匹配。 如果有行包含`CN=*.tt.omtrdc.net`，则实现为&#x200B;**不**&#x200B;就绪。

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
   >如果此命令失败，但上面的`validateEdgeFpsslSni`命令成功，请等待DNS更新完全传播。 DNS记录具有关联的[TTL（生存时间）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，它指示这些记录的DNS回复的缓存过期时间。 因此，您可能需要等待至少TTL长度。 可以使用`dig target.example.com`命令或[G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)查找您的特定TTL。

## 已知限制

* QA模式在您有CNAME和at.js 1.x时不会粘滞，因为它基于第三方Cookie。 解决方法是将预览参数添加到您导航到的每个URL。 QA模式在您有CNAME和at.js 2.x时会很粘滞。
* 当前，在使用at.js 1.8.2和at.js 2.3.1之前的at.js版本时，`overrideMboxEdgeServer`设置无法与CNAME正常一起使用。如果您使用的是at.js的旧版本，应将此设置为`false`以避免出现失败请求。 或者，您也应考虑将[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新为较新的受支持版本。
* 使用CNAME时，[!DNL Target]调用的Cookie头的大小更可能增加。 [!DNL Adobe] 建议将cookie大小保持在8 KB以下。
