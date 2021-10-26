---
keywords: 客户关怀；CNAME；证书程序；规范名称；Cookie；证书；AMC;Adobe托管证书；Digicert；域控制验证；DCV
description: 与Adobe客户关怀团队合作，在Adobe中实施CNAME（规范名称）支持 [!DNL Target] 以处理广告拦截问题。
title: 如何在Target中使用CNAME?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: e51c7805939e8bf32d7f358036c9070931580187
workflow-type: tm+mt
source-wordcount: '1165'
ht-degree: 1%

---

# CNAME和Target

使用说明 [!DNL Adobe] 客户关怀团队，在中实施CNAME（规范名称）支持 [!DNL Adobe Target]. 使用CNAME处理广告拦截问题或与ITP相关（智能防跟踪）Cookie策略。 通过CNAME，会调用客户拥有的域，而不是客户拥有的域 [!DNL Adobe].

## 在Target中请求CNAME支持

1. 确定您的SSL证书所需的主机名列表（请参阅下面的常见问题解答）。

1. 对于每个主机名，在DNS中创建一个指向常规的CNAME记录 [!DNL Target] 主机名 `clientcode.tt.omtrdc.net`.

   例如，如果您的客户端代码为“客户”，而您建议的主机名为 `target.example.com`，则您的DNS CNAME记录类似于：

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Adobe的证书颁发机构DigiCert在此步骤完成之前无法颁发证书。 因此， [!DNL Adobe] 在此步骤完成之前，无法完成您对CNAME实施的请求。

