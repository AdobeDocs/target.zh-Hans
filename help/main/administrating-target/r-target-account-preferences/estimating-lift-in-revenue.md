---
keywords: 收入提升;收入;预计收入提升;计算提升;预计值
description: 如果趋势在测试期间继续显示，则估计在每位访客都看到入选体验时可能实现的提升。
title: 我预计的收入提升是什么？
feature: Administration & Configuration
role: Admin
exl-id: a3c5e20e-f5d5-4b6f-b169-59d5916584ab
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 88%

---

# 预计收入提升

使用 [!DNL Adobe Target] 要估计在所有用户都查看成功体验时将获得的收入提升。

>[!NOTE]
>
>预计提升度不适用于 [!UICONTROL 体验定位] (XT)活动。

默认情况下，预计提升功能处于关闭状态。您可以在帐户首选项中启用此功能。只有 Experience Cloud 管理员用户可以启用或禁用此功能。如果禁用预计提升，则界面中不会显示相应的字段。禁用此功能不会导致数据丢失，包括用于估算的数据。无论是否启用了此功能，都会根据所收集的数据进行估算。

>[!IMPORTANT]
>
>预计提升只是一个估计值。其准确性取决于众多因素，包括在保持当前趋势的前提下估计出来的值。这些值是在过去性能的基础上估计的，不应该用于提供金融指导。将来的结果可能会有所不同。

此预计提升计算的是在活动生命周期内由入选体验和所有访客带来的收入提升量，可显示您在以下前提下可能会实现的提升：每位访客均查看入选体验，且保持测试过程中的访客趋势。

预计收入提升是根据从主要目标量度中获取的每次访问带来的收入 (RPV) 计算出来的。

预计提升的计算公式为：（&lt;入选体验 RPV> - &lt;控制体验 RPV>)*&lt;活动中的访客总数>

最多可以将得出的数值四舍五入到一位小数，但前提是四舍五入后小数点前面只有一位数字。例如：$1.6M、$60K、$900、$8.5K、$205K

例如，如果您的入选体验显示的提升为 $0.59，而控制体验显示的提升为 $0.15，则计算出的每位访客的预计提升将为 $0.44。如果您有 75,000 位访客，则得出的收入提升将为 $33,000，但前提是所有访客都查看入选体验，且可以保持当前趋势。

同样，如果您的入选体验显示的提升比控制体验高出 $0.17，且您在测试周期内的访客数为 192,000 位，那么如果可以保持当前趋势，则预计收入提升将为 $32,640。

在以下情况下，“预计收入提升”字段会显示为“---”：

* 访客不足，无法计算出合理的预计值
* 量度设置页面上未提供量度的预计值
* 最佳性能体验为控制体验

设置活动目标时，“预计值”字段会为目标提供一个值。通过此值，Target 可以计算出预计收入提升。此字段为可选字段；但是，如果没有该字段，便无法计算所有非收入量度的增量收入。数据类型为货币。当用户的操作满足您设置的目标后，该字段会逐渐显示积累的值。

在所有访客都查看入选体验的前提下计算出的预计收入将显示在 Target 报表顶部。