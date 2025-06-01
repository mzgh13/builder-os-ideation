---
url: "https://www.merge.dev/blog/multiple-api-integration"
title: "A guide to integrating multiple APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/multiple-api-integration#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/multiple-api-integration#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/multiple-api-integration#)

Table of contents

[What is multiple API integration?](https://www.merge.dev/blog/multiple-api-integration#what-is-multiple-api-integration)

[Examples of integrating with multiple APIs](https://www.merge.dev/blog/multiple-api-integration#examples-of-integrating-with-multiple-apis)

[Multiple API integration benefits](https://www.merge.dev/blog/multiple-api-integration#multiple-api-integration-benefits)

[Challenges of integrating with multiple APIs](https://www.merge.dev/blog/multiple-api-integration#challenges-of-integrating-with-multiple-apis)

[Criteria for selecting a tool that lets you integrate with multiple APIs](https://www.merge.dev/blog/multiple-api-integration#criteria-for-selecting-a-tool-that-lets-you-integrate-with-multiple-apis)

[How Merge meets this criteria](https://www.merge.dev/blog/multiple-api-integration#how-merge-meets-this-criteria)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmultiple-api-integration)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74fb72017b567d9265_RAG_benefits.webp)**Top challenges of API pagination for multiple integrations**](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb198dcb1a5cce561fd_SaaS_integration_challenges.webp)**The top challenges of normalizing multiple API integrations**](https://www.merge.dev/blog/normalizing-multiple-api-integrations-challenges)

# A guide to integrating multiple APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856caf87ff8c191004f86e_Multiple_API_integration.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

As you build multiple integrations at your organization, you’ll face a number of challenges when trying to ‘unify’ disparate systems. These challenges occur even if the data you’re trying to get is more consistent. For example, there’s no unified data model across the countless HRIS platforms available in the market.

If expanding your integrations is a key focus, then it’s critical to understand what integrating multiple APIs means, the use cases worth building, the challenges worth anticipating, and the criteria for selecting a 3rd-party tool that can support your efforts.

Let’s dive in.

_Note: There are two types of multi-API integrations. There’s integrating with multiple APIs in the same vertical (e.g. connecting to multiple CRM platforms or project management platforms) and there’s integrating with multiple APIs across different verticals (e.g. connecting to both CRM platforms and project management platforms). For the purposes of this article, we’ll focus on the former._

## What is multiple API integration?

It's the process of connecting a software application to many different external APIs with the goal of reading or writing a specific type of customer data. For example, a spend management application may build multiple HRIS integrations in order to ingest employee data from customers that use different HRIS platforms.

[![A visual breakdown of integrating multiple APIs in a single vertical](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237feb276b6473bc59e6e_Yb83on453qTyxzvR-pRhsnSro0gGwU7QTMQ-Dtqa27jBpx3b718107Av1wcFDfob3eG5w3hCQh54Ch0ARUT-V-kPqKgv75YMvgQNMSmd8PNWJkWh61_OaMBj0BvAvUS2uthASXO8MdD9K5i4nS0pI8k.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237feb276b6473bc59e6e_Yb83on453qTyxzvR-pRhsnSro0gGwU7QTMQ-Dtqa27jBpx3b718107Av1wcFDfob3eG5w3hCQh54Ch0ARUT-V-kPqKgv75YMvgQNMSmd8PNWJkWh61_OaMBj0BvAvUS2uthASXO8MdD9K5i4nS0pI8k.webp)

#### Ready to scale your product integrations?

Learn how Merge can help you add hundreds of product integrations across software categories in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmultiple-api-integration)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## Examples of integrating with multiple APIs

The reason to integrate with multiple APIs is simple: SaaS consumers use different platforms to accomplish the same tasks. For example, one security platform may use Greenhouse to source candidates, while another may use Lever. Both deal with candidate and recruiting data, but if you want to sell to both organizations, you need to offer integrations with Greenhouse and Lever.

Let’s go through some common examples of multiple API integration.

### Automate employee onboarding and offboarding

If a software company needed employee data to run key tasks: such as managing a compliance process, provisioning credit cards or software, or assigning courses, they often had an HR admin manually upload CSV records of all employees.

This process proved cumbersome and prone to errors.

Now, many software providers will [build integrations with key HRIS platforms](https://www.merge.dev/blog/guide-to-hris-api-integrations). This API integration allows a SaaS company to automatically pull relevant employee data from their customers. Even better, if an employee changes positions or is let go, that status will be programmatically reflected in the system.

[![A visual breakdown of automating employee onboarding and offboarding with your product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237fe20abb909b12400d5_UfZvAzsk1Wet8hz_ep4GGn_urkFZ-pYvbcZIPONrKdVubAMdAF7gFN3qpkKCXJOXmN_LzPuj056TbCeqKf7qmiEoQVWVQqYyQ88zwwAzsnHnjvxAC5rknYXliV0tB-LtoOAPT2ddRfEewzdP3Im0tBg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237fe20abb909b12400d5_UfZvAzsk1Wet8hz_ep4GGn_urkFZ-pYvbcZIPONrKdVubAMdAF7gFN3qpkKCXJOXmN_LzPuj056TbCeqKf7qmiEoQVWVQqYyQ88zwwAzsnHnjvxAC5rknYXliV0tB-LtoOAPT2ddRfEewzdP3Im0tBg.webp)

_Related:_ [_A guide to automated provisioning_](https://www.merge.dev/blog/automated-provisioning)

### Automating candidate sourcing

By integrating with the ATS a customer uses—such as Greenhouse, Lever, SAP, or UKG—, a candidate sourcing tool can allow a candidate’s profile to get uploaded in real-time, ensuring the company’s recruiting team can track them.

[![A visual breakdown of automating candidate sourcing](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237fef6b9064f3f8ac9d4_e3r0GME0AEdw1BS42nCqzLZ83spknylf_lbbwpOTmJgsClMvlaYO-eK_aH4QY2tKUSl2zlaEIK_9eF3nImzRDi8ujlsLgYOioh52r8acGtb_orKslv1zgSAUvbYZPM8e_r4_SWKdOHPXWFV4mlQr-Kg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655237fef6b9064f3f8ac9d4_e3r0GME0AEdw1BS42nCqzLZ83spknylf_lbbwpOTmJgsClMvlaYO-eK_aH4QY2tKUSl2zlaEIK_9eF3nImzRDi8ujlsLgYOioh52r8acGtb_orKslv1zgSAUvbYZPM8e_r4_SWKdOHPXWFV4mlQr-Kg.webp)

_Related:_ [_Examples of integrating applications_](https://www.merge.dev/blog/application-integration-examples)

### Automating security evidence collection

The process of pulling in relevant files, such as evidence of security processes or documentation, is critical for ensuring compliance, whether it’s ISO 27001 or SOC 2 Type II. However, this process can often be manual. For instance, a company’s security officer may have to manually find, upload, and verify the correct files on a security compliance provider’s application.

However, many compliance applications now offer integrations with file storage systems, such as Google Drive or OneDrive. This means that they can automatically ingest the relevant files, or streamline the file upload process for their customers.

[![A visual breakdown of automating file uploads in your product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6552546a82042c62541a80b6_iXCw_pq14bzwVYtgQfV7qHTB2f-KG24FUlV9reYh5V0K0d30W16xbux3Psp6TzmeZ1KNe23yVCHHpr_ku1XShmNtykyyLyenMcAJiEug0mvDk81rCUnfXAa6gurDl-dnKG_slYwBcDp-UH6W3pRNivo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6552546a82042c62541a80b6_iXCw_pq14bzwVYtgQfV7qHTB2f-KG24FUlV9reYh5V0K0d30W16xbux3Psp6TzmeZ1KNe23yVCHHpr_ku1XShmNtykyyLyenMcAJiEug0mvDk81rCUnfXAa6gurDl-dnKG_slYwBcDp-UH6W3pRNivo.webp)

### Train AI systems

With the recent boom in AI, the “new oil” is data.

Therefore, SaaS applications that want to offer robust and personalized AI capabilities often need to access the data stored in clients’ applications. For example, your app can leverage CRM data to train a model to identify high-propensity deals.

_Related:_ [_The top API integration examples_](https://www.merge.dev/blog/api-integration-examples)

## Multiple API integration benefits

Providing multiple API integrations gives software companies a chance to increase revenue by reaching more customers and the platforms they use. It also improves the overall customer experience: more data flows are automated, which unlocks and streamlines functionality for a software consumer.

Let’s take a closer look at its benefits:

### **Increases customer satisfaction**

Adding more integrations allows your software to provide more functionality. More specifically, it makes automating data workflows, whether it’s employee, sales, or financial data, incredibly easy. This means your customers get to do less work for more benefit: they get instant data updates without the time-consuming process of manually uploading or keying in data.

### **Expands your potential market**

Even if there are one or two major players in a category—think Salesforce for CRM—, there are still thousands of prospects and clients that use lesser-known solutions in that category. By integrating with as many of these platforms as you can, you’ll meet those prospects’ and customers’ expectations.

### **Provides a first-mover advantage**

Being the first to offer certain integrations can create a unique selling point that gives you a strategic edge.

With this in mind, it’s critical to deliberate on the platforms to integrate with, especially those not yet supported by your competitors.

_Related:_ [_The benefits of software integration_](https://www.merge.dev/blog/software-integration)

## Challenges of integrating with multiple APIs

For a product manager tasked with expanding the reach of integrations within the same vertical or category, going from 1 to many can be an arduous task.

Here are a few of the top challenges you’re most likely to encounter.

### Accessing the API

Getting access to a single API is difficult because many APIs require some form of partnership to build into their platform.

This may be a simple form to get listed on their marketplace, or it may be a complicated, multi-month process that can cost you $15-$50k per year.

### Accounting for new integrations within your existing code base

The initial integration often has a code base that's tailored for that sole API, with schemas and tables set up on a 1:1 basis to match a single API’s object structure. Stretching those same tables to accommodate multiple APIs or different data types may lead to complications.

The danger lies in your integrations becoming a patchwork, where you maintain multiple, potentially inconsistent approaches within the same system. As you expand, the complexity and entanglement of integration maintenance can increase significantly.

Some of the biggest pains stem from stretching data normalization, authentication, rate limiting, and pagination across multiple systems.

### Leveraging limited resources to build a new integration (while maintaining existing integrations)

Your limited resources are spread thin across various projects, with each project demanding attention. For instance, integrating a new CRM system involves more than just adding a new feature; it requires a complex process of matching data fields, ensuring compatibility with your user interface, and conducting extensive testing to prevent disruptions to your current service.

You’re likely undertaking this task with a limited number of engineers. To navigate this situation, you’ll need to prioritize integrations that are essential, which you can determine based on customer demand, potential ROI, or the company's needs.

You’ll also need to architect the fundamentals of a [multi-API integration strategy](https://www.merge.dev/blog/api-integration-strategy) that enables both long-term solutions and short-term wins.

### Educating go-to-market teams on your integrations’ feature disparities

You’ll encounter feature disparity when you offer different API integrations for the same feature, as not all APIs handle data in the same way. For example, in the HRIS industry, BambooHR lacks a 'Company' field, whereas AlexisHR includes it.

The particular API you integrate shapes the functionality of your product in distinct ways. Your team must understand these differences and be capable of explaining them to your customers.

You may find yourself instructing your sales team in different methods for each API integration, even if they address the same use case. For instance, Salesforce and HubSpot might both integrate with your CRM solution, but each will require a unique guide, including specific do’s and don’ts.

_Related:_ [_A guide to integrating applications effectively_](https://www.merge.dev/blog/application-integration-best-practices)

### Maintaining and managing the integrations

Here’s another fact of life: building the integrations isn’t even the hardest part. Once you launch an integration to customers, you’ll encounter a wide, unpredictable range of edge cases in data.

These bugs will require you and your team to drop everything and fix them as they come.

[![The two parallel work streams for managing integrations that are live](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a93e6e6a80e90bb32a6_-Qc3hP4REvBEwxzWXKzFDFxO404ZjdJCK478pFJLdMkuLbQrMdloBpsf3KFOjfyAZ-cDPs9GQ838RMhLcgJ6aS8VPS5oc3h4lWTKRn0_pZ7nOJDqrcVyp98z9hB5ky5B2X3Sct964ZzuHBPRt9lWsts.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a93e6e6a80e90bb32a6_-Qc3hP4REvBEwxzWXKzFDFxO404ZjdJCK478pFJLdMkuLbQrMdloBpsf3KFOjfyAZ-cDPs9GQ838RMhLcgJ6aS8VPS5oc3h4lWTKRn0_pZ7nOJDqrcVyp98z9hB5ky5B2X3Sct964ZzuHBPRt9lWsts.webp)

Once you launch your integrations, two critical cycles will begin: an engineer-led maintenance cycle that focuses on bug fixes, and a customer success-led management cycle that focuses on customer adoption and delight.

## Criteria for selecting a tool that lets you integrate with multiple APIs

If you choose to use a [3rd-party to add integrations](https://www.merge.dev/blog/3rd-party-integration), here’s some criteria to consider using during your evaluation:

- Partnership access
- Single point of integration with scalable infrastructure
- Simple and easy to use
- Customizable and extensible
- Maintenance and management included
- Bonus: Future-proof for cross category

### Partnership access

You’ll want to make sure that the 3rd-party provider either has partnerships with existing providers or can help you get partnerships with providers who require your confirmation.

Not doing so poses the risk that your app won’t be able to support specific customer segments (i.e. customers that use a specific application).

_Related:_ [_An easy way to build API integrations_](https://www.merge.dev/blog/easy-api-integration)

### Single point of integration with scalable infrastructure

The difficulty of scaling integrations is that there are so many APIs to both build into and maintain.

Having a single point of access means that your engineers won’t need to maintain a complex codebase, and, ideally, can just “build once” for any of the integrations you need to offer.

### Simple and easy to use

Integrations are high stakes, but so is the need to bring them to market efficiently.

The solution you choose shouldn’t be slower than your default alternative: [building in-house](https://www.merge.dev/blog/native-integrations). In fact, it should be straightforward. This could be through a low-code UI, or, if your developers prefer to code their applications, straightforward and comprehensive documentation.

### Customizable and extensible

Simplicity shouldn’t come at the expense of depth. If your customers have complex set-ups in their third-party platforms, such as using custom fields to hold key pieces of data, then you’ll want a solution provider that'll allow you to get and post that custom data easily.

### Maintenance and management included

Both maintenance (the process of fixing edge cases from malformed data) and management (the tools your customer success team has to interact with customers) shouldn’t be after thoughts.

After you launch an integration, these two components will be the most critical aspects for your team. Therefore, you'll need to make sure that the solution provider has the right tooling for managing and maintaining your integrations long-term.

### Future-proofed for cross-category expansion

Maybe you’re only looking to expand integrations in a single vertical: such as accounting or CRM. But as your business evolves, you might need to expand to more categories.

Choosing a single platform that can assist you in offering additional categories of integrations can help meet your long-term needs.

## How Merge meets this criteria

Merge offers a unified API, which is a single interface for accessing data from multiple third-party platforms. Think one data model for any “Employee” object, regardless of the platform that data came from.

Here’s more on what differentiates Merge:

- **Provides partnership access:** Merge offers partnerships with dozens of API platforms, including ADP, SAP, Justworks, and more.
- **Single point of integration with scalable infrastructure:** Merge’s Unified APIs were built to provide high-quality data from any integration in just a single build.
- **Simple and easy to use:** Companies such as Ramp have implemented Merge in just 2 weeks.
- **Customizable and extensible:** Merge offers a number of features to help you maintain and and manage your integrations, such as fully-searchable logs and automated issue detection functionality.
- **Future-proof for cross category:** Merge already offers 7 categories and continues to launch more.

Curious to see how Merge can support your integration needs? [Schedule a demo with one of our integration experts to find out](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmultiple-api-integration).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c253fa12-e6ec-484f-97d7-6f0a8cba61e7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=88f7f738-bb59-4cef-84ba-0085a370465c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmultiple-api-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c253fa12-e6ec-484f-97d7-6f0a8cba61e7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=88f7f738-bb59-4cef-84ba-0085a370465c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmultiple-api-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ffe3c770-2b00-4c01-b4b0-1d795aa369df&bo=2&sid=5c495e003e8c11f0a4f0db59d589254f&vid=5c499ab03e8c11f0ad9eb95459229041&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20integrating%20multiple%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmultiple-api-integration&r=&lt=526&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=99503)