---
url: "https://www.merge.dev/blog/how-unified-apis-work"
title: "How Unified APIs work"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-unified-apis-work#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-unified-apis-work#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-unified-apis-work#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-unified-apis-work)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**5 benefits of API aggregation**](https://www.merge.dev/blog/api-aggregation)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fbf46295e6417a0804f3b_Universal_API.webp)**What is a universal API? Here’s what you need to know**](https://www.merge.dev/blog/universal-api)

# How Unified APIs work

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cebe8bfa24cca794116_How_a_Unified_API_Works.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

A [Unified API](https://www.merge.dev/blog/what-is-a-unified-api) is an aggregation and abstraction layer on top of multiple underlying APIs. In addition to this aggregation, Unified APIs play several additional roles such as normalizing data across each underlying API, providing features to manage the integration lifecycle, and running infrastructure to sync data to and from each API.

### 5 key aspects of a Unified API

Unified APIs aggregate data from multiple supported integrations, normalize that data across integrations, manage authentication and authorization, consistently access that data via API, and sync the data continuously.

We'll walk through the following five key aspects of how a Unified API works:

1. Aggregation: Scope of data and integrations supported
2. Normalization: How data is mapped across each integration
3. Authentication and authorization: How integrations are set up
4. Access: How data is retrieved from the Unified API
5. Syncing: How the Unified API keeps data up-to-date

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c0d6c2d176faabe8dde_dbdae24d.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c0d6c2d176faabe8dde_dbdae24d.webp)

‍

### Aggregation: How categories and integrations are scoped

Unified APIs are built around software systems of record where there is an industry standard of data definitions and structures. CRM systems, for example, have commonly followed standards for Contacts, Accounts, and Opportunities based on industry-defining products like Salesforce.

When developing a Unified API, architects will look for these systems of record and standard data structures to delineate what is and isn't included in the API. They look for consistency in data objects, fields, and relationships that make normalizing data predictable and useful.

_Related:_ [_Examples of API aggregators_](https://merge.dev/blog/api-aggregator)

### Normalization: How data models are defined

Data normalization is crucial when working with multiple integrations. Each customer will have their chosen integration, and in some cases their own configuration of data in each integration. Data from each of these integrations is normalized by a Unified API in the following scenarios:

**Fields have different data types**

For example, a short integer in one API may be a string in another.

**Fields have different enums or picklists**

For example, country names or currencies have common meanings but different representations in different APIs.

**Required parameters differ**

In particular when POSTing or PATCHing data, required parameters are essential for making a successful API request. For example, recruiting candidate data objects may be structured to require a job application in some systems, but not in others.

**Objects and fields have different relationships**

Object hierarchies and associations vary across APIs and need to be structured in a standard way. For example, project management systems have tickets that can be nested in some APIs, while others may not support nesting of parent and child tickets.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c44add61d5dc74566b6_0819ec48.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c44add61d5dc74566b6_0819ec48.webp)

Example of data transformation and normalization

‍

_Related:_ [_Common examples of unified APIs across software categories_](https://merge.dev/blog/unified-api-examples)

### Authentication and authorization: How users set up an integration

Unified APIs are embedded within software to make it easier for that software's users to add integrations. That means that setting up integrations, including both authentication and authorization, is a very important step to get right and to support at the scale of many hundreds or thousands of users.

Unified APIs prioritize easy developer experience and robust customer data controls in their authentication and authorization components. This makes it simple to offer the end user a menu of integration options, to collect the required authentication credentials, and to limit the scope of data that is accessed. It is a similar user experience to OAuth flows you may be familiar with when authorizing data in a consumer mobile app.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c62230d454fe124c3a6_f49be7d9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c62230d454fe124c3a6_f49be7d9.webp)

Example of a Unified API integration selector

‍

To work, a Unified API must be able to make API requests on behalf of a customer or user to a software provider.

Unified APIs include embeddable authentication components that collect a user's authentication credentials at the time they set up an integration. These credentials are stored as a token and used to make requests on behalf of the customer going forward.

Unified APIs also include authorization functionality, to scope or delimit which data is allowed to be accessed using their authentication credentials. This scope is stored with the user's authentication tokens.

