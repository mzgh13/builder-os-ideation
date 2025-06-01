---
url: "https://www.merge.dev/blog/3rd-party-integration"
title: "What are 3rd-party integrations? What you should know"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/3rd-party-integration#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/3rd-party-integration#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/3rd-party-integration#)

Table of contents

[Definition of 3rd-party integrations](https://www.merge.dev/blog/3rd-party-integration#definition-of-3rd-party-integrations)

[Examples of 3rd-party integrations](https://www.merge.dev/blog/3rd-party-integration#examples-of-3rd-party-integrations)

[Benefits of 3rd-party integrations](https://www.merge.dev/blog/3rd-party-integration#benefits-of-3rd-party-integrations)

[Issues with 3rd-party integrations](https://www.merge.dev/blog/3rd-party-integration#issues-with-3rd-party-integrations)

[3rd-party integration best practices](https://www.merge.dev/blog/3rd-party-integration#3rd-party-integration-best-practices)

[3rd-party integration options](https://www.merge.dev/blog/3rd-party-integration#3rd-party-integration-options)

[3rd-party integration FAQ](https://www.merge.dev/blog/3rd-party-integration#3rd-party-integration-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F3rd-party-integration)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7251ac179ef5aaee50_RAG_examples.webp)**The ultimate guide to SaaS integration**](https://www.merge.dev/blog/saas-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7000295f40b50711b2_API_key_guide.webp)**How to build integrations effectively (5 best practices)**](https://www.merge.dev/blog/building-integrations)

# What are 3rd-party integrations? What you should know

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb1b6c5002162a36293_3rd-party_integration_guide-p-1600.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to build integrations—either with the applications you use internally or between your product and 3rd-party applications—, you might initially decide to [build them natively](https://merge.dev/blog/native-integrations).

In other words, your in-house developers would scope, develop, test, and maintain every integration themselves.

While this approach can work in the beginning, your engineers will likely become overwhelmed and experience difficulty in keeping pace with demand.

This might lead you to invest in 3rd-party integrations.

We'll help you decide whether 3rd-party integrations are right for you by exploring common ways to use them, their benefits and issues, and the different types of solutions you can use.

But first, let’s align on what we mean by 3rd-party integrations.

_Related:_ [_Popular API integration tools_](https://www.merge.dev/blog/api-integration-tools)

## **Definition of 3rd-party integrations**

It’s any integration that a 3rd-party platform helps your organization build and maintain, typically via APIs. The integrations can be either between the applications you use within your organization or between your product and the 3rd-party applications your clients and prospects use.

[![A visual of product integrations alongside a visual of an internal integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be2081f0c3df93352defe_650781e9fa8f5135dc145e7e_Types%2520of%2520API%2520integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be2081f0c3df93352defe_650781e9fa8f5135dc145e7e_Types%2520of%2520API%2520integration.webp)

To provide further clarity on 3rd-party integrations, we’ll share a concise breakdown of [its differences from native integrations](https://merge.dev/blog/native-integrations-vs-api) in the following section.

### **Native integrations vs 3rd-party integrations**

Native integrations require the use of internal resources (typically your developers), while 3rd-party integrations are any that are outsourced to an external vendor. Although each has its pros and cons, 3rd-party integrations are often the more scalable approach to building and maintaining integrations.

#### Ready to scale your 3rd-party integrations?

Simply build to Merge's Unified API to add hundreds of integrations to your product.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F3rd-party-integration)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Examples of 3rd-party integrations**

Here are just a few 3rd-party integration use cases:

### **Sync issues across your ticketing applications**

As your customer success or support teams engage with clients, they’ll inevitably run into issues that require your developers to get involved.

To ensure your developers become aware of such issues quickly and have the context they need to address them, you can use a 3rd-party app to integrate the application your customer-facing teams use to manage issues (e.g. Zendesk) with the application your engineers use (e.g. Jira). You can then build a [bidirectional sync](https://www.merge.dev/blog/bidirectional-synchronization) that works as follows: Any time a ticket gets escalated to engineering, the ticket gets created in engineering’s ticketing app, along with key details on the issue. As engineering updates the ticket over time, the issue in your customer-facing team’s ticketing app gets updated accordingly, all but ensuring the two teams work in lockstep.

### **Issue corporate cards to new hires on their first day**

Imagine you offer a platform that issues corporate cards.

To ensure your clients’ new hires get corporate cards on their first day that include the right spend limits across categories, you can use a 3rd-party solution to [integrate your product](https://merge.dev/blog/product-integrations) with your clients’ HRIS systems and build the following workflow: Once an employee gets added to your HRIS solution, they get added to your platform, along with certain associated fields.

Based on the information populated in those associated fields, such as their location, department, and job level, and the rules your client has set for managing spend limits for employees, your product can automatically generate and issue a corporate card to that employee with the appropriate spend limits.

[_Learn how Ramp leverages Merge to address the use case above—and more_](https://merge.dev/case-studies/ramp) _._

### **Create tasks in your CRM when clients exceed a certain threshold in usage**

While there’s a variety of signals that determine whether a client is ready to spend more with you, product usage is likely at the top of your list.

Once a client exceeds a certain threshold in usage, it’s often a telltale sign that they’re seeing value from your platform and are ready to invest in a more advanced subscription and/or buy complementary products.

You can make sure your reps are aware of these opportunities across your accounts by connecting your data warehouse (e.g. Snowflake) with your CRM (e.g. Salesforce) and then syncing product usage data from tables in the former with associated accounts in the latter.

_Related:_ [_Common API integration examples_](https://merge.dev/blog/api-integration-examples)

## **Benefits of 3rd-party integrations**

Third-party integrations allow you to break down data silos, save developers time, improve client retention, and expand your total addressable market (TAM).

Let’s take a closer look at these benefits:

### **Breaks down data silos**

When employees don’t have access to the data they need within their applications, they can make suboptimal decisions, ignore opportunities, and become misaligned with other teams that have the data.

Fortunately, 3rd-party integrations allow data to flow freely between the connected applications, allowing you to address data silos and resolve the issues they once caused.

### **Saves developers time**

Forcing developers to build and maintain integrations themselves can be extremely tedious and a poor use of their time.

Third-party integrations, by their very nature, allow you to outsource much of this work. This gives time back to your engineers so they can focus on tasks that are more critical to the business.

### **Improves client retention**

Customer-facing integrations enable your clients to access additional data and automated workflows within your application. This ultimately helps them realize more value from your product, which, in turn, makes them all the more likely to renew.

### **Expands your TAM**

As you look to expand into new regions or move upmarket, you’ll likely find that these organizations use a different set of applications for a specific category of software. If you can offer integrations between your product and the applications they use you’ll be more likely to win their business.

_Related:_ [_Common API integration benefits_](https://www.merge.dev/blog/api-integration-benefits)

## **Issues with 3rd-party integrations**

Unfortunately, 3rd-party integrations aren’t without their issues. Here are a few potential drawbacks they present:

### **Technical expertise requirements**

Many 3rd-party integration providers claim to be low-code/no-code, but in reality, their platforms are fairly complex and require some degree of coding. This means your developers will have to build and maintain the integrations themselves.

_Related:_ [_Drawbacks of point-to-point integration_](https://merge.dev/blog/point-to-point-integration)

### **Lack of visibility on performance**

Integrations can fail for a number of reasons—from API outages to expired API keys. Most 3rd-party integration solutions fail to reveal why a specific integration fails as well as how the issue can be resolved. This ultimately allows the issue to persist and cause further harm to your business and your customers.

### **Risks of working with a 3rd-party**

There’s always an inherent risk to outsourcing your integrations. You need the provider to offer solid support, stay in business, provide a reliable, secure solution, and much more. Given the stakes involved, implementing a comprehensive evaluation process is critical.

## 3rd-party integration best practices

As you use a 3rd-party integration solution, you should keep the following best practices top of mind:

### **Test your integrations before pushing them to production**

As you build integrations in the 3rd-party solution, you might inadvertently miss a step or set up a step incorrectly. You might be able to identify these errors by carefully reviewing the integration and asking peers to review it as well, but the best way to pinpoint them is by testing the integration within the application and seeing if it works as intended.

### **Sync integration errors between your integration solution and your monitoring tool(s)**

While identifying issues within your integrations is helpful, the engineering teams that need to diagnose and resolve it often rely on their monitoring tool (e.g. Splunk).

Assuming that’s the case at your organization, you should connect your integration solution with your monitoring tool and build a bidirectional sync for [integration issues](https://www.merge.dev/blog/integration-issues). That way, your engineers can find issues easily and work to resolve them quickly, while your customer-facing team (and other teams that rely on your integration tool) can stay up-to-date on the status of an issue—allowing them to avoid asking engineering for updates.

### **Routinely analyze integration performance on a holistic level**

As integration issues crop up over time, you’ll want to see which issues keep happening, the applications they occur in, when they happen, the clients that are affected (if you’re analyzing product integrations), and so on.

It’s only through this high-level analysis that you can pinpoint trends, prioritize fixes, and allocate resources optimally.

### **Designate specific resources to your integration tool**

Your 3rd-party integration tool likely has a somewhat steep learning curve. As a result, asking several employees to use the tool can take up a lot of their time and come at a high cost to your business (especially when you need engineers to use the solution).

To minimize the number of employees who are involved, it may be worth designating a few of them to be the application’s “power users”. These individuals can perform all of the tasks in the application, either for themselves or on behalf of others.

### **Start the relationship with the vendor by only building a few integrations**

The more integrations you build with the 3rd-party integration solution, the more difficult it becomes to move away from them.

With that in mind, you should start by only building 1 or 2 integrations and see how the experience goes across various dimensions. This includes anything from the time it takes to push the integrations live to how the integrations perform to the customer support the vendor provides. Once the vendor performs up to expectations during this “trial period”, you can move forward in increasing the scope of the engagement (alternatively, you can move on if it doesn’t go as well).

_Related:_ [_Examples of third-party API integrations_](https://www.merge.dev/blog/third-party-api-integration)

## **3rd-party integration options**

Once you’re ready to invest in 3rd-party integrations, you’ll need to determine the type of platform you should use.

We’ll cover common options for integrating your applications internally as well as for integrating your product with 3rd-party applications.

### **3rd-party integration solutions for internally-used applications**

Here are some of the most common options:

#### **iPaaS**

An integration platform as a service (iPaaS) is a cloud-based solution that lets you integrate SaaS applications, databases, on-premises systems, and then implement data flows that work across them.

[![A visual illustration of iPaaS](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2c045eef89e999b2e_VaeSMciUKkeyr6XChP7QycUeuZimzh_JfHhEhQYkc5AnC_9bwUkczLdVMr7ydX15xZM-UZeR-QhL8GjJLmFjLWcp9iiBjCDsiL2ceOGzK9QSNxN-ymqBHO5xS48x7yRkJN5Acx3wyT6wMXfQXJUpcBE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2c045eef89e999b2e_VaeSMciUKkeyr6XChP7QycUeuZimzh_JfHhEhQYkc5AnC_9bwUkczLdVMr7ydX15xZM-UZeR-QhL8GjJLmFjLWcp9iiBjCDsiL2ceOGzK9QSNxN-ymqBHO5xS48x7yRkJN5Acx3wyT6wMXfQXJUpcBE.webp)

The platform offers pre-built application connectors and automation templates to help fast-track integration and automation development. It also offers some visibility on the performance of your integrations.

That said, in spite of their branding, iPaaS solutions often aren’t low-code. As a result, your engineers may have to be the ones who use the platform to build and maintain integrations. In addition, iPaaS solutions generally offer limited management capabilities; you can see when issues occur and the volume of issues that transpire, but your team still needs to determine the root causes of the issues and how to best address them.

#### **RPA software**

Robotic process automation (RPA) software uses scripts (or “bots”) to automate routine tasks that employees would perform. This can be copying and pasting information across applications, running simple computations on a spreadsheet, adding email attachments to a client’s page in your CRM, and so on.

RPA software is ideal when the applications and/or data you want to access are hard to reach (e.g. they don’t offer APIs). However, the application often requires technical expertise to use, and the bots can require significant maintenance over time (any changes to a UI can affect a bot).

### **3rd-party solutions for product integrations**

Here are your top options for implementing customer-facing integrations:

#### **Embedded iPaaS**

An embedded iPaaS is simply an iPaaS that can be embedded directly into your product.

You can deploy it in a few different ways. For instance, you can build and maintain the integrations on your clients’ behalf and simply allow them to access the integrations; you can let clients build the integrations themselves within your application; or you can adopt a combination of both approaches.

While an embedded iPaaS accelerates integration development when you compare it to building integrations natively, the solution forces you to build integrations one at a time. Also, like an iPaaS solution, it requires technical expertise to use. Taken together, it’s clear that the solution makes it difficult to scale product integrations.

#### **Unified API**

A unified API solution, which is also referred to as a [universal API solution](https://merge.dev/blog/universal-api), offers a single, aggregated API. Once you build to the API successfully, you can access several integrations in a specific category of software (e.g. ticketing).

[![A visual illustration of a unified API solution](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2876336ff0190f66a_-bP6-SNcu63bECvnqI1rnm-ENcZlsKKlsmJIw3duX-_y0FqtcKGABNozsBhmdpSrgJ1Ybig5M4r3UGVIHHruw8WzJJbjfvpgJuC6SmBxU4Dj0NmzRL3mIS4XBX9vLGEjd3tu_5NuH9fkF7CSL3_p4cs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2876336ff0190f66a_-bP6-SNcu63bECvnqI1rnm-ENcZlsKKlsmJIw3duX-_y0FqtcKGABNozsBhmdpSrgJ1Ybig5M4r3UGVIHHruw8WzJJbjfvpgJuC6SmBxU4Dj0NmzRL3mIS4XBX9vLGEjd3tu_5NuH9fkF7CSL3_p4cs.webp)

Since a [unified API solution](https://merge.dev/blog/what-is-a-unified-api) lets you integrate with multiple 3rd-party applications quickly and easily, it’s a more scalable approach than an embedded iPaaS and, of course, native integrations.

That said, there are [countless unified API vendors](https://merge.dev/blog/unified-api-examples), and it can get easy to get overwhelmed when choosing the best solution for your organization.

Merge, the leading Unified API platform, is likely best suited to address your ambitions for building product integrations.

The platform offers hundreds of integrations across key software categories, robust integration management capabilities, comprehensive common models across its unified APIs (along with the ability to access data outside of these models), and much more.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2F3rd-party-integration) _._

## **3rd-party integration FAQ**

In case you have any more questions on 3rd-party integrations, we’ve addressed several more below.

#### **What are some best practices for evaluating 3rd-party integration vendors?**

You’ll want to take several measures:

- **Review the platforms’ reviews on 3rd-party review sites (e.g., G2).** Through the reviews, you can get a sense of each platform’s strengths and weaknesses relative to competitors. On some review sites, you can even see how the platforms stack up more holistically within their category

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/675228f2e398e0871a5da449_AD_4nXcEWqtOigDV9DT0gI39yVZAOzMsbMo7CJOOyzpXCs1p6sFJl0X8O_pXx1RIkm3cNe1n2ZsMoUGdRsNJFj8QA54H7O8BYl6M7rpGyjKVtTY4A4bvOz2UFd0pzvaf45TfkGIPCbfyRA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/675228f2e398e0871a5da449_AD_4nXcEWqtOigDV9DT0gI39yVZAOzMsbMo7CJOOyzpXCs1p6sFJl0X8O_pXx1RIkm3cNe1n2ZsMoUGdRsNJFj8QA54H7O8BYl6M7rpGyjKVtTY4A4bvOz2UFd0pzvaf45TfkGIPCbfyRA.webp)

_The_ [_G2® Grid for Unified APIs_](https://www.g2.com/categories/unified-apis#grid) _can help you quickly and easily compare the integration solutions in the space_

- **Go on a proof of concept before investing in a vendor.** Many 3rd-party integration solutions make the same claims, which can make it difficult to determine your best option. To break through the noise, you should go on a proof of concept with one of your top options and confirm that it can support your core use case(s)

- **Read customer success stories and use customer references.** You’ll likely find that certain vendors stand out in both the quality and quantity of case studies they’ve made publicly available. Also, by using customer references for your top vendors, you can better suss out the option that best meets your [integration requirements](http://merge.dev/blog/integration-requirements)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/675228f2c6faf6f88070b5db_AD_4nXfJ1edvhfjaGS3fHhjsGHKrhRSDtnU706q1A0_Ab00IjAnq-AnUMKXR-FYBloA-3_0u0c144YKfF7uJXeYZjFva34oJiKHgI0dtFSNEh_kJqcHPaxXZttC7kDWerh4d3WnrbXPtUw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/675228f2c6faf6f88070b5db_AD_4nXfJ1edvhfjaGS3fHhjsGHKrhRSDtnU706q1A0_Ab00IjAnq-AnUMKXR-FYBloA-3_0u0c144YKfF7uJXeYZjFva34oJiKHgI0dtFSNEh_kJqcHPaxXZttC7kDWerh4d3WnrbXPtUw.webp)

_Merge has dozens of case studies, which include enterprise companies like AngelList, BILL, Ramp, and Drata_

#### **How can you integrate with applications natively?**

Each application has a separate set of steps that you’ll need to follow.

That said, at a high level, the process typically involves:

1\. Determining the appropriate endpoint to build to

2\. Constructing the request to that endpoint in a specific coding language

3\. Testing the connection in a variety of ways to ensure the connection won’t experience serious issues once pushed to production

4\. Pushing the integration to production and confirming that the initial responses come back as expected

5\. Documenting how the integration was built so that other engineers can get onboarded onto the integration and troubleshoot any future issues associated with the integration

_Related:_ [_The steps for building any API integration_](https://www.merge.dev/blog/api-integration-steps)

#### **What are some popular 3rd-party integration tools?**

For internal integrations, some popular vendors include Zapier, Mulesoft, Jitterbit, Make, and Boomi; while for customer-facing integrations, popular vendors include Merge, Tray.ai, Workato, and Codat.

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

[iframe](https://app.qualified.com/w/1/faa5v4dWtZ1a9fXx/messenger?uuid=6ea5083e-41b3-4978-b536-95373f0d2ceb)

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6385ecb9-1a1e-47f2-ba1c-ccd2b34b81ac&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d991bcd1-4003-4ac8-a537-2121e33bb42f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F3rd-party-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6385ecb9-1a1e-47f2-ba1c-ccd2b34b81ac&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d991bcd1-4003-4ac8-a537-2121e33bb42f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F3rd-party-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=15269f5e-f722-4fd1-8437-97616ecabc92&bo=2&sid=b05602703e8c11f0a7d43b47e3f61c0c&vid=b05650303e8c11f0b07f439e047e1ac3&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=What%20are%203rd-party%20integrations%3F%20What%20you%20should%20know&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2F3rd-party-integration&r=&lt=509&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=779319)

[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743443347&cv=11&fst=1748743443347&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&ptag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2F3rd-party-integration&hn=www.googleadservices.com&frm=0&tiba=What%20are%203rd-party%20integrations%3F%20What%20you%20should%20know&npa=0&pscdl=noapi&auid=116314858.1748743442&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743443543&cv=11&fst=1748743443543&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&ptag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2F3rd-party-integration&hn=www.googleadservices.com&frm=0&tiba=What%20are%203rd-party%20integrations%3F%20What%20you%20should%20know&did=dZTQ1Zm&gdid=dZTQ1Zm&npa=0&pscdl=noapi&auid=116314858.1748743442&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)