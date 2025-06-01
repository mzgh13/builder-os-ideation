---
url: "https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges"
title: "The top challenges of normalizing multiple API integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#)

Table of contents

[What is data normalization in the context of integration?](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#what-is-data-normalization-in-the-context-of-integration)

[Challenges of normalizing data](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#challenges-of-normalizing-data)

[Accounting for unique data configurations in enterprise software](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#accounting-for-unique-data-configurations-in-enterprise-software)

[Allowing for user-defined mapping](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#allowing-for-user-defined-mapping)

[Avoid normalization hassles with Merge](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges#avoid-normalization-hassles-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fnormalizing-multiple-api-integrations-challenges)

##### Just for you

No items found.

# The top challenges of normalizing multiple API integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb198dcb1a5cce561fd_SaaS_integration_challenges.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

[Gartner estimates](https://www.gartner.com/smarterwithgartner/how-to-create-a-business-case-for-data-quality-improvement) that poor data quality leads to $15 million in losses per year, on average, at an organization.

Part of the solution to better data quality involves applying the concept of normalization: that is, having a single source of truth for how data can be read and written, regardless of where it comes from.

To help you leverage data normalization effectively, we’ll cover how it works, the top challenges of performing it for multiple API integrations, and a solution to help you overcome these challenges.

Note: Data normalization is used both in internal and external (customer-facing) integrations.

## What is data normalization in the context of integration?

Data normalization accurately and consistently transforms data from a third-party source to a unified destination format, like your database.

In the context of [integrating multiple APIs](https://www.merge.dev/blog/multiple-api-integration), it means you’re normalizing data across multiple unique systems into a single format.

To help clarify this definition, let's use an example: Say you’re looking to integrate an HRIS solution with your product to sync employee start dates (among other fields). The HRIS stores an employee start date as MM-DD-YYYY, while your backend stores it as DD-MM-YYYY. Normalizing this data would involve:

1. Establishing DD-MM-YYYY as the standard date format in your backend.
2. Writing logic to consistently translate source data into your unified format.
3. Anticipating any needs for custom values or insertions that may be required from your customer. For example, a customer might store 'employee start date' in a custom field.

[![A visualization of the normalization process ](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655bdc6f812dfbbd4e5830b2_foVYQ9wzTQeYUJ3yjg_cd4Me68mjpJDN8f__j0WFUfgzFohNZLZs5US3irpk2IlJMo4hCu2jzdB9Gaot8SyffVXvTAJEs-AzpjvmMBlFNZngNrU3yFyMlP82SB9C8sVd_67U7DaO6XNH3CSz_QUJjbk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655bdc6f812dfbbd4e5830b2_foVYQ9wzTQeYUJ3yjg_cd4Me68mjpJDN8f__j0WFUfgzFohNZLZs5US3irpk2IlJMo4hCu2jzdB9Gaot8SyffVXvTAJEs-AzpjvmMBlFNZngNrU3yFyMlP82SB9C8sVd_67U7DaO6XNH3CSz_QUJjbk.webp)

Note: Data normalization and data standardization might seem different. In practice, they aren’t. **Data normalization and data standardization** are functionally the same thing when defining the process of integration **.** For the purposes of this article, we’ll use “data normalization.”

## Challenges of normalizing data

While there are several obstacles, here are the top ones to account for.

### Unifying data models at scale

If you're accustomed to one-to-one or simple integrations, the concept of normalizing data into a ‘common’ data model may be new.

A common data model is a standard data object that’s is flexible enough to represent a single concept from multiple different APIs. Common models represent concepts in the real world; there can be “Employee” models, “Candidate” models, “Invoice” models, and so on.

Determining what a “Common” data model looks like for any external integration ahead of time can save your engineering team headaches and heartaches.

[![Example of normalizing employement_type object](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655b78aae48536df328295cb_dRwXg8C-X-VZLzw-IiYXE2Q4KyZzSrvQuBXKiIRRLhHc5VJI5vzIg75mWEFcOYSMWSNDMW3drD8OYUx1wl8yTiYuAQD2wRyMrPJew_SNKFwm1yFj4E53RwILSyTgX4RJMqTAytRzYeCuDZ1afUH3Juk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655b78aae48536df328295cb_dRwXg8C-X-VZLzw-IiYXE2Q4KyZzSrvQuBXKiIRRLhHc5VJI5vzIg75mWEFcOYSMWSNDMW3drD8OYUx1wl8yTiYuAQD2wRyMrPJew_SNKFwm1yFj4E53RwILSyTgX4RJMqTAytRzYeCuDZ1afUH3Juk.webp)

To help make this point, let’s start with what the world looks like _without_ a common data model.

_Related:_ [_A deep dive on the different types of REST API pagination_](https://www.merge.dev/blog/rest-api-pagination)

#### The scenario without a common data model

Imagine that you’re setting up [applicant tracking system (ATS) integrations](https://www.merge.dev/blog/guide-to-ats-api-integrations). Initially, you focus on Lever, where demand is high. You map Lever’s API fields directly to your backend, creating a simple 1:1 mapping.

Later, you need to integrate with Greenhouse. But there's a twist: The Greenhouse API, unlike Lever’s, has two fields to represent name: \`first\_name\` and \`last\_name.\` You think, "I'll just add a new field to accommodate this."

So, now your schema for an ATS candidate has three separate fields for someone’s name. \`Name\`, \`First\_name\`, and \`Last\_name.\`

As you continue to integrate with more ATS systems, you’ll find that each has a unique conventions for naming fields, leading your backend database to become cluttered with various fields for essentially the same data point.

When does it end? It’s up to you.

To recap, here are the top challenges of operating without a common data model:

- **Increased complexity:** Managing and understanding your database becomes increasingly complex with each new integration.
- **Data redundancy:** You end up with multiple fields in your database that represent the same data, leading to redundancy and potential inconsistencies.
- **Difficult to maintain:** Updating or modifying integrations becomes more difficult as you have to deal with different structures and fields for each ATS.
- **Scalability issues:** As you add more integrations, scaling your integrations' architecture becomes more challenging due to the ever-increasing number of fields and the complex logic required to handle them. And even if you have a common data model set up, you’ll still need to manage and maintain it at scale.

### Transforming 3rd-party data at scale

Field transformation may seem trivial at first. In its most basic format, it’s making sure a field from system “A” fits the standards of system “B.” But its difficulties lie in building a transformation engine that's **adaptable and reliable** at returning consistently transformed data at scale.

To make this point, let’s continue with our example. You’ve chosen to normalize the names of candidates in ATS solutions to “First\_Name” and “Last\_Name.” The data in the source system, Lever, is stored as “FullName.”

Your code’s logic then should just look for the first space in a name, and then store the two strings separately. So, “FullName”:“Hayley Ye” becomes “First\_Name”: “Hayley”, and “Last\_Name”: “Ye”.

This seems simple enough, but your data transformation engine can cause issues.

#### Data transformation engines require consistent fine-tuning

The first issue that you run into is **adaptability around edge cases.**

For example, what if someone has a middle name? Or, what if they have a hyphenated name? Or what if the data is entered incorrectly? Obviously, these basic edge cases can eventually be accounted for. But what you can’t account for is the myriad of edge cases that will continue to add up.

This requires you to invest in integration transformation tooling that’s adaptableand efficient. For example, how can you quickly identify the source of poor data, and update the underlying transformation logic so that existing integrations don’t break?

Additionally, as you onboard customers, you'll need to continually adjust your transformation logic. New customers mean new, unpredictable “inputs” to your transformation engine. This requires you to have invested a lot in a reliable maintenance engine.

_Related:_ [_A guide to integration maintenance_](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance)

### Data transformation engines can prove difficult to scale

Ensuring that the transformation process is both efficient and scalable is another layer of complexity. Your transformation engine can’t just handle data from a single integration: It needs to accommodate dozens of integrations used by hundreds of potential customers.

It’s one thing to ingest and transform 200,000 JSON objects. It’s another to ingest and transform 20M. How you scale your system will require a serious investment in architecture.

While the fundamentals of field and value transformation are simple, the tooling and architecture required to both update transformation logic and maintain it are far from simple.

## Accounting for unique data configurations in enterprise software

The difficulties and nuances of business transformation continue to mount as you move upmarket.

Let’s say you’re trying to onboard X set of enterprise users, however the underlying systems they store their data in are a black box. This is because you only know the output of their APIs.

Enterprise business systems are known for adapting to business needs, and this makes building a generic integration very tough.

Your challenge isn’t to simply transform the data (addressed above), but also to know _how that data changes over time_.

Consider a typical scenario in a CRM system: when an Opportunity, like a potential sale, is successfully closed, it gets converted into a customer record. The question arises: how should your system query this data and understand that that change occurred.

For example, contact details, communication history, and purchase preferences from the Opportunity might need to be migrated to the customer's account. It's crucial to determine how your system will handle the logic of this transformation.

### Keeping data secure while only collecting the information that’s needed

In an era of frequent data breaches and stricter privacy regulations, ensuring security and practicing data minimization are paramount in API integration.

Security concerns aren't just about protecting data from unauthorized access; they're also about ensuring that the data is transmitted, transformed, and stored securely throughout the integration process. This involves implementing robust encryption methods, secure authentication protocols, and a shift left stance for security.

Data minimization, on the other hand, is about only collecting and processing the data that’s absolutely necessary for the intended purpose. This is not only a best practice from a data privacy perspective but also reduces the complexity and potential risks associated with data handling.

Implementing features such as **Scopes**—or the controls that guarantee that you're only syncing the necessary data into your system is—necessary, but far from trivial.

Balancing the need for detailed, comprehensive multi-API integration with the principles of security and data minimization requires careful planning, a thorough understanding of the relevant data privacy laws, and a proactive approach to data governance.

_Related:_ [_The top SaaS integration challenges_](https://www.merge.dev/blog/saas-integration-challenges)

## Allowing for user-defined mapping

Allowing users to define their own data mappings introduces additional complexity. This flexibility can be incredibly powerful, allowing users to tailor integrations to their specific needs. However, it also adds another dimension to the challenge, as you now need to support a wide range of potential mapping configurations, each with its own quirks and complexities.

Providing user-defined mapping capabilities requires robust, intuitive interfaces that allow users to easily configure their data mappings, as well as a backend system capable of handling a diverse array of mapping scenarios. It also necessitates a strong support and documentation system to guide users through the process and help them resolve any issues they might encounter.

## Avoid normalization hassles with Merge

What if there was a platform that normalized all the data your customers care about?

Meet Merge.

Merge is a product integration platform that offers dozens of [common data models](https://www.merge.dev/features/common-models) for 200+ integrations. The platform handles all the underlying logic and transformation, and has robust security and compliance measures in place to guarantee that your customers’ data is kept secure.

You can learn more about how Merge works as well as how it can help your team integrate at scale by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fnormalizing-multiple-api-integrations-challenges).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)

Anthony Lagana

Product Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6cbd41fe-aa67-4ea4-a31a-a1bc0eb69f4e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1cb84283-ed30-4e85-b2b0-8ba54c0087fb&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalizing-multiple-api-integrations-challenges&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6cbd41fe-aa67-4ea4-a31a-a1bc0eb69f4e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1cb84283-ed30-4e85-b2b0-8ba54c0087fb&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalizing-multiple-api-integrations-challenges&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e88a2cbc-effc-4eea-bbfe-69309a15b1ad&bo=2&sid=372502803e8e11f0a6564329c8da8976&vid=37258b103e8e11f0bf21c50545d0d144&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=The%20top%20challenges%20of%20normalizing%20multiple%20API%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalizing-multiple-api-integrations-challenges&r=&lt=437&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=911279)