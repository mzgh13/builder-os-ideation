---
url: "https://www.merge.dev/blog/integration-issues"
title: "5 common integration issues (according to our research)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/integration-issues#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/integration-issues#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/integration-issues#)

Table of contents

[What is an integration issue?](https://www.merge.dev/blog/integration-issues#what-is-an-integration-issue)

[Frequent integration issues](https://www.merge.dev/blog/integration-issues#frequent-integration-issues)

[Handle integration issues effectively with Merge](https://www.merge.dev/blog/integration-issues#handle-integration-issues-effectively-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-issues)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)**‍Build or buy integrations? How to land on the best decision**](https://www.merge.dev/blog/build-vs-buy-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**API response codes: examples and error-handling strategies**](https://www.merge.dev/blog/api-response-codes)

# 5 common integration issues (according to our research)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As organizations build and maintain integrations, they’ll inevitably run into serious issues.

We identified many of them when we surveyed hundreds of product managers and engineers as part of [our State of Product Integrations report](https://www.merge.dev/learning/state-of-product-integrations-2024).

When it comes to building integrations, for example, we uncovered the following issues:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084a6711c5b15428067e_axGHEoUCc0Dy_DsPiZK8LBlwB2YnjADCLevhRHhjbU3WZlj7lpbfdB0mJkTU2qsm6TPqwfV7hhDOXObRtAr_GKVkAPKIf-SHSllOHQDekANHLQ9wwJO1H04g4qJz_LPbJtK5QcM0yvwq8IgrWgrpsr4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084a6711c5b15428067e_axGHEoUCc0Dy_DsPiZK8LBlwB2YnjADCLevhRHhjbU3WZlj7lpbfdB0mJkTU2qsm6TPqwfV7hhDOXObRtAr_GKVkAPKIf-SHSllOHQDekANHLQ9wwJO1H04g4qJz_LPbJtK5QcM0yvwq8IgrWgrpsr4.webp)

And when it comes to maintaining integrations, we discovered several more challenges:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084a42e12b6ccc470cae_VOoP9x39cHjcPurnzGeaeS8LqPkiDhKUi-4WDJimEh2GcvlSGnPXxN_rTONVk6qLd5EFj7HfC5M2NeCItNR_UAEqKFJUrVERsrJkvsrMkDrncwxxvOiebV6ANdIU96XVGnTn2OFw8Dnjkk5lB_0JmX8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084a42e12b6ccc470cae_VOoP9x39cHjcPurnzGeaeS8LqPkiDhKUi-4WDJimEh2GcvlSGnPXxN_rTONVk6qLd5EFj7HfC5M2NeCItNR_UAEqKFJUrVERsrJkvsrMkDrncwxxvOiebV6ANdIU96XVGnTn2OFw8Dnjkk5lB_0JmX8.webp)

We’ll break down some of the most common issues from our research so that you can better prepare for and avoid them. But first, let’s align on the definition of an integration issue.

## **What is an integration issue?**

It’s any issue associated with either building or maintaining an integration. The source of an issue can be on the API provider’s or API consumer’s end.

## Frequent integration issues

Here are a few of the top integration issues to be aware of.

### **Integration performance**

Integrations can break for a seemingly endless number of reasons. For instance, if an API response comes back in a different format (e.g., an array) than what you expected and accounted for in your code base (e.g., a string), your integration can break.

In addition, without a robust and comprehensive process in place to identify, diagnose, and resolve an integration issue, it can persist for a long stretch of time, leaving a lasting effect on everyone involved.

_Related:_ [_Common API integration challenges_](https://www.merge.dev/blog/api-integration-challenges)

### **Difficult to scale**

Every integration requires its own cycle of research, scoping, development, and maintenance, and there’s little-to-no overlap in these areas across integrations.

Given how complex and tedious it is to build and maintain each integration, coupled with the fact that you likely have limited developer resources available to allocate toward this work, it’s difficult—if not impossible—to scale your integrations in-house effectively.

### **API documentation is hard to access**

API documentation is notorious for being mediocre.

Among other issues, this type of documentation is often incomplete, difficult to navigate, out of date, and poorly written, making it difficult to rely on when building and maintaining a given integration successfully.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084ab5799b18ead526b2_RxQZmWH4HJJfBtL5e8a266dyV602RwsBolTryZD-jitq4xanQZTIp6nxyasJCmGtNAwb2SSOmmqzY-iyPLbMsn3QL-3FpYBMnNYbbXIOgCBI1v9154KqmeUMxPY-PiWoaf4fvcpvZXeCTw4CyjfYoxo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665e084ab5799b18ead526b2_RxQZmWH4HJJfBtL5e8a266dyV602RwsBolTryZD-jitq4xanQZTIp6nxyasJCmGtNAwb2SSOmmqzY-iyPLbMsn3QL-3FpYBMnNYbbXIOgCBI1v9154KqmeUMxPY-PiWoaf4fvcpvZXeCTw4CyjfYoxo.webp)

[_Stripe’s API documentation_](https://docs.stripe.com/api) _is easy to reference when building to one of their endpoints. Their documentation is the exception, not the rule_

_Related:_ [_A guide to reading API docs_](https://www.merge.dev/blog/how-to-read-api-documentation)

### **An integrated application, or a feature within the app, gets discontinued**

SaaS applications, or the specific features they offer, constantly get deprecated.

Forcing your engineers to keep tabs on the status of these applications and features, make contingency plans in the event that they get deprecated, and implement those contingency plans on time can prove difficult, especially as you scale your integrations.

### **Challenging to secure partnerships with 3rd-parties**

Some API providers require you to form a certain level of partnership just to access their API documentation and [sandbox accounts](https://www.merge.dev/blog/api-sandbox). And while it depends on the provider, these partnerships can cost tens of thousands of dollars per year.

Some API providers are also exceptionally picky about who they accept as a partner, so even if you’re willing to make the necessary investment, you still might not be able to build to a provider’s endpoints.

## **Handle integration issues effectively with Merge**

Merge offers a unified API that lets you add hundreds of integrations to your product through a single build.

Merge also provides integration maintenance support (through its team of partner engineers) to help you offer resilient and performant integrations. And its platform includes [Integration Observability tooling](https://www.merge.dev/features/integration-observability) that lets your customer-facing employees pinpoint and diagnose integration issues easily and work with affected customers on resolving them quickly.

[![A screenshot of Merge's automated issue detection functionality](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)

_Using Merge, your customer-facing teams can detect specific issues and access the steps for remediating them_

You can learn more about how Merge can help you manage integration issues successfully by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-issues).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=581d98fa-8552-4e92-853f-5232ed4e64f9&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ccdf0489-d68c-41ce-8c4e-4d47d82042de&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-issues&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=581d98fa-8552-4e92-853f-5232ed4e64f9&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ccdf0489-d68c-41ce-8c4e-4d47d82042de&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-issues&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=c7d16bc2-0895-4f2b-99c4-7919ba7cdce7&bo=2&sid=d513e8703e8b11f090b31b98303004b1&vid=d5142dd03e8b11f08573eb4c221dbe9b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=5%20common%20integration%20issues%20(according%20to%20our%20research)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-issues&r=&lt=313&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=341313)