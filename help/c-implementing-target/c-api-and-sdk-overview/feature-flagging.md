---
description: 当代技术产品团队在产品发布时采用持续交付原则。 Target帮助开发人员和产品团队快速、高效地推出新的产品功能。
keywords: 转出；转出；连续交付；产品启动；分阶段转出
seo-description: 当代技术产品团队在产品发布时采用持续交付原则。 Adobe Target帮助开发人员和产品团队通过分阶段推出快速、高效地推出新的产品功能。
seo-title: 当代技术产品团队在产品发布时采用持续交付原则。 Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently.
solution: Target
title: Feature flagging
topic: Standard
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# 功能标记

当代技术产品团队在产品发布时采用持续交付原则。 Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently in a phased rollout.

以下链接提供了您需要了解的关键概念的信息，以实现持续交付：

* [A/B测试活动](/help/c-activities/t-test-ab/test-ab.md)
* [JSON offers](/help/c-experiences/c-manage-content/create-json-offer.md)
* [Audience refinements](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## Continuous delivery

1. By default, turn the feature "off" on release.

   使用服务器端或应用程序内变量来控制此操作。

1. 创建一个将此变量设置为“on”的Target JSON选件。

1. 在 [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)中创建包含两个体验的A/B测试活动，并使用在一个体验中的上一步骤中创建的JSON选件。

   或

   在基于表单的体验书写器中创建 [A/B测试活动](/help/c-experiences/form-experience-composer.md) ，并使用在上一步中创建的JSON选件。

   >[!NOTE]
   >
   >通过基于表单的体验编写器，您可以创建具有单个体验的A/B测试活动。 不能使用VEC创建具有单个体验的活动。

1. 为活动指定所需的流量分配。

   如果您希望首先将此功能向5%的访客推出，请在三部分指导式工作流程的“定位”步骤中指定5个，然后将100%的合格访客发送到JSON选件（体验A）的体验。

   下图显示了具有两种体验的VEC。

   ![VEC中用于功能标记的流量分配](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   下图显示了具有单一体验的基于表单的体验书写器。

   ![基于表单的体验书写器中功能标记的流量分配](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. 您可以通过Target UI或使用API逐渐增加5%的流量分配，以增加此活动的流量分配，直到达到100%的流量分配。

   >[!NOTE]
   >
   >A/B测试活动会在整个会话中对访客进行粘滞。 如果减少流量分配，则开始查看此功能的访客将继续查看该功能，直到其会话重置为止。

## A/B测试功能

如果您使用A/B/..N Test features, use the approach discussed above with the following improvements:

* Each feature variant should be represented using an appropriate JSON offer that makes a Target experience.
* 您可以按照上述方式管理此测试的流量分配。

## Parametrized rollouts

The method described above helps you manage a controlled rollout.

You can roll out a feature for your beta participants only and then later roll out the feature to all other customers. This can be easily achieved by leveraging Target Location (mbox) parameters or profile parameters. [](/help/c-target/c-audiences/c-target-rules/custom-parameters.md)[](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)These parameters can be used in conjunction with phased traffic allocation.

## Server-side vs. client-side

Feature rollouts and testing can be delivered via Target APIs (and server-side SDKs) as well as the client side SDKs (JS, Mobile SDK). [](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)Depending on how your website, mobile app, or kiosk is architected, you can leverage Target's different integration options.