_Related:_ [_A guide to integrating multiple APIs_](https://www.merge.dev/blog/multiple-api-integration)

### Access: How developers interact with endpoints, rate limits, and pagination

Unified APIs present one standardized API for interacting with many APIs of software providers. This standardization takes many forms, including a common set of:

**API endpoints:** Unified APIs present one set of endpoints to access rather than needing to interact with each API individually.

**API request structure:** These Unified API endpoints are typically built to conform to a REST model, whereas underlying APIs may have a variety of structures, including SOAP or GraphQL.

**API response structure:** Unified API endpoints maintain a standard response structure as well, typically using JSON as the response format. Again, underlying APIs vary and may use SOAP or other response formats.

**API methods:** Unified APIs standardize GET, POST, and PATCH methods to ensure that interacting with data can be accomplished with the same requests and responses, regardless of underlying API.

**Pagination:** Unified APIs apply a standard pagination, whereas underlying APIs may have a variety of pagination approaches, page sizes, and ordering.

**Rate limiting:** Unified APIs sync data with each underlying API according to each provider's rate limits so that you can consume data without needing to understand the differences between providers.

**Error handling:** Unified APIs apply a standard set of error codes and responses so you can easily distinguish issues that otherwise are handled differently by each underlying API.

### Syncing: How data is refreshed

Unified APIs don't just normalize data structure and access methods, they also sync the data for you. This has some big implications, so let's run through how it works.

1. Unified APIs make API requests on behalf of your customers for each of their configured integrations.
2. Sync frequencies are defined for each data model and target system. A sync will also be triggered immediately on the integration being configured as well as when a resync is manually triggered.
3. The Unified API diffs the data received with the prior state of the data to notify your app of changes and updates to the data.
4. You access the newly updated data via the Unified API.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c7f4f8b929f72158e76_0b4799e6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c7f4f8b929f72158e76_0b4799e6.webp)

Example of a Unified API syncing data from a third-party platform to your app

‍

Once the data is synced, Unified APIs emit a webhook to your app so that you can take action, such as retrieving the data via the Unified API right away. This is incredibly powerful as it provides near real-time data updates without having to poll each target system or build webhooks with each system yourself.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c9fca2c0045126aa1e4_810d900d.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64668c9fca2c0045126aa1e4_810d900d.webp)

Webhooks from a Unified API enable real-time access to data

‍

With a Unified API syncing data on behalf of your users, you'll be able to tap into a constantly updated and clean set of data. You won't need to run infrastructure to do data polling or transform the data. This is a huge win for your engineering productivity and infrastructure budget. It does mean that Unified APIs store your users' data, so you'll want to select a Unified API that is reliable, secure, and a good data steward. Check out the [Evaluation Guide on how to choose a Unified API](https://www.merge.dev/blog/unified-api-evaluation-guide) that meets your data needs.

### Additional Unified API Resources

If you're looking to go deeper on Unified APIs, check out these essential articles:

- [What is a Unified API](https://www.merge.dev/blog/what-is-a-unified-api)
- [Unified API Pros and Cons](https://www.merge.dev/blog/unified-api-pros-and-cons)
- [Unified API Evaluation Guide](https://www.merge.dev/blog/unified-api-evaluation-guide)
- [Unified API Alternatives](https://www.merge.dev/blog/unified-api-alternatives)

For all of this info in one comprehensive place, download the [Guide to Unified APIs](https://www.merge.dev/learning/guide-to-building-product-integrations-with-unified-apis).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=327feafc-8de3-4c6b-8156-e1f1c8197191&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e2dd5a40-2bdd-4a6f-96b7-0263fd01c5df&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-unified-apis-work&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=327feafc-8de3-4c6b-8156-e1f1c8197191&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e2dd5a40-2bdd-4a6f-96b7-0263fd01c5df&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-unified-apis-work&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=78fc1048-314a-433e-bc53-7d4ac5af6ea7&bo=2&sid=a89bf3603e8c11f0b3f9475ce9b93e16&vid=a89d06703e8c11f09e9bb750c7949bdc&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20Unified%20APIs%20work&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-unified-apis-work&r=&lt=793&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=410341)