---
keywords: 客户关怀；cname；证书项目；规范名称；cookies；证书；amc;adobe托管证书；digicert；域控制验证；dcv
description: 有关与 Adobe 客户关怀一起在 Adobe Target 中实施 CNAME（规范名称）支持的信息。
title: CNAME
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 2%

---


# CNAME 和 Adobe Target

关于与Adobe客户关怀部门协作在[!DNL Adobe Target]中实施CNAME（规范名称）支持的说明。 为了最好地处理广告阻止问题或与ITP相关的cookie策略，会使用CNAME，以便对客户拥有的域而不是Adobe拥有的域进行调用。

## 请求CNAME支持

请执行以下步骤，在[!DNL Target]中请求CNAME支持：

1. 确定SSL证书所需的主机名列表（请参阅常见问题解答）。

1. 对于每个主机名，在DNS中创建一个指向常规[!DNL Target]主机名`clientcode.tt.omtrdc.net`的CNAME记录。

   例如，如果您的客户端代码为“cnamecustomer”，而您提议的主机名为`target.example.com`，则您的DNS CNAME记录应类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >Adobe的证书颁发机构DigiCert在此步骤完成之前无法颁发证书。 因此，Adobe在完成此步骤之前无法满足您对CNAME实施的请求。

1. [填写此表](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) 单，并在打开请求CNAME [支持的Adobe客户关怀票证时将其包含](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe[!DNL Target]客户端代码：
   * SSL证书主机名(示例：`target.example.com target.example.org`):
   * SSL证书购买者(强烈建议使用Adobe，请参阅常见问题解答):Adobe/客户
   * 如果客户正在购买证书（又称BYOC），请填写以下附加详细信息：
      * 证书组织(示例：示例公司公司):
      * 证书组织单位(可选，示例：营销):
      * 证书国家／地区(示例：美国):
      * 证书状态／区域(示例：加利福尼亚):
      * 证书城市(示例：圣何塞):

1. 如果Adobe购买证书，Adobe将与DigiCert合作，在Adobe的生产服务器上购买并部署您的证书。

   如果客户正在购买证书(BYOC),Adobe客户服务中心将向您发送证书签名请求(CSR)，当您通过您选择的证书颁发机构购买证书时，您需要使用该请求。 颁发证书后，您必须将证书和任何中间证书的副本发送回Adobe客户关怀中心进行部署。

   Adobe客户服务中心将在您的实施准备就绪后通知您。

1. 完成上述任务和Adobe客户服务中心通知您实施已就绪后，您必须将`serverDomain`更新到at.js中的新CNAME。

## 常见问题解答

以下信息回答了有关在[!DNL Target]中请求和实施CNAME支持的常见问题：

### 我是否可以提供自己的证书（又称自带证书或BYOC）?

是的，您可以提供自己的证书；但是，不建议这样做。 对于Adobe和您在Adobe购买和控制证书时，SSL证书生命周期的管理都会非常容易。 SSL证书必须每年续订，这意味着Adobe客户服务部门必须每年与您联系，以便及时向Adobe发送新证书。 某些客户可能每年都难以及时生成续订的证书，这会危及其[!DNL Target]实施，因为当证书过期时浏览器将拒绝连接。

>[!IMPORTANT]
>
>请注意，如果您请求[!DNL Target]自带证书CNAME实施，您有责任每年为Adobe客户服务中心提供续订证书。 允许您的CNAME证书在Adobe可以部署续订的证书之前过期，将导致您的特定[!DNL Target]实施中断。

### 新SSL证书到期的时间为多长？

2020年9月1日之前颁发的证书为两年。 2020年9月1日或之后颁发的证书为一年期证书。 您可以在此处](https://www.digicert.com/position-on-1-year-certificates)阅读有关移动到一年证书的更多信息。[

### 我应选择哪些主机名？ 我应选择每个域的主机名数？

[!DNL Target] CNAME实现在SSL证书和客户的DNS中每个域只需要一个主机名，因此我们建议这样做。某些客户可能需要每个域额外的主机名用于自己的用途（例如，在暂存中进行测试），这是受支持的。

大多数客户选择像`target.example.com`这样的主机名，因此我们建议这样做，但最终选择是您的。 请务必不要请求现有DNS记录的主机名，因为这样会导致冲突和延迟时间来解决您的[!DNL Target] CNAME请求。

### 我已经为[!DNL Adobe Analytics]实现了CNAME，我们是否可以使用相同的证书或主机名？

否，[!DNL Target]需要单独的主机名和证书。

### 我当前的目标实施是否受ITP 2.x影响？

在Safari浏览器中，导航到您具有目标JavaScript库的网站。 如果您在CNAME的上下文中看到目标cookie集（如`analytics.company.com`），则ITP 2.x不会影响您。

ITP问题可以通过仅使用Analytics CNAME解决目标。 您仅在广告阻止情况下需要单独的目标CNAME,目标被阻止。

有关ITP的详细信息，请参阅[Apple Intelligent Tracking Prevention(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)。

### 部署CNAME实施时，我预计会发生何种服务中断？

部署证书（包括证书续订）时不会中断服务。 但是，当您将[!DNL Target]实现代码（at.js中的`serverDomain`）中的主机名更改为新的CNAME主机名(`target.example.com`)时，Web浏览器会将返回的访客视为新访客，并且其用户档案数据将丢失，因为以前的Cookie由于浏览器安全模型而无法访问。 `clientcode.tt.omtrdc.net`这只是一次性中断，只针对新CNAME的初始切换。 证书续订没有相同的效果，因为主机名没有更改。

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

1. 下一步粘贴此命令（将`target.example.com`替换为您的主机名）:

   ```
   validateEdgeFpsslSni target.example.com
   ```

   如果实现就绪，您应看到如下输出。 重要的部分是所有行都显示与所需主机名匹配的`CN=target.example.com`。 如果其中任何一个显示`CN=*.tt.omtrdc.net`，则实现为&#x200B;**不**&#x200B;就绪。

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
   >如果此命令失败，但上述`validateEdgeFpsslSni`命令成功，则可能需要等待DNS更新完全传播。 DNS记录具有关联的[TTL（生存时间）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records)，它规定这些记录的DNS回复的缓存到期时间，因此您可能需要等待至少TTL的时间。 可以使用`dig target.example.com`命令或[ G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME)查找特定TTL。

## 已知限制

* QA模式在您有CNAME和at.js 1.x时不会粘滞，因为它基于第三方cookie。 解决方法是将预览参数添加到您导航到的每个URL。 QA模式在您有CNAME和at.js 2.x时是粘滞的。
* 当前，在使用at.js 1.8.2和at.js 2.3.1之前的at.js版本时，`overrideMboxEdgeServer`设置无法与CNAME一起正常使用。如果您使用的是at.js的旧版本，应将其设置为`false`以避免请求失败。 或者，您应考虑将at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)更新为较新、受支持的版本。[
* 使用CNAME时，目标调用的cookie头大小更有可能增加。 我们建议将Cookie大小保持在8KB以下。
