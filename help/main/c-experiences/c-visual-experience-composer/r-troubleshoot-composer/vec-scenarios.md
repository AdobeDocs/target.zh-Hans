---
keywords: 推荐
description: 浏览一些常见方案，这些方案显示了在可视化体验编辑器(VEC)中对页面所做的更改如何影响Adobe Target显示体验的功能。
title: 哪些是常见的页面修改方案？
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# 页面修改方案 {#vec-scenarios}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解对[!DNL Target]之外的页面所做的更改如何影响[!DNL Target]显示体验的功能，具体方法为：通过七种包含示例的场景。

>[!ENDSHADEBOX]

[!DNL Target]选择器可确定体验的显示位置。 当页面在[!DNL Target]之外修改时，更改可能会影响[!DNL Target]查找该位置并显示体验的能力。

选择器始终与唯一类一起使用，此类不等同于ID。 如果没有为元素分配类，则选择器计算具有相同标记名称的前几个同级节点。

>[!NOTE]
>
>这些方案使用列表项作为示例，但概念适用于任何元素。

下表汇总了方案。 在每个方案中，选择器为`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`。

| 场景 | 已应用操作 | 原因 |
|---|---|---|
| 在选定元素之前插入具有不同类名称的元素 | 是 | `li.women-section:eq(0)`不受影响 |
| 插入与选定元素具有相同类名称的元素 | 否 | 新元素占据第一个位置，这会破坏选择器 |
| 在选定元素之后插入元素 | 是 | 新元素将添加到相对于父元素的相同位置 |
| 删除紧靠选定元素之前的元素 | 是 | 所选项目的类未更改 |
| 删除紧跟在选定元素后面的元素 | 是 | 所选项目的类未更改 |
| 删除所选的元素 | 是 | 已成功移除元素 |
| 重命名所选元素的类 | 否 | 未找到`class` |

## 在选定元素之前插入具有不同类名称的元素

在[!DNL Target]选择器中插入新元素作为该元素的同级。 如果元素上的第一个类由JavaScript添加，则投放失败并且不应用操作。

**插入的元素：**

```html
<li class="kids-section">Kids</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;选择器按预期工作，因为`li.women-section:eq(0)`不受影响。

**之前：**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**之后：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## 插入与选定元素具有相同类名称的元素

在选择列表项时插入列表。

**插入的元素：**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;选择器无法正常工作。 `ul.nav:eq(0)`现在指向动态添加的不可用的元素，因此不应用操作。 创建活动后，动态或手动添加具有相同类的类似列表项会将新元素放置在第一个位置，这会破坏选择器。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**之后（尝试）：**

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## 在选定元素之后插入元素

在选定列表项之后插入列表。

**插入的元素：**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**选定的元素：**

`<li class="women-section">Women Shoes</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;在以选定项结尾的列表之后插入列表按预期工作。 新元素将添加到与选定元素相对父元素的相同位置。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**之后：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## 删除紧靠选定元素之前的元素

删除所选元素之前的列表项。

**删除的元素：**

```html
<li class="men-section"> Men </li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;已成功删除该元素，因为未更改所选项目的类。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之后：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 删除紧跟在选定元素后面的元素

删除所选元素之后的列表项。

**删除的元素：**

```html
<li class="kids-section">Kids</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;已成功删除该元素，因为未更改选定项的类，并且删除的元素在其父子树中具有一个唯一类。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**之后：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 删除所选的元素

已删除所选的列表项。

**删除的元素：**

```html
<li class="women-section">Women</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;已成功移除该元素。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之后：**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## 重命名所选元素的类

选定列表项的类已更改。

**更改的元素：**

```html
<li class="women-section">Women</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

**选择器：** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**&#x200B;无法重命名类，因为找不到`class`。

**之前：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**之后（尝试）：**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```
