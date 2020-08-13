---
keywords: Recommendations
description: 本主题中的方案显示了对页面所做的更改如何影响 Target 显示体验的功能。
title: 页面修改方案
feature: vec
uuid: bb868f55-7e77-49c4-81b5-3aff5b63b827
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 100%

---


# 页面修改方案 {#page-modification-scenarios}

本主题中的方案显示了对页面所做的更改如何影响 Target 显示体验的功能。

Target 选择器可决定要在何处显示体验。如果页面在 Target 之外进行修改，则所做的更改可能会影响 Target 显示体验的功能。

使用选择器时，唯一类并不等同于 ID。选择器始终要与唯一类结合使用。如果未将任何类分配到元素，则选择器会计算之前具有相同标记名称的同级元素的数量。

>[!NOTE]
>
>虽然以下方案使用列表项目作为示例，但所述的概念适用于任何元素。

## 方案：在选定元素之前插入一个具有不同类名称的元素 {#section_298F661F72384F6AB957D5885A99D822}

在此示例中，新元素将作为选定元素的同级元素插入到 Target 选择器中。

该元素上显示的第一个类可能是由 JavaScript 添加的。如果是这样，交付将失败，并且操作也无法应用。

**插入的元素：**

```
<li class="kids-section">Kids</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

由于 `li.women-section:eq(0)` 未受到影响，因此选择器可以按预期工作。

之前：

```
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

之后:

```
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## 方案：插入一个与选定元素具有相同类名称的元素 {#section_0969B88C2F154E648D9969C8C85EF55A}

在此方案中，选定的元素是列表中的一个项目，同时将尝试插入一个列表。

**插入的元素：**

```
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**选定的元素**

`<li class="women-section">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

选择器无法正常工作，因为 `ul.nav:eq(0)` 提供了一个动态添加的元素。此元素将不可用，并且操作也无法应用。创建活动后，如果动态或手动添加具有相同类的相似列表项目，则会在第一个位置上创建一个新元素。这会破坏选择器。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

之后（尝试）：

```
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

## 方案：在选定元素之后插入一个元素 {#section_15B07B84BEE94ED39D85BBBE0733E170}

在此方案中，将在选定元素之后插入一个列表项目。

**插入的元素：**

```
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**选定的元素：**

`<li class="women-section">Women Shoes</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

在此例中，在以选定列表项目作为最后一项的列表之后插入一个列表后，可按预期工作。新元素所添加到的位置与选定元素相对于父元素的位置相同。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

之后:

```
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## 方案：删除紧靠某个元素之前的元素 {#section_F193674F04F84AA593EAA1137C880EBA}

在此方案中，将删除选定元素之前的列表项目。

**删除的元素：**

```
<li class="men-section"> Men </li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

成功删除了元素，因为选定项目的类未更改。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

之后:

```
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 方案：删除紧靠某个元素之后的元素 {#section_F83B51BE54924FB58679D512DAF1EBB2}

在此方案中，将删除选定元素之后的列表项目。

**删除的元素：**

```
<li class="kids-section">Kids</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

成功删除了元素，因为选定项目的类未更改。删除的元素在其父级子树中包含一个唯一类。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

之后:

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## 方案：删除选定的元素 {#section_1989CF1E2C344CC5963084ED83C18F9C}

在此方案中，将删除选定的列表项目。

**删除的元素：**

```
<li class="women-shoes">Women</li>
```

**选定的元素：**

`<li class="women-shoes">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

成功删除了元素。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

之后

```
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## 方案：重命名选定元素的类 {#section_79D244C588BA452DB8E433D82B7F63EA}

在此方案中，选定列表项目的类将发生更改。

**更改的元素：**

```
<li class="women-section">Women</li>
```

**选定的元素：**

`<li class="women-section">Women</li>`

选择器：`#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**结果：**

无法重命名元素类，因为未找到 `class`。

之前：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

之后（尝试）：

```
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
