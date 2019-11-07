---
description: Target 如何从您的页面发出调用以及如何响应从您的页面发出的调用，取决于您使用的 Target 库的版本、Experience Cloud 访客 ID 实施是否存在以及访客 ID 是否存在。
title: 按 mbox.js 库版本确定的 Target 页面方法
uuid: 66f7753e-d9c1-4efa-8b10-fd637c8f53f6
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 按 mbox.js 库版本确定的 Target 页面方法{#target-page-methods-by-mbox-js-library-version}

Target 如何从您的页面发出调用以及如何响应从您的页面发出的调用，取决于您使用的 Target 库的版本、Experience Cloud 访客 ID 实施是否存在以及访客 ID 是否存在。

>[!NOTE]
>
>如果您使用 [!DNL at.js]，则所有调用均会使用 JSON 来执行。本页提供了有关 [!DNL mbox.js] 库版本的详细信息。下面各种情景中描述的行为不适用于 [!DNL at.js]。

本节提供了有关每个版本的 [!DNL Target] 库在以下各种情景中如何响应来自页面的 [!DNL Target] 调用的信息。

有多种类型或端点，具体取决于您的实施和库版本。您应该熟悉每个类型，以了解在各种情景中 [!DNL Target] 如何对调用做出响应。

| 类型/端点 | 调用方法 | 响应内容 |
|--- |--- |--- |
| 自动创建全局 mbox - 同步 | 使用 document.write 进行调用 | 无 document.write() 的 JavaScript |
| 自动创建全局 mbox - 异步 | createElement() 将调用附加到主体 | 无 document.write() 的 JavaScript |
| 标准 | 使用 document.write 进行调用 | 包含 document.write() 的 JavaScript |
| ajax | createElement() 将调用附加到主体 | 无 document.write() 的 JavaScript |
| json | 使用 XMLHTTPrequest() 执行调用 | 返回 JSON 响应 |

>[!IMPORTANT]
>
>对于除标准以外的任何类型，编写的所有自定义代码和选件都应支持 ajax 环境。例如，如果您使用包含 `document.write()` 的 JavaScript，则脚本将不会按预期运行。

## 无访客 ID 实施 {#section_C6F7213FDE4D48E8BBCB1A9A26310FEE}

如果您通过 [!DNL Target Standard] 使用 [!DNL Premium] 或 [!DNL mbox.js]，并且已为帐户启用“[!UICONTROL 创建全局 Mbox]”，则无论使用的是哪个 **版本，都会执行**&#x200B;自动创建全局 mbox - 同步[!DNL mbox.js]类型的调用和响应。

如果您不使用[!UICONTROL 可视化体验编辑器]操作，而是自行编写自定义代码，请确保您的代码适用于 ajax 环境。例如，如果您使用包含 `document.write()` 的 JavaScript，则脚本将不会按预期运行。

>[!NOTE]
>
>具有相同名称但是不同参数的多个 ajax mbox 调用无法在同一个页面上运行。只有第一个调用可以运行。

如果您的页面上使用“自动创建全局 mbox”，但也存在 `mboxCreate` 调用（例如，假设您在以前用于旧版实施中的某个页面上实施 [!DNL Target Standard] 或 [!DNL Premium]），则会使用**自动创建全局 mbox - 标准**端点执行全局 mbox 调用，使用&#x200B;**标准**&#x200B;端点执行 `mboxCreate` 调用。**标准**&#x200B;端点使用 `document.write()` 执行调用和做出响应。在下载完所有信息之前，这会阻止页面加载，包括在 ajax 响应中交付的内容。

如果您仅使用 mboxCreate（例如在使用 [!DNL Target Classic] 创建的页面上），则页面会正常运行。

| 创建方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| 自动创建全局 mbox | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 同步 |
| mboxCreate | 标准 | 标准 | 标准 | 标准 |

## 有访客 ID 实施，但未设置访客 ID {#section_29888A119C7A4753AD287FC845AA63F4}

如果未设置访客 ID，则用户不会有 [!DNL Experience Cloud] 访客 Cookie。页面会从外部调用访客 ID 服务以获取访客 ID。 会等待包含 ID 的响应，以便调用 [!DNL Target]Target。

>[!NOTE]
>
>强烈建议使用 [!DNL Mbox.js] 版本 58，以确保访客 ID 在执行 Target 调用之前返回。

如果在此情景中您使用的是 [!DNL mbox.js] 版本 57，一切都会像没有访客 ID 实施的情况那样运行，正如前一个情景中所述。自 [!DNL mbox.js] 版本 58 开始，[!DNL Experience Cloud Visitor ID] 服务会在调用 [!DNL Target] 之前返回访客 ID。这可以确保在访客会话中首次调用 [!DNL Target] 时可以使用通过 Profiles &amp; Audiences 核心服务共享的受众数据。为避免默认内容在测试内容返回之前闪烁，在访客 ID 服务返回之前，[!DNL Target] 会隐藏 `<BODY>`。在版本 58 中，使用 `display:none` 来隐藏页面。在响应式网站中，这会造成某些问题，因此自版本 59 开始，便使用 `opacity:0` 来隐藏内容。

| 创建方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| 自动创建全局 mbox | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 异步 | 自动创建全局 mbox - 异步 | 自动创建全局 mbox - 异步 |
| mboxCreate | 标准 | ajax | ajax | ajax |

## 有访客 ID 实施，且存在访客 ID {#section_9CD4AE4C8186425D886398BC3CE6C46D}

如果存在访客 ID Cookie，则 [!DNL Target] 不需要调用访客 ID 服务。在这种情况下，显示内容之前不需要等待访客 ID 服务。对于版本 57 到 59，会使用&#x200B;**自动创建全局 mbox - 同步**&#x200B;类型，因此页面会等待 [!DNL Target] 调用返回后再继续加载。这样可确保默认内容不会出现闪烁情况。对于版本 60，会使用&#x200B;**全局 mbox - 异步**&#x200B;类型，以确保 [!DNL Target] 等待 [!DNL Experience Cloud] 选择退出服务做出响应。该选择退出服务属于 2016 年秋季发布的“数据协作”功能的一部分。由于所有调用均使用 ajax 返回，因此对于 `document.write()` 版本 60，不应使用 [!DNL mbox.js]。

| 创建方法 | mbox.js v57 | mbox.js v58 | mbox.js v59 | mbox.js v60 |
|---|---|---|---|---|
| 自动创建全局 mbox | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 同步 | 自动创建全局 mbox - 异步（为将于 2016 年下半年发布的“数据协作”功能的开发提供支持） |
| mboxCreate | 标准 | 标准 | 标准 | ajax |