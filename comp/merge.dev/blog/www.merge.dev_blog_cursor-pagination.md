---
url: "https://www.merge.dev/blog/cursor-pagination"
title: "Cursor pagination: how it works and its pros and cons"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/cursor-pagination#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/cursor-pagination#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/cursor-pagination#)

Table of contents

[What is cursor pagination?](https://www.merge.dev/blog/cursor-pagination#what-is-cursor-pagination)

[Cursor pagination examples](https://www.merge.dev/blog/cursor-pagination#cursor-pagination-examples)

[Pros and cons of cursor pagination](https://www.merge.dev/blog/cursor-pagination#pros-and-cons-of-cursor-pagination)

[Manage pagination with ease by using Merge](https://www.merge.dev/blog/cursor-pagination#manage-pagination-with-ease-by-using-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcursor-pagination)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74fb72017b567d9265_RAG_benefits.webp)**Top challenges of API pagination for multiple integrations**](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is integration monitoring? Plus tips for performing it**](https://www.merge.dev/blog/integration-monitoring)

# Cursor pagination: how it works and its pros and cons

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to optimize your API requests, you’ll likely consider different types of pagination, or methods of returning data from API calls.

One of your options is cursor-based pagination, or, put more simply, cursor pagination.

We’ll break down how this method works and its pros and cons so that you can better decide whether to use it for your API-based integrations.

## **What is cursor pagination?**

It’s a pagination method that lets you fetch data from a resource incrementally. The method involves a cursor that uses a unique identifier (e.g., timestamp) to fetch data in a specific order.

The cursor is typically included as a parameter in an API request, as is the amount of data that should be returned.

[![An example of a request that uses cursor pagination](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf41f8f17940c5518d2e62_668c9dfb5fc478bb9bcab1d6_Screenshot%25202024-07-08%2520at%252010.18.01%25E2%2580%25AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf41f8f17940c5518d2e62_668c9dfb5fc478bb9bcab1d6_Screenshot%25202024-07-08%2520at%252010.18.01%25E2%2580%25AFPM.webp)

The response payload will include the next and previous cursors, which inform what the cursor should be for the following request (assuming there’s data left to be fetched).

_Related:_ [_What is REST API pagination?_](https://www.merge.dev/blog/rest-api-pagination)

#### **Cursor pagination vs offset pagination**

It’s easy to confuse cursor pagination with other approaches, particularly [offset pagination](https://www.merge.dev/blog/offset-pagination).

However, offset pagination presents an entirely different way to fetch data; it lets you determine the starting point for returning records and the number of records to retrieve from a given request.

You’ll likely need to evaluate their respective pros and cons before choosing between them. But in some cases, you may not have an option; the API provider may force you to use a specific approach.

#### Avoid managing pagination across your integrations

Simply build to Merge's Unified API to add hundreds of API-based integrations to your product.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcursor-pagination)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Cursor pagination examples**

To help bring our definition of cursor pagination to life, let’s break down a few examples.

#### **Retrieving tickets**

Say you want to fetch support tickets and want the cursor to be based on the time a ticket gets created. That way, you can collect all the tickets that get created over time. You’ll also want each request to fetch a certain amount of ticket data.

Here’s an example of a follow-up API request:

```python

GET /api/tickets?page_size=15&cursor=eyJjcmVhdGVkX2F0Ij

```

#### **Gathering employees**

Let’s also imagine that you want to gather all the employees at your organization via cursor pagination.

You can use hire date as the cursor to ensure every employee gets accounted for, and you can limit the employee data that gets collected for each response by a certain figure.

Here’s how a noninitial request can look:

```python

GET /api/employees?page_size=10&cursor=eyJoaXJlX2RhdGUiO

```

_Related:_ [_Best practices for performing API pagination_](https://www.merge.dev/blog/api-pagination-best-practices)

#### **Collecting sales orders**

Finally, if you want to collect your business’ sales orders, you can use cursor pagination to prevent any transaction from slipping through the cracks.

The cursor can be set as the order date and, like our other examples, the number of orders retrieved per request can be limited by a predefined number.

Here’s how you can structure a request that comes after the first one:

```python

GET /api/sales_orders?page_size=5&cursor=eyJvcmRlcl9kYXRlIjoiMj

```

## **Pros and cons of cursor pagination**

To help you decide whether you should implement cursor pagination, it’s worth understanding and weighing the approach’s pros and cons.

#### **Benefits of cursor pagination**

- Enables you to collect every item in a list, regardless of a data set’s size or how frequently it changes
- Allows you to define how much data gets collected in every request, which helps ensures that requests get processed quickly
- Offers a simple way to fetch data over time, as you only need to track requests by the last record fetched

#### **Drawbacks of cursor pagination**

- Requires a certain level of technical expertise to set up and maintain cursors, leaving the task to select members of your engineering team
- Fails to accommodate relatively complex sorting scenarios that, in some cases, are necessary
- Forces you to gather all of the data sequentially, which can be inconvenient if you’re only looking to collect a specific part of a data set

_Related:_ [_Benefits and drawbacks of keyset pagination_](https://www.merge.dev/blog/keyset-pagination)

## **Manage pagination with ease by using Merge**

Merge, the leading unified API solution, lets you connect your product with hundreds of 3rd-party SaaS applications through the platform’s unified API.

This means you only have to consider how [Merge’s Unified API handles pagination](https://docs.merge.dev/basics/pagination/) (among other items, like rate limits and authentication), helping you scale your integration builds more quickly and maintain them more easily.

You can learn more about Merge’s Unified API, among the platform’s other features, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcursor-pagination).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a12b86df-eef1-486d-9f65-eac17455097b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=abc294f0-f5d5-4ced-89ff-ee734ad10e6a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcursor-pagination&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a12b86df-eef1-486d-9f65-eac17455097b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=abc294f0-f5d5-4ced-89ff-ee734ad10e6a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcursor-pagination&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=462d5c64-6d1a-46f8-8767-23609e990a9c&bo=2&sid=269730603e8d11f0b986a7cf6ce9f732&vid=2697bc203e8d11f0ac9d7f2a1083c1c2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Cursor%20pagination%3A%20how%20it%20works%20and%20its%20pros%20and%20cons&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcursor-pagination&r=&lt=1091&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=43929)