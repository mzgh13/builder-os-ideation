---
url: "https://www.merge.dev/blog/a-guide-to-application-integration-maintenance"
title: "A guide to maintaining your product integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#)

Table of contents

[What is integration maintenance?](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#what-is-integration-maintenance)

[How are integration maintenance and management different?](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#how-are-integration-maintenance-and-management-different)

[Challenges of integration maintenance](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#challenges-of-integration-maintenance)

[What to look for in a integration maintenance provider](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#what-to-look-for-in-a-integration-maintenance-provider)

[Let Merge maintain your integrations for you](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance#let-merge-maintain-your-integrations-for-you)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fa-guide-to-application-integration-maintenance)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API error handling: definition, example, best practices**](https://www.merge.dev/blog/api-error-handling)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)**‍How to calculate the costs of API integrations**](https://www.merge.dev/blog/cost-of-api-integrations)

# A guide to maintaining your product integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

Building integrations is just the initial step in ensuring successful connectivity between applications over time.

You’ll also need to maintain the integrations as you onboard customers. Response bodies from API providers can vary wildly, and so every time you onboard a customer onto an integration, you are at risk of having your existing code throwing an error.

“Integration Maintenance'' is the work done by your engineers to fix bugs, edge cases, and unexpected errors caused by varying response bodies from third-party API through the entire lifecycle of your product.

These activities may seem trivial if you haven’t built an integration before. But when you have to perform them across dozens, if not hundreds, of integrations, the work can quickly overwhelm your in-house development team.

We’ll review the top challenges of integration maintenance, and how you can address them. But first, let’s align on the definition of application integration management.

## **What is integration maintenance?**

It’s when your in-house development team performs a specific activity on an integration that’s already built. These activities can be performed on integrations that are either customer-facing (i.e. product integrations) or that support internal processes.

They’re often centered around resolving bugs or issues. For example, unexpected API responses being returned by a third party are a painful, well known cause of integration maintenance.

_Related:_ [_What is an API integration strategy?_](https://www.merge.dev/blog/api-integration-strategy)

## **How are integration maintenance and management different?**

Integration maintenance deals with changes to your code base and is done by engineers. Maintenance, though not always customer-facing, affects your customers by potentially leading to data quality issues.

Integration management relates to business operations that focus on how your customer interacts with their integration. This includes your customer success and engineering team’s response to issues with customer authentication, onboarding, or data normalization.

Both integration maintenance and management are similar in that they occur after the initial build of your integrations. Additionally, there is no ‘end’ to this work — it will always be required as long as you have customers.

Note: The rest of this article is focused on maintaining **product** integrations. However, many of the points below also apply to managing internal integrations.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a93e6e6a80e90bb32a6_-Qc3hP4REvBEwxzWXKzFDFxO404ZjdJCK478pFJLdMkuLbQrMdloBpsf3KFOjfyAZ-cDPs9GQ838RMhLcgJ6aS8VPS5oc3h4lWTKRn0_pZ7nOJDqrcVyp98z9hB5ky5B2X3Sct964ZzuHBPRt9lWsts.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a93e6e6a80e90bb32a6_-Qc3hP4REvBEwxzWXKzFDFxO404ZjdJCK478pFJLdMkuLbQrMdloBpsf3KFOjfyAZ-cDPs9GQ838RMhLcgJ6aS8VPS5oc3h4lWTKRn0_pZ7nOJDqrcVyp98z9hB5ky5B2X3Sct964ZzuHBPRt9lWsts.webp)

_Integration maintenance and management happen in two parallel cycles for the lifetime of integrations._

## **Challenges of integration maintenance**

Until you encounter it, integration maintenance is underestimated work. Here are the top reasons it’s an ongoing burden.

### **Challenge 1: Unexpected edge cases and response bodies**

Most engineering problems have an existing problem space. They have known outputs and inputs.

Integrations are a different problem: the inputs are completely unpredictable. You don’t control the returned third-party API data. The data your application ingests can be different not just across integrations, but even on the same platform.

Your application has to programmatically and intelligently handle variable, unpredictable API response bodies at scale.

_Related:_ [_3 scenarios that can break your product integrations_](https://www.merge.dev/blog/scenarios-that-break-product-integrations)

### **Challenge 2: 3rd party support**

When a problem does pop up in a 3rd party API, it’s often best to go to the source: that platform’s documentation.

Unfortunately, the documentation of 3rd party platforms is fine at best, and downright unhelpful at worst.

Here’s a nightmare scenario: you have an upset customer seeing incorrect data on one end, and a helpless engineer looking for the meaning of an error code on the other end.

Dependence on external platforms, especially for customer-facing integrations, introduces risks due to their lack of obligation to support your product.

_Related:_ [_Why support from 3rd-party APIs falls short of your wants and needs_](https://www.merge.dev/blog/support-from-3rd-party-apis)

### **Challenge 3: Long-term horizon**

Ultimately, integration maintenance is so darn tough because it doesn’t end.

Every new customer you onboard becomes a new test-case for how well you’ve built your integration up until now. Every new customer you onboard also becomes a risk for the on call engineer.

Your engineer organization has to be dedicated to maintaining integrations for the long haul.

_Related:_ [_How performing integration maintenance on an ongoing basis can hurt your business_](https://www.merge.dev/blog/integration-maintenance-long-term-costs)

## **What to look for in a integration maintenance provider**

Even if you leverage an embedded iPaaS solution, such as Workato or Tray.io, integration maintenance will still fall on your in-house development team.

Newer tools, such as **Unified APIs**, take on the full spectrum of maintenance for your engineers. Here’s what to look for when scoping a solution.

### **Experienced in-house integration team**

Specialist and generalist skills are required to truly maintain integrations. Specialists are needed for the subject-matter expertise they bring for understanding how a given system works. For example, debugging an ERP system requires a deep understanding of accounting and related concepts.

Generalists are critical because much of the underlying logic for managing integrations at scale can be applied to any type of integration, whether it’s in accounting, file storage, or CRM. Having experts in integrations as a field of development leads to faster response times and more robust integrations.

The right integration team can rapidly scale and maintain integrations for you.

[_Merge’s Partner Engineering_](https://www.linkedin.com/pulse/partner-engineering-team-behind-merges-api-ecosystem-tara-pichumani%3FtrackingId=6Eo4pMoMTQC6ISMn3664Rw%253D%253D/?trackingId=6Eo4pMoMTQC6ISMn3664Rw%3D%3D) _team possesses a blend of business operations and engineering skills. This makes them well suited to not just solve, but proactively build the operations layer that keep Merge customer integrations healthy._

### **Battle-tested with real customers**

Remember how integrations aren’t a typical engineering problem? This is where “economies of scale” for integrations truly matter.

Only integration partners who have already seen millions of response bodies can accurately safe-guard against unexpected API responses and potentially breaking bugs.

In a saturated Unified API market, having a proven track record of  battle-tested integrations serves as a meaningful moat.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a932e921340fc3583e0_mrBrYTlbJfP9VEZ7nPX7MRLyaCa5JwnDrtlHMjLkD2YFrYGyvYj3hV1jmhyDbSYnxK-ZBR4GJM3dpD7v9CB4Os3gn3PJthgo4oAcZp82c7_XWFZlwCPITQ9wSLHBEZqRwRPOM4PHVf7zQPiOqE3fxEA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653b1a932e921340fc3583e0_mrBrYTlbJfP9VEZ7nPX7MRLyaCa5JwnDrtlHMjLkD2YFrYGyvYj3hV1jmhyDbSYnxK-ZBR4GJM3dpD7v9CB4Os3gn3PJthgo4oAcZp82c7_XWFZlwCPITQ9wSLHBEZqRwRPOM4PHVf7zQPiOqE3fxEA.webp)

_Merge is used by over 10,000 organizations, including enterprise clients like Korn Ferry and Navan. Merge's integrations have handled over 80M API responses_

### **Customer success and communication**

Even with a third-party integration provider, bugs inevitably occur. Integrations are inherently reactive.

It's desirable to have a partner with a proven history of proactive communication, collaboration, and ultimately, customer satisfaction.

Leveraging platforms such as G2 or even your own networks is a great way to validate whether an integration provider is a right fit for your team.

_Related:_ [_How to monitor integrations_](https://www.merge.dev/blog/integration-monitoring)

## **Let Merge maintain your integrations for you**

Merge, the leading [unified API solution](https://www.merge.dev/blog/what-is-a-unified-api), addresses all the maintenance capabilities outlined above (and much more) to keep your clients’ data safe and keep your engineers doing what they do best: building.

The platform also provides a [variety of unified APIs](https://www.merge.dev/categories) for key software categories, from CRM to File Storage to HRIS, to ensure you can build all the integrations your customers want and need, quickly.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/campaigns/pain-free-integrations) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1efeb0d9-8a14-40af-bd39-d6f6fc255bcc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b915cc92-a261-4b87-aeac-20aba1bf91b6&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fa-guide-to-application-integration-maintenance&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1efeb0d9-8a14-40af-bd39-d6f6fc255bcc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b915cc92-a261-4b87-aeac-20aba1bf91b6&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fa-guide-to-application-integration-maintenance&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=74ca6ade-2df5-42fa-a803-574008bd3117&bo=2&sid=9e9403f03e8c11f0bfdfe90de1a11c51&vid=9e9457403e8c11f09332179c224f1a9a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20maintaining%20your%20product%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fa-guide-to-application-integration-maintenance&r=&lt=1865&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=136852)