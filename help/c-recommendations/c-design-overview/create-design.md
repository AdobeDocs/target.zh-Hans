---
keywords: 推荐设计;创建设计;复制设计
description: 了解如何使用默认设计或通过创建最适合页面布局的自定义设计来创建Adobe [!DNL Target] Recommendations设计。
title: 如何在Recommendations中创建设计？
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 31%

---

# ![PREMIUM](/help/assets/premium.png) 创建设计

设计可定义推荐在页面上的显示方式。

您可以使用默认设计或通过创建自定义设计来创建[!UICONTROL 推荐]设计。**[!UICONTROL “Recommendations”>“设计”]**&#x200B;屏幕显示默认设计卡和在您的帐户中创建的任何设计。

处理设计时，请牢记以下信息：

* 您可以使用默认设计创建推荐设计，也可以创建自定义设计。
* 不能编辑或删除默认设计。
* 您可以编辑、复制或删除自定义设计。
* 要基于默认设计创建设计，必须先复制设计，然后编辑副本。

此插图显示了默认的1 x 4设计：

![1 x 4默认设计](/help/c-recommendations/c-design-overview/assets/default-design.png)

此插图显示自定义设计：

![自定义设计](/help/c-recommendations/c-design-overview/assets/custom-design.png)

在活动创建过程中，您可以从Visual Experience Composer(VEC)中或在活动创建之外的设计库中创建设计。 以下部分假定您从库创建设计，但步骤类似。

## 创建设计

您可以基于默认设计创建设计，也可以创建自定义设计。

### 基于默认设计创建设计

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 设计]**&#x200B;以显示[!UICONTROL 设计]库。

   ![设计库](/help/c-recommendations/c-design-overview/assets/design-library.png)

1. 将鼠标悬停在要创建的设计的卡上，然后单击&#x200B;**[!UICONTROL 复制]**&#x200B;图标。

   ![](assets/Card_CopyDesign.png)

   此时将显示[!UICONTROL 创建设计]对话框。

   ![](assets/createDesign.png)

1. 在&#x200B;**[!UICONTROL 信息]**&#x200B;面板中，添加要在设计卡上显示的&#x200B;**[!UICONTROL 内容名称]**&#x200B;和可选预览图像。

   使用默认设计时，设计名称和“Copy”将显示在&#x200B;**[!UICONTROL 内容名称]**&#x200B;字段中。 您可以编辑该名称。您还可以选择要在设计卡上显示的图像。

1. （视情况而定）根据需要编辑设计&#x200B;**[!UICONTROL 代码]**。

   推荐设计使用的是开源 Velocity 设计语言。有关Velocity的信息，请访问[https://velocity.apache.org](https://velocity.apache.org)和[使用Velocity](/help/c-recommendations/c-design-overview/customizing-a-template.md)自定义设计。

   设计可以是 HTML 形式，也可以是非 HTML 形式。默认情况下，HTML 设计将使用`<div>`标记封装，以便允许在 Web 环境中进行点击跟踪。非 HTML 设计适用于无法进行点击跟踪的非 Web 环境。将[!UICONTROL HTML Design]切换到“off”位置以使用非HTML代码。

   >[!NOTE]
   >
   >可在设计中引用的最大图元数为99。

1. 单击&#x200B;**[!UICONTROL 保存]**。

### 创建自定义设计

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL 设计]**&#x200B;以显示[!UICONTROL 设计]库。

1. 单击&#x200B;**[!UICONTROL 创建设计]**。

   如果要将新的自定义设计基于现有设计，请将鼠标悬停在所需设计上，然后单击[!UICONTROL 复制]图标。 然后，您可以编辑副本以创建新的自定义设计。

1. 添加&#x200B;**[!UICONTROL 内容名称]**&#x200B;和可选预览图像。

1. （视情况而定）根据需要编辑设计&#x200B;**[!UICONTROL 代码]**。

   有关详细信息，请参阅上面步骤4中的信息。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 编辑、复制或删除设计

请记住，您无法编辑或复制默认设计；您只能复制默认设计。

将鼠标悬停在[!UICONTROL Design]库中所需的设计上，然后单击相应的图标：编辑、复制或删除。

![悬停设计图标](/help/c-recommendations/c-design-overview/assets/hover-icons-design.png)

您可以复制现有设计以创建随后可以修改的重复设计。 这样您可以更轻松地创建类似的设计。

请注意，整个帐户中都提供设计。 在删除设计之前，请务必考虑这一点。 无法恢复已删除的设计。

## JSON 示例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

以下示例显示如何在通过基于表单的编辑器配置活动时返回JSON响应。

1. 从设计库或基于表单的工作流程中创建设计。 如果在Visual Experience Composer(VEC)工作流程中尝试执行此操作，则不能创建除HTML设计之外的任何内容，HTML设计打包在`<div>`中，用于单击跟踪。

1. 确保已关闭“HTML 设计”选项：

   ![](assets/html_design_toggle.png)

1. 以下代码是您可以粘贴到设计中的内容示例：

   ```javascript
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. 设置使用此设计的基于表单的[!DNL Recommendations]活动。

   1. 导航到&#x200B;**[!UICONTROL 活动]**&#x200B;页。
   1. 单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 推荐]**。
   1. 在&#x200B;**[!UICONTROL 选择体验书写器]**&#x200B;下，选择&#x200B;**[!UICONTROL 表单]**，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. 在“位置”下方，输入文本：“Sample_Recs_Response”
   1. 在&#x200B;**[!UICONTROL 默认内容]**&#x200B;下方，单击向下箭头，然后单击&#x200B;**[!UICONTROL 添加推荐]**。
   1. 选择一种页面类型。这决定了对接下来要显示的屏幕的初步筛选。
   1. 选择一个标准卡片，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. 选择您在上一步中创建的设计，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. 完成设置过程。
   1. 单击&#x200B;**[!UICONTROL 不活跃]**&#x200B;旁边的向右箭头，然后选择&#x200B;**[!UICONTROL 激活]**。

1. 设置活动并将其激活后，您可以设置示例请求，以获取简洁的 JSON 响应。

   保存活动后，[!DNL Target]将需要构建一个模型以支持选定的标准配置。 此过程可能会花费一些时间，具体时间取决于众多因素。构建模型后，便会显示结果。

   例如：

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   其中

   | 参数 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | 目标客户端代码(可在/help/target/products.html#recsSettings > Recommendations API令牌>客户端代码上找到。 |
   | `[YOUR_MBOX_NAME]` | 您在基于表单的Recommendations的“位置”部分中选择的名称，在此例中为Sample_Recs_Response。 |
   | `[ENTITY_ID` | 您目录中的项目的 `entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | （可选）如果您在活动设置过程中选择了某个属性（“企业权限”的一部分），则需添加此参数。 |

在运行算法并获取结果后，您的响应应当类似于以下示例：

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## 其他JSON对象提示与技巧{#section_C305673C68944749969DB239E3221DC2}

您还可以使用以下语法设置设计，以便仅发送回以逗号分隔的项目简单列表：

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

或者，您也可以在响应中发送更多信息。下面是一个更为复杂的代码文件示例，此代码不仅仅返回了实体 ID 及其关联的版块（顺序），还返回了更多其他内容。此设计示例还返回活动详细信息、目标用户档案详细信息（如果适用）以及与返回的项关联的其他`entity.attributes`。

```javascript
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

## 培训视频：在Recommendations中创建自定义设计(3:20)![概述徽章](/help/assets/overview.png)

本视频包含以下信息：

* 创建自定义设计
* 了解如何在设计中引用显示变量

>[!VIDEO](https://video.tv.adobe.com/v/27687)
