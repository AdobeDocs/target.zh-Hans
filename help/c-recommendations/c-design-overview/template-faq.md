---
keywords: 推荐;常见问题解答;FAQ
description: 有关“推荐”设计的常见问题解答 (FAQ) 列表。
title: 设计常见问题解答
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) 设计常见问题解答{#design-faq}

有关“推荐”设计的常见问题解答 (FAQ) 列表。

## 推荐项目的价格并没有在小数点的右侧显示两个值。我该如何显示它们？

默认情况下，设计模板中返回的数值（如 `entity.value`）不会在小数点之后显示任何尾随的零。例如，如果某个项目的价格为 $35.00，则 `entity.value` 等于 35，并且页面上仅显示 35，而不是 $35.00。

有两种方法可用于解决此问题。

* 您可以使用 Velocity 脚本或 Javascript 对返回的值应用格式设置。

* 您可以将项目的价格传递到两个单独的实体属性中。第一个属性 `entity.value` 可用于进行数值比较（例如价格比较规则）。第二个应该是自定义属性，例如 `entity.displayValue`，用于将实体的值存储为字符串以正确进行渲染。

   例如：

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## 设计中为何没有显示类别？我使用的是 $entity1.categoryId。{#section_073309B8051049C7953D396A93EA0713}

类别 ID 无法在设计中显示。由于可以存储多个类别，因此系统不知道要显示哪个类别。

## 我应该如何更改设计才能实现即时更新？ {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

对当前正在使用的设计进行更改后，需要等待一段时间才会更新。要即时更改设计，请创建一个新设计，然后在营销活动中选择该设计，并保存推荐。

## 如何捕捉要在设计中显示的关键信息？示例：如果我们想要显示关键产品的类别，如何在 Velocity 设计中对该值进行编码？ {#section_F08043B14BA24BC8815FEF25F4F84C39}

`$key. *`value`*` 参数可以捕捉要在设计中显示的大多数关键产品信息。示例：如果您需要显示关键产品的缩略图，则应当使用 `$key.thumbnailURL`。

## 使用哪个版本的 Velocity？{#section_28F00E15A4A54A768782A3F5BB0CDB21}

没有添加任何其他工具或库的 1.7 版。仅提供基本的 Velocity 功能。

## 如何将现有的实体值替换为空格？例如，在促销活动结束后，需要清除某个项目的 entity.message。{#section_B88F2C2925DC4508974B2F8B13F961CB}

以 JavaScript 不间断空格的形式发送似乎可做到这一点。让开发人员发送 `\u00A0` 作为值。示例：`entity.message=\u00A0`。在没有显示值的情况下，您应当考虑将此设为默认值，而不是为 null。

## 能否在推荐设计中使用配置文件脚本？{#section_6BD55203984A4D80A0C6F241AD7806DF}

是. 但是，您必须在配置文件脚本名称中的 $ 符号前面添加一个反斜杠 (\)。
