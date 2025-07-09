---
keywords: 故障诊断;常见问题解答;FAQ;锁定;受众
description: 查看有关Adobe [!DNL Target] 活动中使用的体验定位和受众的常见问题解答(FAQ)。
title: 可在何处找到关于目标和受众的问答？
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
source-git-commit: cf7f18b5fd9647bbecda2e6b6419c3a927708bd6
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 53%

---

# 锁定和受众常见问题解答

有关体验定位和受众的常见问题解答 (FAQ) 列表。

## [!DNL Target]如何在定位中评估URL？ {#url}

Target对URL的评估有所不同，具体取决于您在创建活动时是使用受众URL定位，还是在创建受众时使用URL定位。

请考虑以下URL：

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### 受众URL定位

要在创建活动时应用受众URL定位，请在&#x200B;**[!UICONTROL Experiences]**&#x200B;页面（三步引导式工作流的步骤一）上单击&#x200B;**[!UICONTROL Configure]**&#x200B;图标（![配置图标](/help/main/assets/icons/Setting.svg)），单击&#x200B;**[!UICONTROL Page Delivery]**，然后指定所需的URL。

![页面交付URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

受众URL定位会查找精确的URL匹配项。 如果URL匹配，则Target不考虑进一步逻辑。 在上述URL中，如果活动设置为在`www.example.com`上触发，则该URL与以下URL匹配，因为受众URL定位与查询无关：

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

除了URL上的受众定位之外，您还可以指定查询中可以包含的特定值。

通过[!UICONTROL Template Rules]添加的受众URL定位和URL定位将评估为URL定位（请参阅下面的URL定位）。

### URL定位 {#url-targeting}

要在创建受众时应用URL定位，请单击将&#x200B;**[!UICONTROL Site Pages]**&#x200B;拖放到[!UICONTROL Create Audiences]窗格中，单击&#x200B;**[!UICONTROL Site Pages]**，从第一个下拉列表（[!UICONTROL Current Page]、[!UICONTROL Previous Page]或[!UICONTROL Landing Page]）中选择一个选项，从第二个下拉列表中选择[!UICONTROL URL]，指定计算器，然后指定所需的URL。

![网站页面>当前页面> URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL定位会将URL转换为一组规则以进行评估：

* URL = `example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`
* 域= `example.com`
* 路径= `path1/path2/path3`
* 查询= `queryStringParam1=test123&queryStringParam2=test7`

## 创建复杂的URL字符串时，[!DNL Target]是否计算整个URL？

如果在URL字符串中多次使用相同的参数名称，则HTTP会考虑第一个参数名称，并忽略具有相同名称的后续参数。

例如，在以下URL字符串中：

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

计算`Category`参数的第一个实例，并忽略第二个`Category`参数。

最佳实践为将多个值关联到单个类别，如下所示：

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## 构建受众时，为何会在其他类别下找到[!DNL Target]库下的预构建受众？ {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

“定位库”类别中预先构建的受众是旧版受众，它们存在于其他类别中。例如，旧版“定位库”>“新访客”中的受众在更新后会相应地移到“访客配置文件”>“新访客”。

最佳做法是使用新版受众，因为新版受众在性能方面做出了改进。有些客户可能还在使用预先构建的旧版受众，因此旧版受众尚未从 Target 用户界面中删除。

## 我如何了解受众间的流量分配方式？ {#section_067EEFB956E7465CBF77EC86834470AB}

默认情况下，流量会在体验之间平均拆分。但是，您可以为每个体验指定百分比目标。 在这种情况下，会生成随机编号，这个编号用于选择要显示的体验。最终的百分比可能与指定定位不完全匹配，但是流量越多，体验的划分应越接近定位目标。

## 如果用户符合某个活动的参加条件，而该活动包含多个体验且具有多个符合条件的受众，那么会显示哪个体验？ {#section_94A60B11212D48FD8AB0803C6C7E7253}

该用户符合在活动[!UICONTROL Target]页面上显示的第一个体验/受众的条件。

例如，假设该体验/受众将Windows列为体验A，将iOS列为体验B，将加利福尼亚列为体验C。来自加利福尼亚州的使用Windows设备的用户同时符合体验A（Windows受众）和体验C（加利福尼亚受众）的条件。 但由于在“Target”页面上的列表中，体验 A 显示在体验 C 上方，因此会向该用户显示体验 A。

## 为何同一个受众在[!DNL Target]、Adobe Audience Manager (AAM)以及核心服务中的受众库中具有不同的名称？ {#section_F67E61A607B6444C8DAA4F99C3E95AED}

[!DNL Target] 中的受众名称是唯一的；但是，在 [!DNL AAM] 和 [!DNL Audience Library] 中，您可以使用同一个名称来命名多个受众（前提是这些受众位于不同的文件夹中）。如果 [!DNL Target] 中某个受众名称恰巧与 [!DNL AAM] 或 [!DNL Audience Library] 中相应受众的名称相同，则 [!DNL Target] 会将“#&lt;number>”附加到该受众名称。

例如，您可能会看到以下受众：“PC Users”（位于 [!DNL AAM] 中）和“PC Users #1”（位于 [!DNL Target] 中）。

## 为何无法重命名受众？ {#section_54E420556F534D20836E261E253D8B97}

有些 Target 受众是预先构建的，例如“新访客”和“旧访客”。用户无法对这些预先构建的受众进行重命名。

## 为什么所有配置文件参数都没有显示在[!DNL Target]用户界面中？ {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] 限制每个 mbox 调用只能包含 50 个唯一的轮廓属性。如果您需要将50个以上的配置文件属性传递到[!DNL Target]，则可以使用[!UICONTROL Profile Update] API方法来传递它们。 有关更多信息，请参阅 Adobe Target API 文档中的[配置文件更新](https://developers.adobetarget.com/api/#authentication-tokens)。

## 为何访客在 AP 活动中看到他们不应看到的体验？ {#section_41CECEAE0881446A8D9F3B016857914B}

自动个性化活动会在每次会话中都进行一次评估。如果之前已有活跃会话符合某个特定体验的条件，且现在已在该体验中添加了新选件，则用户会同时看到新的内容以及之前显示的选件。因为用户之前符合这些体验的参加条件，因此他们在会话持续期间仍会看到这些体验。如果您希望在每一次进行页面访问时都进行评估，则应该切换到体验定位 (XT) 活动类型。

## 为何对通过API创建的受众所做的更改未反映在[!DNL Target] UI中？ {#section_6BEB237CAC004A06A290F9644E5BF0FB}

与产品建议和轮廓脚本不同，API 对通过 Target Standard 创建的受众所做的更改当前不会同步回 Target UI。

## 表示数字的字符串（也支持浮点数）作为数字进行比较。{#strings-that-represent-numbers}

如果等式的左侧和右侧部分可以解析为数字，则这两部分将作为数字进行比较，而不是作为字符串进行比较。

例如：

| 值 | 定位标准 | 结果 |
| --- | --- | --- |
| 1.0 | 等于 1 | true |
| 1 | equalsIgnoreCase 1.0 | true |
| 1.230 | 等于 1 | true |
| 1.500 | 等于 1.5 | true |
| 1.200 | 小于 2 | true |
| 2 | 大于 3.0 | false |
| 045 | 等于 45 | true |

用科学记数法编写的数字将始终作为字符串进行比较。

例如：

“4e-2”将仅等于“4e-2”。而&#x200B;*不*&#x200B;等于“0.04”。
