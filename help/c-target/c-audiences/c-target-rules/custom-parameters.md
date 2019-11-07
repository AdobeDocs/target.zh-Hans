---
keywords: 自定义参数;Target 自定义参数;targetpageparams;定位 mbox 参数
description: 自定义参数为 mbox 参数。如果将任何 mbox 参数传递到 mbox，或者使用 targetPageParams 函数，则此处将显示这些参数，以供在受众中使用。
title: Adobe Target 中的自定义参数
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 自定义参数{#custom-parameters}

自定义参数为 mbox 参数。如果将任何 mbox 参数传递到 mbox，或者使用 targetPageParams 函数，则此处将显示这些参数，以供在受众中使用。

For more information, see [Pass parameters to a global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

创建基于 mbox 参数的自定义受众时，`mboxParameter` 将不再提示您输入 `mboxName`。mbox 名称现在是可选的。通过这项更改，您可以使用多个 mbox 中的参数或引用尚未记录到 Edge 的参数。

1. 在 [!DNL Target] 界面中，单击&#x200B;**[!UICONTROL 受众]** &gt; **[!UICONTROL 创建受众]**。
1. 对受众进行命名。
1. 单击&#x200B;**[!UICONTROL 添加规则]** &gt; **[!UICONTROL 自定义]**。

   要选择所需的参数，请执行以下操作：

   * 在创建新受众时，从列表中选择一个参数名称，开始键入所需参数名称的前面几个字符，或键入所需参数名称的全名。
   * 如果您记得 mbox 名称而不记得参数名称，则使用复选框筛选传递所需参数的已知 mbox。
   无论使用哪种方法，mbox 和参数之间均没有链接。受众的运行将以传递参数的所有 mbox 中的相应参数为基础。

   如果您编辑现有受众，则会显示筛选标准以及在创建期间提供的 mbox 名称。

1. 选取计算器：

   * 包含（不区分大小写）
   * 不包含（不区分大小写）
   * 等于
   ![自定义参数受众](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. 在新行中输入每个值。
1. （可选）单击&#x200B;**[!UICONTROL 添加规则]，然后为受众设置更多规则。**
1. 单击&#x200B;**[!UICONTROL 保存]**。

受众的[定义详细信息弹出卡片](../../../c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)会在“规则”部分中显示参数名称。没有对用于筛选的 mbox 的引用。

>[!NOTE]
>
>对于在 Target 18.5.1 版本（2018 年 5 月 22 日）之前创建的自定义受众，mbox 名称不会显示在受众的定义弹出卡片中。必须重新保存自定义受众才能使 mbox 名称显示在该卡片中。

## 注意事项 {#considerations}

* 针对特定 mbox 评估受众和活动。例如，如果全局 mbox 传递了某个参数，但区域 mbox 没有，则针对该参数的活动/受众将不符合区域 mbox 上的条件。
* 定位不会根据内部mbox参数（如mboxPC、mboxSession、mbox3rdPartyId、mboxCount、mboxId和mboxVersion）进行评估。

## 培训视频：创建受众

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=chi_hans)