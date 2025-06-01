---
url: "https://www.merge.dev/blog/api-throttling-best-practices"
title: "5 API throttling best practices worth following"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-throttling-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-throttling-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-throttling-best-practices#)

Table of contents

[Review how the API provider implements throttling](https://www.merge.dev/blog/api-throttling-best-practices#review-how-the-api-provider-implements-throttling)

[Make efficient API calls](https://www.merge.dev/blog/api-throttling-best-practices#make-efficient-api-calls)

[Establish your own throttling mechanism](https://www.merge.dev/blog/api-throttling-best-practices#establish-your-own-throttling-mechanism)

[Use caching to retrieve previous responses](https://www.merge.dev/blog/api-throttling-best-practices#use-caching-to-retrieve-previous-responses)

[Leverage webhooks when possible](https://www.merge.dev/blog/api-throttling-best-practices#leverage-webhooks-when-possible)

[Avoid dealing with API throttling for each provider by using Merge](https://www.merge.dev/blog/api-throttling-best-practices#avoid-dealing-with-api-throttling-for-each-provider-by-using-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-throttling-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cef5c33a545135e9dde_How_to_get_your_ChatGPT_API_key.webp)**7 API logging best practices worth implementing**](https://www.merge.dev/blog/api-logging-best-practices)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**7 best practices for polling API endpoints**](https://www.merge.dev/blog/api-polling-best-practices)

# 5 API throttling best practices worth following

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Managing an API provider’s throttling policies (or the number of requests they allow you to make over a certain period) effectively allows you to avoid 429 “Too Many Requests” errors, additional costs, and even a temporary or permanent ban from accessing the API.

We’ll help you manage any API provider’s approach to throttling by breaking down several best practices.

## **Review how the API provider implements throttling**

Every API provider can impose throttling differently and/or in multiple ways.

API providers typically impose rate limits to set a cap on the number of requests a consumer can make. But they can also set limits on the number of requests that can be made concurrently, and use quota-based throttling, where an API provider sets a request limit for a longer timeframe.

All this to say, it’s worth evaluating the specific throttling policies each API provider puts into place by [reviewing their API documentation](https://www.merge.dev/blog/how-to-read-api-documentation).

## **Make efficient API calls**

To ensure that you’re not making unnecessary API calls and retrieving as much data as possible from each, you can call specific endpoints that are likely to retrieve more data than others.

For instance, let’s say that you want to retrieve employees from BambooHR, a widely-used HRIS solution.

Instead of calling a specific endpoint that returns individual employees, like `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/`, you can call the endpoint `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/reports/custom` to retrieve a custom report of all the employees.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660af02aa88facaf90f26cc6_HqRLquGEzGuDzL0oanqoG7RRPyqSSW4mMTm_XBIDqhImrWzQDBjiG6o2L9Krs5wl82NClHEENBLESek0UXNWmoaxyNJXeJBSS6wAMbM2ITPdTau05V39ccODQC_P6QcVYFUuDlmePsd6_ncRY8jOfCY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/660af02aa88facaf90f26cc6_HqRLquGEzGuDzL0oanqoG7RRPyqSSW4mMTm_XBIDqhImrWzQDBjiG6o2L9Krs5wl82NClHEENBLESek0UXNWmoaxyNJXeJBSS6wAMbM2ITPdTau05V39ccODQC_P6QcVYFUuDlmePsd6_ncRY8jOfCY.webp)

_BambooHR mentions that calling the custom report endpoint can be a more efficient way to fetch employees in_ [_their API documentation_](https://documentation.bamboohr.com/reference/get-employee)

_Related:_ [_How to manage rate limits effectively_](https://www.merge.dev/blog/api-rate-limit-best-practices)

## **Establish your own throttling mechanism**

Once you determine an API provider’s approach to throttling, you can use custom code to automate the process of making requests. Moreover, these automated requests could be set up to occur on a cadence that falls within the provider’s rate limit.

As an example, you can use what’s referred to as the “Token Bucket Algorithm”, where tokens get added to a bucket at a fixed rate. A token gets consumed with every request and once the bucket is empty, no requests can occur until a token gets added. You can learn more about implementing this method by reading [this tutorial](https://dev.to/satrobit/rate-limiting-using-the-token-bucket-algorithm-3cjh).

## **Use caching to retrieve previous responses**

Many types of data change infrequently, (e.g., employee fields, like first and last names, job titles, departments, addresses, etc.). To help you avoid making an API request every time you need to get data that falls within this category, you can simply cache their API responses and retrieve them when they're needed.

You can also call these endpoints on an infrequent basis to determine if there have been any changes. And if there are, you can replace the data that’s cached with what’s changed.

_Related:_ [_Best practices for managing API pagination_](https://www.merge.dev/blog/api-pagination-best-practices)

## **Leverage webhooks when possible**

Webhooks, which allow you to get notified when a certain event occurs in an application (via a POST request), let you avoid making API requests while still allowing you to get the data you need, when you need it.

That said, not all API providers offer webhooks, or they only offer them for certain endpoints, so you’ll need to review their API documentation to confirm that they do.

‍

[![A screenshot of GitHub's webhooks documentation](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438aa604c5350ce5888f_xL_4hPnLItfUaRFIJG8KWHvI63A5sY9SN0hS_89TEqOUICyan0TQO-PUGNjNg0nwc2fkJvOZmk62TV4dZuzu5HXBi1J4XD5U32Hf9L2mE_blW8C2ICLfUnZzZxv6cI3HauxFAIsJ9fJ4Wev3jV1iRvI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6604438aa604c5350ce5888f_xL_4hPnLItfUaRFIJG8KWHvI63A5sY9SN0hS_89TEqOUICyan0TQO-PUGNjNg0nwc2fkJvOZmk62TV4dZuzu5HXBi1J4XD5U32Hf9L2mE_blW8C2ICLfUnZzZxv6cI3HauxFAIsJ9fJ4Wev3jV1iRvI.webp)

_GitHub, a developer platform, has dedicated ample_ [_documentation on its webhooks_](https://docs.github.com/en/webhooks) _, allowing its API consumers to not only confirm which endpoints they support but also how you can create and troubleshoot them effectively_

## **Avoid dealing with API throttling for each provider by using Merge**

Merge, the leading unified API solution, lets you add hundreds of integrations to your product through its unified API. This means that you only have to consider Merge’s approach to API throttling to access all the 3rd-party integrations you want and need.

You can learn more about Merge and its throttling policies by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-throttling-best-practices).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e726f8d1-7427-4e03-9219-6068c5e4a0ea&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=825cd1e1-1518-48c3-8399-d69ad9e7b03b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-throttling-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e726f8d1-7427-4e03-9219-6068c5e4a0ea&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=825cd1e1-1518-48c3-8399-d69ad9e7b03b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-throttling-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=80c8812c-df2f-4641-a929-ff42e442297d&bo=2&sid=a7f0cfd03e8c11f0a0ae8d538ad99af0&vid=a7f2a6903e8c11f0a17b3dcc20de4be9&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=5%20API%20throttling%20best%20practices%20worth%20following&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-throttling-best-practices&r=&lt=598&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=918104)