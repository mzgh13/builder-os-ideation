---
url: "https://www.merge.dev/blog/api-polling-best-practices"
title: "7 best practices for polling API endpoints"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-polling-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-polling-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-polling-best-practices#)

Table of contents

[What is API polling?](https://www.merge.dev/blog/api-polling-best-practices#what-is-api-polling)

[API polling best practices](https://www.merge.dev/blog/api-polling-best-practices#api-polling-best-practices)

[Poll 3rd-party APIs effectively and at scale with Merge](https://www.merge.dev/blog/api-polling-best-practices#poll-3rd-party-apis-effectively-and-at-scale-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-polling-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c750ee25c62b0a40a3d_Two-way_API_integration.webp)**Common examples of API polling**](https://www.merge.dev/blog/api-polling-examples)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadbbb5568970b2d91a_8.webp)**4 common API integration challenges (based on our research)**](https://www.merge.dev/blog/api-integration-challenges)

# 7 best practices for polling API endpoints

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to interact with 3rd-party APIs, you’ll likely defer to polling API endpoints.

The reason can come down to a number of factors: It’s supported by nearly all HTTP-based APIs; it offers predictability, which can help your team identify requests that don’t work as expected; and it allows you to control how often requests are made—enabling you to accommodate a range of scenarios.

The process of implementing API polling effectively, however, can be difficult.

We’ll help you set it up effectively—no matter your integration scenario—by covering several best practices. But first, let’s align on the definition of API polling.

_Related:_ [_A guide to API error handling_](https://www.merge.dev/blog/api-error-handling)

## **What is API polling?**

It’s when a client makes an API request to a 3rd-party API endpoint at recurring intervals. These intervals are typically time-based (e.g. every hour), but they can also be randomized.

[![A visualization of API polling](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecdf6c69d207d93768a_zfx7reFlc5qzy4KJlQYsbpKbnEdA7a7QIqt4etaEvRdYyw7QUZZ1ZF8Ckzui3w3YZP_8MP68GFvfaBd6GsavLNynZfSDH-a-NYQG3OcvAPYfy9JZC_tdfG3XsCPJoNcEfoz0KGmRWJuUDc5rDCby-TQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecdf6c69d207d93768a_zfx7reFlc5qzy4KJlQYsbpKbnEdA7a7QIqt4etaEvRdYyw7QUZZ1ZF8Ckzui3w3YZP_8MP68GFvfaBd6GsavLNynZfSDH-a-NYQG3OcvAPYfy9JZC_tdfG3XsCPJoNcEfoz0KGmRWJuUDc5rDCby-TQ.webp)

#### Avoid managing API syncs at scale

Simply build to Merge's Unified API to add hundreds of integrations to your product.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-polling-best-practices)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **API polling best practices**

While it’s impossible to cover every best practice, here are several worth following.

### **1\. Set up your API call frequency based on how often the requested data changes**

Certain types of data will naturally get added, modified, or removed more frequently than others. This includes data on leads, product inventory, and support tickets. On the other hand, there’s data that’s less likely to change as often, such as data on clients or employees.

It’s worth taking the time to evaluate how often certain types of data change at your business, and, based on what you find, implement requests that correspond with that frequency.

### **2\. Implement exponential backoffs to minimize unnecessary API calls**

Your API requests can fail for reasons that fall outside your control (e.g. a temporary server outage).

You can use exponential backoff to reduce your polling frequency whenever this happens. In return, you’ll potentially help the server recover faster, make fewer API calls that return errors, and reduce your chances of hitting your rate limit.

### **3\. Incorporate error-handling workflows to manage potential errors successfully**

Your API requests can also fail for a number of reasons. For instance, the server may be experiencing a temporary outage, a high load, or undergoing maintenance. And your requests can be faulty, whether that’s because they don't include authorization details in the header, use the wrong data format, overlook pagination, etc.

To account for every potential issue, you can implement error-handling processes for different scenarios. For instance, if the issue is on the server side, you can use exponential backoffs, timeouts, fallback mechanisms, and more to limit adverse outcomes.

_Related:_ [_Best practices for managing API logs_](https://www.merge.dev/blog/api-logging-best-practices)

### **4\. Notify affected users when API requests get delayed**

You likely have key stakeholders who expect data to get added to, modified in, or removed from  the applications they use on time.

If your API integrations fail to deliver on this expectation, it’s critical to let them know there’s a delay, why it’s happening, and how long the request will likely take to complete. You can deliver this message in a place they likely check often, such as Slack or their email, so it’s easy for them to keep abreast of the situation.

[![A visualization of a workflow that notifies users when there are integration issues](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc0e_PyU_jPFYmCbajJTG8WHXwZ0lFhbycikT31_bIuRi-cwjXLpZJaUysnLRjuk_1Rnd0bv2RYrTvS3MFUJWecXwnOBxcPC-f8CH0O_6ZdrSnnf8I5FeXD-uYpMq0gXuWh9ID7b66IBjik_fb9x6m4TH_Pw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc0e_PyU_jPFYmCbajJTG8WHXwZ0lFhbycikT31_bIuRi-cwjXLpZJaUysnLRjuk_1Rnd0bv2RYrTvS3MFUJWecXwnOBxcPC-f8CH0O_6ZdrSnnf8I5FeXD-uYpMq0gXuWh9ID7b66IBjik_fb9x6m4TH_Pw.webp)

_Using a monitoring tool like Datadog, your team can identify issues and then go on to diagnose them. Your team can then share updates with affected individuals through apps like Slack and Gmail._

### **5\. Perform load testing to proactively assess your polling strategy**

While you may want to make make requests at a certain cadence, the server that receives the requests may be unable to handle that frequency—leading the server to increase its response time or even fail to respond.

You can determine the optimal polling frequency by performing load testing; which essentially involves testing the server with varying volumes of requests over specific intervals to see how it responds.

_Related:_ [_Examples of webhook events_](https://www.merge.dev/blog/webhook-events)

### **6\. Evaluate the API provider’s pricing model to optimize your costs**

Every API provider offers different pricing models; and while many providers charge based on the number of requests you make, some don’t or they’ll offer a generous number of requests for a specific time period.

[![A screenshot of GitHub's API documentation](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc32_CK20egd59IRGxzBo7cIE8SKpxxsKG10Pv5h_lvFbTAXHiOfSsamIOKqm82JOrAPxy2QQ_bxHPTGPT6rMV4zjxO9znh9V_QRTGJkul4zplxPfFLvkY70pvXPxDU66QTRigGkSY5bO8SMYXDuEJkyVZkc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc32_CK20egd59IRGxzBo7cIE8SKpxxsKG10Pv5h_lvFbTAXHiOfSsamIOKqm82JOrAPxy2QQ_bxHPTGPT6rMV4zjxO9znh9V_QRTGJkul4zplxPfFLvkY70pvXPxDU66QTRigGkSY5bO8SMYXDuEJkyVZkc.webp)

_GitHub, a developer platform for creating, storing, managing, and sharing code, allows users on their free plan to make 5,000 requests every hour. Most API providers aren’t that giving._

It’s worth taking the time to understand each API provider’s pricing model across subscription levels so that you can set up your requests in a way that’s most cost-effective for your business.

### **7\. Track the server’s performance so that you can adjust your polling as necessary**

A server’s load will likely vary over time. Keeping tabs on it consistently allows you to identify when it’s overloaded—in which case you may want to decrease the frequency of your requests—and underutilized—which can encourage you to make more requests, or at least keep the cadence unchanged.

The server may also change in meaningful ways over time that impact their performance (e.g. configuration changes). Staying on top of these changes can help you adjust your polling strategy effectively.

_Related:_ [_A guide to API integration best practices_](https://www.merge.dev/blog/api-integration-best-practices)

## **Poll 3rd-party APIs effectively and at scale with Merge**

Implementing these best practices for _every customer-facing integration_ you want to support can be extremely resource and time intensive.

Fortunately, you can avoid this work all together with Merge, a single API to offer hundreds of integrations with your product.

Through Merge, you can build once and only poll our unified API. We’ll poll the 3rd-party applications on your behalf and follow each vendor’s nuanced integration requirements, from their rate limits to their approach to pagination—ensuring that our data syncs optimally for every integration.

Learn more about how Merge approaches polling and uncover additional facets of our platform by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-polling-best-practices).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=0f7580f8-5ddd-4fbc-b7b9-db011a69a8b7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6703ace9-f091-4ca4-8909-45174ada1b6a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=0f7580f8-5ddd-4fbc-b7b9-db011a69a8b7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6703ace9-f091-4ca4-8909-45174ada1b6a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e6b68aff-5574-46cc-96c5-0177177b3110&bo=2&sid=c17a86903e8b11f0be711fe4db44a6f7&vid=c17aac303e8b11f0bb97ad4bf90fd48a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=7%20best%20practices%20for%20polling%20API%20endpoints&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-best-practices&r=&lt=703&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=13894)