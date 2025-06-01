---
url: "https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests"
title: "Learn to handle any edge case with Authenticated Passthrough Requests"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#)

Table of contents

[How an Authenticated Passthrough Request Benefits You](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#how-an-authenticated-passthrough-request-benefits-you)

[Example of an Authenticated Passthrough Request](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#example-of-an-authenticated-passthrough-request)

[As you build](https://www.merge.dev/blog/learn-to-handle-any-edge-case-with-authenticated-passthrough-requests#as-you-build)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Flearn-to-handle-any-edge-case-with-authenticated-passthrough-requests)

##### Just for you

No items found.

# Learn to handle any edge case with Authenticated Passthrough Requests

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c73e308c8ec126f3a56_14.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5384ca3e2516664e343b_62eff97f1cef2853122da72f_pritak.webp)

Pritak Patel

Head of Technical Services

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5384b860cf29c5270652_62eff8e6043a362cf7ff9c92_kevin.webp)

Kevin Zhang

Growth

@Merge

Central to your experience with Merge is our Common Models. As robust representations of common entities across multiple third-party platforms, they're built to handle and anticipate the most typical use cases in a given category.

Of course, as you explore your own use case with Merge there might be endpoints and edge cases that aren’t covered by our Common Models. A [unified API](https://www.merge.dev/blog/product/what-is-a-unified-api/) means being opinionated about how to represent a given category, which means deciding what _not_ to include is just as critical as choosing what to include (because, really, who wants to have to use a bloated API?).

Instead, to help you take advantage of all that Merge has to offer, our platform feautres Authenticated Passthrough Requests. Curious how to handle any use case your product might encounter when it comes to integrations? Let's dive right in.

_You can learn more about Authenticated Passthrough Requests by attending_ [_our upcoming webinar_](https://app.livestorm.co/merge/authenticated-passthrough) _._

## How an Authenticated Passthrough Request Benefits You

An Authenticated Passthrough Request is an API call you make to Merge that we pass on to the third-party API of your choosing.

While your request headers are Merge-specific, the request method and path are formed to meet the requirements of the API you want to access directly (more on that below).

**Core benefits of using Authenticated Passthrough Requests:**

1. Merge handles authentication for you (so you save development time)
2. You never have to store authorization credentials while making these requests (so you don’t have to worry about security issues and token management)
3. Merge provides human-readable error messages across platforms to help you troubleshoot (so, you save even more development time!)

In short, anything you can do with direct integration, you can do with Merge. Only with Merge, it’s just a little (or, a lot) easier.

## Example of an Authenticated Passthrough Request

A common example of when to use a Passthrough is to get information about **‘trainings’** from a specific HRIS system,such as BambooHR. While the ‘training’ model is not common across most HRIS providers, it factors into BambooHR's platform, and may play a crucial role in your product's use case.

So, let’s see how you can reliably and easily call BambooHR using Merge.

**Pre-requisites**

Before you make this request, you would need to sign-up for Merge and create a Linked Account.

Luckily, our [Get Started](https://merge.dev/docs/guides/) guide walks you through what a Linked Account is, and how to create one. If you're totally new, make sure you sign up first - we'll still be here.

**Step 1. Make a Passthrough Request**

Here’s an example of a GET passthrough request for a training type via BambooHR.

```python
curl --location --request POST 'https://api.merge.dev/api/hris/v1/passthrough' \
--header 'X-Account-Token: {{INSERT_ACCOUNT_TOKEN_HERE}}' \
--header 'Authorization: Bearer {{INSERT_PRODUCTION_KEY_HERE}}' \
--data-raw '{
    "method": "GET",
    "path": "/training/type"
}
```

If you’re familiar with requests to Merge, you’ll see it’s quite similar to a normal request to our API. Even better: it doesn’t include any **BambooHR-specific authentication**. Merge will automatically handle authentication when you submit the request with the credentials we already have stored from your customer.  In the example, those credentials are represented by {{INSERT\_ACCOUNT\_TOKEN\_HERE}} and {{INSERT\_PRODUCTION\_KEY\_HERE}}.

**Step 2. Read the Response from BambooHR**

You’ll receive something like this response, directly from BambooHR!

```python
{
    "method": "GET",
    "path": "/training/type",
    "status": 200,
    "response": {
        "15": {
            "id": "15",
            "name": "New Hire Training",
            "renewable": false,
            "frequency": 0,
            "dueFromHireDate": {
                "unit": "day",
                "amount": "14"
            },
            "required": true,
            "category": [],
            "linkUrl": null,
            "description": null
        },
        "19": {
            "id": "19",
            "name": "Working from home during COVID-19",
            "renewable": false,
            "frequency": 0,
            "dueFromHireDate": {
                "unit": "day",
                "amount": "3"
            },
            "required": true,
            "category": {
                "id": "18353",
                "name": "COVID-19"
            },
            "linkUrl": "https://www.bamboohr.com/blog/get-the-most-from-remote-workers/",
            "description": "Description Box:  Please review the online documentation linked below for our working from home expectations."
        }
    },
    "headers": {
        "User-Agent": "python-requests/2.27.1",
        "Accept-Encoding": "gzip, deflate",
        "Accept": "<redacted>",
        "Connection": "keep-alive",
        "Authorization": "Basic {{token}}",
    }
}
```

It’s that simple.

_Pro-tip:_ Think you might need some help constructing your own Passthrough request? Customers on our Professional and Enterprise plans are assisted by our [expert Growth and Solutions Engineering team](https://www.g2.com/products/merge-api/reviews#survey-response-6875420) with custom code that fits their use case.

## As you build

Remember: anything that can be done via a direct integration can be done via Passthrough as well. The added benefit to you is being able to utilize our Common Models, tokenized authentication, and standardized errors and logging messages to aid your development.

Interested in using Passthrough alongside our Unified API, and want to discuss your use case even more? Reach out to a [member of our Sales team](https://merge.dev/get-in-touch/?utm_btn=dr-page-blog%2Flearn-to-handle-any-edge-case-with-authenticated-passthrough-requests) \- we’re always happy to help you determine if Merge is the right solution for you.

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Pritak Patel

Head of Technical Services

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Kevin Zhang

Growth

@Merge

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=820f3a1a-0fae-4c81-8bc8-971981f5d870&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8b7e88d1-439e-44c4-82a9-47f2fae3209e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flearn-to-handle-any-edge-case-with-authenticated-passthrough-requests&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=820f3a1a-0fae-4c81-8bc8-971981f5d870&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8b7e88d1-439e-44c4-82a9-47f2fae3209e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flearn-to-handle-any-edge-case-with-authenticated-passthrough-requests&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=98e5c224-e362-40a8-84fd-57d4883235a5&bo=2&sid=3d9fffb03e8e11f0856c9fa222dbc778&vid=3da043603e8e11f0a9ddc3202044f736&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Learn%20to%20handle%20any%20edge%20case%20with%20Authenticated%20Passthrough%20Requests&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flearn-to-handle-any-edge-case-with-authenticated-passthrough-requests&r=&lt=303&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=500334)