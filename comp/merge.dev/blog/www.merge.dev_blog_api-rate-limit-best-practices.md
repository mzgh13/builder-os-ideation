---
url: "https://www.merge.dev/blog/api-rate-limit-best-practices"
title: "7 API rate limit best practices worth following"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-rate-limit-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-rate-limit-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-rate-limit-best-practices#)

Table of contents

[Understand your specific rate limits](https://www.merge.dev/blog/api-rate-limit-best-practices#understand-your-specific-rate-limits)

[Use webhooks when they’re available](https://www.merge.dev/blog/api-rate-limit-best-practices#use-webhooks-when-theyre-available)

[Adopt exponential backoffs to minimize your rate limit errors](https://www.merge.dev/blog/api-rate-limit-best-practices#adopt-exponential-backoffs-to-minimize-your-rate-limit-errors)

[Track your API usage through the provider’s dashboard and/or endpoint](https://www.merge.dev/blog/api-rate-limit-best-practices#track-your-api-usage-through-the-providers-dashboard-andor-endpoint)

[‍Cut down on your API requests by batching them](https://www.merge.dev/blog/api-rate-limit-best-practices#cut-down-on-your-api-requests-by-batching-them)

[Cache responses for data that changes infrequently](https://www.merge.dev/blog/api-rate-limit-best-practices#cache-responses-for-data-that-changes-infrequently)

[Avoid concurrent requests](https://www.merge.dev/blog/api-rate-limit-best-practices#avoid-concurrent-requests)

[Integrate with the applications you care about without worrying about their rate limits with Merge](https://www.merge.dev/blog/api-rate-limit-best-practices#integrate-with-the-applications-you-care-about-without-worrying-about-their-rate-limits-with-merge)

[API rate limit FAQ](https://www.merge.dev/blog/api-rate-limit-best-practices#api-rate-limit-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-rate-limit-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**7 examples of using webhooks**](https://www.merge.dev/blog/webhook-examples)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)**A guide to managing REST API rate limits**](https://www.merge.dev/blog/rest-api-rate-limits)

# 7 API rate limit best practices worth following

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735d06bd38a725e7fb_Rate_limiting_best_practices.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As your organization builds to an API, you’ll need to ensure that the build carefully abides by the API provider’s rate limit policies.

Violating them can lead the provider to throttle your requests, block you from accessing their endpoints for a defined period of time, and/or charge you more.

To help you avoid these consequences, we’ll break down several best practices for staying within your rate limit for a given window.

## **Understand your specific rate limits**

Rate limits don’t just vary from application to application; they can also vary based on the endpoints you’re interested in, whether your requests are authenticated or not, the subscription you’re on, etc.

[![A screenshot from GitHub's documentation that confirms that authenticated requests have a higher rate limit than unauthenticated requests](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438a7afe10fcaa3bb9f2_9qAZUk4_n3XaiDfPiXiEk5OfWan-ajT9eZH_J95kOLVocrtS2qia5c2KI4U8Xr7ud3QiWkA53dhWl8ekO0vtHW05qw-0pr85FIWhuR9AaDJhMdKQ997aP99bGRC6iVLW8xAbbnfhx1Cw9Y8-QJnE4Lo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438a7afe10fcaa3bb9f2_9qAZUk4_n3XaiDfPiXiEk5OfWan-ajT9eZH_J95kOLVocrtS2qia5c2KI4U8Xr7ud3QiWkA53dhWl8ekO0vtHW05qw-0pr85FIWhuR9AaDJhMdKQ997aP99bGRC6iVLW8xAbbnfhx1Cw9Y8-QJnE4Lo.webp)

_GitHub, a developer platform, states in_ [_their API docs_](https://docs.github.com/en/rest/using-the-rest-api/best-practices-for-using-the-rest-api?apiVersion=2022-11-28) _that authenticated requests have a higher rate limit than unauthenticated requests_

Given all the variables that can influence a provider’s rate limits, it’s worth [taking a close look at their API documentation](https://www.merge.dev/blog/how-to-read-api-documentation) to understand your specific situation.

_Related:_ [_Best practices for managing API logs_](https://www.merge.dev/blog/api-logging-best-practices)

## **Use webhooks when they’re available**

Polling API endpoints to see if a resource has been modified, added, or removed can lead to countless wasted API calls. This is especially true when the requested resources change infrequently.

Webhooks allow you to avoid making these calls; you’ll simply receive responses from an application in real-time once the event you care about (e.g., new lead gets created in a CRM) is detected.

It’s worth noting that not all applications support webhooks for the endpoints you care about. So, like the previous best practice, you should review the application’s documentation to see whether they cover it.

[![A screenshot of GitHub's webhooks documentation](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438aa604c5350ce5888f_xL_4hPnLItfUaRFIJG8KWHvI63A5sY9SN0hS_89TEqOUICyan0TQO-PUGNjNg0nwc2fkJvOZmk62TV4dZuzu5HXBi1J4XD5U32Hf9L2mE_blW8C2ICLfUnZzZxv6cI3HauxFAIsJ9fJ4Wev3jV1iRvI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438aa604c5350ce5888f_xL_4hPnLItfUaRFIJG8KWHvI63A5sY9SN0hS_89TEqOUICyan0TQO-PUGNjNg0nwc2fkJvOZmk62TV4dZuzu5HXBi1J4XD5U32Hf9L2mE_blW8C2ICLfUnZzZxv6cI3HauxFAIsJ9fJ4Wev3jV1iRvI.webp)

_GitHub has dedicated ample_ [_documentation on its webhooks_](https://docs.github.com/en/webhooks) _, allowing its API consumers to not only confirm which endpoints they support but also how you can create and troubleshoot them effectively_

## **Adopt exponential backoffs to minimize your rate limit errors**

Exponential backoffs, which extend the length of time that passes for retrying requests every time a rate limit error occurs, aren’t a foolproof solution. That said, they can help minimize the number of times that you exceed an API provider’s limits in a given window.

Your exponential backoffs can start by doubling the waiting period for every failed attempt. But if that proves insufficient, you can use more aggressive increments for the delay period.

_Related:_ [_API pagination best practices_](https://www.merge.dev/blog/api-pagination-best-practices)

## **Track your API usage through the provider’s dashboard and/or endpoint**

You can proactively stay on top of your rate limits in a given window by using the API providers’ dashboards. Among other insights, they can show you how many API requests you’ve made in a given timeframe, along with how many requests you have available.

Similarly, some API providers let you call specific endpoints to get in-depth insights on your rate limit for a certain window.

For example, you can make the following API call to GitHub’s /rate\_limit endpoint—using cURL—to uncover all of the following information for a given window: the number of requests you’ve made to the endpoint, the amount of requests remaining, your total request limit, and when the window expires.

```python

curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer " \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/rate_limit

```

Note: Many API providers share information on the API calls remaining in the current rate limit window, when the window resets, and the total number of requests allowed during a window within their response headers. When that's the case, it won't make sense to call endpoints like the one referenced above.

## ‍ **Cut down on your API requests by batching them**

You can make less requests while still performing the same set of actions on resources by grouping, or batching, your requests.

However, not all API providers support batch requests, so you’ll need to review their API documentation to confirm that they do. In addition, API providers might have specific requirements, whether that's a certain limit in the number of requests you can make in a given batch, a maximum payload size per batch, etc. So you’ll need to research and understand these requirements for each API provider before going on try this approach.

_Related:_ [_How to poll API endpoints effectively_](https://www.merge.dev/blog/api-polling-best-practices)

## **Cache responses for data that changes infrequently**

In some cases, you’ll need to fetch the same resources over time and they won’t change often. This can take the form of an image, details on a product, information on an employee, etc.

Whenever that’s the case for your integration(s), you can cache the initial API response, allowing you to fetch it in the future quickly and without having to make additional API calls. Moreover, you can adopt caching mechanisms that use expiration policies (based on how often the data typically changes), and time your API requests at points of expiration.

## **Avoid concurrent requests**

Concurrent requests, or requests that overlap in timing for a given API, can also lead you to hit your rate limit quickly, preventing you from accessing the data you need on a steady cadence over time.

To help prevent concurrent requests, you can adopt any number of approaches, from using request queues to implementing request throttling to leveraging caching (see previous best practice).

## **Integrate with the applications you care about without worrying about their rate limits with Merge**

Merge, the leading unified API solution, lets you add hundreds of integrations to your product by integrating with its unified API.

Merge's unified approach to integration removes the complexities associated with building and maintaining individual customer-facing API integrations. In other words, you don’t need to worry about individual API provider’s rate limits, along with other aspects, like how they approach pagination and authentication.

You can learn more about Merge and its unified API by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-rate-limit-best-practices).

## **API rate limit FAQ**

In case you have any more questions on API rate limits, we’ve addressed several more below.

### **What is API rate limiting?**

It’s the maximum number of requests that an API provider permits a client. This limit is imposed to prevent the provider’s server from getting overwhelmed, avoid security incidents, allow for equal usage across consumers, and more.

### **What is a typical API rate limit?**

There isn’t a typical API rate limit; every API provider imposes unique limits on their endpoints. With this in mind, you’ll need to carefully review each API provider’s documentation to better understand the limits for the endpoints you’re planning to use.

### **How long does a rate limit last?**

There isn’t a hard set rule for a rate limit window’s duration. It depends on the API provider and the specific endpoint you’re looking at using, so you should review the API provider's documentation to get a better idea of a given endpoint's rate limit window.

### **What is the difference between API rate limiting and API throttling?**

API rate limiting is a subset of API throttling. The latter can include other methods to manage clients’ requests over time, such as the Token Bucket Algorithm or the Leaky Bucket Algorithm.

### **What is the main goal of an API rate limit?**

It’s to control the volume of requests clients make to an endpoint over time. By doing so, the API provider can provide a consistent level of service to consumers, ensure access to more consumers, avoid security issues (e.g., denial-of-service attacks), control computational costs, and more.

### **What is the problem with rate limiting?**

It can prevent consumers from accessing a resource on time, which, depending on the scenario, can have negative consequences for clients.

For instance, if a client is trying to get warm leads from a marketing automation system and they have to wait until the rate limit window resets, enough time may pass such that the leads go cold and have a lower chance of responding.

### **What is a good rate limit for an API?**

It depends on the type of resource you’re looking to access and your specific syncing needs. In some cases, a good rate limit can be thousands of requests per hour while in other cases it can be tens of requests within that same timeframe.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e4b02437-650c-4efe-b2b2-f1617c69f8c0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1b8d0dac-8a66-475d-80ec-9e02b01526d1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-rate-limit-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e4b02437-650c-4efe-b2b2-f1617c69f8c0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1b8d0dac-8a66-475d-80ec-9e02b01526d1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-rate-limit-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=88bc6bf8-7ecc-45fa-9898-b027863b03d3&bo=2&sid=97567be03e8c11f087d455fe35115914&vid=9756f7303e8c11f0a506fd63e5c3cb07&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=7%20API%20rate%20limit%20best%20practices%20worth%20following&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-rate-limit-best-practices&r=&lt=481&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=475618)