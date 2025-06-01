---
url: "https://www.merge.dev/blog/mcp-best-practices"
title: "3 insider tips for using the Model Context Protocol effectively"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/mcp-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/mcp-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/mcp-best-practices#)

Table of contents

[Review the MCP servers’ security controls](https://www.merge.dev/blog/mcp-best-practices#review-the-mcp-servers-security-controls)

[Learn how the MCP servers manage integrations](https://www.merge.dev/blog/mcp-best-practices#learn-how-the-mcp-servers-manage-integrations)

[Assess the MCP servers’ tools carefully](https://www.merge.dev/blog/mcp-best-practices#assess-the-mcp-servers-tools-carefully)

[Start using Merge MCP in a matter of minutes](https://www.merge.dev/blog/mcp-best-practices#start-using-merge-mcp-in-a-matter-of-minutes)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmcp-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**MCP vs RAG: how they overlap and differ**](https://www.merge.dev/blog/rag-vs-mcp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**Why MCP token management falls short of your security needs**](https://www.merge.dev/blog/mcp-token-management)

# 3 insider tips for using the Model Context Protocol effectively

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

The Model Context Protocol (MCP) offers an extremely powerful way to connect LLMs with outside data sources.

But using it effectively involves carefully reviewing MCP servers and picking the one that best meets your [integration requirements](https://www.merge.dev/blog/integration-requirements).

To help you navigate this, I’ve broken down some best practices you can apply—based on our experience testing MCP servers and [building one ourselves](https://www.merge.dev/features/mcp).

#### Ready to connect your LLM to hundreds of applications?

Learn how Merge MCP can support all your customer-facing integrations by connecting with our team.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmcp-best-practices)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Review the MCP servers’ security controls**

The LLM you use can easily confuse data types with one another, leading it to inadvertently share sensitive information to users.

For example, say you want to use a tool that can create employees in your HR software.

If your HR software labels the first name field “FN” and the last name field “SN” (short for surname), the LLM can accidentally mistake SN for social security number, leading it to write the employee’s social security number there. Any employee with access to the HR platform can then see the SSN.

To prevent security incidents like these from happening, adopt an MCP server that takes a few measures:

- **Access control levels (ACLs):** This only allows users to perform actions that fall within their level of permissions in the integrated application. In our example, if the employee wants to create a user, they wouldn’t be able to unless they’re an admin of the HR software

- **Schema enforcement:** A tool can define the parameters for specific fields, and any inputs that don't meet these parameters couldn’t get POSTed into an application

Going back to our example, the tool can use the following input schema to ensure “sn” doesn’t include numbers:

```python
‍{
  "name": "process_user_info",
  "description": "Processes user information including first name (fn) and surname (sn).",
  "inputSchema": {
    "type": "object",
    "properties": {
      "fn": {
        "type": "string",
        "description": "First name of the user"
      },
      "sn": {
        "type": "string",
        "description": "Surname of the user",
        "pattern": "^[a-zA-Z-]+$"
      }
    },
    "required": ["fn", "sn"]
  }
}

```

[Related](https://www.merge.dev/blog/model-context-protocol-security?blog-related=image)

#### [The hidden security threats of MCP—and how to mitigate them](https://www.merge.dev/blog/model-context-protocol-security?blog-related=image)

[![The hidden security threats of MCP—and how to mitigate them](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)](https://www.merge.dev/blog/model-context-protocol-security?blog-related=image)

## **Learn how the MCP servers manage integrations**

If you use MCP to [support product integrations](https://www.merge.dev/blog/product-integrations), you’ll probably still be responsible for:

- Handling API providers’ unique requirements, which includes incorporating rate limiting strategies like exponential backoff, retries, and pagination

- Dealing with the complexities of syncing data, whether that’s managing computational resources at scale efficiently or ensuring data consistency across distributed systems

- Implementing and updating authentication flows (OAuth 2.0, API keys, etc.) and onboarding instructions

- Handling errors gracefully and ensuring end users get instructions on fixing issues related to permissions and authentication

- Defining and maintaining normalized data models across categories (e.g., CRM, file storage, ticketing) to ensure your LLM generates reliable, non-sensitive, and accurate outputs

All of this work is extremely time intensive for your engineers, and if you’re looking to implement several integrations, this workload only grows exponentially.

To address this, look for MCP servers that offer ongoing support for their integrations.

Merge, for instance, offers [Merge MCP](https://www.merge.dev/features/mcp), a server that not only facilitates access to customers’ applications but also fully maintains and enhances these integrations over time—from data normalization to auth handling—so your engineers don’t have to.

[![A visualization of how Merge normalizes data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f7f6b361fe7f4a5503841f_AD_4nXcq4clDNURHPaJC5mgHsvC5VoF4xP7gXU8sKyXsLFdiu2WoJge7UtHxnrRI_liQTUK_yAHI1NI1n6zUPiE3Z2wYzF1cwMz7M6VvlKJlbkh6DnhVVGUyjDF31dgcmOL3x4MIif2S.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f7f6b361fe7f4a5503841f_AD_4nXcq4clDNURHPaJC5mgHsvC5VoF4xP7gXU8sKyXsLFdiu2WoJge7UtHxnrRI_liQTUK_yAHI1NI1n6zUPiE3Z2wYzF1cwMz7M6VvlKJlbkh6DnhVVGUyjDF31dgcmOL3x4MIif2S.png)

_Merge transforms all of your customer data (e.g., vendor bills) into normalized data models before syncing it with your product_

_Related:_ [_How MCP compares with APIs_](https://www.merge.dev/blog/api-vs-mcp)

## **Assess the MCP servers’ tools carefully**

Your LLM can easily perform the wrong action if the MCP server’s tools aren’t descriptive, comprehensive, and unique from one another.

To help you assess the quality of an MCP server’s tools, look for:

- **Detailed names and descriptions:** Each tool should have a unique name that explains its function clearly and a description that highlights what the tool does, what its purpose is, and the specific action(s) it takes. The same goes for the tool’s parameters


- **Explicit parameter requirements**: The tools should use JSON Schema to define each parameter, including specifying the data types, required fields, and constraints to ensure inputs are validated and correctly formatted


- **Clear examples:** While this isn’t necessary, providing sample inputs and expected outputs can help clarify how a tool works


- **Robust error handling and validation:** Check to see if the schemauses strict validation to ensure all inputs conform to the defined schema. This prevents errors and enhances reliability

[![A look at some of the tools available via Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f7f6b3c6c47675c88ada00_AD_4nXc2bJ9uAokSOZeIKnxowhcxVLIEJjbnkSs9Vlq4xoQnHurVrannUcJ1VgFkc_nhPDKJ6wzmeuJTIa9H5MKln-DFR7iF_4wp7rHEEfHx3mmeEBg6vceFyMsmsDXgPEVHxXE5gZGY_w.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f7f6b3c6c47675c88ada00_AD_4nXc2bJ9uAokSOZeIKnxowhcxVLIEJjbnkSs9Vlq4xoQnHurVrannUcJ1VgFkc_nhPDKJ6wzmeuJTIa9H5MKln-DFR7iF_4wp7rHEEfHx3mmeEBg6vceFyMsmsDXgPEVHxXE5gZGY_w.png)

_In addition to providing schema that addresses the requirements above, Merge MCP transformed its schema into readable tools for end users, allowing them to easily understand the tools available_

_Related:_ [_How to build an MCP server quickly_](https://www.merge.dev/blog/how-to-build-mcp-server)

## **Start using Merge MCP in a matter of minutes**

Merge MCP is now available to every user across our plans!

Through Merge MCP, you’ll have access to all of our integrations and endpoints, [Integration Observability tooling](https://www.merge.dev/features/integration-observability), advanced syncing features (e.g., [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/)), and more to help your LLM access customer data securely, quickly, and reliably.

Best of all, Merge MCP is incredibly easy to adopt.

Simply copy this code to your MCP client configuration to start using it today.

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

#### Ready to connect your LLM to hundreds of applications?

Learn how Merge MCP can support all your customer-facing integrations by connecting with our team.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmcp-best-practices)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6dcf8d64-1cc3-4445-81d8-21530bb1da97&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=53cf4f32-f11e-4e70-a350-d12159724837&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmcp-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6dcf8d64-1cc3-4445-81d8-21530bb1da97&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=53cf4f32-f11e-4e70-a350-d12159724837&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmcp-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=43cf2fce-2db7-47a5-befd-18cddafe45b6&bo=2&sid=4d8a16403e8c11f0981f4397fe3fb678&vid=4d8a4f003e8c11f0b730011d7abef8dd&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=3%20insider%20tips%20for%20using%20the%20Model%20Context%20Protocol%20effectively&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmcp-best-practices&r=&lt=789&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=342211)