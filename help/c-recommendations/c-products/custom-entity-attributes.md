---
keywords: 多值实体属性;自定义实体属性;有效 JSON;实体属性值;JSON 数组;多值的;多值
description: 可使用单值和多值自定义实体属性来对目录中的项目定义其他相关信息。
title: 自定义实体属性
uuid: ccebcd16-7d8f-468f-8474-c89b0f029bdb
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) 自定义实体属性{#custom-entity-attributes}

可使用单值和多值自定义实体属性来对目录中的项目定义其他相关信息。

## 限制 {#limits}

您最多可以包含 100 个自定义实体属性，来对目录中的项目定义其他相关信息。例如，您可以创建一个名为 `entity.genre` 的自定义属性，用来定义一本书籍或一部电影。或者，票务供应商可以为活动场地创建属性以包括辅助表演，例如体育赛事中的客队或音乐会上的开场表演。

单值实体自定义属性的最大长度为 15,000 个字符（对于单字节和双字节 UTF-8 编码语言，例如英语和其他拉丁文字字母）或 10,000 字符（对于三字节 UTF-8 编码语言，例如中文、日语和韩语）。

多值实体自定义属性最多可以包含 500 个值。每个值的限制为 100 个字符。所有值的字符总数必须符合单值实体自定义属性的最大长度限制（请参阅上文）。

## 自定义实体属性值 {#section_313331A9F8194A89B5EDD89363018651}

自定义实体属性可以包含单个值或多个值。实体属性值会显示在产品视图中。

![](assets/multi-value_product.png)

具有单个值的自定义实体属性的构成方式与单值预定义实体属性相同：

```
entity.genre=genre1
```

多值自定义实体属性必须作为有效的 JSON 数组来发送：

```
entity.genre=[“genre1”, “genre2”]
```

[!DNL Recommendations] 支持的有效 JSON 数组的示例：

* `["AB","BC"]` 所有值均为字符串
* `[1,2]` 所有值均为数字

>[!NOTE]
>
>[!DNL Recommendations] 不支持多值实体属性中存在混合值类型。例如，`["AB",1,true, [1,2,3]]` 是有效的 JSON 数组，但在 [!DNL Recommendations] 中不受支持，因为它包含混合值类型（字符串、数字、布尔值、对象）。

将自定义属性作为有效的 JSON 数组发送后，该属性会被视为目录中所有产品的多值属性。

>[!NOTE]
>
>要将多值属性更改为单值属性，您必须删除目录并上传已更正的产品数据。删除目录不会删除与您的产品 ID 关联的历史数据。有关更多信息，请参阅 Adobe Recommendations Classic ** 文档中的[删除系统中的所有项目](../../assets/adobe-recommendations-classic.pdf)。

**限制**：

* 您无法将预定义实体属性的名称用于自定义实体属性。（请参阅[实体属性](../../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F)。）
* `entity.environment` 属性由系统保留，该属性不能用于自定义实体属性。尝试使用 `entity.environment`、信息源或 API 来传递 `targetPageParams` 的操作将会被忽略。
* 数组必须包含单值类型。不支持混合值数组 ( `["AB",1,true]` )。
* 包含嵌套 JSON 数组 ( `[10,12,[1,2,3]]` ) 的多值属性会被视为单值属性。

## 实施多值属性 {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

使用信息源 (CSV)、`targetPageParams`、交付 API 和保存实体 API 上传产品时，支持多值自定义实体属性。新值会替换当前值，而不进行附加。空数组 ( [] ) 会被视为没有值。

必须对双引号进行转义。例如，`"[""test"", ""value""]"` 是可在 CSV 中使用的有效 JSON 数组。

您最多可以在多值属性中包含 500 个值。

**使用 targetPageParams**

以下示例显示了如何使用 `targetPageParams`。

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

**使用 CSV**

您可以使用文本编辑器以原始格式管理 CSV 文件，也可以使用电子表格软件。

原始 CSV 将如下所示：

![](assets/multi-value_example_raw.png)

电子表格中的相同目录将如下所示：

![](assets/multi-value_example_excel.png)

在转换为 [!DNL .csv] 格式时，电子表格软件会在单元格内容两侧添加双引号，以防止单元格内的逗号充当列分隔符。它还会在自定义多值属性中包含的 JSON 字符串值两侧添加双引号标记。这样可直接处理庞杂的原始文件。例如：

* 电子表格：`["1","2","3"]`
* 原始：`"[""1"",""2"",""3""]"`

直接编辑原始目录 CSV 文件时务必要小心。

**使用 API**

See the [Adobe Recommendations API documentation](http://developers.adobetarget.com/api/recommendations) for information about
using the Delivery and Save entities APIs.

## 将运算符与多值属性配合使用 {#section_83C2288A805242D9A02EBC4F07DEE945}

在算法包含规则、目录规则和排除规则中将运算符应用于多值自定义属性时，如果列表中至少有一个值符合运算规则（布尔运算“或”**），则结果将为 *true*。

在下面的示例中，规则为 `message contains abc`。

用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 false，因为没有值包含 `abc`。

用例 2：`entity.genre = ["abcde","de","ef"]`结果为 true，因为有一个值包含 `abc`。

对于否定运算符，所有属性值必须都符合运算规则（布尔运算“和”**）。例如，如果运算符为 `notEquals`，则当有任何值匹配时，结果将为 *false*。

有关算法包含规则、目录规则和排除规则中的运算符行为，请参阅下表。

| 运算符 | 行为 | 示例 |
|--- |--- |--- |
| 等于 | 如果有任何属性值等于输入值，则结果为 true。 | `genre equals abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 false，因为没有值等于 `abc`。<br>用例 2：`entity.genre = ["abc", "de", "ef"]`。结果为 true，因为有一个值等于 `abc`。<br>用例 3：`entity.genre = ["abcde", "de", "ef"]`结果为 false，因为 `abc` 不等于列表中的任何元素。 |
| 不等于 | 如果没有属性值等于输入值，则结果为 true。 | `genre not equals abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 true，因为没有值等于 `abc`。<br>用例 2：`entity.genre = ["abc", "de", "ef"]`。结果为 false，因为有一个值等于 `abc`。<br>用例 3：`entity.genre = ["abcde", "de", "ef"]`结果为 true，因为 `abc` 不等于列表中的任何元素。 |
| 包含 | 如果有任何属性值包含输入值，则结果为 true。 | `genre contains abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 false，因为没有值包含 `abc`。<br>用例 2：`entity.genre = ["abcde", "de", "ef"]`。结果为 true，因为有一个值包含 `abc`。 |
| 不包含 | 如果没有属性值包含输入值，则结果为 true。 | `genre does not contain abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 true，因为没有值包含 `abc`。<br>用例 2：`entity.genre = ["abcde", "de", "ef"]`。结果为 false，因为有一个值包含 `abc`。 |
| 开始于 | 如果有任何属性值以输入值开头，则结果为 true。 | `genre starts with abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 false，因为没有值开始于 `abc`。<br>用例 2：`entity.genre = ["abcde", "de", "ef"]`。结果为 true，因为有一个值开始于 `abc`。<br>用例 3：`entity.genre = ["ab", "de", "abc"]`结果为 true，因为有一个值开始于 `abc`（不一定是列表中的第一个元素）。 |
| 结束于 | 如果有任何属性值以输入值结尾，则结果为 true。 | `genre ends with abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 false，因为没有值结束于 `abc`。<br>用例 2：`entity.genre = ["deabc", "de", "ef"]`。结果为 true，因为有一个值结束于 `abc`。 |
| 大于或等于（仅限数字值） | 属性值会被转换为双精度类型。运行规则时将跳过无法转换的属性。<br>处理后，任何大于或等于输入值的属性值都将导致结果为 true。 | `price greater than or equal to 100`<br>用例 1：`entity.price = ["10", "20", "45"]`。结果为 false，因为没有值大于或等于 100。跳过了值 `de`，因为无法将其转换为双精度类型。<br>用例 2：`entity.price = ["100", "101", "90", "80"]`。结果为 true，因为有两个值大于或等于 100。 |
| 小于或等于（仅限数字值） | 属性值会被转换为双精度类型。运行规则时将跳过无法转换的属性。<br>处理后，任何小于或等于输入值的属性值都将导致结果为 true。 | `price less than or equal to 100`<br>用例 1：`entity.price = ["101", "200", "141"]`。结果为 false，因为没有值小于或等于 100。跳过了值 `de`，因为无法将其转换为双精度类型。<br>用例 2：`entity.price = ["100", "101", "90", "80"]`。结果为 true，因为有两个值小于或等于 100。 |
| 动态匹配（仅在基于项目的算法中可用） | 如果有任何属性值与输入值匹配，则结果为 true。 | `genre matches abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`结果为 false，因为没有值与 `abc`。<br>用例 2：`entity.genre = ["abc", "de", "ef"]`。结果为 true，因为有一个值与 `abc`。 |
| 动态不匹配（仅在基于项目的算法中可用） | 如果有任何属性值与输入值匹配，则结果为 false。 | `genre does not match abc`<br>用例 1：`entity.genre = ["ab", "bc", "de"]`。结果为 true，因为没有值与 `abc`。<br>用例 2：`entity.genre = ["abc", "de", "ef"]`。结果为 false，因为有一个值与 `abc`。 |
| 动态范围（仅在基于项目的算法中可用，仅限数字值） | 如果有任何数字属性值位于指定的范围内，则结果为 true。 | `price dynamically ranges in 80% to 120% of 100`<br>用例 1：`entity.price = ["101", "200", "125"]`。结果为 true，因为 `101` 在 100 的 80% 到 120% 范围内。跳过了值 `de`，因为无法将其转换为双精度类型。<br>用例 2：`entity.price = ["130", "191", "60", "75"]`。结果为 false，因为没有值在 100 的 80% 到 120% 范围内。 |

>[!NOTE]
>
>*双精度类型*&#x200B;是一种 Java 数据类型。对于需要使用数字值的运算符，转换为双精度类型可避免在结果中考虑非数字值。

## 设计中的多值属性 {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

多值属性在设计中引用时，将显示为以逗号分隔的列表。

示例：

当 `entity.genre=["genre1","genre2"]` 在设计中以 `$entity<N>.genre` 方式引用时，结果为 `genre1, genre2`。

>[!MORELIKETHIS]
>
>* [实体属性](../../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F)

