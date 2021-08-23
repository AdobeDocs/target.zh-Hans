---
keywords: 配置文件脚本；配置文件脚本属性；配置文件脚本最佳实践；调试；脚本；配置文件脚本；属性；参数
description: 了解存储在访客配置文件中的特定于访客的属性，以提供可在您的Adobe [!DNL Target] 活动中使用的相关信息。
title: 什么是配置文件属性？
feature: 受众
exl-id: 6c689629-bbd3-461e-9a68-5b16d4eb4250
source-git-commit: f509fca07305d72cfc3ffd99d0e9a21b19dc6521
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 49%

---

# 配置文件属性

[!DNL Adobe Target]中的配置文件属性是特定于访客的参数。 这些属性存储在访客的配置文件中，提供了可在您的活动中使用的关于访客的信息。

用户配置文件包含网页访客的人口统计和行为信息。 此信息可能包括年龄、性别、购买的产品、上次访问时间等，[!DNL Target]用于将其提供给访客的内容个性化。

当访客浏览您的网站或返回网站进行其他会话时，配置文件中保存的配置文件属性可用于定位内容或记录信息以便进行区段过滤。

要设置配置文件属性，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 受众]** > **[!UICONTROL 配置文件脚本。]**

   ![“配置文件脚本”选项卡](/help/c-target/c-visitor-profile/assets/create-script.png)

1. 单击&#x200B;**[!UICONTROL 创建脚本]**。

   ![“创建配置文件脚本”对话框](/help/c-target/c-visitor-profile/assets/profile-script.png)

   可以使用以下类型的配置文件属性：

   | 参数类型 | 描述 |
   |--- |--- |
   | mbox | 创建 mbox 时，直接通过页面代码传入。请参阅[将参数传递到全局 mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)。<br>****&#x200B;注意： 限制每个 mbox 调用只能包含 50 个唯一的配置文件属性。[!DNL Target]如果必须将50个以上的配置文件属性传递到[!DNL Target]，请使用配置文件更新API方法进行传递。 有关更多信息，请参阅 [!DNL Adobe Target] API文档](https://developers.adobetarget.com/api/#updating-profiles)中的[配置文件更新。 |
   | Profile | 直接使用 JavaScript 代码段定义。这些片段可以存储运行总数，如消费者所花费的总资金，并在每个mbox请求中执行。 请参阅下面的“配置文件脚本属性”。 |

## 配置文件脚本属性 {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

可使用关联的 JavaScript 代码段定义配置文件脚本属性。

您可以使用配置文件脚本，在多次访问中捕获访客属性。配置文件脚本是在[!DNL Target]中使用服务器端JavaScript形式定义的代码片段。 例如，您可以使用配置文件脚本捕获访客访问您网站的频率以及该访客上次访问的时间。

配置文件脚本与配置文件参数不同。配置文件参数使用[!DNL Target]的mbox代码实施来捕获有关访客的信息。

## 创建配置文件脚本 {#section_CB02F8B97CAF407DA84F7591A7504810}

配置文件脚本位于 [!UICONTROL  界面的“]受众[!DNL Target]”选项卡下。

要添加配置文件脚本，请单击&#x200B;**[!UICONTROL 配置文件脚本]**&#x200B;选项卡、**[!UICONTROL 创建脚本]**，然后编写您的脚本。

或

要复制现有的配置文件脚本，请从[!UICONTROL 配置文件脚本]列表中，单击所需脚本的省略号图标，然后单击&#x200B;**[!UICONTROL 复制]**。

然后，您可以对受众进行编辑以创建一个类似的受众。

配置文件脚本会对每个位置请求运行配置文件属性“catchers”。收到位置请求后，[!DNL Target]会确定应运行哪个活动并显示适合该活动和该体验的内容。 [!DNL Target] 还会跟踪活动的成功情况并运行任何相关的配置文件脚本。通过此过程，您可以跟踪有关访问的信息，如访客的位置、时间、访客访问网站的次数、访客以前购买过的次数等。 然后，这些信息将添加到访客的配置文件中，以便您可以更好地跟踪访客在您网站上的活动。

配置文件脚本属性在属性名称之前插入 `user.` 标记。例如：

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

请牢记以下信息：

