---
keywords: 轮廓脚本;轮廓脚本属性;轮廓脚本最佳实践;调试;调试;脚本;轮廓脚本;属性;属性;参数
description: 了解访客专属的一些属性，这些属性存储在访客的轮廓中，以提供可在您的 Adobe  [!DNL Target]  活动中使用的信息。
title: 什么是轮廓属性？
feature: Audiences
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '2426'
ht-degree: 91%

---

# 轮廓属性

[!DNL Adobe Target] 中的轮廓属性是特定于某个访客的参数。这些属性存储在该访客的轮廓中，以提供可在您的活动中使用的关于该访客的信息。

用户轮廓包含网页访客的人口统计和行为信息。这些信息可以包括年龄、性别、购买的产品、上次访问时间等。[!DNL Target] 使用此信息来个性化为该访问者提供的内容。

在访客浏览您的网站时或在访客因另一会话而返回时，可使用保存在该轮廓中的轮廓属性锁定内容或记录信息以供进行区段过滤。

设置轮廓属性：

1. 单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Profile Scripts.]**

   ![“轮廓脚本”选项卡](/help/main/c-target/c-visitor-profile/assets/create-script.png)

1. 单击 **[!UICONTROL Create Script]**。

   ![“创建轮廓脚本”对话框](/help/main/c-target/c-visitor-profile/assets/profile-script.png)

   可以使用以下类型的配置文件属性：

   | 参数类型 | 描述 |
   |--- |--- |
   | mbox | 在创建 mbox 时通过页面代码直接传入。请参阅[Target开发人员指南](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=zh-Hans){target=_blank}中的&#x200B;*将参数传递到全局Mbox*。<P>**注意**：[!DNL Target] 对于每个 mbox 调用有 50 个唯一轮廓属性的限制。如果必须将超过50个配置文件属性传递到[!DNL Target]，请使用[!UICONTROL Profile Update API]方法传递它们。 有关详细信息，请参阅[Target开发人员指南](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=zh-Hans){target=_blank}中的&#x200B;*更新配置文件*。 |
   | 轮廓 | 直接使用 JavaScript 代码段定义。这些代码段可存储运行总计，如消费者消费的总金额，并在每次 mbox 请求时执行这些代码段。请参阅以下&#x200B;*轮廓脚本属性*。 |

## 轮廓脚本属性 {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

可使用关联的 JavaScript 代码段定义配置文件脚本属性。

您可以使用配置文件脚本，在多次访问中捕获访客属性。轮廓脚本属性是在 [!DNL Target] 中使用某种形式的服务器端 JavaScript 定义的代码段。例如，可使用轮廓脚本捕获某位访客访问您网站的频繁程度以及该访客上次访问的时间。

轮廓脚本与轮廓参数不同。轮廓参数使用 [!DNL Target] 的 mbox 代码实现捕获关于访客的信息。

## 创建轮廓脚本 {#section_CB02F8B97CAF407DA84F7591A7504810}

配置文件脚本在[!UICONTROL Audiences]界面的[!DNL Target]选项卡下可用。

要添加配置文件脚本，请单击&#x200B;**[!UICONTROL Profile Scripts]**&#x200B;选项卡&#x200B;**[!UICONTROL Create Script]**，然后编写您的脚本。

或

要复制现有的配置文件脚本，请从[!UICONTROL Profile Scripts]列表中单击所需脚本的省略号图标，然后单击&#x200B;**[!UICONTROL Duplicate]**。

然后，您可以对受众进行编辑以创建一个类似的受众。

轮廓脚本对每个位置请求都运行轮廓属性“catchers”。收到位置请求后，[!DNL Target] 确定应该运行什么活动，并显示适合该活动和该体验的内容。[!DNL Target] 还跟踪该活动的成功情况，并运行任何相关的轮廓脚本。通过此过程可跟踪关于访问的信息，如访客的位置、访问时间是几点、访客访问网站的次数、以前是否购买过等等。然后，将这些信息添加到访客的轮廓，以使您可更好地跟踪该访客在您网站上的活动。

轮廓脚本属性在属性名称之前插入 `user.` 标记。例如：

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

请记住以下信息：

* 在代码中使用 `user.get('parameterName')` 引用轮廓脚本属性（包括本身）。
* 使用 `user.setLocal('variable_name', 'value')` 保存下次运行脚本时可以访问的变量（在下一个 mbox 请求上）。使用 `user.getLocal('variable_name')` 引用变量。在您需要引用上个请求的日期和时间时，此过程非常有用。

  这些值就像轮廓脚本一样持续存在，但您只能在设置这些值的脚本中访问它们。

