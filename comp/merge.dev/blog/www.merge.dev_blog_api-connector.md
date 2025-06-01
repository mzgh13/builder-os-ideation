---
url: "https://www.merge.dev/blog/api-connector"
title: "API connectors: how they work and their pros and cons"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-connector#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-connector#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-connector#)

Table of contents

[What is an API connector?](https://www.merge.dev/blog/api-connector#what-is-an-api-connector)

[Examples of API connectors](https://www.merge.dev/blog/api-connector#examples-of-api-connectors)

[Benefits of API connectors](https://www.merge.dev/blog/api-connector#benefits-of-api-connectors)

[Drawbacks of API connectors](https://www.merge.dev/blog/api-connector#drawbacks-of-api-connectors)

[How to evaluate 3rd-party API connectors](https://www.merge.dev/blog/api-connector#how-to-evaluate-3rd-party-api-connectors)

[Avoid API connectors' drawbacks and integrate at scale with Merge](https://www.merge.dev/blog/api-connector#avoid-api-connectors-drawbacks-and-integrate-at-scale-with-merge)

[API connector FAQ](https://www.merge.dev/blog/api-connector#api-connector-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-connector)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7e97dbabfb2ed0eb210_Accounting_integration.webp)**Unified API vs embedded iPaaS: a look at their key differences**](https://www.merge.dev/blog/embedded-ipaas-vs-unified-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)**A guide to embedded workflow tools**](https://www.merge.dev/blog/embedded-workflow)

# API connectors: how they work and their pros and cons

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7aa7b8f7dfdc10c9817_API_Connector_%2525281%252529.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

To help you build API integrations faster, integration platform as a service (iPaaS) and embedded iPaaS solutions offer “API connectors.”

These connectors offer several advantages to building either internal or customer-facing integrations, but they also aren’t without their drawbacks.

To help you evaluate and decide whether it makes sense to use them, we’ll break down how they work, highlight real-world examples, and cover their pros and cons.

## **What is an API connector?**

It’s a pre-built API connection that iPaaS or embedded iPaaS solutions offer and that you can access by passing an authentication and authorization flow.

API connectors also provide a specific set of triggers and actions that are based on API endpoints, enabling you to build trigger-based automations that work across the integrated applications.

_Related:_ [_What is an API connection?_](https://www.merge.dev/blog/api-connection)

#### **API connector vs API**

API connectors are often used interchangeably with APIs. However, they’re completely different.

An API is a method of accessing and interacting with data or functionality from a 3rd party system, while an API connector offers a way to access certain 3rd-party API endpoints from an iPaaS or embedded iPaaS solution.

## **Examples of API connectors**

Here are just a few API connectors from iPaaS and embedded iPaaS vendors.

#### **Workato’s Salesforce connector**

Their connector lets you access and perform actions on accounts, opportunities, contacts, and a host of other records, making the connector well suited to support various use cases.

[![A screenshot of the triggers and actions from Workato's Salesforce connector](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b29daab0f45e5130be_AD_4nXeekrFvZZi00V_yjYMWVAj_9Ox67mbTZUjf-_Qx0yzGxfx1INXkNtmRFzC-IA1lRYn0cJ47qlg9eOUODvYxpr1vJ7kPH5NBnb8jQ_jb505NnwcRX2mJTDVlo5RJ3FfTtFP3e37Kq6-uAJjU9EBcvwRjpGPX.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b29daab0f45e5130be_AD_4nXeekrFvZZi00V_yjYMWVAj_9Ox67mbTZUjf-_Qx0yzGxfx1INXkNtmRFzC-IA1lRYn0cJ47qlg9eOUODvYxpr1vJ7kPH5NBnb8jQ_jb505NnwcRX2mJTDVlo5RJ3FfTtFP3e37Kq6-uAJjU9EBcvwRjpGPX.webp)

This connector is relatively deep for a few reasons. Namely, Salesforce is likely one of Workato’s most in-demand integrations, and their customers have diverse integration needs for the CRM; and unlike many other iPaaS and embedded iPaaS solutions, Workato has been around 10+ years, so they’ve had more time to invest in their connectors.

_Related:_ [_A look at Workato's competitors_](https://www.merge.dev/blog/workato-alternatives)

#### **Prismatic’s NetSuite connector**

The [embedded iPaaS solution](https://www.merge.dev/blog/embedded-ipaas) supports a more finite list of actions with their NetSuite connector.

[![A screenshot of the actions with Prismatic's NetSuite connector](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b2a5849726f189a74f_AD_4nXfrT8P8bC_qeNmDIZvYc51R9D6KvXiRxTyt3rriPxnT7SNB1o1yH9p7IOQF5kk0ftXK2IS2wdhkLN56LRAwOFJih03QHH1eoYCJ4rbIR3zZozzmut432pC3m6IXhO9xJwkhVJyrUnpYL6PdKkdnS8rV6CuF.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b2a5849726f189a74f_AD_4nXfrT8P8bC_qeNmDIZvYc51R9D6KvXiRxTyt3rriPxnT7SNB1o1yH9p7IOQF5kk0ftXK2IS2wdhkLN56LRAwOFJih03QHH1eoYCJ4rbIR3zZozzmut432pC3m6IXhO9xJwkhVJyrUnpYL6PdKkdnS8rV6CuF.webp)

The “records” may refer to a wide range of resources. Given that they aren’t listed (or they’re buried within their site), it’s fair to assume that the connector doesn’t cover the vast majority of NetSuite’s endpoints.

The reason for their shallow connector can potentially be explained by the fact that [NetSuite’s API](https://www.merge.dev/blog/netsuite-api) is complex and difficult to build to, and/or the team at Prismatic hasn’t prioritized building and maintaining this integration (assuming they have the resources to build and maintain this integration).

[Related](https://www.merge.dev/blog/prismatic-pricing?blog-related=image)

#### [Why Prismatic's pricing doesn’t meet your integration needs](https://www.merge.dev/blog/prismatic-pricing?blog-related=image)

[![Why Prismatic's pricing doesn’t meet your integration needs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)](https://www.merge.dev/blog/prismatic-pricing?blog-related=image)

#### **Paragon’s Workday connector**

The embedded iPaaS solution supports “Beta” versions of certain API connectors, such as Workday.

[![A screenshot of Paragon's Workday connector, which is in Beta](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b2608dbf0a59e2c45f_AD_4nXevTQPjyQoUVdBcIPRHWAzJW2pv4w9EyVR5iBMMh38NNqaVXPa9-H-OiSjAuAPnCQ_9wA6r7U0SqYBVnyX4u9jevCNIWPsUKQ1bn0h1ba2fT1eAl2TkMHzd_a4zpW16FVh5cWwvn4T9TCIzo6n7bICzKSBK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fd62b2608dbf0a59e2c45f_AD_4nXevTQPjyQoUVdBcIPRHWAzJW2pv4w9EyVR5iBMMh38NNqaVXPa9-H-OiSjAuAPnCQ_9wA6r7U0SqYBVnyX4u9jevCNIWPsUKQ1bn0h1ba2fT1eAl2TkMHzd_a4zpW16FVh5cWwvn4T9TCIzo6n7bICzKSBK.webp)

Unlike the non-Beta API connectors listed on their site, the integrations page for Workday doesn’t list out any triggers and actions, making it seem as though it isn’t quite built yet or offers very limited functionality.

_Related:_ [_What you need to know about AI connectors_](https://www.merge.dev/blog/ai-connector)

## **Benefits of API connectors**

API connectors offer a specific set of pros and cons. Let’s start with the former:

- **Accelerates integration development.** Your team doesn’t need to worry about building to individual endpoints and maintaining those connections

- **Offers flexible implementation options.** In the case of embedded iPaaS solutions, you can leverage them to build automations within your product, and/or you can enable customers to pick and choose the ones they want and use them however they see fit

- **Lets you offer white label connectors.** This makes it seem as though your team built and maintains the integrations

[![A screenshot of white labeled API connectors](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/664663394aa87e28d91035db_-XFlcUFQseYkrjs-8nDU_KGF_CWKvtYVIRlB-xBsz3yNZBUiKXpV1S1jLWn01Q1B0LQB9mHcJawi-9yEIzzVz8dpzwnnTZLu0xVni9_5ARj8TMXZ0VX_EEioOs0hjA3QvGpV-vzAzzuC4_Sj8hNKCxg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/664663394aa87e28d91035db_-XFlcUFQseYkrjs-8nDU_KGF_CWKvtYVIRlB-xBsz3yNZBUiKXpV1S1jLWn01Q1B0LQB9mHcJawi-9yEIzzVz8dpzwnnTZLu0xVni9_5ARj8TMXZ0VX_EEioOs0hjA3QvGpV-vzAzzuC4_Sj8hNKCxg.webp)

_Pandium, another embedded iPaaS solution, lets you white label API connectors and provide them through a_ [_customizable integration marketplace_](https://www.merge.dev/blog/integration-marketplace)

- **Helps you focus less on building integrations.** You can focus instead on building uniquely powerful automations

## **Drawbacks of API connectors**

API connectors also have notable cons worth considering:

- **They may not offer the endpoints you need.** Whenever that’s the case, you’ll either need to build directly to the API provider or work with the integration solution to improve their connector (which can take time and may even come at an additional cost to your business)

- **It’s still difficult to scale your integration builds, quickly.** While the process of accessing API connectors may be relatively straightforward, the other steps involved in implementing integrations can be anything but. The workflow builders associated with these tools can be surprisingly complex and require extensive onboarding—even for engineers

- **Integration solutions may falsely advertise their API connectors.** In some cases, an iPaaS or embedded iPaaS vendor will say they support an API connector and that it covers certain triggers and actions just to stay competitive. And while they may start building them if you invest in their platform, the process of building and supporting the connector will take time, leading you to face a long time to value

## **How to evaluate 3rd-party API connectors**

API connectors are, clearly, not created equal. To help you find the best one for a given application, you should consider the following:

#### **Supported endpoints**

A connector’s API endpoint support is abstracted away with terms like triggers and actions. As a result, you’ll need to review the full scope of triggers and actions available for a given connector across providers.

Fortunately, this work is made relatively easy, as most vendors list out the specific triggers and actions they support across their connectors.

#### **AI capabilities for development and maintenance**

LLMs are making the process of developing and improving connectors easier. But only some integration providers are taking full advantage.

Workato falls into the camp that does.

They offer several copilots that support different facets of connector development and maintenance: Their Connector Copilot provides suggestions and instructions for implementing authentication logic, actions, and more for any new connector you want to develop; their Mapper Copilot can help you identify the appropriate fields to map between applications—and the list goes on.

#### **Available authentication methods**

API providers often support several forms of authentication, from OAuth 2.0 to basic authentication to [API keys](https://www.merge.dev/blog/api-key).

Based on the integrations you’re looking to build, you may want to use the most secure method—OAuth 2.0—if possible.

Fortunately, integration providers typically shed insight on the specific authentication methods individual connectors support via their docs, making it easy to compare your authentication options across providers.

#### **Customizability**

An API connector may not offer all the functionality your integration needs out of the box.

With that in mind, you should look for connectors that let you add additional endpoints, provide several options for transforming data during the mapping process, and can access custom objects and fields.

## **Avoid API connectors' drawbacks and integrate at scale with Merge**

Merge, the leading unified API solution, lets you add hundreds of integrations across several software categories—including HRIS, ATS, CRM, file storage, accounting, and ticketing—through a single integration build.

[![A visualization of Merge API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95334b70d02265124abc_AD_4nXcip3i0tVg9-gBvsQIlb4oLIa4f2YJpQ5PfVnrd79QhR0CzAW7QUYvCgDE-LGcndFw2WHICi6LvMRSqAU0hbNqIBTIzcKjX2KltS54FINbPvS7vqUv_mBREg9lWNPmkdaJ5SlxfkSv5bW1UNLBDtPj3xEHi.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95334b70d02265124abc_AD_4nXcip3i0tVg9-gBvsQIlb4oLIa4f2YJpQ5PfVnrd79QhR0CzAW7QUYvCgDE-LGcndFw2WHICi6LvMRSqAU0hbNqIBTIzcKjX2KltS54FINbPvS7vqUv_mBREg9lWNPmkdaJ5SlxfkSv5bW1UNLBDtPj3xEHi.webp)

These integrations can support your data coverage needs through Merge's comprehensive Common Models and advanced features for syncing custom data; and your customer-facing teams can even monitor your integrations’ health and address any issues on time through Merge’s suite of Integration Observability features.

Learn more about Merge’s approach to building and managing integrations by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-connector).

## **API connector FAQ**

In case you have any more questions on API connectors, We've answered several more commonly-asked questions below.

#### **What are some synonyms of API connector?**

API connectors are also often referred to as app connectors, pre-built integrations, or third-party connectors.

They can also be application-specific. For example, an API connector for Salesforce can be called a “Salesforce connector.”

#### **What is the difference between an API connector and a custom connector?**

An API connector offers the same functionality for every user out of the box while a custom connector refers to any connector that’s been modified to meet a user’s specific integration requirements.

#### **When does it make sense to use API connectors?**

It can make sense to use them for a wide range of reasons:

- You need to accelerate your time to build integrations
- You don’t have enough developer resources to build integrations natively
- Your engineers don’t have bandwidth to maintain the integrations after they’re built
- The API provider doesn’t offer enough—or any—documentation

#### **What are common examples of API connectors?**

Popular software applications that offer APIs are widely offered as API connectors. To that end, Salesforce, Google Sheets, HubSpot, Dropbox, Workday, and QuickBooks are common connectors.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a40f60ef-50ee-48a1-999e-0ad2f02608de&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b326c162-966d-4639-9a48-8db6b7aaae03&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-connector&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a40f60ef-50ee-48a1-999e-0ad2f02608de&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b326c162-966d-4639-9a48-8db6b7aaae03&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-connector&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=d7f36953-aaf9-4a73-ada1-d7771ca82188&bo=2&sid=c3307a603e8c11f0a1be87fe3a9d2180&vid=c330caf03e8c11f08a0617c301a4a45f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=API%20connectors%3A%20how%20they%20work%20and%20their%20pros%20and%20cons&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-connector&r=&lt=801&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=687220)