* 在具有`user.get('parameterName')`的代码中引用配置文件脚本属性（包括其自身）。
* 保存下次使用`user.setLocal('variable_name', 'value')`运行脚本时（对下一个mbox请求）可访问的变量。 使用 `user.getLocal('variable_name')` 引用变量。当您想引用上次请求的日期和时间时，此过程非常有用。
* 参数和值区分大小写。 匹配您在活动或测试期间收到的参数和值的大小写。
* 有关更多的 JavaScript 语法，请参阅下文中的“脚本配置文件参数的 JavaScript 引用”部分。
* 禁用脚本后，参数会保留在配置文件中。 其用户档案已包含活动受众中使用的参数，且该用户有资格参与该活动。
* 配置文件脚本在活动中使用时无法删除。
* 不建议创建使用另一个配置文件脚本中一个配置文件脚本结果的从属配置文件脚本。 配置文件脚本的执行顺序无法得到保证。

## 查看配置文件脚本信息卡片 {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

您可以查看配置文件脚本信息弹出卡片，该卡片类似于选件信息卡片。通过这些配置文件脚本信息卡片，您可以查看引用了所选配置文件脚本的活动列表，以及其他有用的元数据。

例如，通过单击列表中所需配置文件脚本的[!UICONTROL 信息]图标（[!UICONTROL 受众] > [!UICONTROL 配置文件脚本]），可访问以下配置文件脚本信息卡。

[!UICONTROL 脚本信息]选项卡包含以下信息：名称、描述和脚本代码。

![配置文件脚本信息卡](assets/profile_script_info_card.png)

单击&#x200B;**[!UICONTROL 查看完整详细信息]**&#x200B;可查看引用所选配置文件脚本的受众和活动。

![配置文件脚本信息卡 >“脚本使用情况”选项卡](assets/profile_script_info_card_usage_tab.png)

>[!NOTE]
>
>在以下情况下，[!UICONTROL 脚本使用情况]选项卡不显示引用所选配置文件脚本的活动：
>
> * 活动处于[!UICONTROL 草稿]状态。
> * 活动中使用的内容或选件使用了脚本变量（活动中的内联选件或选件库中的选件）。


## Target 在某些情况下会禁用配置文件脚本 {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] 在某些情况下（例如，如果配置文件脚本执行时间过长或指令过多）会自动禁用配置文件脚本。

禁用某个配置文件脚本后，Target UI 中的该配置文件脚本旁边会显示一个黄色警报图标，如下图所示：

![](assets/profile_script_invalid.png)

将鼠标悬停在该配置文件脚本上时，会显示有关错误的详细信息，如下图所示：

![](assets/profile_script_hover.png)

系统禁用配置文件脚本的典型原因包括：

* 引用了未定义的变量。
* 引用了无效值。此错误通常是由引用URL值和其他用户输入的数据而未进行正确验证所导致。
* 使用了过多 JavaScript 指令。[!DNL Target] 限制每个脚本只能使用2,000个JavaScript指令，但是，不能简单地通过手动读取JavaScript来计算此限制。例如，Rhino 会将所有函数调用和“新”调用视为 100 条指令。对任何函数的任何调用都会使用100个说明。 此外，任何输入数据（例如 URL 值）的大小可能会对指令计数产生影响。
* 不遵循以下[最佳实践](/help/c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0)部分重点列举的项目。

## 最佳实践 {#best}

下列准则旨在帮助编写简化的配置文件脚本，尽量减少出现错误，从而无需强制中断系统脚本即可对脚本进行处理。这些准则是从经过验证可高效运作的最佳实践中得出的。这些规范将与 Rhino 开发社区制定的原则和建议一起应用。

