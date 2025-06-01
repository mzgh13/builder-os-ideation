---
url: "https://www.merge.dev/blog/custom-api-integration"
title: "Custom API integration: here’s what you need to know"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/custom-api-integration#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/custom-api-integration#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/custom-api-integration#)

Table of contents

[What is a custom API integration?](https://www.merge.dev/blog/custom-api-integration#what-is-a-custom-api-integration)

[Custom API integration examples](https://www.merge.dev/blog/custom-api-integration#custom-api-integration-examples)

[The challenges of building and maintaining custom API integrations](https://www.merge.dev/blog/custom-api-integration#the-challenges-of-building-and-maintaining-custom-api-integrations)

[How to build custom API integrations](https://www.merge.dev/blog/custom-api-integration#how-to-build-custom-api-integrations)

[Custom API integration FAQ](https://www.merge.dev/blog/custom-api-integration#custom-api-integration-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcustom-api-integration)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)**‍How to calculate the costs of API integrations**](https://www.merge.dev/blog/cost-of-api-integrations)

# Custom API integration: here’s what you need to know

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As your organization looks to build either internal or customer-facing API integrations, you’ll often need to sync custom objects and fields.

The process of building and maintaining these custom integrations can be time-intensive and complex, which can make the process of scaling them difficult.

We’ll further explore the challenges of implementing and overseeing custom API integrations, break down several examples of how they can work, and then go on to explore your options in building any. But first, let’s align on the definition of a custom API integration.

## **What is a custom API integration?**

It’s any API-based integration that syncs non-standard objects and fields in order to [meet specific integration requirements](https://www.merge.dev/blog/integration-requirements). These integrations can either be built between internal applications or between your product and clients’ applications.

[![The two types of custom API integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6508b70cb24460f1d64da87f_xTOUc4nXEuO3PsZrEKdkozC6O2D1HCxkgsZG9DaspojlWVlpLby0jduy0UVBQ3syWzx0FaVtjea6WRHJ5lTq8WXHWYe8JovwPS6ZlrKzi9ra3oqqKpGwbRkGMAyVvAJ0Iqb2SGrnz4d7U73yH1ueIwE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6508b70cb24460f1d64da87f_xTOUc4nXEuO3PsZrEKdkozC6O2D1HCxkgsZG9DaspojlWVlpLby0jduy0UVBQ3syWzx0FaVtjea6WRHJ5lTq8WXHWYe8JovwPS6ZlrKzi9ra3oqqKpGwbRkGMAyVvAJ0Iqb2SGrnz4d7U73yH1ueIwE.webp)

_Related:_ [_What is a custom integration?_](https://www.merge.dev/blog/custom-integrations)

## **Custom API integration examples**

To help make our definition more tangible, let’s break down some examples of custom API integrations.

_Note: Our first example will be an internal integration and our second_ [_example will be a customer-facing integration_](https://www.merge.dev/blog/customer-facing-integration) _._

### **Syncing customer satisfaction scores with your CRM**

Let’s imagine that you use a survey tool to gather customer feedback at regular intervals (e.g., every 3 months).

As part of these surveys, you ask customers how happy they are through a specific rating scale and then ask them an open-ended question around why they gave that rating.

You’d like to add each client's answers to these questions in their associated account in your CRM. That way, the account owner can quickly discover the rating, the reason behind it, and then respond accordingly.

To help facilitate this, you can build a custom API integration that works as follows: Any time a client completes the survey, their score and open-ended response on their score get added to custom-built fields in the client’s associated CRM account, which you refer to as “CSAT rating” and “CSAT rating explanation.”

[![Custom integration between SurveyMonkey and Salesforce](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567eb5546e744c11c2dc_MDy0kz5s1KX3yvrVAlsujjwyf85Fr_DoGCnBZLHuv3yBN2GC1lkagypXolStK7rlavcQHD3mVowLL9QvCbf65lP9GmsyJeQDqzapPauikUSa6yYk71nfBtTYmSDDznI4uwS02lNjmMcoXyA2guREU54.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567eb5546e744c11c2dc_MDy0kz5s1KX3yvrVAlsujjwyf85Fr_DoGCnBZLHuv3yBN2GC1lkagypXolStK7rlavcQHD3mVowLL9QvCbf65lP9GmsyJeQDqzapPauikUSa6yYk71nfBtTYmSDDznI4uwS02lNjmMcoXyA2guREU54.webp)

### **Syncing candidate fit ratings in clients’ ATSs**

Say you offer a candidate sourcing tool that helps clients identify candidates for certain open roles.

Every candidate your product recommends comes with a “Candidate rating” field that specifies the candidate’s level of fit for the role.

To help your clients' recruiting teams access this rating for every candidate they’re evaluating, you can integrate your product with clients’ ATSs and build the following sync: Any time a new candidate gets recommended and has a certain rating, their profile gets added to the associated client’s ATS (which includes the candidate's rating).

[![Custom integration between your product and clients' ATSs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567e14c4a37a04bbd19e_RE7UstTEkgkoRLNplzy_YF-I1kFW-OIypGbalkhTX_DkRNfMEbbanyH9qx5Ox3ugPrCv37eQugA6D6z3tQKmrjVCkN54eES-t-ViiiVy_vwNqp5rkGazKf7eUoWQxNROQVg490xhd0D3NP4Te3J31m0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567e14c4a37a04bbd19e_RE7UstTEkgkoRLNplzy_YF-I1kFW-OIypGbalkhTX_DkRNfMEbbanyH9qx5Ox3ugPrCv37eQugA6D6z3tQKmrjVCkN54eES-t-ViiiVy_vwNqp5rkGazKf7eUoWQxNROQVg490xhd0D3NP4Te3J31m0.webp)

_Related:_ [_Internal and customer-facing examples of API integration_](https://www.merge.dev/blog/api-integration-examples)

## **The challenges of building and maintaining custom API integrations**

The process of building out custom API integrations can prove more difficult than you might expect. Here are some of the challenges to look out for:

### **Mapping fields between systems can be complex**

With standard data types, the process of mapping fields is often fairly intuitive. For instance, an “Account” in a CRM can be mapped with a “Customer” in the ERP system.

But when you start dealing with niche fields, determining the corresponding fields in other applications can become subjective and might even require you to add new fields in those applications. For example, if your customer success tool uses a custom “Customer Health Score” field that you’d like to map to your CRM, you might need to add the field to the latter before building the sync.

### **Requires custom-built data transformations**

Your developers might have already built the data transformation logic for standard objects and fields. Using custom objects and fields requires them to add additional logic, which can be time intensive, especially if you need to build several custom integrations.

### **Additional integration maintenance work**

Custom integrations can introduce new errors for your team (e.g., the custom transformation logic starts passing incorrect data between applications). Your developers will, as a result, need to build additional error-handling processes that account for these issues. Moreover, these integrations (like any) will need to be updated over time as the business processes they support evolve.

Managing this additional proactive and reactive work successfully can be a significant burden to your developers over time.

_Related:_ [_Challenges of building API integrations_](https://www.merge.dev/blog/api-integration-challenges)

## **How to build custom API integrations**

You generally have two options: building the integrations in-house and using a [3rd-party integration solution](https://www.merge.dev/blog/3rd-party-integration).

Since APIs differ in significant ways from one provider to the next—from their rate limit policies to their approaches to paginating responses to their methods of authenticating requests—each custom integration build is inherently unique and complex. In addition, many popular types of software are often highly customized (e.g., CRM systems), making several of your integrations all the more difficult to setup and sustain for your developers.

In the context of customer-facing integrations, a unified API solution can help.

The platform normalizes the 3rd-party APIs' data models to a standard schema, allowing you to interact with the integrated data more easily. Also, you’ll only need to worry about the unified API platform’s rate limit, approach to pagination, and authentication method, which further simplifies the integration build and any of the maintenance and management work involved afterwards.

[![How a unified API solution normalizes rate limits, pagination, and authentication](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567efb30490add46b6a9_g02Zj0Zax_y9J5S-B2oBxdzu6MgDhhlmXKsnF9cSeCfZUmcrqTQX7QASd1HmwHQfycOss3kpNIifa3TGXOGIgTFcfAj06mFV9i75Bb3-rQ_kWmosBCuxBjqqYKZ_3IYqDt3AiTEVqKWjEOgvmdrZUvY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660c567efb30490add46b6a9_g02Zj0Zax_y9J5S-B2oBxdzu6MgDhhlmXKsnF9cSeCfZUmcrqTQX7QASd1HmwHQfycOss3kpNIifa3TGXOGIgTFcfAj06mFV9i75Bb3-rQ_kWmosBCuxBjqqYKZ_3IYqDt3AiTEVqKWjEOgvmdrZUvY.webp)

Finally, using Merge, the leading unified API solution, you and/or your clients can use [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) to add custom objects and fields to Merge’s Common Models (Merge’s normalized data models for its software categories) to build highly-custom, customer-facing API integrations with ease.

[![How Merge's Field Mapping feature works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)

_You can use Field Mapping to add the “custom score” field in a client’s ATS solution to_ [_Merge’s Candidate Common Model_](https://docs.merge.dev/ats/candidates/) _, allowing you to sync this field with your product_

‍

Learn more about Merge and how you can use the platform to build customizable API integrations at scale by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcustom-api-integration).

## **Custom API integration FAQ**

In case you still have any questions on custom API integrations, we’ve addressed several more frequently-asked ones below.

### **What is needed for custom API integrations?**

At the most basic level, you need to know the endpoints that correspond to the objects and fields you want to connect to and either use a tool or rely on in-house developers to build and maintain the connections to these endpoints.

That said, since every custom API integration has unique requirements, sometimes you’re best suited to leverage in-house developers while in other cases it can make more sense to use a specific 3rd-party solution.

### **What are the benefits of custom API integrations?**

The benefits largely align with the [benefits of API integrations](https://www.merge.dev/blog/api-integration-benefits) more broadly.

In the case of internal custom API integrations, these include time savings, improved employer satisfaction, happier customers, and fewer human errors. And for custom API integrations that are customer-facing, you can experience higher customer retention, an improved close rate, and an easier path in expanding to more markets.

### **What is the difference between an API and a custom API?**

Standard API endpoints offer the same set of data and functionality for any consumer, while custom API endpoints can be tailored to a specific client or subset of clients. The vast majority of organizations provide and consume standard API endpoints.

### **What is the difference between a custom integration and a custom API integration?**

The only difference is in the method of connectivity that’s used. Like its name implies, custom API integrations only use API endpoints, while custom integration can also rely on files, screen scraping, among other approaches.

### **What are the different types of custom API integrations?**

As our examples showed, there are seemingly endless types of custom API integrations spanning different teams, applications, and data. Moreover, these integrations can be internal (i.e., between your organization’s applications) or customer-facing (i.e., between your product and your customers’ applications), which only increases the types of API integrations that can be built.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5464ae1a-2b93-4e90-bc13-e6bfbbc181c2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1552084f-504c-4307-ba8c-2d9f428a79fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-api-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5464ae1a-2b93-4e90-bc13-e6bfbbc181c2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1552084f-504c-4307-ba8c-2d9f428a79fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-api-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=c7698dd9-bb73-40a9-9f41-fbfc35d803db&bo=2&sid=afd969b03e8d11f0ac988f1c304495e4&vid=afd993c03e8d11f08280c1b0a5fdd59b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Custom%20API%20integration%3A%20here%E2%80%99s%20what%20you%20need%20to%20know&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcustom-api-integration&r=&lt=624&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=353577)