---
url: "https://www.merge.dev/blog/offset-pagination"
title: "A guide to offset pagination"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/offset-pagination#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/offset-pagination#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/offset-pagination#)

Table of contents

[What is offset pagination?](https://www.merge.dev/blog/offset-pagination#what-is-offset-pagination)

[Offset pagination examples](https://www.merge.dev/blog/offset-pagination#offset-pagination-examples)

[Offset pagination pros and cons](https://www.merge.dev/blog/offset-pagination#offset-pagination-pros-and-cons)

[Manage pagination with ease by using Merge](https://www.merge.dev/blog/offset-pagination#manage-pagination-with-ease-by-using-merge)

[Offset pagination FAQ](https://www.merge.dev/blog/offset-pagination#offset-pagination-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Foffset-pagination)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How to use SDKs to build and maintain API integrations**](https://www.merge.dev/blog/sdk-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is integration monitoring? Plus tips for performing it**](https://www.merge.dev/blog/integration-monitoring)

# A guide to offset pagination

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

To help you fetch data from a 3rd-party resource quickly and without overwhelming your server, you’ll need to leverage API pagination.

And while there are many pagination methods to consider, offset pagination, or offset-based pagination, is likely at the top of your list.

We’ll break down how this method works so that you can decide whether it’s the right fit for any of your integration scenarios.

## **What is offset pagination?**

It’s an approach to pagination that, for a given request, uses an offset to determine the starting point of data to fetch and a limit to cap the volume of data that's returned.

[![Example of offset pagination](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf3dd0dceb8a7109a9ba48_AD_4nXd0g3EQpD440a1rOhELFdt3hv72umCVW8qjbJf4XN0xxWdXfo80tzTvm5ttpLe6SxuU_bZTYuCNRXko6hD-JNGW0KA2OmiOQenJP4PaTH_cUMYG9wHQgwP9EoDY11wwk4BLAwEg09gtUfKM6OZ8jxwyZDCv.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf3dd0dceb8a7109a9ba48_AD_4nXd0g3EQpD440a1rOhELFdt3hv72umCVW8qjbJf4XN0xxWdXfo80tzTvm5ttpLe6SxuU_bZTYuCNRXko6hD-JNGW0KA2OmiOQenJP4PaTH_cUMYG9wHQgwP9EoDY11wwk4BLAwEg09gtUfKM6OZ8jxwyZDCv.webp)

To prevent any confusion, we’ll distinguish offset pagination from other methods.

#### **Offset pagination vs cursor pagination**

[Cursor pagination](https://www.merge.dev/blog/cursor-pagination) lets you define the starting point of each request via a unique identifier (e.g., a timestamp), while offset pagination simply skips a predefined set of items with each request.

#### **Offset pagination vs keyset (i.e., seek) pagination**

[Keyset pagination](https://www.merge.dev/blog/keyset-pagination) uses a key to determine the starting point of a request while offset pagination just skips a predetermined set of data.

#### **Offset pagination vs token-based pagination** ‍

Similar to the methods above, token-based pagination uses a token in a given request to signify the starting point for fetching data; offset pagination doesn’t use a token—or any unique identifier—to fetch data across requests.

#### Avoid managing pagination across your integrations

Simply build to Merge's Unified API to add hundreds of API integrations to your product.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Foffset-pagination)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Offset pagination examples**

To help bring our definition to life, let’s walk through a few examples of offset pagination.

#### **Employees**

Say you want to get a list of employees from an HRIS solution and each page includes 30 employees.

Your first request can be structured as follows:
`GET /v1/employees/?offset=0&limit=30`

#### **Product reviews**

Say you want to fetch reviews from a specific product (e.g., product ID=12345) and from a certain site. Let’s also assume that the site shows 10 reviews per page and you only want to get reviews that are on the 3rd page.

To retrieve these reviews, you can make the following request:
`GET /v1/products/12345/reviews?offset=20&limit=10`

_Related:_ [_Everything you need to know about REST API pagination_](https://www.merge.dev/blog/rest-api-pagination)

#### **Invoices**

Imagine that you want to retrieve invoices from your ERP system. You also only want to retrieve invoices from a certain vendor (e.g., vendor ID=12345) and you decide to only retrieve 5 invoices at a time.

You can structure your first request to something as follows:
`GET /v1/invoices/12345/?offset=0&limit=5`

## **Offset pagination pros and cons**

Now that you know how offset pagination works and how it differs from other methods, you may be wondering what its benefits and drawbacks are.

We’ve broken them down below.

#### **Pros**

- It’s relatively easy to implement and understand, as the offset is usually determined by the page size
- It’s easy to access a specific set of data via the offset
- It’s widely support by API providers, so understanding how it works and how to leverage it can prove useful for many, if not all, of your integrations

#### **Cons**

- If a dataset grows or shrinks, you can end up skipping or double counting data
- Even with a large offset, every data point needs to be processed. As a result, requests with a large offset can take a while to execute and consume significant computational resources
- If a dataset isn’t paginated or sequentially ordered in another intuitive way, offset pagination can end up yielding confusing and inconsistent responses

_Related:_ [_Tips for implementing API pagination effectively_](https://www.merge.dev/blog/api-pagination-best-practices)

## **Manage pagination with ease by using Merge**

Merge, the leading unified API solution, lets you connect your product with hundreds of 3rd-party SaaS applications through the platform’s unified API.

This means you only have to consider how [Merge’s Unified API handles pagination](https://docs.merge.dev/basics/pagination/) (among other items, like rate limits and authentication), which helps you scale your integration builds more quickly and maintain them more easily.

You can learn more about Merge’s Unified API, among the platform’s other features, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Foffset-pagination).

## **Offset pagination FAQ**

In case you have any more questions on offset pagination or API pagination more broadly, we’ve addressed several more commonly-asked questions below.

#### **What is API pagination?**

It refers to any pagination method that lets you fetch a subset of data with each request.

And while the methods differ, they serve the same purpose: to help you retrieve data from a large data set in a way that won’t overwhelm the server and that'll allow you to receive responses relatively quickly.

#### **What is the best API pagination method?**

The “best” pagination method largely depends on the type of data you’re pulling from.

For example, if the data set changes frequently, the best method can be one that uses a unique identifier, like cursor-based pagination. But if the data set changes infrequently, offset pagination can be the best option since it’s relatively easy to implement and would fetch data reliably.

That said, in some cases, you won’t have the ability to choose a method, so your “best” pagination option would be whatever method the API provider allows.

#### **What are some best practices for using offset pagination?**

Here are just a few to keep in mind:

- **Sort the data with immutable fields.** By using fields that won’t change the position of data over time (e.g., `created_at` instead of `updated_at`), you can avoid dealing with duplicate and/or missing data

- **Avoid setting a high limit.** This ensures that you’re able to reap the benefits of pagination—minimal server strain and fast response times

- **Review the API provider’s documentation.** Their docs may provide useful insights, like the maximum limit that can be used in a request or the default volume of data that’s returned when a limit isn’t provided

- **Log the offset and limit used in each request.** These logs can make it easier for your team to debug issues quickly over time

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