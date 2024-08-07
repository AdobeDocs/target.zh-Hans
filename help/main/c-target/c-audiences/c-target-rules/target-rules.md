---
keywords: 定位;定位类别;定位条件;Audience Manager;自定义配置文件参数;访客配置文件;自定义用户参数;定位规则
description: 了解如何使用类别（如浏览器、地域、网络、操作系统、访客配置文件）来定位内容。
title: 受众的类别是什么？
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 47%

---

# 受众类别

您可以使用[!DNL Adobe Target]定位多个类别属性中的任意一个。 要为每个属性创建定位规则（或组），请将所需属性拖放到受众生成器窗格中。

![受众的属性](/help/main/c-target/c-audiences/assets/attributes.png)

当选定某个特定类别时，您可以应用一个或多个定位条件。例如，在“地域”类别中定义一个规则，如 City=San Francisco。添加多个值，创建一个“或”条件。访客只需匹配其中一个值，即可满足定位条件。对于同一参数中的“与”条件，请创建自定义的定位表达式。

创建规则后，单击&#x200B;**[!UICONTROL Done]**。 规则的概要会显示在您正在定位的级别的定位链接旁边。

您可以通过添加更多条件或在其他类别中创建更多规则，来进一步优化规则。例如，您只能定位从Google访问您网站的旧金山Firefox用户。 设置[!UICONTROL Geo]类别以定位来自旧金山的用户，设置[!UICONTROL Browser]类别以定位使用Firefox的用户，设置[!UICONTROL Traffic Sources]类别以定位来自[!UICONTROL From Google]的用户。 跨类别创建的规则将与AND运算符相结合。

要创建包含跨类别的OR操作的复杂定位规则，请创建表达式目标。

您还可以定位自定义配置文件参数和 `user.` 参数。添加受众时，拖放&#x200B;**[!UICONTROL Visitor Profile]**，然后选择要用于定位活动的参数。 如果未显示所需的参数，则该参数未由mbox触发。

使用搜索框搜索您的[!UICONTROL Audiences]列表。 您可以搜索受众名称的任意部分，或将特定字符串用引号引住。

您可以按受众名称或上次修改日期对[!UICONTROL Audience]列表进行排序。 要按名称或上次修改日期进行排序，请单击列标头，然后选择受众显示的顺序（升序或降序）。

## 培训视频：创建受众![教程徽章](/help/main/assets/tutorial.png)

以下视频包含有关使用受众类别的信息。

* 创建受众
* 定义受众类别

>[!VIDEO](https://video.tv.adobe.com/v/17392)
