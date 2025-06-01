---
url: "https://www.merge.dev/blog/api-pagination-best-practices"
title: "10 API pagination best practices in 2025"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-pagination-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-pagination-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-pagination-best-practices#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-pagination-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**7 best practices for polling API endpoints**](https://www.merge.dev/blog/api-polling-best-practices)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**A guide to offset pagination**](https://www.merge.dev/blog/offset-pagination)

# 10 API pagination best practices in 2025

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7ab3275842f0c7906f8_API_pagination_best_practices.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

A wide range of API providers use pagination to help preserve their server load, deliver responses faster, and only provide clients the data they need, when they need it.

That said, using API pagination effectively—both as a consumer and as a provider—isn’t necessarily easy.

We’ll help both parties leverage [API pagination](https://www.merge.dev/blog/rest-api-pagination) successfully by breaking down several best practices. To start, let’s cover a few best practices for providers.

### **Adopt the pagination type that’s best suited for each endpoint**

Some of your endpoints will naturally return a high volume of data, such as employees if you’re a large company; while other types of data will return a smaller volume, like candidates if your company isn't hiring aggressively. In addition, many of your endpoints will return data types that frequently change (e.g., marketing qualified leads) and others that won’t (e.g., files on employees).

Based on how frequently data changes and the volume of data that’s stored, you’ll want to adopt a specific type of pagination.

[![The different types of API pagination](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673f7ff9d6cba6e9ca70169f_673f7fc37ca707439fc33edc_API%2520Pagination%2520Types.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673f7ff9d6cba6e9ca70169f_673f7fc37ca707439fc33edc_API%2520Pagination%2520Types.webp)

For example, when a data set changes frequently and is large, it might be best to use [cursor-based pagination](https://www.merge.dev/blog/cursor-pagination). Reason being, if data in the data set is modified, added, or removed, your future requests can capture these changes. Moreover, it can use database indexes to quickly find the starting point for the next set of results, which naturally lowers the load on the database and improves response times.

_Related:_ [_How keyset pagination works_](https://www.merge.dev/blog/keyset-pagination)

### **Use page sizes that provide ample information but don’t compromise on performance**

In many, if not most, cases, your API consumers won’t provide explicit guidance on how they want to paginate the responses, putting the burden on you instead.

With that in mind, you should opt for page sizes that won’t strain your resources and delay your response time but still provide enough information per page that clients aren’t forced to make immediate follow-up requests.

It’s a tricky balance to strike and might require some level of optimization over time, but the long-term benefits for both clients and your business make the effort worthwhile.

### **Don’t use pagination for certain endpoints**

In cases where an API endpoint typically returns a small set of data (and that’s unlikely to change) and/or when the API endpoint’s data is constantly evolving, it might not make sense to use pagination. There’s countless examples here, from getting the status of an IoT device to receiving a report from a security scan.

### **Share details on how to use pagination in your documentation**

Your API consumers might struggle with incorporating pagination in their requests.

To provide some guidance, you can outline the specific query parameters they should use and how each works. You can go a step further by showing a specific example of using these parameters and how the response can look.

For example, [Sendoso’s documentation](https://developer.sendoso.com/rest-api/overview/pagination) clearly outlines all of these details.

They explain that you can use _page_ and _page\_size_ query parameters to retrieve specific results. They then go on to use the following example:

```python

GET https://app.sendoso.com/campaigns?page=2&per_page=50

```

They explain that the consumer is looking to get campaigns run through Sendoso, but to bucket the campaigns by 50 per page and to only share the 2nd page of campaigns.

They then provide the following response (which uses an ellipses in place of where the campaign data would appear):

```python

{
  "campaigns": [...],
  "current_page": 2,
  "per_page": 50,
  "total_campaigns": 234
}

```

### **Test for edge cases**

To validate a pagination build and save your engineers and API consumers future headaches, you should test for less common scenarios prior to releasing the associated API endpoint.

More specifically, you can test how a response comes back for any of the following scenarios:

- When one of the pages is empty, as none of the data on the page matches what you’re requesting
- When items on a page are below the limit (e.g., the last page in a data set)
- When a page contains one item, either due to filtering or because the data set is small

Note: The rest of our best practices apply to API consumers.

### **Research the different pagination options to pinpoint the best one for your needs**

For some endpoints, you have the choice of which API pagination approach to use; while other endpoints don’t provide pagination at all.

In cases where your situation is the former, you should carefully consider your options and see which one best meets your needs. As an example, NetSuite, an ERP system, [offers offset-based pagination](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_156414087576.html#Collection-Paging) and [page-based pagination](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_N3523074.html#bridgehead_1509528108).

_Related:_ [_Best practices for managing API rate limits_](https://www.merge.dev/blog/api-rate-limit-best-practices)

### **Use parameters to only retrieve the data you need, quickly**

Use certain parameters, like _limit_ or _offset_, to minimize the data you get in a given response. This gives you more control over how much data you collect, which in turn can let you balance receiving the data you need while not straining your resources.

### **Leverage pagination metadata**

API responses typically include metadata in responses that share how pagination is handled (e.g., `next` or `has_more`).

You should proactively research the metadata the API provider uses so that you can add logic to paginate through responses either automatically or on time-based intervals (to avoid the provider’s rate limits).

You can also build logic such that once the metadata reveals that there’s no more data (e.g., `next` field is null or `has_more` is false), you’ll stop making requests to that endpoint.

### **Prevent cursors or session tokens from expiring**

Cursors or session tokens are typically valid for a specific period of time, which is determined by the API provider.

To prevent using any that expired, you can check the API provider’s documentation to confirm their validity period and then structure your requests with the appropriate cadence.

Some cursors and session tokens may also include metadata around their expiration or length of validity (e.g., `cursor_expiration`). You can use this data to determine how quickly to sequence your requests and when you need to refresh the cursor. In the case of the latter, you can use something like the code snippet below to request a new cursor before the existing one expires:

```python

from datetime import datetime
if 'cursor_expiration' in metadata:
    expiration_time = datetime.fromisoformat(metadata['cursor_expiration'])
    if expiration_time <= datetime.now():
        cursor = None  # Reset and request a fresh cursor

```

In cases where cursors or session tokens don't provide metadata, it may be best to make all of the requests within a cursor's/token's lifespan (assuming this still follows the API provider's rate limits). And as you receive responses you don't immediately need, you can cache them and then process them later.

### **Store your last cursor or field value in a secure place**

APIs that use cursor or keyset-based pagination will provide a cursor or field value, respectively, that lets you determine the starting point of the next page.

By storing either of these items, you can reuse them when unforeseen events take place, such as app crashes, API outages, network issues, etc. and not lose data or make redundant requests.

### **Avoid dealing with different API providers’ approaches to pagination with Merge**

As you look to build and maintain customer-facing integrations, the process of understanding how different API endpoints use pagination—and then structuring your responses accordingly—can prove overwhelming.

To help you avoid this complexity, you can use Merge, the leading unified API solution.

Through Merge, you can simply build to a single, aggregated API to add hundreds of integrations to your product. This means that you only have to consider [Merge’s approach to pagination](https://docs.merge.dev/basics/pagination/)—along with rate limits and authentication.

You can learn more about how Merge handles pagination—and how Merge works more broadly—by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-pagination-best-practices).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5100b8ec-1e8f-44bc-b88c-abcf84a44001&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5cb3c10c-8841-4cf7-bc28-989491f84054&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5100b8ec-1e8f-44bc-b88c-abcf84a44001&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5cb3c10c-8841-4cf7-bc28-989491f84054&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=83306fd5-8529-4e2f-b763-8136c98e4521&bo=2&sid=edfd32b03e8b11f08c900f042800be76&vid=edfd98903e8b11f0ae5bef145f4a2362&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=10%20API%20pagination%20best%20practices%20in%202025&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-best-practices&r=&lt=531&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=587230)