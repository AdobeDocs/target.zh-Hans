---
keywords: 推荐设计;创建设计;复制设计
description: 了解如何使用默认设计或通过创建自定义设计来创建[!DNL Target Recommendations]设计，从而最好地适应页面的布局。
title: 创建设计
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="查看Target Premium中包含的内容。"
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
TQID: 'https://experienceleague.adobe.com/GLWcKaQGl6TmL9i7LYUiYepg6SkAjBtL-78-zlaWCTk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 11%
---
# 创建设计 {#create-design}

>[!BEGINSHADEBOX]

**在此页面上：**&#x200B;了解如何在[!DNL Adobe Target Recommendations]中创建、编辑、复制和删除设计，以及如何以JSON格式返回推荐。

>[!ENDSHADEBOX]

设计可定义推荐在页面上的显示方式。 设计可以基于默认设计或创建为自定义设计。 **[!UICONTROL 推荐]** > **[!UICONTROL 设计]**&#x200B;屏幕同时显示默认设计卡片和在帐户中创建的设计。

* 默认设计无法编辑或删除。
* 可以编辑、复制或删除自定义设计。
* 要基于默认设计创建设计，请首先复制设计，然后编辑副本。

在活动创建过程中，可以从&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)中创建设计，也可以在活动创建之外从设计库创建设计。 以下步骤假定设计是从库创建的，但步骤相似。

## 从库创建设计 {#steps}

1. 单击&#x200B;**[!UICONTROL 推荐]** > **[!UICONTROL 设计]**&#x200B;以显示&#x200B;**[!UICONTROL 设计]**&#x200B;库。

1. 通过以下方式之一开始设计：

   * 若要使设计基于默认设计或基于现有设计，请单击该设计的“更多操作”图标（ ![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)），然后单击“**[!UICONTROL 复制]**”。 此时将显示&#x200B;**[!UICONTROL 创建设计]**&#x200B;对话框。 编辑的副本将变成新的自定义设计。
   * 要从头开始创建自定义设计，请单击&#x200B;**[!UICONTROL 创建设计]**。

     ![突出显示了“创建设计”按钮的设计库](../assets/design_1.png)

1. 键入&#x200B;**[!UICONTROL Name]**&#x200B;并选择要在设计卡片上显示的可选预览图像。

   使用默认设计时，**[!UICONTROL 内容名称]**&#x200B;字段中会显示设计名称后跟“副本”。 该名称可以编辑。

1. （视情况而定）根据需要编辑设计&#x200B;**[!UICONTROL 代码]**。

   推荐设计使用的是开源 Velocity 设计语言。 有关Velocity的信息，请参阅[https://velocity.apache.org](https://velocity.apache.org)和[使用Velocity自定义设计](/help/main/c-recommendations/c-design-overview/customizing-a-template.md)。

   设计可以是 HTML 形式，也可以是非 HTML 形式。 默认情况下，HTML设计使用`<div>`标记封装，以便允许在Web环境中进行点击跟踪。 非 HTML 设计适用于无法进行点击跟踪的非 Web 环境。 将&#x200B;**[!UICONTROL HTML设计]**&#x200B;切换开关滑动到“关闭”位置以使用非HTML代码。

   >[!NOTE]
   >
   >设计中可引用（硬编码或通过循环）的最大实体数为99。

1. 单击&#x200B;**[!UICONTROL 创建]**。

1. 单击设计中的“更多操作”图标（![更多操作图标](/help/main/assets/icons/MoreSmallList.svg)）以编辑、复制或删除，然后单击相应的选项： **[!UICONTROL 编辑]**、**[!UICONTROL 复制]**&#x200B;或&#x200B;**[!UICONTROL 删除]**。

   ![打开“更多操作”菜单的设计库，显示“编辑”、“复制”和“删除”](../assets/design_2.png)

设计可在整个帐户中使用。 在删除设计之前，必须考虑跨帐户的使用情况。 无法恢复已删除的设计。

## JSON示例 {#json-example}

以下示例显示了使用基于[表单的编辑器](/help/main/c-experiences/form-experience-composer.md)配置活动时如何返回JSON响应。

1. 从&#x200B;**[!UICONTROL 设计库]**&#x200B;或在基于表单的工作流中创建设计。 在&#x200B;**[!UICONTROL 可视化体验编辑器]** (VEC)工作流中创建的设计只能是HTML设计，它封装在`<div>`中以进行点击跟踪。

1. 确保已关闭&#x200B;**[!UICONTROL HTML设计]**&#x200B;选项：

   ![HTML设计切换开关处于关闭位置](/help/main/c-recommendations/c-design-overview/assets/html_design_toggle.png)

1. 将以下示例等代码粘贴到设计中：

   +++ 返回实体ID列表的示例设计代码

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

   +++

1. 设置使用此设计的基于表单的[!DNL Recommendations]活动。

   +++ 了解如何设置基于表单的[!DNL Recommendations]活动 

   1. 导航到&#x200B;**[!UICONTROL 活动]**&#x200B;页面。
   1. 单击&#x200B;**[!UICONTROL 创建活动]** > **[!UICONTROL 推荐]**。
   1. 在&#x200B;**[!UICONTROL 选择体验编辑器]**&#x200B;下，选择&#x200B;**[!UICONTROL 表单]**，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. 在“位置”下，输入文本“Sample_Recs_Response”。
   1. 在&#x200B;**[!UICONTROL 默认内容]**&#x200B;下方，单击向下箭头，然后单击&#x200B;**[!UICONTROL 添加推荐]**。
   1. 选择一种页面类型。 这决定了对接下来要显示的屏幕的初步筛选。
   1. 选择一个标准卡片，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. Select在上一步中创建的设计，然后单击&#x200B;**[!UICONTROL 下一步]**。
   1. 完成设置过程。
   1. 单击&#x200B;**[!UICONTROL 不活跃]**&#x200B;旁边的向右箭头，然后选择&#x200B;**[!UICONTROL 激活]**。

   +++

1. 设置和激活活动后，可以设置示例请求以恢复干净的JSON响应。

   从保存活动开始，[!DNL Target]需要构建模型以支持所选标准配置。 根据多种因素，此过程可能需要一些时间。 一旦建立了模型，就会显示结果。

   例如：

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   其中

   | 参数 | 值 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | [!DNL Target]客户端代码（位于#recsSettings >推荐API令牌>客户端代码）。 |
   | `[YOUR_MBOX_NAME]` | 在基于表单的“推荐”活动的“位置”部分中选择的名称，在本例中为Sample_Recs_Response。 |
   | `[ENTITY_ID]` | 目录中的项目的`entity.id`。 |
   | `[AT_PROPERTY_TOKEN]` | （可选）在活动设置期间选择资产（企业权限的一部分）时添加。 |

在算法运行并获得结果后，响应将类似于以下内容：

包含推荐项目的![JSON响应](/help/main/c-recommendations/c-design-overview/assets/json_recommendation.png){width="575px"}

## 其他JSON对象提示 {#json-tips}

此外，还可以通过设置具有以下语法的设计，发送回以逗号分隔的简单项目列表：

```
$entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

其他信息也可在响应中发送。 以下代码是一个更复杂的示例，此代码不仅返回实体ID及其关联的版块（顺序），还返回更多其他内容。 此设计示例还返回了活动详细信息、**[!UICONTROL Target配置文件]**&#x200B;详细信息（如适用）以及与返回的项目关联的其他`entity.attributes`。

+++ 返回活动、个人资料和实体详细信息的示例设计代码

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

+++

