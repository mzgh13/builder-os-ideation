---
url: "https://www.merge.dev/blog/custom-integrations"
title: "How to build custom integrations successfully"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/custom-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/custom-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/custom-integrations#)

Table of contents

[What is a custom integration?](https://www.merge.dev/blog/custom-integrations#what-is-a-custom-integration)

[Custom integration examples](https://www.merge.dev/blog/custom-integrations#custom-integration-examples)

[Benefits of custom integrations](https://www.merge.dev/blog/custom-integrations#benefits-of-custom-integrations)

[Challenges of custom integrations](https://www.merge.dev/blog/custom-integrations#challenges-of-custom-integrations)

[Leverage Merge as your custom integration solution](https://www.merge.dev/blog/custom-integrations#leverage-merge-as-your-custom-integration-solution)

[Custom integration FAQ](https://www.merge.dev/blog/custom-integrations#custom-integration-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcustom-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is integration monitoring? Plus tips for performing it**](https://www.merge.dev/blog/integration-monitoring)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How to build secure integrations (5 tips)**](https://www.merge.dev/blog/integration-security)

# How to build custom integrations successfully

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to integrate applications, you might find that you need to sync non-standard—or custom—fields.

For a CRM, this can be fields like “Lifetime Value”, “Satisfaction Rating”, and “Preferred Contact Method”; for an HRIS, this can be “Shift Schedule”, “Manager Name”, and “Preferred First Name”; for an ATS, this can be “Application Source”, “Expected Salary”, and “Technical Skills”—and the list goes on as you look at different types of software applications.

To help you sync custom data successfully, we’ll break down the concept of a custom integration, impactful custom integrations you can implement, common challenges associated with building them, and more.

## **What is a custom integration?**

It’s either an internal or customer-facing integration that syncs non-standard data. The integration is typically built via APIs, but it can also be implemented through other means, such as files or screen scraping.

[![The two types of custom integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe578d0606a7042d36bf0_AD_4nXdrh2wNANCOcNC_QIXubDTyhpo2fU8hXiMfol0mW7IHasT2Xo4Q2DE3-vcb3lNQHVVAdotzzkTDO5sz4Lk9Ttg5CK4jDCDct9V_lCSD3iJBnmvtC37cfMLfzi8FDluE8RYTcKIaONYGAz6e-HmbzG43pMU3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe578d0606a7042d36bf0_AD_4nXdrh2wNANCOcNC_QIXubDTyhpo2fU8hXiMfol0mW7IHasT2Xo4Q2DE3-vcb3lNQHVVAdotzzkTDO5sz4Lk9Ttg5CK4jDCDct9V_lCSD3iJBnmvtC37cfMLfzi8FDluE8RYTcKIaONYGAz6e-HmbzG43pMU3.webp)

_Custom integrations are either between your product and your customers’ applications (left) or between your internal applications (right)_

_Related:_ [_A guide to custom API integrations_](https://www.merge.dev/blog/custom-api-integration)

## **Custom integration examples**

Let’s break down an example of an internal custom integration and then showcase a few customer-facing use cases.

### **Sync custom data between your HRIS and ATS**

Let’s say that a candidate signs their offer letter and you need to add them to your HRIS to kickstart their onboarding.

With this in mind, you can integrate your ATS and HRIS, and build a flow where once a candidate is marked as “Hired” in the former, their new profile gets created in the latter. This new profile can include all of the custom fields that are pertinent to onboarding the new hire, like their “Preferred First Name.”

[![Custom integration between Greenhouse and Workday](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe577bb2edd383d5f9dd9_AD_4nXfnSV1XoWhE6lIJXtReCGtIl2MyC5imRrJKK9opIgYE2ZeYVvTcNMaKQSpKwgQ61O0Vt-UAmfl6-qM3RHevOrlCRWhRmpAoLAr_Gl4cUKNGNSP5n3YRaukL-JCk8cHSk6R-AqBjMTx1gu4zowj4NyQNT6xI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe577bb2edd383d5f9dd9_AD_4nXfnSV1XoWhE6lIJXtReCGtIl2MyC5imRrJKK9opIgYE2ZeYVvTcNMaKQSpKwgQ61O0Vt-UAmfl6-qM3RHevOrlCRWhRmpAoLAr_Gl4cUKNGNSP5n3YRaukL-JCk8cHSk6R-AqBjMTx1gu4zowj4NyQNT6xI.webp)

### **Sync custom data between your CRM and customers’ ERP software**

Let’s imagine that you offer a CRM system. To help your customers kickstart the invoicing process seamlessly whenever an opportunity is marked as “Closed-won” in your solution, you can build the following integration:

Once an opportunity is changed to “Closed-won” in your platform, the client’s account gets created in your customer’s ERP system. This can include syncing custom fields that help your customer’s finance team invoice the client appropriately, such as “Payment Method” and “Discount Percentage.”

[![Custom integration between Salesforce and NetSuite](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5774890db3dab96d189_AD_4nXctgJXtKyq1O0n4xR8iVeSBFOQa9wlU_kU_8GwRMKlYgfbUzmGMiKtD4fdvEyrGW-iCTp_4WpTI4l6OGQbqxtX1QvANXXo2UScmIsspd7QbnLit9vvaWdvbxq-e2S-XX1Wr10zdZE3xJNoCScY_BTTkbLx2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5774890db3dab96d189_AD_4nXctgJXtKyq1O0n4xR8iVeSBFOQa9wlU_kU_8GwRMKlYgfbUzmGMiKtD4fdvEyrGW-iCTp_4WpTI4l6OGQbqxtX1QvANXXo2UScmIsspd7QbnLit9vvaWdvbxq-e2S-XX1Wr10zdZE3xJNoCScY_BTTkbLx2.webp)

_Related:_ [_Common two-way syncs_](https://www.merge.dev/blog/two-way-sync)

## **Benefits of custom integrations**

Custom integrations offer a variety of critical business benefits. Here are just a few worth considering for both internal and customer-facing scenarios.

### **Addresses customers’ unique syncing requirements**

Your customers likely operate differently, leading the data they collect and the ways in which they use their data to be inherently unique to their business.

By offering custom, customer-facing integrations, you can let customers sync and build flows with whatever types of data are important to their business, enabling you to meet them where they are.

### **Empowers your employees to perform better**

Through custom, internal integrations, you can provide your teams with the data they need to make smarter decisions. This can take the form of arming reps with more personalized data on leads, providing finance with more comprehensive billing information, sharing additional insights on support tickets for customer success, etc.

### **Unlocks improved business outcomes**

Given the previous benefit, it’s perhaps little surprise that custom integrations can help you improve key business metrics, from your close rate to your retention rate.

For instance, by providing reps with personalized data on leads, they can respond to leads faster and with more relevant messages, helping them get more responses and, eventually, convert more prospects into clients. And, by helping customer success access more details on support tickets, they can troubleshoot issues faster and and more successfully.

_Related:_ [_The benefits of API integrations_](https://www.merge.dev/blog/api-integration-benefits)

## **Challenges of custom integrations**

Unfortunately, custom integrations aren’t necessarily easy to build and maintain. Here are some of the top challenges to be aware of.

### **Mapping custom fields can prove difficult**

The process of mapping custom fields in one application with fields in another can prove difficult.

You might, for instance, not find similar fields in the other application, forcing you to add new ones.

Moreover, the process of determining the best field mappings can require cross-functional alignment; the teams that use these systems and rely on this custom data will need to know how, exactly, the mappings will work and should be bought into your proposals. Otherwise, the data can be less actionable and valuable for these stakeholders.

### **API providers can prevent you from syncing custom fields**

Depending on the API provider, you might only be able to access and sync standard fields.

You can, potentially, turn to other integration methods to sync custom data instead, but alternative approaches come with other notable drawbacks. For instance, [file-based integrations](https://www.merge.dev/blog/flat-file-integration) fail to sync data in, or near, real-time; while UI-based integrations (i.e., screen scraping) can easily break whenever there’s a small change to an application’s UI.

### **Often requires complex data transformation logic**

In order to sync custom data, your engineers will need to implement data transformation logic.

This logic is often time and resource-intensive to set up and maintain, especially if you need to build several custom integrations over time. As a result, this work can pull your engineers away from the projects they’re uniquely qualified to take on and that drives meaningful impact for your business.

_Related:_ [_The challenges of building and maintaining integrations_](https://www.merge.dev/blog/integration-challenges)

## **Leverage Merge as your custom integration solution**

If you’re looking to outsource your customer-facing integrations and need to build unique integrations for different customers, you can use Merge—the leading unified API solution.

Through Merge, you can use Field Mapping to add and sync additional fields to our Common Models; Remote Data to access and sync custom fields in the original format they appear in in the 3rd-party application; Authenticated Passthrough Request to make API requests to endpoints that let you access custom data—and more.

[![An example of using Field Mapping](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)

_Using Field Mapping, you can hypothetically map the custom field “custom\_score” in Greenhouse to a new Common Model field in Merge’s ATS Unified API, “technical\_assessment\_score”_

Learn more about using Merge to build custom integrations by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcustom-integrations).

## **Custom integration FAQ**

In case you have any more questions on custom integration, we’ve addressed several additional ones below.

### **What is the difference between standard and custom integrations?**

Standard integrations sync common data types that are typically provided by SaaS applications out of the box; while custom integrations sync data types that you or your customers add to the connected SaaS applications.

### **How are out-of-the-box—or off-the-shelf—integrations different from custom integrations?**

Out-of-the-box integrations allow you to build integrations faster by letting you access prebuilt functionality, such as specific transformations, authentication protocols, and triggers and actions. Custom integrations, on the other hand, need to be built from the ground up.

### **How does an API differ from a custom API?**

A custom API is built to accommodate a specific set of API consumers, while a standard API lets a broad range of consumers access and interact with its endpoints.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jon Gitlin is the Managing Editor of Merge's blog. He has several years of experience in the integration and automation space; before Merge, he worked at Workato, an integration platform as a service (iPaaS) solution, where he also managed the company's blog. In his free time he loves to watch soccer matches, go on long runs in parks, and explore local restaurants.

## Read more

[Software scalability: design, strategies and best practices](https://www.merge.dev/blog/software-scalability)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)

### Software scalability: design, strategies and best practices

Insights

[How to integrate with the SharePoint API via Python](https://www.merge.dev/blog/sharepoint-api-python)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)

### How to integrate with the SharePoint API via Python

Engineering

[How to build integrations for AI agents](https://www.merge.dev/blog/ai-agent-integrations)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)

### How to build integrations for AI agents

AI

## Subscribe to the Merge Blog

Get stories from Merge straight to your inbox

[Subscribe](https://www.merge.dev/get-in-touch?utm_btn=dr-page-root)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67a0696c88fcb6b1a1d8ad6f_CTA%20Background%20Logo.svg)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Get our best content every week

Our weekly newsletter provides the best practices you need to build high performing product integrations.

Your email

Thank you! Your submission has been received!

Oops! Something went wrong while submitting the form.

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8f85b1ca-2f1e-4545-b440-2dc3aa1b3ac1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6f508349-3246-458d-ae3a-16af1dd6edfb&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8f85b1ca-2f1e-4545-b440-2dc3aa1b3ac1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6f508349-3246-458d-ae3a-16af1dd6edfb&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f74b1fa7-8782-4e49-862b-5c0b10b8772c&bo=2&sid=c06a87303e8d11f093917970d9cf9923&vid=c06c72b03e8d11f09bd95569e6cafbea&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20build%20custom%20integrations%20successfully&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-integrations&r=&lt=872&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=290015)