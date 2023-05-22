---
keywords: 发行说明;版本;更新;未来版本;增强;新功能;修复;更新;预发行
description: 了解即将发布的 [!DNL Adobe Target]版本中包括的新功能、增强功能和修复，包括 SDK、API 和 JavaScript 库。
title: 即将发布的 [!DNL Target] 版本中包括哪些新增功能和增强功能？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2f553151e480d48178389132a0a97fa7de4e04c5
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 54%

---

# [!DNL Target] 发行说明（预发行版本）

本文包含即将发布的 [!DNL Adobe Target] 版本的预发行信息，包括 SDK、API 和 JavaScript 库。

**上次更新日期：2023 年 5 月 22 日**

>[!NOTE]
>
>发布日期、功能及其他信息如有更改，恕不另行通知。
>
>要查看有关当前版本的信息，请参阅 [Target 发行说明](release-notes.md)。根据发布时机的不同，这些页面上的信息可能相同。括号中的问题编号供 [!DNL Adobe] 内部使用。

## [!DNL Target] Standard/Premium 23.5.1（2023 年 5 月 23-25 日）

将按以下交错的时间表发布此版本：

5月23日：歐洲、中東和非洲(EMEA)區域5月24日：亞太(APAC)區域5月25日：美洲區域

此版本包含以下新功能、增强和修复：

| 功能 | 详细信息 |
|--- |--- |
| 与 [!DNL Target] 共享的 Real-Time CDP 配置文件属性 | Real-Time CDP 配置文件属性可以共享给 [!DNL Target]，用于 HTML 选件和 JSON 选件。<P>有关更多信息，请参阅 [与  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) 共享 Real-Time CDP 配置文件属性。 |

* 已修正導致某些客戶無法使用「大於」或「小於」運運算元，以訪客設定檔建立對象的問題。 (TGT-45271)

## [!DNL Target] Standard/Premium 23.5.2（2023 年 5 月 31 日）

此版本包含以下增强功能和修复：

* 修正產生設定檔API授權權杖時導致顯示空白頁面的問題。 (TGT-45387)
* 修正影像無法在「 」中顯示的問題。 [!UICONTROL 建立設計] 面板(如果影像名稱包含GB 18030字元)。 (TGT-44614)
* 修正導致下列專案產生報表的問題： [!UICONTROL 自動個人化] 分析期間凍結的活動。 (TGT-44820)
* 已修正導致某些客戶的預設工作區的Target UI中未顯示任何活動的問題。 (TGT-45286)
* 更新「不允許重複專案」標幟的行為。 排除的重複選件旗標已更新，如果重複選件是預設內容選件（適用於API v3、v4），則允許重複選件；如果選項參考預設內容選件且未定義範本，則允許重複選項。 (TNT-46617)
* 修正在URL中新增查詢引數，導致頁面無法在視覺化體驗撰寫器(VEC)中載入的問題。 (TGT-44873)
* 修正體驗中文字/HTML部分字元錯誤逸出的問題。 (TGT-44600)

## [!DNL Target] Standard/Premium 23.5.3 （日期待定）

此版本包含以下增强功能：

| 功能 | 详细信息 |
|--- |--- |
| [!UICONTROL QA模式] 的 [!UICONTROL Automated Personalization] 活動 | [!DNL Adobe Target] [!UICONTROL QA模式] 現在已適用於 [!UICONTROL Automated Personalization] 活動，取代 [!UICONTROL 預覽連結] 功能。<P>有关更多信息，请参阅[活动 QA](/help/main/c-activities/c-activity-qa/activity-qa.md)。。 |

* 效能增強功能，不允許重複資料功能（包括減少載入時間），同時 [管理排除專案](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) 在 [!UICONTROL Automated Personalization] 活動。

## 其他发行说明和版本详细信息

| 资源 | 详细信息 |
|--- |--- |
| [发行说明：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=zh-Hans) | 有关 Platform Web SDK 各个版本中的更改的详细信息。 |
| [at.js 版本详细信息](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | 有关 [!DNL Adobe Target] at.js JavaScript 库每个版本中的更改的详细信息。 |

## 预发行信息 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

要提前收到关于 [!DNL Target] 和其他 [!DNL Adobe Experience Cloud] 解决方案即将发行产品改良的通知，请注册 [!DNL Adobe Priority Product Update]：

[https://www.adobe.com/cn/subscription/priority-product-update.html](https://www.adobe.com/cn/subscription/priority-product-update.html)
