---
keywords: 移动设备应用程序;移动设备应用程序发送数据;定位移动设备应用程序;移动设备自定义用户数据;移动设备应用程序自定义数据
description: 您可以将有关位置或用户的其他信息以名称-值对的形式发送给 Target。
title: iOS - 发送自定义用户数据
topic: Target
uuid: 00baa1e2-4d1c-4835-ac55-47c9ac8985ac
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# iOS - 发送自定义用户数据{#ios-send-custom-user-data}

您可以将有关位置或用户的其他信息以名称-值对的形式发送给 Target。

此信息可用于在报表中构建自定义受众（例如，距离超过 25000 英里的用户）。

通过 Target 调用可以发送以下两种类型的参数：

* mbox 参数

   mbox 参数不可跨会话持久保留。
* 配置文件参数

   配置文件参数存储在访客配置文件存储区，且可跨会话持久保留。mbox 参数则不可持久保留。虽然保留了一些键，但是配置文件参数和 mbox 参数都可以是自定义键值对。

虽然存在一些保留键，但是配置文件参数和 mbox 参数都可以包含自定义键值对。

1. 创建字典。

   首先，使用您发送的要传递到 Target 的值创建一个字典。为方便起见，请将此字典添加到 `welcomeMessageCampaign` 方法中，这样便无需担心范围问题。

   以下是一个示例字典。您可以将此字典复制并粘贴到 `(void)welcomeMessageCampaign` 中。在此示例中，对 `userLevel` 和 `userMiles` 等键的值进行了硬编码。一般情况下，您需要传入对应的变量。

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * 前缀为“profile”的键（例如 `profile.persona`）存储在用户的配置文件中。

      这些配置文件属性可以在不同的活动和渠道中使用。

   * 没有任何前缀的键（例如 `userMiles`）为 mbox 参数。

      这些参数只能在会话期间使用。

   * 前缀为“entity”的键（例如 `entity.category.id`）用于产品推荐。

1. 验证数据。
   1. 在应用程序 `didFinishLaunchingWithOptions` 中，取消注释或添加 `[ADBMobile setDebugLogging:YES];`。

      这会打印详细的调试日志。
   1. 构建应用程序。
   1. 确认已将参数传入 Target 调用。

      在调试控制台中搜索您的 Target 位置名称。您将会看到对 `YOUR-CLIENT-CODE.tt.omtrdc.net` 的调用，其中包含您刚刚传递的所有参数。

      ![](assets/mobile-debug.png)
   您可以在 Target Standard 中使用这些参数构建受众，并限制或定位内容显示。
