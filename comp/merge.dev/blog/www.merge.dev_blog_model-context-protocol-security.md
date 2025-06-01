---
url: "https://www.merge.dev/blog/model-context-protocol-security"
title: "The hidden security threats of MCP—and how to mitigate them"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/model-context-protocol-security#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/model-context-protocol-security#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/model-context-protocol-security#)

Table of contents

[Prompt injection threats](https://www.merge.dev/blog/model-context-protocol-security#prompt-injection-threats)

[Comprehensive API scopes](https://www.merge.dev/blog/model-context-protocol-security#comprehensive-api-scopes)

[A single point of failure](https://www.merge.dev/blog/model-context-protocol-security#a-single-point-of-failure)

[Poorly-documented tools](https://www.merge.dev/blog/model-context-protocol-security#poorly-documented-tools)

[How to address these security threats](https://www.merge.dev/blog/model-context-protocol-security#how-to-address-these-security-threats)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmodel-context-protocol-security)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**MCP vs RAG: how they overlap and differ**](https://www.merge.dev/blog/rag-vs-mcp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**Why MCP token management falls short of your security needs**](https://www.merge.dev/blog/mcp-token-management)

# The hidden security threats of MCP—and how to mitigate them

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

The Model Context Protocol (MCP) offers an incredibly powerful way to integrate your LLM with outside data sources, but you’ll need to take certain security measures when using it.

Otherwise, you risk leaking sensitive information on your business, your customers’ businesses, and—if you’re implementing customer-facing integrations—your end users.

Here are some of the biggest security threats to consider and how you can address them.

#### Ready to add enterprise-grade integrations to your AI product?

Learn how Merge MCP can help you add hundreds of integrations in minutes by scheduling a demo with one of our integration experts.

[Schedule demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmodel-context-protocol-security)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Prompt injection threats**

If your customers use API keys to authenticate with your MCP server, they’re trusting you—the MCP provider—to keep these credentials safely stored and away from malicious actors.

Unfortunately, you can easily break their trust.

[Researchers at Cornell found](https://arxiv.org/abs/2504.03767?utm_source=chatgpt.com) that Malicious actors can find ways to use inputs—such as a document with instructions—that coerce you LLM to provide authentication credentials.

This isn't a hypothetical scenario. We're now seeing catastrophic incidents come up. Case in point: [attackers recently exploited a prompt injection vulnerability on GitHub’s MCP server to access private repository data](https://invariantlabs.ai/blog/mcp-github-vulnerability).

[Related](https://www.merge.dev/blog/how-to-build-mcp-server?blog-related=image)

#### [3 steps to build an MCP server from scratch](https://www.merge.dev/blog/how-to-build-mcp-server?blog-related=image)

[![3 steps to build an MCP server from scratch](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffc161529060fb1994a3c2_MCP%20server%20guide.png)](https://www.merge.dev/blog/how-to-build-mcp-server?blog-related=image)

## **Comprehensive API scopes**

Since [MCP](https://www.merge.dev/blog/model-context-protocol) is so flexible, you’ll likely want to expose as many tools (which correspond to API endpoints) as possible.

This’ll lead you to support keys that access a wide range of sensitive data across applications, whether that's social security numbers, business financials, customers’ payment information, and so on.

This will only up the stakes of a key interception.

## **A single point of failure**

MCP servers might store API keys in a single place. This gives an attacker a single target to access API keys that—as our previous section touched on—support multiple services.

For instance, if you’re using MCP to support internal integrations, you now have a single service that exposes data and functionality for multiple services, like a CRM (e.g., Salesforce), a marketing automation platform (e.g., HubSpot), and a ticketing solution (e.g., Zendesk). This means that if the agent or server is successfully attacked, data from all of the applications can be exposed.

[![Why MCP server is a single point of failure](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6809334f61567108255be13b_AD_4nXdCAk2C1D17MF9uB4gsyrfgw21BamTWS0PD1iK40wnbAjbN76FW-E6Wv4Nx6D98H0e8Q8zu_dCqBF5jJ4Cfayt0FQIWCTvYVHIzURXGHkUDp7bsIzwLZBilvGhoTYrQlMbOiy346w.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6809334f61567108255be13b_AD_4nXdCAk2C1D17MF9uB4gsyrfgw21BamTWS0PD1iK40wnbAjbN76FW-E6Wv4Nx6D98H0e8Q8zu_dCqBF5jJ4Cfayt0FQIWCTvYVHIzURXGHkUDp7bsIzwLZBilvGhoTYrQlMbOiy346w.png)

Scenarios like these would be extremely difficult to address, and even if they are, they’d cause long-term damage to your company’s reputation both internally and externally.

[Related](https://www.merge.dev/blog/mcp-best-practices?blog-related=image)

#### [3 insider tips for using the Model Context Protocol effectively](https://www.merge.dev/blog/mcp-best-practices?blog-related=image)

[![3 insider tips for using the Model Context Protocol effectively](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)](https://www.merge.dev/blog/mcp-best-practices?blog-related=image)

## **Poorly-documented tools**

If your MCP server’s tools aren’t descriptive or use names that don’t accurately describe their functions, your LLM can easily choose the wrong tool from a given input and potentially invoke a tool that reveals sensitive information.

For instance, if a user wants to get an update on a ticket related to onboarding a specific customer from their project management system, the LLM can mistakenly share another ticket that includes information on a new hire—such as sensitive details from the new hire’s collected documents.

[![A screenshot of some of the available tools for Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb1243c607e032ffe629_AD_4nXcwRbYvGUSypciK5-5jhhKn9nO2BKyAP2f7-ST3n6fcBF_vBqumYIR8ji2_P9n5U_pySV2zbcbIm04ms33Z4z2nx7qh8i-IpL7bAAC1rry-eM6x5aXZMM63AVqfKz6UhI5xi7iwuA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb1243c607e032ffe629_AD_4nXcwRbYvGUSypciK5-5jhhKn9nO2BKyAP2f7-ST3n6fcBF_vBqumYIR8ji2_P9n5U_pySV2zbcbIm04ms33Z4z2nx7qh8i-IpL7bAAC1rry-eM6x5aXZMM63AVqfKz6UhI5xi7iwuA.png)

_Merge MCP, our newly-released MCP server, provides detailed names and descriptions for each tool to prevent LLMs from using the wrong ones by mistake_

[Related](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

#### [MCP vs API: how to understand their relationship](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

[![MCP vs API: how to understand their relationship](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67eaee364b71b526302499ce_Blog%20Header%20Brand%20Refresh%20(8).png)](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

## **How to address these security threats**

When you put all of this together, the security threats associated with MCP only grow in severity and likelihood.

For example, if an MCP server stores a few comprehensive API keys in a single place, a significant amount of sensitive information is more vulnerable to exposure. And if you consider the different attack vectors—from prompt injections to indirect access via unsecure connections—your chances of getting breached will be higher.

Fortunately, you can use [Merge MCP](https://www.merge.dev/features/mcp) to avoid these security issues altogether.

Our MCP server lets your LLM access 220+ CRM, HRIS, ATS, ERP, file storage, and ticketing integrations across your customer base.

[![A screenshot of Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6809334f0de541aab49f7856_AD_4nXfonYqQ7-bAjIEBQIonV9_d16pv1H1UmR-BUT3wUKBYEevP6xJLlGaBO1ucPy7FwldBFK9cYD-Swz73Q1dqOW__muylKsTaPrrdJmAGrCmcvc-5SfGii8ZXH0OEhBVlvalO-nfS6g.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6809334f0de541aab49f7856_AD_4nXfonYqQ7-bAjIEBQIonV9_d16pv1H1UmR-BUT3wUKBYEevP6xJLlGaBO1ucPy7FwldBFK9cYD-Swz73Q1dqOW__muylKsTaPrrdJmAGrCmcvc-5SfGii8ZXH0OEhBVlvalO-nfS6g.png)

Merge MCP also offers enterprise-grade secure integrations by providing advanced authentication support (e.g., OAuth 2.0), fully-searchable and comprehensive logs, encryption in transit and at rest, granular data access controls, and more.

#### Ready to add enterprise-grade integrations to your AI product?

Learn how Merge MCP can help you add hundreds of integrations in minutes by scheduling a demo with one of our integration experts.

[Schedule demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmodel-context-protocol-security)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)

Gil Feig

CTO and co-founder

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5f16c70-8297-4411-b4ad-016b87bf52e5&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=08580f15-6f8b-4d73-9588-6f18e1cd0bfa&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol-security&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5f16c70-8297-4411-b4ad-016b87bf52e5&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=08580f15-6f8b-4d73-9588-6f18e1cd0bfa&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol-security&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=38640743-ac0d-42eb-b274-19173b2aa0f2&bo=2&sid=213b1e603e8d11f0b323f960d3738be2&vid=213bd5903e8d11f0abb71bd176121798&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=The%20hidden%20security%20threats%20of%20MCP%E2%80%94and%20how%20to%20mitigate%20them&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol-security&r=&lt=590&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=275652)