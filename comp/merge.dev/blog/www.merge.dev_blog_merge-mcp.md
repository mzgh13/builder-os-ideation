---
url: "https://www.merge.dev/blog/merge-mcp"
title: "We’ve launched Merge MCP to help AI companies leverage our integrations in minutes! Here’s how to use it"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/merge-mcp#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/merge-mcp#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/merge-mcp#)

Table of contents

[Overview on Merge MCP](https://www.merge.dev/blog/merge-mcp#overview-on-merge-mcp)

[Example of using Merge MCP](https://www.merge.dev/blog/merge-mcp#example-of-using-merge-mcp)

[How to access Merge MCP](https://www.merge.dev/blog/merge-mcp#how-to-access-merge-mcp)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-mcp)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)**Building AI chatbots with RAG: a step-by-step guide**](https://www.merge.dev/blog/how-to-build-ai-chatbot)

# We’ve launched Merge MCP to help AI companies leverage our integrations in minutes! Here’s how to use it

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

The Model Context Protocol (MCP) is quickly becoming the go-to standard for facilitating communication between LLMs and outside data sources.

The reasons behind its early success aren’t hard to discern: It’s easy to use, its open-source model has helped make it widely available, and it’s been adopted by leading AI companies (e.g., OpenAI)—prompting the broader AI market to trust it.

We’re committed to helping AI companies build the most reliable and powerful integrations at scale, so we’ve released Merge MCP to help any company use [the Model Context Protocol](https://www.merge.dev/blog/model-context-protocol) across our integrations and endpoints!

Here’s more on [how Merge MCP works](https://www.merge.dev/features/mcp), how you can use it, and what you can do to access it.

#### Want to learn more about Merge MCP?

Learn more about Merge MCP and how it can power your AI product by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-mcp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Overview on Merge MCP**

We’ve built an MCP server that allows any LLM to access our integrations’ endpoints as tools.

[![Visualization of Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5afb99635c2721497090f_AD_4nXfBnFs_tyw_RNwP8jF477uqRe0rYlmrVLYdL7EPyhcL9CefG5g5MRr6qyAvwvP1zKI2AybBFbeGZ4HJtqOpS9CfYryfP03aQSuy_ZRQmv7LHz0MRi6LYK_c8scFxKAE2B4714zjkw.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5afb99635c2721497090f_AD_4nXfBnFs_tyw_RNwP8jF477uqRe0rYlmrVLYdL7EPyhcL9CefG5g5MRr6qyAvwvP1zKI2AybBFbeGZ4HJtqOpS9CfYryfP03aQSuy_ZRQmv7LHz0MRi6LYK_c8scFxKAE2B4714zjkw.png)

Our integrations will also operate the same through MCP.

Once your user authenticates a connection with Merge MCP, we'll handle the integration’s rate limits, pagination, day-to-day maintenance, and more; we’ll also continue to provide the enterprise-grade security features you need, such as access control levels (ACLs) and [Common Model Scopes](https://help.merge.dev/en/articles/5950052-what-are-common-model-scopes); and your customer-facing teams can still use [our Integration Observability features](https://www.merge.dev/features/integration-observability) to manage the integrations.

We’ve even made Merge MCP’s tools highly detailed to help you review the available tools and enable your LLM to choose the appropriate tools consistently and in real-time.

[![How Merge MCP tools look for users](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5afbac73999cf4df84cd9_AD_4nXfyHKKrIycqfhI10IhAh97YC43zEs9EkYuqcseD7_ikDkj5N_8FVkDyNiK4hyeen2wfdzdpzdwQoE-imxPUn9XSCov5I_qOKhrEu2306SZzF8QkSzkWTX0JthfsggfLW_yhLDaQAA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5afbac73999cf4df84cd9_AD_4nXfyHKKrIycqfhI10IhAh97YC43zEs9EkYuqcseD7_ikDkj5N_8FVkDyNiK4hyeen2wfdzdpzdwQoE-imxPUn9XSCov5I_qOKhrEu2306SZzF8QkSzkWTX0JthfsggfLW_yhLDaQAA.png)

_A snapshot of how some of Merge MCP’s tools appear within Claude_

Best of all, the process of adopting Merge MCP is incredibly simple. You’ll just need to write a few lines of code (you can find them near the end of this article) to add Merge MCP as a set of tools for your LLM. From there, your LLM can read and write data across our 220+ integrations!

[Related](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

#### [MCP vs API: how to understand their relationship](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

[![MCP vs API: how to understand their relationship](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67eaee364b71b526302499ce_Blog%20Header%20Brand%20Refresh%20(8).png)](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

## **Example of using Merge MCP**

Since Merge MCP lets an LLM perform a certain task on integrated customer data based on an end user’s prompt, the use cases for Merge MCP are endless.

To make it more tangible, let’s walk through how Merge MCP can support a specific ticketing use case:

1\. One of your users enters a prompt that details a specific ticket they want to create.

2\. The LLM decides on the tool to use. In this case, it would pick the create\_ticket tool to add the ticket in the customer's integrated project management system.

3\. The LLM can then confirm that the ticket has been created and even share a link to it in case the user wants to review it.

[![How Merge MCP can help you create tickets](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b148366685820bf0ff50_Frame%202087327513.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b148366685820bf0ff50_Frame%202087327513.png)

_Related:_ [_Best practices for using the Model Context Protocol_](https://www.merge.dev/blog/mcp-best-practices)

## **How to access Merge MCP**

Merge MCP is now available to all of our customers. We’ve also made all of our Common Model endpoints available as tools in Merge MCP so that it can support any of your product’s AI use cases!

To get started with Merge MCP, you’ll just need to write a few lines of code:

```python
{
  "mcpServers": {
    "merge-mcp": {
      "command": "uvx",
      "args": ["merge-mcp"],
      "env": {
        "MERGE_API_KEY": "xxxxxxx",
        "MERGE_ACCOUNT_TOKEN": "xxxxxxx"
      }
    }
  }
}

```

To learn more about Merge MCP, you can visit [our Docs page](https://docs.merge.dev/basics/mcp/). We also encourage you to either [schedule a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-mcp) or (if you already use Merge) reach out to your dedicated customer success manager.

We can’t wait to see all of the innovative ways that our customers use Merge MCP!

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