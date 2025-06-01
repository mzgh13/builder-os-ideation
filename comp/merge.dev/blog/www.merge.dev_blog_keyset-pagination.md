---
url: "https://www.merge.dev/blog/keyset-pagination"
title: "Keyset pagination: how it works, examples, and pros and cons"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/keyset-pagination#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/keyset-pagination#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/keyset-pagination#)

Table of contents

[What is keyset pagination?](https://www.merge.dev/blog/keyset-pagination#what-is-keyset-pagination)

[Examples of keyset pagination](https://www.merge.dev/blog/keyset-pagination#examples-of-keyset-pagination)

[Keyset pagination pros and cons](https://www.merge.dev/blog/keyset-pagination#keyset-pagination-pros-and-cons)

[Integrate at scale without worrying about pagination by using Merge](https://www.merge.dev/blog/keyset-pagination#integrate-at-scale-without-worrying-about-pagination-by-using-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fkeyset-pagination)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is a two-way sync? Here’s what you need to know**](https://www.merge.dev/blog/two-way-sync)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74fb72017b567d9265_RAG_benefits.webp)**Top challenges of API pagination for multiple integrations**](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations)

# Keyset pagination: how it works, examples, and pros and cons

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

To help you collect API responses more efficiently, save bandwidth, reduce memory consumption, and improve performance, you can use API pagination—a method of retrieving response data in manageable chunks.

And while there’s a variety of different types of API pagination to choose from, one of the options at the top of your list is likely keyset pagination (i.e., "seek pagination").

We’ll help you determine whether you should use keyset pagination by breaking down how it works, highlighting examples of it, sharing its pros and cons, and more.

## **What is keyset pagination?**

It’s a pagination method that uses a key (e.g., ID) to help the client and the server request and provide progressive sets of data.

More specifically, the client uses the key within the request to indicate the starting point for the next set of results; while the API response includes what the next key should be.

[![How keyset pagination works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf41e0eb4ae1116039e507_66956a518f29f0a91b625b0b_Screenshot%25202024-07-15%2520at%25202.28.12%25E2%2580%25AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf41e0eb4ae1116039e507_66956a518f29f0a91b625b0b_Screenshot%25202024-07-15%2520at%25202.28.12%25E2%2580%25AFPM.webp)

_The key in this example is an ID. It can also use other identifiers, such as a timestamp_

To help clarify our definition, let’s differentiate keyset pagination from other pagination methods.

#### Avoid managing pagination across your integrations

Simply build to Merge's Unified API to add hundreds of API-based integrations to your product.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fkeyset-pagination)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### **Keyset pagination vs offset pagination**

While both methods use a starting point to fetch records and define how much data to fetch from a given request, keyset pagination doesn’t skip records, while [offset pagination](https://www.merge.dev/blog/offset-pagination) can.

### **Keyset pagination vs cursor pagination**

The two methods are very similar to one another. The main difference between them is how they handle position tracking and the continuation of data retrieval.

_Related:_ [_What is cursor-based pagination?_](https://www.merge.dev/blog/cursor-pagination)

## **Examples of keyset pagination**

To help bring our definition to life, let’s break down a few examples of keyset pagination.

### **IDs**

Say an application tracks a certain type of data, like a product, by its IDs.

To help you fetch the next set of products in that application's server, you can include the ID in the API request as follows: `GET /api/products?last_id=1023&limit=10`

### **Timestamps**

Imagine the data you want to retrieve uses timestamps that are structured in a certain format.

You can then use a key that denotes the last timestamp you fetched in your API request using that format. Here’s how it can look: `GET /api/events?last_timestamp=2023-07-14T12:00:00Z&limit=10`

### **IDs and timestamps combination**

In some cases, you might need to rely on both IDs and timestamps to gather data in the correct order.

When that’s the case, you can use both the last ID and the last timestamp fetched, leading your request to look something like the following: `GET /api/messages?last_id=5678&last_timestamp=2023-07-14T11:59:59Z&limit=10`

_Related:_ [_Best practices for performing API pagination_](https://www.merge.dev/blog/api-pagination-best-practices)

## **Keyset pagination pros and cons**

To help you decide whether to perform keyset pagination, you’ll need to consider the approach’s pros and cons.

### **Benefits of keyset pagination**

- **Isn’t affected by most changes in the server’s database** since each request’s key points to the last item retrieved and generally only needs this reference point to function properly **‍**
- **Saves computational costs** since each API request doesn’t require counting and skipping rows **‍**
- **Offers consistent performance** since each API request jumps to a defined point in the dataset and retrieves the same number of records **‍**
- **Relatively easy to implement** since it primarily just requires using a last seen key in the requests. That said, the implementation can vary depending on the data's structure and the complexity of the API's requirements

### **Drawbacks of keyset pagination**

- **Forces you to collect each data point.** In some cases, you’ll want to skip certain parts of a data set; doing so through keys can prove technically complex when compared to, say, offset pagination
- **Volatile data sets can negatively affect performance.** For instance, if the last seen key is deleted, your implementation of keyset pagination may not function correctly **‍**
- **Requires you to use forward navigation.** Collecting previous data can be difficult to set up since keyset pagination uses forward navigation by default **‍**
- **Handling non-uniform data can be difficult.** For example, if data points have overlapping timestamps, your implementation of keyset pagination may fail to segment and return the data properly

## **Integrate at scale without worrying about pagination by using Merge**

While implementing keyset pagination for one API provider might not be time and resource intensive, you’re likely looking to integrate with several other API providers. And since each provider has unique pagination requirements, your engineers will likely quickly find themselves consumed with meeting them.

To help you avoid this challenge, you can use Merge, the leading unified API solution.

[![How Merge works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669569d52620aafabacd40f6_AD_4nXfNLaah1tt2Gni4AnpodYj_uilB_Oh2zcgXfetsKxJFjjz19BkP0KqGn60yD-QTfquIAr9QiRtvaEigrAQoO1ht4vlzBwB4kevuiwUYiix0WlkBH8WBNJjcyca5CKb6njEcJCxgZHha_Sy0EF47NWagVzTp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669569d52620aafabacd40f6_AD_4nXfNLaah1tt2Gni4AnpodYj_uilB_Oh2zcgXfetsKxJFjjz19BkP0KqGn60yD-QTfquIAr9QiRtvaEigrAQoO1ht4vlzBwB4kevuiwUYiix0WlkBH8WBNJjcyca5CKb6njEcJCxgZHha_Sy0EF47NWagVzTp.webp)

Merge lets you avoid dealing with individual API providers' approaches to authentication, rate limits, and pagination, allowing you to scale your integration builds more easily

Merge lets you only worry about their unified API’s approach to pagination, rate limits, and authentication, while letting you access hundreds of integrations across software categories, such as HRIS, file storage, ATS, and accounting.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fkeyset-pagination).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=72e0e105-60e5-4a57-96ac-68bbb997edc2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=55edc112-beed-4f41-a4d7-f8af9231230b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fkeyset-pagination&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=72e0e105-60e5-4a57-96ac-68bbb997edc2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=55edc112-beed-4f41-a4d7-f8af9231230b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fkeyset-pagination&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=1100b9ac-f6c7-415d-afe5-552309d9f017&bo=2&sid=ebd53fe03e8d11f098d12945004aaee0&vid=ebd584203e8d11f08fb7695203ef0356&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Keyset%20pagination%3A%20how%20it%20works,%20examples,%20and%20pros%20and%20cons&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fkeyset-pagination&r=&lt=459&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=964832)