* 将当前脚本值设置为用户脚本中的本地变量，将故障转移设置为空字符串。
* 通过确保局部变量为非空字符串验证局部变量。
* 使用基于字符串的操作函数与正则表达式。
* 使用限制性 for 循环与开放式 for 或 while 循环。
* 切勿超过 1,300 个字符或 50 次循环迭代。
* 切勿超过 2,000 条 JavaScript 指令。[!DNL Target] 限制每个脚本只能使用2,000个JavaScript指令，但是，不能简单地通过手动读取JavaScript来计算此限制。例如，Rhino 会将所有函数调用和“新”调用视为 100 条指令。此外，任何输入数据（例如 URL 值）的大小可能会对指令计数产生影响。
* 不仅要注意脚本性能，还要注意所有脚本的组合性能。作为最佳实践，[!DNL Adobe]建议的指令总数少于5,000个。 计算指令数量并不明显，但需要注意的重要一点是，超过2,000条指令的脚本会自动禁用。 有效配置文件脚本的数量不应超过300个。 每个脚本都通过每个mbox调用执行。 应只运行所需数量的脚本。
* 在正则表达式中，在开头使用点和星形符号(例如：`/.*match/`、`/a|.*b/`)几乎从不需要。 正则表达式搜索将从字符串中的任意位置开始（除非与 `^` 绑定），因此其已经假定包含点和星形符号。如果此类正则表达式与足够长的输入数据相匹配（最少可达几百个字符），则脚本执行可能会中断。
* 如果全部失败，则将脚本嵌套在 try/catch 中。
* 以下建议可帮助您限制配置文件脚本的复杂性。 配置文件脚本可以执行有限数量的指令。

   作为最佳实践：

   * 尽量保持配置文件脚本小而简单。
   * 避免使用正则表达式或仅使用简单的正则表达式。 即使是简单的表达式，也可能需要许多说明来进行评估。
   * 避免递归。
   * 配置文件脚本在添加到[!DNL Target]之前应该先进行性能测试。 所有配置文件脚本都会在每个mbox请求中执行。 如果配置文件脚本无法正确执行，则执行mbox请求的时间会更长，这可能会影响流量和转化。
   * 如果配置文件脚本过于复杂，请考虑改用[响应令牌](/help/administrating-target/response-tokens.md)。

* 有关更多信息，请参阅JS Rhino引擎文档。

## 调试配置文件脚本 {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

以下方法可用于调试配置文件脚本：

>[!NOTE]
>
>在配置文件脚本中使用[!DNL console.log]不会输出配置文件值，因为配置文件脚本在服务器端执行。

* **将配置文件脚本添加为响应令牌以调试配置文件脚本：**

   在[!DNL Target]中，单击&#x200B;**[!UICONTROL 管理]**，单击&#x200B;**[!UICONTROL 响应令牌]**，然后启用要调试的配置文件脚本。

   无论您何时加载带有[!DNL Target]的网站页面，来自[!DNL Target]的部分响应都会包含给定配置文件脚本的值，如下所示：

   ![](assets/debug_profile_script_1.png)

* **使用mboxTrace调试工具调试配置文件脚本。**

   此方法需要授权令牌，您可以通过单击&#x200B;**[!UICONTROL Target]** > **[!UICONTROL 管理]** > **[!UICONTROL 实施]** > **[!UICONTROL 在[!UICONTROL Debugger tools]部分中生成授权令牌]**&#x200B;来生成该令牌。

   然后，将以下两个参数添加到页面URL中的“？”之后：`mboxTrace=window&authorization=YOURTOKEN`。

   添加这些参数比响应令牌的信息量更大，因为您会获得配置文件的执行前快照和执行后快照。 它还会显示所有可用的用户档案。

   ![](assets/debug_profile_script_2.png)

## 配置文件脚本常见问题解答 {#section_1389497BB6D84FC38958AE43AAA6E712}

**是否可以使用配置文件脚本捕获位于数据层中的页面信息？**

由于配置文件脚本在服务器端执行，因此它们无法直接读取页面。数据必须通过 mbox 请求或其他[将数据传入 Target 的方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)传递。在数据位于[!DNL Target]中后，配置文件脚本可以将数据作为mbox参数或配置文件参数读取。

## 脚本配置文件参数的 JavaScript 引用

要有效使用脚本配置文件，需要具备简单的Javascript知识
参数。 本节提供了一个快速参考，借助此参考，您在几分钟内便可以高效地使用此功能。

“脚本配置文件参数”位于 mbox/配置文件选项卡下。您可以编写返回任何 Javascript 类型（字符串、整数、数组等）的 Javascript 程序。

### 脚本配置文件参数示例 {#examples}

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

创建一个以毫秒为单位的“天数”变量。如果mbox名称为`orderThankyouPage`，请设置名为`lastPurchaseTime`的本地（不可见）用户配置文件属性，以显示当前日期和时间的值。 读取上次购买时间的值，如果定义，[!DNL Target]将返回自上次购买时间以来经过的时间除以一天中的毫秒数（其结果是自上次购买后的天数）。

**名称：***user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

创建一个名为`frequency`的变量，将其初始化为前一个值，如果没有前一个值，则初始化为0。 如果 mbox 名称为 `orderThankyouPage`，则返回递增的值。

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

