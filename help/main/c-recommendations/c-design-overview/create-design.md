---
keywords: 推荐设计;创建设计;复制设计
description: 了解如何使用默认设计或通过创建自定义设计来创建 [!DNL Target Recommendations] 设计，以便最好地配合页面的布局。
title: 如何在“推荐”中创建设计？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=zh-Hans#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 19%

---

# 创建设计

设计可定义推荐在页面上的显示方式。

您可以使用默认设计或通过创建自定义设计来创建[!UICONTROL Recommendations]设计。 **[!UICONTROL Recommendations > Designs]**&#x200B;屏幕显示默认设计卡片以及在您的帐户中创建的所有设计。

在处理设计时，请牢记以下信息：

* 您可以使用默认设计创建推荐设计，也可以创建自定义设计。
* 不能编辑或删除默认设计。
* 您可以编辑、复制或删除自定义设计。
* 要基于默认设计创建设计，必须首先复制设计，然后编辑副本。

此图显示了默认的1 x 4设计：

![1 x 4默认设计](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

此图显示了一个自定义设计：

![自定义设计](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

您可以在活动创建过程中从[!UICONTROL Visual Experience Composer] (VEC)中创建设计，也可以在活动创建之外从设计库中创建设计。 以下部分假定您是从库中创建设计，但步骤类似。

## 创建设计

您可以基于默认设计创建设计，也可以创建自定义设计。

### 基于默认设计创建设计

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Designs]**&#x200B;以显示[!UICONTROL Designs]库。


1. 单击要创建的设计的“更多操作”图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击&#x200B;**[!UICONTROL Copy]**。

   此时将显示[!UICONTROL Create Design]对话框。

1. 键入&#x200B;**[!UICONTROL &#x200B; Name]**&#x200B;和要在设计卡片上显示的可选预览图像。

   当您使用默认设计时，设计名称和“副本”将出现在&#x200B;**[!UICONTROL Content Name]**&#x200B;字段中。 您可以编辑该名称。您还可以选择要在设计卡片上显示的图像。

1. （视情况而定）根据需要编辑设计&#x200B;**[!UICONTROL Code]**。

   推荐设计使用的是开源 Velocity 设计语言。有关Velocity的信息可在[https://velocity.apache.org](https://velocity.apache.org)和[使用Velocity自定义设计](/help/main/c-recommendations/c-design-overview/customizing-a-template.md)中找到。

   设计可以是 HTML 形式，也可以是非 HTML 形式。默认情况下，HTML设计使用`<div>`标记封装，以便允许在Web环境中进行点击跟踪。 非HTML设计适用于无法进行点击跟踪的非Web环境。 将[!UICONTROL HTML Design]切换开关滑动到“关闭”位置以使用非HTML代码。

   >[!NOTE]
   >
   >设计中可引用（无论是以硬编码方式引用还是通过循环引用）的最大实体数为99。

1. 单击 **[!UICONTROL Create]**。

### 创建自定义设计

1. 单击&#x200B;**[!UICONTROL Recommendations]** > **[!UICONTROL Designs]**&#x200B;以显示[!UICONTROL Designs]库。

1. 单击 **[!UICONTROL Create Design]**。

   如果要将新的自定义设计基于现有设计，请单击要创建的设计的[!UICONTROL More Actions]图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击[!UICONTROL Copy]。 然后，您可以编辑副本以创建新的自定义设计。

1. 添加&#x200B;**[!UICONTROL Name]**&#x200B;和可选的预览图像。

1. （视情况而定）根据需要编辑设计&#x200B;**[!UICONTROL Code]**。

   有关更多信息，请参阅上述步骤4中的信息。

1. 单击 **[!UICONTROL Create]**。

## 编辑、复制或删除设计

请记住，您不能编辑或复制默认设计；您只能复制默认设计。

单击要编辑或删除的设计的[!UICONTROL More Actions]图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击相应的图标： [!UICONTROL Edit]、[!UICONTROL Copy]或[!UICONTROL Delete]。

您可以复制现有设计以创建复制设计，然后可对其进行修改。 此过程可让您用更少的工作量创建类似设计。

请注意，设计可在整个帐户中使用。 确保在删除设计之前考虑跨帐户的使用情况。 无法恢复已删除的设计。

## JSON 示例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

以下示例显示了在通过基于[表单的编辑器](/help/main/c-experiences/form-experience-composer.md)配置活动时如何返回JSON响应。

1. 在[!UICONTROL Design library]内或基于表单的工作流内创建设计。 如果尝试在[!UICONTROL Visual Experience Composer] (VEC)工作流中创建设计，则无法创建除了HTML设计之外的任何其他内容，该产品封装在`<div>`中以进行点击跟踪。

1. 确保已关闭“HTML 设计”选项：

   ![html_design_toggle图像](assets/html_design_toggle.png)

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

   1. 导航到&#x200B;**[!UICONTROL Activities]**&#x200B;页面。
   1. 单击&#x200B;**[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**。
   1. 在&#x200B;**[!UICONTROL Choose Experience Composer]**&#x200B;下，选择&#x200B;**[!UICONTROL Form]**，然后单击&#x200B;**[!UICONTROL Next]**。
   1. 在“位置”下方，输入文本：“Sample_Recs_Response”
   1. 在&#x200B;**[!UICONTROL Default Content]**&#x200B;下，单击向下箭头，然后单击&#x200B;**[!UICONTROL Add Recommendation]**。
   1. 选择一种页面类型。这决定了对接下来要显示的屏幕的初步筛选。
   1. 选择标准卡片，然后单击&#x200B;**[!UICONTROL Next]**。
   1. 选择在上一步中创建的设计，然后单击&#x200B;**[!UICONTROL Next]**。
   1. 完成设置过程。
   1. 单击&#x200B;**[!UICONTROL Inactive]**&#x200B;旁边的向右箭头，然后选择&#x200B;**[!UICONTROL Activate]**。

1. 设置活动并将其激活后，您可以设置示例请求，以获取简洁的 JSON 响应。

   从您保存活动开始，[!DNL Target]需要构建模型以支持所选标准配置。 根据多种因素，此过程可能需要一些时间。 构建模型后，便会显示结果。

   例如：

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   其中

   | 参数 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Target客户端代码(位于/help/target/products.html#recsSettings >推荐API令牌>客户端代码)。 |
   | `[YOUR_MBOX_NAME]` | 您在基于表单的“推荐”的“位置”部分中选择的名称，在本例中为Sample_Recs_Response。 |
   | `[ENTITY_ID` | 您目录中的项目的 `entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | （可选）如果您在活动设置过程中选择了某个属性（“企业权限”的一部分），则需添加此参数。 |

在运行算法并获取结果后，您的响应应当类似于以下示例：

![json_recommendation图像](assets/json_recommendation.png){width="575px"}

## 其他JSON对象提示和技巧 {#section_C305673C68944749969DB239E3221DC2}

您还可以通过以下语法设置设计，以逗号分隔的简单项目列表发送回来：

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

或者，您也可以在响应中发送更多信息。下面是一个更为复杂的代码文件示例，此代码不仅仅返回了实体 ID 及其关联的版块（顺序），还返回了更多其他内容。此设计示例还返回了活动详细信息、[!UICONTROL Target Profile]详细信息（如适用）以及与返回的项目关联的其他`entity.attributes`。

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

## 培训视频：在推荐(3:20) ![概述徽章](/help/main/assets/overview.png)中创建自定义设计

本视频包含以下信息：

* 创建自定义设计
* 了解如何在设计中引用显示变量

>[!VIDEO](https://video.tv.adobe.com/v/27687)
