---
keywords: 浏览器选项;类型;浏览器类型;浏览器语言;语言;版本;浏览器版本
description: 了解如何在 [!DNL Adobe Target] 中创建受众，以定位访问您的页面时使用特定浏览器或特定浏览器选项的用户。
title: 我是否可以根据浏览器类型定位访客？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 33%

---

# [!UICONTROL Browser]

您可以定位使用特定浏览器或特定浏览器选项访问您的页面的用户。

可以定位以下浏览器：

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>从[!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）开始，使用Target UI创建的内置受众（如`Browser:iPad`和`Browser:iPhone`）已更新，以便使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`对[!DNL iPad]和[!DNL iPhone]执行正确的定位。
>
>客户无需对此更新执行任何操作。 [!DNL Target] UI中的标签将来将更改，在进行这些更改时，将在[[!DNL Target] 发行说明（当前版本）](/help/main/r-release-notes/release-notes.md)中公布。
>
>有关解决方法设置，请参阅以下[!UICONTROL Browser]受众属性（2024年4月30日）](#updates)中的[更新 [!DNL iPad] 和 [!DNL iPhone] 。

定位浏览器的方式有两种：

* **预先构建的受众：**&#x200B;如果您希望仅定位使用特定浏览器访问您的网站的访客，请使用预先构建的受众。例如，如果您提供[!DNL Chrome]扩展，则只针对[!DNL Chrome]用户。

   1. 设置活动时，从下拉列表中选择浏览器。

      此选项可将活动仅定位到使用指定浏览器的访客。

      ![定位Chrome用户](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **自定义浏览器受众规则：**&#x200B;自定义受众允许您定位多个浏览器，或者针对特定浏览器、浏览器版本或浏览器语言设置规则或排除项。 根据浏览器属性定位活动时，此功能可提供极大的灵活性。

   1. 在[!DNL Target]界面中，单击&#x200B;**[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**。
   1. 命名受众并添加可选描述。
   1. 将&#x200B;**[!UICONTROL Browser]**&#x200B;拖放到受众生成器中。

      ![规则>浏览器](assets/target_browser.png)

   1. 单击&#x200B;**[!UICONTROL Select]**，然后选择以下选项之一：

      * **类型：**&#x200B;定位或排除特定浏览器。请参阅[类型](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)。
      * **语言：**&#x200B;定位或排除设置为使用特定语言的特定浏览器。 请参阅[语言](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)。
      * **版本：**&#x200B;定位或排除特定浏览器版本。请参阅[版本](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)。

   1. （可选）为受众设置其他规则。
   1. 单击 **[!UICONTROL Done]**。

  以下示例显示了一个受众，其中包含版本91或92上的[!DNL Microsoft Edge]用户：

  ![定位Edge 91或92](assets/target_edge.png)

## 浏览器选项 {#concept_221D8EEF53CC45AEACEB17CF336A3658}

根据浏览器的类型、语言或版本，定位或排除活动参加者。

### 类型 {#section_6ADC758F23F145B3A310151546D83D56}

定位或排除特定浏览器。

选择&#x200B;**[!UICONTROL Type]**，然后选择等于或不等于。

* [!UICONTROL Equals]：定位所选的浏览器。
* [!UICONTROL Does not equal]：排除所选的浏览器。

选择一种或多种浏览器。多个选项之间使用 OR 进行连接。

### 语言 {#section_7520D1AA464A45A6843EABE2D2B431A1}

定位或排除设置为使用特定语言的特定浏览器。

例如，如果某个选件只有英语版，则您可以定位将语言设置为英语的浏览器。或者，如果您的页面未启用双字节，则您可以排除设置为使用东亚语言的浏览器。

在语言比位置更为重要的情况下，包含或排除浏览器语言与根据地域进行定位相比，前者可以实现更准确的访客定位。例如，如果您提供的是一篇英语文章，您既可以定位讲英语的国家/地区，也可以定位设置为英语的浏览器。不过，使用后者，您还可以将这篇文章提供给来自主要语言并不是英语的国家/地区、但却会讲英语的用户。

选择&#x200B;**[!UICONTROL Language]**，然后选择等于或不等于。

* [!UICONTROL Equals]：定位所选的浏览器语言。
* [!UICONTROL Does not equal]：排除所选的浏览器语言。

选择一种或多种浏览器语言。多个选项之间使用 OR 进行连接。

可以定位或排除以下浏览器语言：

* 英语
* 法语
* 德语
* 日语
* 韩语
* 葡萄牙语
* 俄语
* 西班牙语
* 繁体中文

### 版本 {#section_37CC8CE45DA04E8682AE6388321BA6EF}

定位或排除特定浏览器版本。

例如，如果您的页面在[!DNL Internet Explorer]版本11或更早版本中无法正确显示，您可以创建排除这些版本的受众。 在这种情况下，您将设置一个浏览器类型等于[!DNL Internet Explorer]的规则，并添加第二个版本小于或等于11的规则。

选择&#x200B;**[!UICONTROL Version]**，然后选择运算符：

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* 高于或等于
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

键入版本号。 在文本字段中只能输入主要版本。指定的版本包括该版本的任何次要版本。例如，如果您指定版本10，则还包括版本10.1上的访客。

多个选项之间使用 OR 进行连接。

## 培训视频：创建受众![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## [!UICONTROL Browser]受众属性中[!DNL iPad]和[!DNL iPhone]的更新（2024年4月30日） {#updates}

[!DNL Adobe Target]允许您[定位多个类别属性中的任意一个](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)，包括访问您的页面时使用特定浏览器或浏览器选项的用户。

从[!DNL Target] Standard/Premium 24.3.1（2024年3月4日至6日）开始，使用Target UI创建的内置受众（如`Browser:iPad`和`Browser:iPhone`）已更新，以便使用`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`和`profile.mobile.isTablet`对[!DNL iPad]和[!DNL iPhone]执行正确的定位。

使用[!DNL Target] UI创建的内置受众（例如`Browser:iPad`和`Browser:iPhone`）将自动移至新的受众定义，无需客户执行任何操作。 但是，以后，您应该使用下面描述的设置[](#ui)。

如果您在任何配置文件脚本中使用`user.browserType`来检查它是[!DNL iPhone]还是[!DNL iPad]（例如，`user.browserType == 'iphone'`或`user.browserType != 'ipad'`），则在2024年4月30日之前，应按照](#profile-scripts)下的说明更改这些配置文件脚本[，以确保这些受众继续按预期运行。

JavaScript受众是使用[!DNL Target]表达式的旧版受众，已在[!DNL Target Classic] UI中弃用。 这些受众只能通过API进行修改。 只有在活动中继续使用旧受众时，客户才必须更新这些受众。

### 使用[!DNL Target] UI创建的受众 {#ui}

以后可以使用以下设置：

* **对于浏览器匹配[!DNL Apple]**： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **对于与平板电脑**&#x200B;匹配的浏览器： [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![移动设备为平板电脑](/help/main/r-release-notes/assets/is-tablet.png)

* **对于与iPad**&#x200B;匹配的浏览器： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad]，其包含的And容器为[!UICONTROL Mobile] > [!UICONTROL Is Tablet]为[!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **对于与iPhone**&#x200B;匹配的浏览器： [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone]，其包含的And容器为[!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone]为[!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

还可以使用许多其他可能的设置，例如，当条件被否定时。 否定条件的示例可能如下所示：

* **对于浏览器与iPhone**&#x200B;不匹配： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple]，其中的Or容器为[!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone]为[!UICONTROL false]

  ![不是手机](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **对于浏览器与iPad**&#x200B;不匹配： [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple]，其中的Or容器为[!UICONTROL Mobile] > [!UICONTROL Is Tablet]，是[!UICONTROL false]。

  ![不是平板电脑](/help/main/r-release-notes/assets/tablet-false.png)

### 使用个人资料脚本创建的受众 {#profile-scripts}

如果您在旧版[!DNL Target Classic]受众或配置文件脚本中使用`user.browserType`，则更改应包括以下内容：

* **BrowserType是iPhone**：

  替换：

  `user.browserType=="iphone"`

  替换为：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType不是iPhone**：

  替换：

  `user.browserType!="iphone"`

  替换为：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType是iPad**：

  替换：

  `user.browserType=="ipad"`

  替换为：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType不是iPad**：

  替换：

  `user.browserType!="ipad"`

  替换为：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`