* 参数和值区分大小写。请对照您在活动或测试期间收到的参数和值的大小写。
* 有关更多 JavaScript 语法，请参阅下方的“脚本轮廓参数的 JavaScript 参考”部分。
* 禁用脚本后，参数保留在轮廓中。对于用户，如果其轮廓已包含活动受众使用的参数，则符合该活动的资格。
* 不能删除活动中正在使用的轮廓脚本。
* 建议不要创建在一个轮廓脚本中使用另一个轮廓脚本所得结果的依赖性轮廓脚本。因为无法保证轮廓脚本执行的顺序。

## 查看轮廓脚本信息卡片 {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

您可以查看配置文件脚本信息弹出卡片，该卡片类似于选件信息卡片。通过这些配置文件脚本信息卡片，您可以查看引用了所选配置文件脚本的活动列表，以及其他有用的元数据。

例如，通过单击列表([!UICONTROL Info] > [!UICONTROL Audiences])中所需配置文件脚本的[!UICONTROL Profile Scripts]图标，访问以下配置文件脚本信息卡片。

[!UICONTROL Script Info]选项卡包含以下信息：名称、描述和脚本代码。

![轮廓脚本信息卡片](assets/profile_script_info_card.png)

单击&#x200B;**[!UICONTROL View full details]**&#x200B;可查看引用所选配置文件脚本的受众和活动。

