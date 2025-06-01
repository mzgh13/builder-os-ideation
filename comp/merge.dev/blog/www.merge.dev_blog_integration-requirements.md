---
url: "https://www.merge.dev/blog/integration-requirements"
title: "How to collect every integration requirement"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/integration-requirements#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/integration-requirements#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/integration-requirements#)

Table of contents

[What are integration requirements?](https://www.merge.dev/blog/integration-requirements#what-are-integration-requirements)

[Why integration requirements are important](https://www.merge.dev/blog/integration-requirements#why-integration-requirements-are-important)

[Technical requirements](https://www.merge.dev/blog/integration-requirements#technical-requirements)

[Organizational requirements](https://www.merge.dev/blog/integration-requirements#organizational-requirements)

[How to gather integration requirements](https://www.merge.dev/blog/integration-requirements#how-to-gather-integration-requirements)

[Avoid dealing with complex integration requirements with Merge](https://www.merge.dev/blog/integration-requirements#avoid-dealing-with-complex-integration-requirements-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-requirements)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)**7 best practices for building and maintaining API integrations**](https://www.merge.dev/blog/api-integration-best-practices)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)**Custom API integration: here’s what you need to know**](https://www.merge.dev/blog/custom-api-integration)

# How to collect every integration requirement

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c70eb21529aacad5861_Integration_Requirements_Checklist.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to build either an internal or customer-facing integration, you’ll first need to gather certain types of information.

We’ll review what this information looks like so that you can build any integration successfully. But first, let’s align on the definition of integration requirements and why they matter.

## **What are integration requirements?**

They’re areas your team needs to address when building to a specific 3rd-party API provider’s endpoint. Accounting for these areas successfully lets you build secure, performant, and reliable integrations.

These requirements typically fall in one of two buckets: technical and organizational. We’ll take a closer look at each after breaking down why integration requirements are critical.

_Related:_ [_What are API connectors?_](https://www.merge.dev/blog/api-connector)

## **Why integration requirements are important**

Every integration build is unique.

API providers have different endpoints, rate limits, SDKs, and may offer different authentication and pagination methods. Without a deep understanding of each of these areas for a given build, you won’t be able to implement an integration successfully.

Equally important, you likely have unique integration requirements. Perhaps you need to build either a one way or bidirectional sync; or you need to sync data at a specific frequency; or you need the integrated data to appear in a certain format in the destination system.

In short, your team needs to make the effort of researching and documenting the requirements for every integration project so that they can be prepared to build it successfully from the beginning.

## **Technical requirements**

This typically includes the core facets of any integration build: endpoints, SDKs, authentication, pagination, and rate limits.

#### **Endpoints**

Some API providers offer a broad range of endpoints that seemingly overlap or that can be easy to mix up. You’ll need to carefully review each in the provider’s API documentation so that you can pinpoint the best one for your integration scenario.

In many cases, reviewing the sample responses can help you do just that.

For example, say you want to access time off policies for employees in BambooHR and you see the following:

‍

- A [time off types endpoint](https://documentation.bamboohr.com/reference/get-time-off-types): `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/meta/time_off/types/`
- A [time off policies endpoint](https://documentation.bamboohr.com/reference/get-time-off-types): `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/meta/time_off/policies/`

By reviewing a sample response like below for the time off policies endpoint, you can tell that it’s the one you want to use.

[![Sample response for BambooHR's policies endpoint](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed114d276084da17ee817_AD_4nXdganDbMNNc1syRb9BUX7ErvSemmbBW08K8gGFI9QjlqeX1bJeV2Vr63rSqaI9WFr6nVBBEodEeouYERtt5c7hOnec1pHwzLtxtynXhXUmRT0J3OYvyhHxfv-SfskoamPfHQaw2pCWuhqFrdYBsdqWTqiVu.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed114d276084da17ee817_AD_4nXdganDbMNNc1syRb9BUX7ErvSemmbBW08K8gGFI9QjlqeX1bJeV2Vr63rSqaI9WFr6nVBBEodEeouYERtt5c7hOnec1pHwzLtxtynXhXUmRT0J3OYvyhHxfv-SfskoamPfHQaw2pCWuhqFrdYBsdqWTqiVu.webp)

#### **SDKs**

Most API providers offer software development kits (SDKs) to help you build integrations faster and more effectively within the programming language you and your team are most comfortable with.

To that end, you should review the API provider’s available SDKs (typically in language-specific package management systems), read though the instructions for importing a package into your code base, and learn how to use it after it’s installed.

_Related:_ [_A guide to using SDKs_](https://www.merge.dev/blog/sdk-integration)

#### **Pagination**

API providers offer different forms of pagination, whether it’s offset pagination, keyset pagination, cursor-based pagination, etc.

Understanding which method(s) a given endpoint supports and how that method works is critical to ensuring that you structure your requests and process responses correctly.

Greenhouse, for instance, includes the URL for the next page of results within the response’s header, allowing you to call it automatically.

Using their candidates endpoint as an example, the response header below shows the URL for fetching the second page of results, which includes 2 candidates.

`Link: https://harvest.greenhouse.io/v1/candidates?page=2&per_page=2; rel="next"`

#### **Rate limits**

Every API provider offers a unique set of rate limits and presents them differently.

For instance, Greenhouse uses `X-RateLimit-Limit` in its header to indicate the number of requests you can make to the endpoint in a given 10 second window; while GitHub sets rate limits by the hour (e.g., 5,000 requests per hour) and can provide a variety of headers in addition to `X-RateLimit-Limit` to provide you with additional insights on your rate limit situation.

[![GitHub's response headers](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed11402dee04ccf05cb28_AD_4nXdOVkcIvK6hvdtHR1Yjgnhn5vv5Y9fTlIKRa_IC8naoOx_wfEi5YBD0gR24iDVNBDpJ8fjpbyuJ3VTUk0A2SBsJFY_JTQf3_OTGNzhQEAqs2KzprgrUAVTdA3UyGBlyxwnksGNDM7quCxh4dvTUVhz_uKtr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed11402dee04ccf05cb28_AD_4nXdOVkcIvK6hvdtHR1Yjgnhn5vv5Y9fTlIKRa_IC8naoOx_wfEi5YBD0gR24iDVNBDpJ8fjpbyuJ3VTUk0A2SBsJFY_JTQf3_OTGNzhQEAqs2KzprgrUAVTdA3UyGBlyxwnksGNDM7quCxh4dvTUVhz_uKtr.webp)

_A snapshot of the_ [_response headers GitHub offers_](https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api?apiVersion=2022-11-28) _around rate limits_

Understanding and following your rate limits across integrations consistently is critical to helping you build integrations that sync data frequently and reliably, as well as avoid additional costs.

#### **Authentication and authorization**

Like many of the other requirements, API providers typically offer varying approaches to authentication and authorization, whether that’s OAuth, API keys, or basic authentication.

You can spot these differences just from looking at a few similar tools. For instance, Lever lets you use OAuth, while Greenhouse, another ATS, only offers basic authentication (your username is your Greenhouse API token and you don’t need to provide a password).

You’ll need to review each API provider’s specific approach so that your integration requests are processed successfully.

## **Organizational requirements**

Aside from the technical requirements, you’ll also need to consider factors like the engineering resources at your disposal, your plan for prioritizing integrations, and how you’ll take the integrations to market (in the case of [product integrations](https://www.merge.dev/blog/product-integrations)).

#### **Engineering resources**

Each integration build takes tens of hours, and the work involved in maintaining an integration is never-ending; your engineers will likely need to spend a couple hours every week maintaining an integration.

Given the level of resource investment that's involved, you’ll need to align on the engineers within your team who can build and maintain the integrations, the ones they’ll focus on, and how much time they should be spending on both implementation and maintenance.

#### **Prioritizing integrations**

Each integration offers unique business value.

In the case of customer-facing integrations, for instance, some may help you increase your close rate, others may help you retain customers, and others still can help you expand to new markets.

At the same time, every integration has a unique cost associated with it, whether that’s the direct cost of forming a partnership with an API provider or the resource cost in building and maintaining the integration.

Given the unique benefits and costs associated with each integration, you’ll likely need to develop an integration scorecard that helps you determine and prioritize the best opportunities.

Here’s how it can look for customer-facing integrations:

[![Integration scorecard for product integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed11479f76b2f61c16aaa_AD_4nXfSmZ5yWAzOHpAEb7ovl73Zc5BQnYhC6NwkaJZHMG3GycI8Poziv8NagcQNysb7anojD6JdPUqiQX-M_5ZFb7hcl3CVddZgMhlo19rAVGk-i3_RuGpTTv9XL8Nigfowx6Z-72nymgQxD7e39rDPdHg43ATz.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed11479f76b2f61c16aaa_AD_4nXfSmZ5yWAzOHpAEb7ovl73Zc5BQnYhC6NwkaJZHMG3GycI8Poziv8NagcQNysb7anojD6JdPUqiQX-M_5ZFb7hcl3CVddZgMhlo19rAVGk-i3_RuGpTTv9XL8Nigfowx6Z-72nymgQxD7e39rDPdHg43ATz.webp)

#### **Go-to-market strategy**

In the case of customer-facing integrations, you’ll also need to decide on [pricing each integration](https://www.merge.dev/blog/pricing-software-integrations), marketing it, and supporting it.

- **Pricing:** If an integration is critical for every type of customer, it may be worth including it at no additional cost; while if an integration is only relevant to larger companies, it can make sense to tack on an additional charge

[![Siit's integration pricing model](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed115fb586c0da49e835b_AD_4nXfkNff2WVGjWph093Yf_sey6SR2JgcPnVh9d5wat8LLgvWqAU-JfgmMcx_jdtVbTNeqQYgkk0QCOKnQVUTT-qdRZQVf3oXaqOzmWy3ZiVqdSzeyAW9hmsCgBDDYZE5az30QlnkYQGwKFcrXGr-sA-Y3sqmC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fed115fb586c0da49e835b_AD_4nXfkNff2WVGjWph093Yf_sey6SR2JgcPnVh9d5wat8LLgvWqAU-JfgmMcx_jdtVbTNeqQYgkk0QCOKnQVUTT-qdRZQVf3oXaqOzmWy3ZiVqdSzeyAW9hmsCgBDDYZE5az30QlnkYQGwKFcrXGr-sA-Y3sqmC.webp)

_Siit, an internal helpdesk software, offers HRIS integrations as part of their Essentials subscription as its table stakes for using their product; ticketing integrations are part of their Custom subscription as larger companies often use these tools to manage requests_

- **Marketing:** Various marketing activities can help you raise awareness and adoption of your integrations, from writing up blog posts to amplifying the integrations across your social channels to even announcing them in emails

[![an email from allwhere that announces their integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d90ace966f395fce9580b3_QlZhFykz3kgmdKjQk0zFzOrBiSq5U6p-kNRvHK_K2XOdMBEhs35HOz0bH0vW-GZ6-d50rxgoS4cn4NGxP4_FpHRfUNxwAaJf64sgFyykOKmjZE2xMDBTGn3Nt-yzwUUgyvyQbBdrFC2e2Ej8RypmiHY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d90ace966f395fce9580b3_QlZhFykz3kgmdKjQk0zFzOrBiSq5U6p-kNRvHK_K2XOdMBEhs35HOz0bH0vW-GZ6-d50rxgoS4cn4NGxP4_FpHRfUNxwAaJf64sgFyykOKmjZE2xMDBTGn3Nt-yzwUUgyvyQbBdrFC2e2Ej8RypmiHY.webp)

_allwhere, an IT asset management platform, shares new integration releases to customers via email blasts_

- **Support:** You’ll need to decide who within your support team will support the integrations, the SLAs you’ll offer for specific issues, and more

## **How to gather integration requirements**

Your team will need to ask themselves a certain set of questions to help them gather the requirements successfully. Here are just a few worth asking:

#### Does the API provider offer publicly-available documentation and a sandbox account for testing?

Hopefully, the answer is yes and you can move on to gathering more integration-specific requirements.

But you might end up learning that you need to enter into a formal business partnership with the vendor before you can access either documentation or a sandbox account. Assuming that’s the case, you’ll need to put a pause on gathering additional requirements and work with your business development or partnerships team on forming a business relationship with that API provider (which will likely take time and require ample investment).

_Related:_ [_A guide to integration partnerships_](https://www.merge.dev/blog/integration-partners)

#### What resource do we need to access and what actions do we want to perform on it?

Once you’re able to answer this, you can review the API provider’s documentation to suss out the most relevant endpoint for that resource. From there, you can determine the parameters you'll need to pass, the HTTP method you should use (assuming they support it), the authentication and authorization details you'll need to access the resource, etc.

#### How frequently do we want to sync data?

Certain scenarios, like syncing data on new leads, may require real-time—or near real-time—syncs, while syncing, say financial documents with a file storage tool, can be a daily or even weekly sync.

You can confirm whether the API provider supports your desired sync frequency via their documentation. For instance, you can learn if they support real-time syncs for a given resource—via a webhook—within their documentation.

#### What error messages does the API provider typically use?

While many [API error messages](https://www.merge.dev/blog/api-response-codes) are standard across providers (e.g., “429 Too Many Requests”), others are more specific to a given provider. Understanding all of the ones you might see for a given integration can help you build more reliable error-handling processes upfront.

#### Who on the team is responsible for certain facets of an integration project?

An integration project often can and should require several stakeholders to get involved.

For example, maybe certain engineers should be responsible for the initial implementation, while other engineers should be responsible for maintaining that integration afterwards.

Whatever the case may be, you’ll need to craft and align on a plan that the relevant stakeholders can review and sign off on.

#### For a customer-facing integration: How will it be taken to market?

Your team will need to decide whether the integration should be available for “free” or if it should be included in a certain subscription tier(s). Moreover, your team will need to align on the processes for supporting the integration (e.g., the SLA for responding to issues), the marketing activities worth pursuing, when and how to introduce and speak about it during the sales cycle, and more.

‍ _Related:_ [_Our best resources for taking your integrations to market_](https://www.merge.dev/blog/taking-product-integrations-to-market-resources)

## **Avoid dealing with complex integration requirements with Merge**

Using Merge, the leading unified API platform, you can add hundreds of integrations to your product through a single integration build.

This means you only have to worry about a single approach to rate limiting, authentication, and pagination—saving your engineers time and helping you take a wide range of integrations live quickly.

Merge’s customer success team will also partner with you on taking your integrations to market successfully, whether that’s training your customer-facing teams or providing resources that can help you manage specific facets of your GTM strategy.

Learn more about how Merge can meet your customer-facing integration requirements by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-requirements).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=494e6ab6-887b-4bd7-b066-400161c0aa53&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=46439e13-6f12-48c3-88b6-077431322783&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-requirements&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=494e6ab6-887b-4bd7-b066-400161c0aa53&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=46439e13-6f12-48c3-88b6-077431322783&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-requirements&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e67ece57-2f74-4604-b379-3fd7ecf21511&bo=2&sid=ccaa68603e8b11f09ce2b3dfb2d72819&vid=ccabcb503e8b11f09c58918f154e4c8f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20collect%20every%20integration%20requirement&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-requirements&r=&lt=354&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=293622)