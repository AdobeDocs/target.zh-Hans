---
keywords: 点击跟踪;跟踪点击次数;点击次数;AppMeasurement
description: 了解如何 [!DNL Adobe Target] 用于将任何元素的点击作为成功量度进行跟踪。
title: 点击跟踪是什么？
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 67%

---

# 点击跟踪

[!DNL Adobe Target] 用于将任何元素的点击作为成功量度进行跟踪。

>[!NOTE]
>
>全局上不支持跟踪点击 [!DNL Target] 请求（当它在基于表单的活动中用作位置时）。

## 设置点击跟踪 {#section_5540C5A533114E57BAE022A600B02E72}

1. 在“[!UICONTROL 目标和设置]”页面上为活动设置目标时，选择&#x200B;**[!UICONTROL 转化]**&#x200B;成功量度。
1. 在此步操作中，选择&#x200B;**[!UICONTROL 已单击元素]**，然后单击&#x200B;**[!UICONTROL 选择元素]**。

   随即会在[!UICONTROL 可视化体验编辑器] (VEC) 中打开您的页面。

1. 选择要跟踪的任何元素。

   有关选择元素的提示，请参阅下面的&#x200B;*注意事项*&#x200B;部分。

1. 单击 **[!UICONTROL 保存]** 以保存您的选择。

当活动参加者点击某个选定元素时，该点击即会被计为一次转化。

## “选定的元素”面板 {#selected-elements}

对象 [!UICONTROL A/B测试]， [!UICONTROL 体验定位] (XT)， [!UICONTROL Automated Personalization] (AP)，和 [!UICONTROL 多变量测试] (MVT)活动， [!UICONTROL 选定的元素] 面板在右侧列出了为点击跟踪选择的元素。

![“选定的元素”面板](/help/main/c-activities/r-success-metrics/assets/selected-elements.png)

将鼠标悬停在 [!UICONTROL 选定的元素] 面板。 下表介绍了可对元素执行的各项操作：

| 操作 | 描述 |
| --- | --- |
| 信息 | 显示元素类型和选择器的完整 DOM 路径。 |
| 编辑 | 允许您编辑 CSS 选择器。 |
| 删除 | 删除元素。 |

### 添加元素

如果您已经知道选择器的DOM路径，则可以通过单击面板顶部的加号图标手动添加该路径。

![“添加元素”图标](/help/main/c-activities/r-success-metrics/assets/add-element.png)

### “选定的元素”弹出窗口

为点击跟踪选择多个元素后，您可以单击活动的“[!UICONTROL 目标和设置]”步骤中的“[!UICONTROL 选定的元素]”链接，以查看为点击跟踪选定的元素的完整列表。该列表包含元素的完整 DOM 路径，可帮助您验证选定的元素是否将用于点击跟踪。

![“选定的元素”链接](/help/main/c-activities/r-success-metrics/assets/elements-selected-link.png)

## 注意事项 {#considerations}

选择元素时，需注意以下几个事项：

* 设置点击跟踪时，可使用 DOM 路径功能。单击页面上的某个元素时，将显示 VEC 选项菜单。另外，相应的 DOM 路径将显示在页面底部。您可以使用 DOM 路径快速查看有关所选元素（类型、ID 和类）的信息，并向上或向下移动 DOM 路径以选择所需的元素。

   ![DOM 路径插图](/help/main/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   与在活动创建工作流的步骤1中创建体验类似，您可以通过页面底部的DOM路径选择器来选择元素。 在从 DOM 路径中选择元素时，VEC 中的相应元素将显示为“已选定”。要取消选择选定的元素，您可以再次单击DOM路径选择器中的元素，或单击VEC中的“选定”框。

   有关更多信息，请参阅&#x200B;*可视化体验编辑器选项*&#x200B;中的[使用 DOM 路径浏览元素](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)。

* 您可以浏览到其他页面，以跟踪您可能不会更改内容的页面上的点击次数。但前提是该页面必须包含在使用 [多页功能](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) 和 [!DNL at.js] 必须在其上实施。
* 如果您选择了多个元素，则当参加者点击任一选定元素时，即会被计为一次点击。要单独对每个项目进行计数，需为每个元素分别设置成功量度。要通过单击页面上的多个元素而计算一项，请编辑CSS元素选择器以匹配多个元素。
* 务必选择要跟踪的元素的级别。例如，指定按钮时，请务必选择链接，而不要选择按钮文本。
* 点击事件会在发生点击的同一页面上发送到 [!DNL Target]。
* 如果点击跟踪指标是的目标指标， [!UICONTROL 目标分析] (A4T)活动，访客必须在页面加载后60秒内单击此元素，才能跟踪指标。
* 如果元素的选择器中包含转义字符（包括以下字符），则无法对这些元素执行点击跟踪：

   | 字符 | 描述 |
   |---|---|
   | # | 数字符号或井号 |
   | : | 冒号 |
   | . | 句点 |
   | $ | 美元符号 |
   | `[ ]` | 方括号 |

* 如果您同时使用 [!DNL at.js][!DNL Analytics] 点击跟踪和 AppMeasurement，则 [!DNL at.js] 点击跟踪会取消所有其他点击事件处理程序。因此，AppMeasurement 点击处理程序将从不会执行。

   当基础元素为 [!DNL at.js]（链接）标记或 `A` 标记时，`FORM` 具有特殊的点击跟踪处理方式。

   将点击跟踪事件附加到 [!DNL at.js]（链接）标记或 `A` 标记后，`FORM` 会执行以下步骤：

   1. 调用 `event.preventDefault()`。

   1. Fire [!DNL Target] 请求。

   1. 日期 [!DNL Target] 请求成功或错误回调，执行默认行为：

      * `A`（链接）标记：默认行为是导航到由 HREF 属性定义的 URL。
      * `FORM` 标记：默认行为是提交表单。

   此默认行为可能会妨碍 [!DNL Analytics] 点击跟踪。 如果您使用 [!DNL Analytics]，您应该依靠 [!DNL Analytics] 的点击跟踪，而不是 [!DNL Target].

* 如果页面和活动 URL 属于不同的属性，则不会在该页面上记录点击跟踪。企业用户权限是 [!DNL Target Premium] 功能。 有关更多信息，请参阅[企业用户权限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

* 点击跟踪量度未关联活动中的任何特定体验。

* 如果有必要限制点击跟踪量度的范围，则使用受众。

* 多个活动可以为同一个选择器定义一个点击跟踪量度。如果是这样，当访客符合这些活动中的某个活动的资格并单击该选择器时，访客符合资格的所有相关活动的点击跟踪量度都会增加。

## 培训视频 {#section_36607204DAE146E3B8E2C609D244EDB1}

以下视频包含有关创建点击跟踪成功量度的信息。

* 了解“目标”量度
* 了解和构建 [!UICONTROL 转化]， [!UICONTROL 收入]、和 [!UICONTROL 参与] 量度
* 构建点击跟踪量度

>[!VIDEO](https://video.tv.adobe.com/v/17380)