![轮廓脚本信息卡片 >“脚本使用情况”选项卡](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>在下列情况下，[!UICONTROL Script Usage]选项卡不显示引用所选配置文件脚本的活动：
>
> * 该活动处于[!UICONTROL Draft]状态。
> * 活动中使用的内容或产品建议使用了脚本变量（活动中的内联产品建议或产品建议库中的产品建议）。

## Target 在某些情况下禁用轮廓脚本 {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] 在某些情况下自动禁用轮廓脚本，例如，如果脚本执行耗时过长或其指令过多。

禁用某个轮廓脚本后，Target UI 中的该轮廓脚本旁边会显示一个黄色警报图标，如下图所示：

![profile_script_invalid 图像](assets/profile_script_invalid.png)

将鼠标悬停在该配置文件脚本上时，会显示有关错误的详细信息，如下图所示：

![profile_script_hover 图像](assets/profile_script_hover.png)

系统禁用配置文件脚本的典型原因包括：

* 引用了未定义的变量。
* 引用了无效值。此错误一般是引用 URL 值和其他用户输入的数据但未经适当的验证所致。
* 使用了过多 JavaScript 指令。[!DNL Target] 具有每个脚本 2000 条 JavaScript 指令的限制，但无法通过手动阅读 JavaScript 而简单地计算此限制。例如，Rhino 将所有函数调用和“new”调用视为 100 条指令。对任何函数的任何调用占用 100 条指令。此外，任何输入数据（例如 URL 值）的大小可能会对指令计数产生影响。
* 不遵循以下[最佳实践](/help/main/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0)部分重点列举的项目。

## 最佳实践 {#best}

下列准则旨在帮助编写简化的配置文件脚本，尽量减少出现错误，从而无需强制中断系统脚本即可对脚本进行处理。这些准则是从经过验证可高效运作的最佳实践中得出的。这些规范将与 Rhino 开发社区制定的原则和建议一起应用。

* 将当前的脚本值设置为用户脚本中的局部变量，设置故障转移到空白字符串。
* 通过确保该局部变量不是空白字符串而验证它。
* 使用基于字符串的操作函数与正则表达式。
* 使用有限制的 for 循环与无限制的 for 或 while 循环。
* 切勿超过 1,300 个字符或 50 次循环迭代。
* 切勿超过 2,000 条 JavaScript 指令。[!DNL Target] 具有每个脚本 2000 条 JavaScript 指令的限制，但无法通过手动阅读 JavaScript 而简单地计算此限制。例如，Rhino 将所有函数调用和“new”调用视为 100 条指令。此外，任何输入数据（例如 URL 值）的大小可能会对指令计数产生影响。
* 不仅要注意脚本性能，还要注意所有脚本的组合性能。作为最佳实践，[!DNL Adobe] 建议指令总数小于 5000 条。清点指令数量并不显而易见，但重要的是要记住，将自动禁用超过 2000 条指令的脚本。活动的轮廓脚本数不应超过 300。随每个 mbox 调用执行每个脚本。应只运行所需数量的脚本。
* 在正则表达式中，几乎从不需要以点星开头（例如：`/.*match/`、`/a|.*b/`）。正则表达式搜索将从字符串中的任意位置开始（除非与 `^` 绑定），因此其已经假定包含点和星形符号。如果此类正则表达式与足够长的输入数据相匹配（最少可达几百个字符），则脚本执行可能会中断。
* 如果全部失败，则将脚本嵌套在 try/catch 中。
* 以下建议可帮助您限制轮廓脚本的复杂性。轮廓脚本可执行的指令数量有限。

  作为最佳实践：

   * 使轮廓脚本保持小规模且尽可能简洁。
   * 避免使用正则表达式或仅使用简单的正则表达式。即使简单的表达式也需要使用许多指令求值。
   * 避免出现递归。
   * 应测试轮廓脚本的性能后再将轮廓脚本添加到 [!DNL Target]。在每次执行 mbox 请求时执行所有轮廓脚本。如果轮廓脚本无法正确执行，则执行 mbox 请求耗时更长，而这可能会影响流量和转化。
   * 如果轮廓脚本过于复杂，请考虑改为使用[响应令牌](/help/main/administrating-target/response-tokens.md)。

* 有关更多信息，请参阅 JS Rhino 引擎文档。

## 调试轮廓脚本 {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

以下方法可用于调试轮廓脚本：

>[!NOTE]
>
>在轮廓脚本中使用 [!DNL console.log] 不会输出轮廓值，因为轮廓脚本在服务器端执行。

* **添加轮廓脚本作为响应令牌以调试轮廓脚本：**

  在[!DNL Target]中，单击&#x200B;**[!UICONTROL Administration]**，单击&#x200B;**[!UICONTROL Response Tokens]**，然后启用要调试的配置文件脚本。

  只要加载上面有 [!DNL Target] 的网站的页面，[!DNL Target] 产生的部分响应就会包含给定轮廓脚本的值，如下所示：

  ![debug_profile_script_1 图像](assets/debug_profile_script_1.png)

* **使用 mboxTrace 调试工具调试轮廓脚本。**

  此方法需要授权令牌，您可以通过单击&#x200B;**[!UICONTROL Target]**&#x200B;部分中的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Generate Authorization Token]** > [!UICONTROL Debugger tools]来生成该令牌。

  然后，可将 `mboxTrace=window&authorization=YOURTOKEN` 这两个参数添加到页面 URL 的“?”之后。

  添加这些参数比响应令牌能够提供更多的信息，因为您可以获得轮廓的执行前快照和执行后快照。它还显示您所有可用的轮廓。

  ![debug_profile_script_2 图像](assets/debug_profile_script_2.png)

## 轮廓脚本常见问题解答 {#section_1389497BB6D84FC38958AE43AAA6E712}

**是否可以使用配置文件脚本捕获位于数据层中的页面信息？**

由于配置文件脚本在服务器端执行，因此它们无法直接读取页面。数据必须通过mbox请求或将数据传入Target[的其他](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=zh-Hans){target=_blank}方法传入。 当数据进入 [!DNL Target] 之后，轮廓脚本可按照 mbox 参数或轮廓参数的形式读取数据。

## 脚本轮廓参数的 JavaScript 参考

有效地使用脚本轮廓参数需要一点简单的 Javascript 知识。本节提供了一个快速参考，借助此参考，您在几分钟内便可以高效地使用此功能。

“脚本轮廓参数”位于 mbox/轮廓选项卡下。您可以编写返回任何 Javascript 类型（字符串、整数、数组等）的 Javascript 程序。

### 脚本轮廓参数示例 {#examples}

**名称：***user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

创建一个以毫秒为单位的“天数”变量。如果 mbox 名称为 `orderThankyouPage`，请设置一个名为 `lastPurchaseTime` 的局部（不可见）用户轮廓属性以显示当前日期和时间的值。其中读取上次购买时间的值，如果已定义，[!DNL Target] 还返回自上次购买时间以来过去的时间除以一天的毫秒数（得出自上次购买以来的天数）。

**名称：***user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

创建名为 `frequency` 的变量，并将其初始化为以前的值，如果没有以前的值，则初始化为 0。如果 mbox 名称为 `orderThankyouPage`，则返回递增的值。

**名称：***user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

创建一个名为 `monetaryValue` 的变量，查找给定访客的当前值（如果没有前一个值，则设置为 0）。如果 mbox 名称为 `orderThankyouPage`，则通过添加前一个值和传递给 mbox 的 `orderTotal` 参数值来返回新的货币值。

**名称：** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

创建名为 `adobeQA` 的变量以跟踪[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md) 的用户。

### 对象和方法 {#objects}

脚本轮廓参数可引用以下对象和方法：

| 对象或方法 | 详细信息 |
| --- | --- |
| `page.url` | 当前 URL。 |
| `page.protocol` | 页面使用的协议（http 或 https）。 |
| `page.domain` | 当前的 URL 域（第一个斜杠之前的所有内容）。例如，`http://www.acme.com/categories/men_jeans?color=blue&size=small` 中的 `www.acme.com`。 |
| `page.query` | 当前页面的查询字符串。“?”之后的所有内容。例如，`http://www.acme.com/categories/mens_jeans?color=blue&size=small` 中的 `blue&size=small`。 |
| `page.param('<par_name>')` | `<par_name>` 表示的参数的值。如果当前 URL 是 Google 搜索页面，而且您已经输入 `page.param('hl')`，则对于 URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`，您将获得“en”。 |
| `page.referrer` | 与上述相同的一组操作适用于反向链接和登陆（即 referrer.url 是反向链接的 url 地址）。 |
| `landing.url`, `landing.protocol`, `landing.query`, 和 `landing.param` | 类似于此类页面，但登陆页面除外。<P>要使登陆页面 URL 按预期工作，请设置 `context` > `browser` > `host`。 |
| `mbox.name` | 活动 mbox 的名称。 |
| `mbox.param('<par_name>')` | 活动 mbox 中给定名称的 mbox 参数。 |
| `profile.get('<par_name>')` | 客户端创建的用户轮廓参数，名称为 `<par_name>`。例如，如果用户设置了名为“gender”的配置文件参数，则可以使用“profile.gender”提取该值。返回为当前访客设置的“`profile.<par_name>`”值；如果尚未设置任何值，则返回 null。请注意，`profile.get(<par_name>)` 被认定为函数调用。 |
| `user.get('<par_name>')` | 返回为当前访客设置的“`user.<par_name>`”值；如果尚未设置任何值，则返回 null。 |
| `user.categoryAffinity` | 返回最佳类别的名称。 |
| `user.categoryAffinities` | 返回具有最佳类别的数组。 |
| `user.isFirstSession` | 如果这是访客的第一个会话，则返回 true。 |
| `user.browser` | 返回 HTTP 标头中的用户代理。例如，您可以创建仅针对 Safari 用户的表达式目标：`if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### 常用运算符

所有标准的 JavaScript 运算符均已列出并可用。JavaScript 运算符可用于字符串和数字（和其他数据类型）。简要介绍：

| 运算符 | 描述 |
| --- | --- |
| `==` | 表示相等。当两边的操作数相等时，为 true。 |
| `!=` | 表示不相等。当两边的操作数不相等时，为 true。 |
| `<` | 表示左侧的变量小于右侧的变量。如果变量相等，则得出的值为 false。 |
| `>` | 表示左侧的变量大于右侧的变量。如果变量相等，则得出的值为 false。 |
| `<=` | 除了如果变量相等，则其所得的值为 true 之外，与 `<` 相同。 |
| `>=` | 除了如果变量相等，则其所得的值为 true 之外，与 `>` 相同。 |
| `&&` | 从逻辑上讲，对于“AND”左侧和右侧的表达式，仅当两侧都为 true 时才为 true（否则为 false）。 |
| `\|\|` | 从逻辑上讲，对于“OR”左侧和右侧的表达式，仅当一侧为 true 时才为 true（否则为 false）。 |
| `//` | 检查源是否包含目标布尔值所包含的所有元素（源数组，目标数组）。<br>`//` 从（正则表达式对应的）目标提取子字符串并将它解码 `Array/*String*/ decode(String encoding, String regexp, String target)`。<br>此功能还支持使用常量字符串值、分组(`condition1 \|\| condition2) && condition3`)和正则表达式(`/[^a-z]$/.test(landing.referring.url)`)。 |

## 培训视频：轮廓脚本 ![“教程”标记](/help/main/assets/tutorial.png)

以下视频包含有关使用和创建配置文件脚本的信息。

* 阐明配置文件脚本是什么
* 介绍配置文件脚本与配置文件参数的不同之处
* 创建简单的配置文件脚本
* 使用“可用令牌”菜单访问可用选项
* 启用和禁用配置文件脚本

>[!VIDEO](https://video.tv.adobe.com/v/17394)
