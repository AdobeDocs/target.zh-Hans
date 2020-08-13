---
keywords: Profile script;profile script attributes;mutually exclusive activities
description: 您可以使用配置文件属性来设置比较两个或更多活动的测试，但是不允许同一访客参加所有活动。
title: 使用用户档案脚本测试互斥的活动
feature: visitor profiles
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 81%

---


# Use profile scripts to test mutually exclusive activities {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

您可以使用配置文件属性来设置比较两个或更多活动的测试，但是不允许同一访客参加所有活动。

测试互斥活动可防止一个活动中的访客影响其他活动的测试结果。当访客参加多个活动时，很难确定访客在一个活动中的体验产生的是正提升度还是负提升度，或者多个活动之间的交互是否影响了一个或多个活动的结果。

例如，您可以测试电子商务系统的两个区域：您可能希望测试“添加到购物车”按钮是红色而非蓝色。 另外还测试从五个步骤减少到两个的新的结账流程。如果两个活动具有相同的成功事件（完成的购买），则很难确定红色按钮是否提高了转化率，或者由于改进了结帐流程，这些相同的转化率是否也提高了。 通过将测试分为互斥活动，您可以独立测试每个更改。

使用下面的任一配置文件脚本时，请注意以下信息：

* 配置文件脚本必须在活动启动之前运行，且该脚本必须在活动持续时间段内保持不变。
* 此技术可减少活动中的流量，这可能要求活动运行更长。 您在估算活动的持续时间时必须考虑到这一事实。

## 设置两个活动

要将访客分到可查看不同活动的各个组中，您必须创建一个配置文件属性。配置文件属性能够将一个访客分类到两个或多个群组的某一组中。创建下面的脚本可设置名为“twogroups”的配置文件属性：

```
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` 确定 *twogroups* 配置文件属性是否针对当前访客设定。如果是，则无需进行下一步操作。

* `var ran_number=Math.floor(Math.random() *99)` 声明了一个名为 ran_number 的新变量，将其值设置为介于 0 和 1 之间的随机小数，然后乘以 99 并进行四舍五入以创建 100 (0-99) 以内的范围，这用于指定查看活动的访客百分比。

* `if (ran_number <= 49)` 开始一个例程，确定访客属于哪一群组。如果返回 0-49，则将访客分配到 GroupA。如果返回 50-99，则分配到 GroupB。组决定了访客可查看的活动。

After you create the profile attribute, set up the first activity to target the desired population by requiring that the user profile parameter `user.twogroups` matches the value specified for GroupA.

>[!NOTE]
>
>请尽早在页面上选择一个 mbox。此代码确定访客是否体验活动。 只要浏览器第一次遇到 mbox，就能利用该 mbox 设置此值。

设置第二个营销活动，使用户配置文件参数 `user.twogroups` 匹配 GroupB 指定的值。

## 设置三个或更多活动

设置三个或更多互斥活动的方式与设置两个活动类似，只不过您必须更改配置文件属性 JavaScript 来为每个活动创建单独的组并确定可查看每个活动的对象。随机数生成是不同的，取决于您创建了偶数个组还是奇数个组。

例如，要创建四个组，请使用下面的 JavaScript：

```
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

在此例中，用于创建随机数的数学方法与创建两个组的方法相同，该随机数用于将访客分配到某个组。随机小数生成之后，向下取整创建一个整数。

如果创建了奇数个组或者群组数量无法被 100 整除，则不应将小数向下取整。不取小数的整数就会指定一个非整数范围。要实现此操作，请将以下行：

`var ran_number=Math.floor(Math.random()*99);`

更改为：

`var ran_number=Math.random()*99;`

例如，若要将访客划分到三个相等的群组时，可使用如下代码：

```
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