1. [填好这张表](/help/assets/FPC_Request_Form.xlsx) 在您 [打开Adobe客户关怀票证，请求CNAME支持](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * Adobe [!DNL Target] 客户端代码：
   * SSL证书主机名(示例： `target.example.com target.example.org`):
   * SSL证书购买者(强烈建议购买Adobe，请参阅常见问题解答):Adobe/客户
   * 如果客户购买的证书也称为“自带证书”(BYOC)，请填写以下附加详细信息：
      * 证书组织(示例：Example Company Inc):
      * 证书组织单位(可选，示例：营销):
      * 证书国家/地区(示例：美国):
      * 证书状态/区域(示例：加州):
      * 证书城市(示例：圣何塞):

1. 如果 [!DNL Adobe] 购买证书， [!DNL Adobe] 与DigiCert合作，在Adobe的生产服务器上购买并部署您的证书。

   如果客户购买证书(BYOC), [!DNL Adobe] 客户关怀团队会向您发送证书签名请求(CSR)。 通过您选择的证书颁发机构购买证书时，请使用CSR。 证书签发后，将证书副本和任何中间证书发送至 [!DNL Adobe] 客户关怀团队进行部署。

   [!DNL Adobe] 客户关怀会在您的实施准备就绪后通知您。

1. 更新 `serverDomain` ([文档](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#serverDomain))到新CNAME主机名并设置 `overrideMboxEdgeServer` to `false` ([文档](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#overridemboxedgeserver))。

## 常见问题解答

以下信息回答了有关在 [!DNL Target]:

### 我能否提供我自己的证书（自带您自己的证书或BYOC）？

您可以提供自己的证书。 但是， [!DNL Adobe] 不建议使用此做法。 对于这两者而言，SSL证书生命周期的管理都更轻松 [!DNL Adobe] 如果 [!DNL Adobe] 购买并控制证书。 必须每年续订SSL证书。 因此， [!DNL Adobe] 客户关怀团队必须每年与您联系，以及时获取新证书。 某些客户可能难以及时生成续订的证书。 您的 [!DNL Target] 证书过期时，由于浏览器拒绝连接，因此实施会受到威胁。

>[!IMPORTANT]
>
>如果您请求 [!DNL Target] 自带证书的CNAME实施，您负责为 [!DNL Adobe] 客户关怀团队。 允许CNAME证书在之前过期 [!DNL Adobe] 可以部署续订的证书，导致您的特定 [!DNL Target] 实施。

### 新SSL证书过期多长时间？

所有Adobe购买的证书的有效期为一年。 请参阅 [Digicert关于1年证书的文章](https://www.digicert.com/blog/position-on-1-year-certificates) 以了解更多信息。

### 我应选择哪些主机名？ 我应选择每个域的主机名数量？

[!DNL Target] CNAME实施在SSL证书和客户DNS中每个域只需要一个主机名。 Adobe建议每个域使用一个主机名。 某些客户出于自身目的而要求每个域的主机名更多（例如，在暂存环境中进行测试），这是受支持的。

大多数客户选择的主机名如 `target.example.com`. Adobe建议遵循此做法，但最终由您选择。 请求现有DNS记录的主机名。 这样做会导致冲突并延迟解决 [!DNL Target] CNAME请求。

### 我已在 [!DNL Adobe Analytics]，我能否使用相同的证书或主机名？

不， [!DNL Target] 需要单独的主机名和证书。

### 我当前的实施是 [!DNL Target] 受ITP 2.x的影响？

Apple智能防跟踪(ITP)版本2.3引入了其CNAME隐藏缓解功能，该功能可检测Adobe Target CNAME实施并将Cookie的过期时间缩短为七天。 当前 [!DNL Target] 没有解决ITP CNAME隐匿问题的方法。 有关ITP的更多信息，请参阅 [Apple智能防跟踪(ITP)2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).


### 部署CNAME实施后，我可以期待哪种服务中断？

部署证书时（包括证书续订）不会中断服务。

但是，在您更改 [!DNL Target] 实施代码(`serverDomain` （在at.js中）到新CNAME主机名(`target.example.com`)，则Web浏览器会将旧访客视为新访客。 旧访客的配置文件数据丢失，因为以前的Cookie在旧主机名(`clientcode.tt.omtrdc.net`)。 由于浏览器安全模型，无法访问之前的Cookie。 此中断仅在初始切换到新CNAME时发生。 证书续订没有相同的效果，因为主机名不会更改。

### 我的CNAME实施使用哪种密钥类型和证书签名算法？

默认情况下，所有证书都是RSA SHA-256和密钥是RSA 2048位。 当前不支持大于2048位的键大小。

### 如何验证我的CNAME实施是否已准备好进行流量测试？

使用以下命令集(在macOS或Linux命令行终端中，使用bash和curl >=7.49):

1. 将此bash函数复制并粘贴到终端中，或将该函数粘贴到bash启动脚本文件中(通常 `~/.bash_profile` 或 `~/.bashrc`)，以便函数在终端会话之间可用：

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. 粘贴此命令(替换 `target.example.com` 使用您的主机名):

   ```
   adobeTargetCnameValidation target.example.com
   ```

   如果实施已准备就绪，您将看到如下输出。 重要部分是所有验证状态行都显示 `✅` 而不是 `🚫`. 每个 [!DNL Target] 边缘CNAME共享应显示 `CN=target.example.com`，与请求证书上的主主机名匹配（证书上的其他SAN主机名不会打印在此输出中）。

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >如果此验证命令在DNS验证时失败，但您已进行必要的DNS更改，则可能需要等待DNS更新完全传播。 DNS记录具有关联 [TTL（存留期）](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) 指示这些记录的DNS回复的缓存过期时间。 因此，您可能需要至少等待TTL的长时间。 您可以使用 `dig target.example.com` 命令或 [G Suite工具箱](https://toolbox.googleapps.com/apps/dig/#CNAME) 查找您的特定TTL。 要检查DNS在世界各地的传播，请参阅 [whatsmydns.net](https://whatsmydns.net/#CNAME).

### 如何将选择退出链接与 CNAME 配合使用

如果您使用的是CNAME，则选择退出链接应包含“client=`clientcode` 参数，例如：
`https://my.cname.domain/optout?client=clientcode`.

替换 `clientcode` ，然后将要链接的文本或图像添加到 [选择禁用URL](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## 已知限制

* 当您拥有CNAME和at.js 1.x时，QA模式不会粘滞，因为它基于第三方Cookie。 解决方法是，将预览参数添加到您导航到的每个URL中。 当您拥有CNAME和at.js 2.x时，QA模式会很粘滞。
* 使用CNAME时， [!DNL Target] 调用会增加。 [!DNL Adobe] 建议将Cookie大小保持在8 KB以下。
