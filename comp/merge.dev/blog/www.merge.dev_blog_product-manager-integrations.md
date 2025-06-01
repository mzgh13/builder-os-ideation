---
url: "https://www.merge.dev/blog/product-manager-integrations"
title: "How product managers can build and maintain integrations successfully"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/product-manager-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/product-manager-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/product-manager-integrations#)

Table of contents

[Adopt a scoring methodology to prioritize your integration requests](https://www.merge.dev/blog/product-manager-integrations#adopt-a-scoring-methodology-to-prioritize-your-integration-requests)

[Work with your engineers to set up automated alerting workflows](https://www.merge.dev/blog/product-manager-integrations#work-with-your-engineers-to-set-up-automated-alerting-workflows)

[Adopt a go-to-market strategy for every integration while building it](https://www.merge.dev/blog/product-manager-integrations#adopt-a-go-to-market-strategy-for-every-integration-while-building-it)

[Leverage a unified API solution](https://www.merge.dev/blog/product-manager-integrations#leverage-a-unified-api-solution)

[Product manager integrations FAQ](https://www.merge.dev/blog/product-manager-integrations#product-manager-integrations-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fproduct-manager-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7387ff8c191004c1e8_6.webp)**How startups can successfully price their customer-facing integrations**](https://www.merge.dev/blog/pricing-customer-facing-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7de0a9323838512e363_Autoprovisioning.webp)**5 integration trends to keep an eye on in 2025**](https://www.merge.dev/blog/integration-trends)

# How product managers can build and maintain integrations successfully

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7000295f40b50711b2_API_key_guide.webp)

No items found.

Product integrations, or integrations that are built between your product and your customers’ applications, are a critical way for SaaS companies to generate more revenue.

Case in point: Through [our State of Product Integrations report](https://www.merge.dev/learning/state-of-product-integrations-2024), which involved surveying hundreds of PMs and engineers, we learned that product integrations help more than half of SaaS companies reduce churn, increase new business sales, and expand to new markets.

[![benefits of offering product integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baa9723febb07fb1425_4vOZbEgReYtB15A_xZVjhkYdxSVclPMn2_gmd1ZZp6gLYWkmONgiYommjK_K0guJZNSSh_d-pY0Acr7xMfQd1j7bb9PGLjvool4POXn0skSZ7sBgVjHHN_9uieIpfhORUWGxXT6V6PO0p2NRzbuF7vs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baa9723febb07fb1425_4vOZbEgReYtB15A_xZVjhkYdxSVclPMn2_gmd1ZZp6gLYWkmONgiYommjK_K0guJZNSSh_d-pY0Acr7xMfQd1j7bb9PGLjvool4POXn0skSZ7sBgVjHHN_9uieIpfhORUWGxXT6V6PO0p2NRzbuF7vs.webp)

To reap these benefits over time, we’ll break down specific tactics to [implement and maintain product integrations](https://www.merge.dev/blog/product-integrations) successfully.

## **Adopt a scoring methodology to prioritize your integration requests**

Your engineers likely can’t handle more than a handful of integration requests at a time, which means that you'll need to pick and choose the integrations that get prioritized.

To prioritize requests strategically and objectively, you can score them against several variables:

- **The number of customers and/or prospects requesting an integration.** In other words, the relative level of demand for an integration.

- **The specific companies that request an integration.** Generally speaking, the larger the accounts that request an integration are, the higher your score should be (as they’ll likely be willing and able to spend more on them).

- **The level of difficulty in building an integration.** You can suss out how long it’ll take your developers to build the integration by reviewing the API provider’s documentation, getting feedback from other developers in online forums, etc.

Note: There may be other factors worth considering as you review and compare integration requests. The guidance on this page is just meant to help you start building your own assessment methodology.

Once you know the answers to these questions for a given integration and can assign specific ranges for each criteria that correspond to certain values (e.g., 0, 1, 2), you can score each integration.

[![Integration request assessments](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6638e4dae6496be06435aa4a_USIOcl8g4dlkCPV6D8c01F8oPwOFs7dTw7J9vsBPUjIgv-DtfOds8DBpq3k-8qN9Z947jqi-yhP3R3VHI0TKYp7_0KbNgIL2zl5DhJ9uEzA5NW3wRCXd7gqexbDn3pIFxtd-L7O60bldf_OP3f715Gk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6638e4dae6496be06435aa4a_USIOcl8g4dlkCPV6D8c01F8oPwOFs7dTw7J9vsBPUjIgv-DtfOds8DBpq3k-8qN9Z947jqi-yhP3R3VHI0TKYp7_0KbNgIL2zl5DhJ9uEzA5NW3wRCXd7gqexbDn3pIFxtd-L7O60bldf_OP3f715Gk.webp)

_Related:_ [_How to choose between building and buying integrations_](https://www.merge.dev/blog/build-vs-buy-integrations)

## **Work with your engineers to set up automated alerting workflows**

Product integrations will, inevitably, break. When they do, your engineers will need to pinpoint the issue quickly so that they can work on resolving it as soon as possible.

To that end, you can connect the monitoring tool your engineers use to collect logs of API requests and responses (e.g., Datadog) with the platforms these teams tend to check often already, such as Slack and Gmail.

Once you’ve built the integration, you can build an automation where once a specific alert is detected via an [API log](https://www.merge.dev/blog/api-logs), key details from that alert get routed to a predefined email alias and/or channel in your messaging tool.

[![Issue routing workflow for integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baaa131ae5f2daf36ba_4KgkosGoJffHvTNYHQi_HQuigSEasWFVgHnE_AAkQ5Mvolv-BSqMAh2uv9OyFHWB8P4zb4Oiv-e1BZxZvIjFMxxZDCw4b1q0FKQHPHhqMZCfM2QpXZlAZThbUU9pdl4b2EtOQiEDc6X-sGksyPXl0V8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baaa131ae5f2daf36ba_4KgkosGoJffHvTNYHQi_HQuigSEasWFVgHnE_AAkQ5Mvolv-BSqMAh2uv9OyFHWB8P4zb4Oiv-e1BZxZvIjFMxxZDCw4b1q0FKQHPHhqMZCfM2QpXZlAZThbUU9pdl4b2EtOQiEDc6X-sGksyPXl0V8.webp)

You can take this a step further by [using a large language model (LLM)-powered agent as part of the workflow automation](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations). More specifically, based on the information provided in the log, the agent can attempt to diagnose the issue and, based on its diagnosis, provide a potential solution. The agent can then include all of this information within the email or chat message, allowing engineering to resolve the issue faster.

_Related:_ [_A guide to building a product integration strategy_](https://www.merge.dev/blog/product-integration-strategy)

## **Adopt a go-to-market strategy for every integration while building it**

To ensure that each of your product integrations generates a meaningful ROI, you’ll need to take a thoughtful approach to raising awareness of them (both with customers and prospects), pricing them, enabling sales to talk about them, etc.

And while it’s impossible to cover each of each of these areas in depth here, here are some high-level guidelines to keep in mind:

- **Pricing:** If an integration is critical in improving the customer experience, it’s likely in your best interest to offer it for “free”. The returns from clients that adopt the integration (in the form of higher retention) will likely make up for the costs of building and maintaining it. Otherwise, you can experiment with other pricing models, such as only including integrations in certain plans.

[![Under.io's pricing plans](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baa3727eb21807b4f8d_LPDx0vhhzh6c6WOK-61jXebJMWGyCPecmI6I3DWUZD2Ah4ExNwEpokKfctOrRwOpSXPv3Ty7AgeSpBo4gyfvMAdjPfC3VygIlTZx3WKm1kG2c9bKwWJ_QugRkGJsP1gu6_GvDFU7aRQidJIXSyaNaoM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66341baa3727eb21807b4f8d_LPDx0vhhzh6c6WOK-61jXebJMWGyCPecmI6I3DWUZD2Ah4ExNwEpokKfctOrRwOpSXPv3Ty7AgeSpBo4gyfvMAdjPfC3VygIlTZx3WKm1kG2c9bKwWJ_QugRkGJsP1gu6_GvDFU7aRQidJIXSyaNaoM.webp)

_Under.io, a digital onboarding platform for financial services companies, only offers integrations on their “Custom plan”_

- **Marketing:** It’s worth announcing key integration launches on your social channels, highlighting integrations on your site through an [integration marketplace](https://www.merge.dev/blog/integration-marketplace), emailing clients and prospects about the integrations, and even including them in case studies when possible.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e589d3cd85d73a04289489_Screenshot%202025-03-27%20at%201.24.19%E2%80%AFPM.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e589d3cd85d73a04289489_Screenshot%202025-03-27%20at%201.24.19%E2%80%AFPM.png)

_ExpenseOnDemand, a leading expense management platform, highlights integration announcements across their site with a banner_

- **Sales enablement:** It’s not only critical to help reps understand which integrations are available and which are on the roadmap. You’ll also want them to understand the various use cases they enable, as that can help prospects better understand their value and whether they’re a fit for their business.

In addition, if you can provide demo accounts that show certain integrations in action and train the reps on using them, prospects can better visualize how certain integrations work and get excited about adopting them.

_Related:_ [_How to evaluate product management tools_](https://www.merge.dev/blog/product-management-tools)

## **Leverage a unified API solution**

Your product and engineering teams don’t have to manage integrations on their own. In fact, they shouldn’t, as integration development and maintenance likely isn’t one of your engineering team’s core competencies. It also distracts them from working on your product, which can have a significant long-term impact on your business.

While you have a few [options for outsourcing integrations](https://www.merge.dev/blog/outsourcing-integration), your best option is a [universal API solution](https://www.merge.dev/blog/universal-api)(otherwise known as a unified API solution).

Using this type of solution, you can build to a single, aggregated API and then access hundreds of customer-facing integrations. This makes the process of scaling integrations significantly easier and faster.

[![A visual of a unified API solution](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c3c8875180f5277de43e80_TReTB_C5UF49Vqfon9-jMh6TlTxeYjpzS4_sJOgcRI6DxILgEXQKGKRPTT5PdZSE_71Hn7q_UZXI8Muj4KdaTX9A3VnLzezIyjzQrEnH_JICaOs72hltj4HFQL_UfPSgeJO9zOZeMLNcjUPnSJsaWso.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64c3c8875180f5277de43e80_TReTB_C5UF49Vqfon9-jMh6TlTxeYjpzS4_sJOgcRI6DxILgEXQKGKRPTT5PdZSE_71Hn7q_UZXI8Muj4KdaTX9A3VnLzezIyjzQrEnH_JICaOs72hltj4HFQL_UfPSgeJO9zOZeMLNcjUPnSJsaWso.webp)

In addition, with Merge, the leading universal API platform, you can access [Integration Observability tooling](https://www.merge.dev/features/integration-observability) to easily detect, diagnose, and resolve issues. And you’ll receive integration maintenance support on your engineers’ behalf.

#### Ready to scale your product integrations?

Learn how Merge can help you build reliable, secure, and performant integrations at scale by scheduling a demo with us.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fproduct-manager-integrations)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Product manager integrations FAQ**

In case you have any more questions, we’ve addressed several more common ones below.

### **What does a product manager (PM) for integrations do?**

Among other tasks, a product manager for integrations usually decides which integrations get prioritized, scope out the requirements for building each, and ensure that go-to-market teams are enabled to sell, support, and market each integration successfully.

### **What are some common interview questions for a PM for integrations role?**

Here are a few to keep in mind and prepare for:

- What does your process of prioritizing product integrations look like?
- How do you measure the success of a product integration?
- How do you forecast the potential benefits of a product integration?
- Do you have experience working with 3rd-party integration tools, like a unified API or an embedded iPaaS solution?
- How do you decide which engineers should work on specific facets of an integration project?

### **How do you decide between building integrations in-house and outsourcing them to a 3rd-party?**

‍

The decision depends on several factors, and you’ll need to review each carefully.

- **How important is the integration to your business?** If it’s core to using your product, it may not be worth outsourcing. The 3rd-party may not resolve issues as quickly as you’d like and/or enhance the integration as much as you and your customers/prospects want over time

- **Do you have engineering capacity to not only build but also maintain the integration throughout its lifespan?** Product integrations typically require hundreds of engineering hours every year, which may not be feasible for your business and/or desirable, as it prevents your engineers from building out and improving your core product

- **How customized does the integration need to be?** If it has to be highly customized, it may be difficult to outsource. That said, 3rd-party integration solutions—like Merge—now offer features to help you customize each integration

Here’s a decision tree that can help you decide whether to outsource a given product integration:

[![Decision tree for prioritizing product integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e1bc6b0705618c9793e225_AD_4nXeK_SsxovFPUJ8yClGdq26mLWvtRDbUSofCn8-uG8vQ4oq7PwiByVaVkBJHzkM400NA3Pj4UFQIyOWXXj7aKi2XbgHg0NULh_5hxosxUsUBIKCU4SuX9TOwpZQiWcSZS2J-pdBi1oMz_If7GBVtyKrLF-62.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e1bc6b0705618c9793e225_AD_4nXeK_SsxovFPUJ8yClGdq26mLWvtRDbUSofCn8-uG8vQ4oq7PwiByVaVkBJHzkM400NA3Pj4UFQIyOWXXj7aKi2XbgHg0NULh_5hxosxUsUBIKCU4SuX9TOwpZQiWcSZS2J-pdBi1oMz_If7GBVtyKrLF-62.webp)

### **How does adding product integrations differ from building other product features?**

Unlike other product features, product integrations require working with a 3rd-party provider’s API. This introduces risk, as your team can’t fully control the 3rd-party API provider’s performance and improvements over time.

Moreover, the timeline of building a product integration largely depends on the 3rd-party API provider. For instance, they may require you to enter into a formal partnership agreement to access their sandbox environment and documentation, which can take months.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

No items found.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=54e4782c-67d0-4f8f-b629-071cbd8ffdaf&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=38766c30-17fa-43c3-b07c-7d1af168d4ff&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-manager-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=54e4782c-67d0-4f8f-b629-071cbd8ffdaf&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=38766c30-17fa-43c3-b07c-7d1af168d4ff&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-manager-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=eaee5532-fc22-460d-9f3d-3c1d66a8392a&bo=2&sid=0831d6d03e8d11f081eef1cb06801b33&vid=08332f703e8d11f0a4051f36adf6bd87&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20product%20managers%20can%20build%20and%20maintain%20integrations%20successfully&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-manager-integrations&r=&lt=566&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=243851)