创建一个名为`adobeQA`的变量以跟踪用户的[活动QA](/help/c-activities/c-activity-qa/activity-qa.md)。

### 对象和方法

脚本配置文件参数可以引用以下属性和方法：

| 对象或方法 | 详细信息 |
| --- | --- |
| `page.url` | 当前 URL。 |
| `page.protocol` | 页面使用的协议（http 或 https）。 |
| `page.domain` | 当前的 URL 域（第一个斜杠之前的所有内容）。例如，`http://www.acme.com/categories/men_jeans?color=blu e&size=small` 中的 `www.acme.com`。 |
| `page.query` | 当前页面的查询字符串。“?”之后的所有内容。例如，`http://www.acme.com/categories/mens_jeans?color=blue&size=small` 中的 `blue&size=small`。 |
| `page.param(‘<par_name>’)` | `<par_name>` 表示的参数的值。如果当前 URL 是 Google 搜索页面，而且您已经输入 `page.param('hl')`，则对于 URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`，您将获得“en”。 |
| `page.referrer` | 与上述操作集相同，适用于反向链接和登陆（即referrer.url是反向链接的URL地址）。 |
| `landing.url`, `landing.protocol`, `landing.query`, 和 `landing.param` | 类似于此类页面，但登陆页面除外。 |
| `mbox.name` | 活动 mbox 的名称。 |
| `mbox.param(‘<par_name>’)` | 活动 mbox 中给定名称的 mbox 参数。 |
| `profile.get(‘<par_name>’)` | 客户端创建的用户配置文件参数，名称为 `<par_name>`。例如，如果用户设置了名为“gender”的配置文件参数，则可以使用“profile.gender”提取该值。返回为当前访客设置的“`profile.<par_name>`”值；如果未设置任何值，则返回 null。请注意，`profile.get(<par_name>)`符合函数调用的条件。 |
| `user.get(‘<par_name>’)` | 返回为当前访客设置的“`user.<par_name>`”值；如果未设置任何值，则返回 null。 |
| `user.categoryAffinity` | 返回最佳类别的名称。 |
| `user.categoryAffinities` | 返回具有最佳类别的数组。 |
| `user.isFirstSession` | 如果这是访客的第一个会话，则返回 true。 |
| `user.browser` | 返回 HTTP 标头中的用户代理。例如，您可以创建仅针对 Safari 用户的表达式目标：`if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### 常用运算符


所有标准的 JavaScript 运算符均已列出并可用。JavaScript运算符可用于字符串和数字（以及其他数据类型）。 简要介绍：

| 运算符 | 描述 |
| --- | --- |
| `==` | 表示相等。当两边的操作数相等时，为 true。 |
| `!=` | 表示不相等。当两边的操作数不相等时，为 true。 |
| `<` | 表示左侧的变量小于右侧的变量。如果变量相等，则计算结果为false。 |
| `>` | 表示左侧的变量大于右侧的变量。如果变量相等，则计算结果为false。 |
| `<=` | 与`<`相同，除非变量相等，则其计算结果为true。 |
| `>=` | 与`>`相同，除非变量相等，则其计算结果为true。 |
| `&&` | 从逻辑上讲，对于“AND”左侧和右侧的表达式，仅当两侧都为 true 时才为 true（否则为 false）。 |
| `||` | 从逻辑上讲，对于“OR”左侧和右侧的表达式，仅当一侧为 true 时才为 true（否则为 false）。 |
| `//` | 检查源是否包含目标布尔值所包含的所有元素（源数组，目标数组）。<br>`//` 从目标（对应于 regexp）中提取子字符串并将其解码为 `Array/*String*/ decode(String encoding, String regexp, String target)`。<br>该功能还支持使用常量字符串值、分组 (`condition1 || condition2) && condition3` 和正则表达式 (`/[^a-z]$/.test(landing.referring.url)`)。 |

## 培训视频：配置文件脚本![教程徽章](/help/assets/tutorial.png)

以下视频包含有关使用和创建配置文件脚本的信息。

* 阐明配置文件脚本是什么
* 介绍配置文件脚本与配置文件参数的不同之处
* 创建简单的配置文件脚本
* 使用“可用令牌”菜单访问可用选项
* 启用和禁用配置文件脚本

>[!VIDEO](https://video.tv.adobe.com/v/17394)
