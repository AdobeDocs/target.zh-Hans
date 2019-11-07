---
keywords: 移动设备应用程序 VEC;移动设备可视化体验编辑器;移动设备体验编辑器选项;移动设备体验选项;定位视图;点击量;点击跟踪;跟踪
description: 移动设备可视化体验编辑器 (VEC) 支持为 Adobe Target 活动设置点击跟踪目标。
title: 在移动设备应用程序 VEC 中设置点击跟踪
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 在移动设备应用程序 VEC 中设置点击跟踪 {#set-up-click-tracking-in-the-mobile-vec}

移动设备应用程序 VEC 支持为 [!DNL Target] 活动设置点击跟踪目标。

1. 在“目标和设置”页面上为活动设置目标时，选择[!UICONTROL 转化]成功量度。

   ![](assets/mobile-vec-clicktrack1.png)

1. 在此步操作中，选择&#x200B;**[!UICONTROL 已单击元素]**，然后单击&#x200B;**[!UICONTROL 选择元素]**。

   您的移动设备应用程序将在移动设备可视化体验编辑器 (VEC) 中打开。

   ![](assets/mobile-vec-clicktrack2.png)

1. 选择要跟踪的任何元素。

   有关选择元素的提示，请参阅下面的[!UICONTROL 注意事项]部分。

   ![](assets/mobile-vec-clicktrack3.png)

1. 单击屏幕顶部的复选标记，以保存您所做的选择。

如果需要重新开始，您还可以编辑并更改点击选定内容或删除这些选定内容。

![](assets/mobile-vec-clicktrack4.png)

当活动参加者点击某个选定元素时，该点击即会被计为一次转化。

## 注意事项 {#considerations}

选择元素时，需注意以下几个事项：

* 选择多个元素后，如果访客点击其中任一元素，则会对此次点击进行计数。要单独对每次点击进行计数，需为每个元素分别设置成功量度。
* 用户点击元素后，点击事件会立即发送到 Target。
* 在移动设备应用程序 VEC 中，只允许选择附加了点击处理程序的那些元素。
* 您可以浏览应用程序的任何部分，但请确保为您选择点击跟踪元素的部分定义了[视图](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views)。
* 在编辑活动时，如果已在步骤 1 中选择设备，则无需再次选择设备。但是，如果您直接登陆点击跟踪页面，则将显示设备选择屏幕以选择授权设备。
* 移动设备应用程序 VEC 中将显示一个“修改”面板，该面板可显示您为点击跟踪设置的各个元素。

   ![显示点击跟踪的修改面板
   ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/assets/click-track-modifications-panel.png)