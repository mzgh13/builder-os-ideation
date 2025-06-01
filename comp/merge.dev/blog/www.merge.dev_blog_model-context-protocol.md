---
url: "https://www.merge.dev/blog/model-context-protocol"
title: "What you need to know about the Model Context Protocol (MCP)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/model-context-protocol#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/model-context-protocol#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/model-context-protocol#)

Table of contents

[What is the Model Context Protocol?](https://www.merge.dev/blog/model-context-protocol#what-is-the-model-context-protocol)

[Examples of using MCP](https://www.merge.dev/blog/model-context-protocol#examples-of-using-mcp)

[Benefits of using MCP](https://www.merge.dev/blog/model-context-protocol#benefits-of-using-mcp)

[What MCP doesn’t address at the moment](https://www.merge.dev/blog/model-context-protocol#what-mcp-doesnt-address-at-the-moment)

[How unified APIs relate to MCP](https://www.merge.dev/blog/model-context-protocol#how-unified-apis-relate-to-mcp)

[Enable your LLM to access all of your customers' data via Merge MCP](https://www.merge.dev/blog/model-context-protocol#enable-your-llm-to-access-all-of-your-customers-data-via-merge-mcp)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmodel-context-protocol)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**10 AI product ideas worth building in 2025**](https://www.merge.dev/blog/ai-product-ideas)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**3 RAG use cases—plus tips for implementing them**](https://www.merge.dev/blog/rag-use-cases)

# What you need to know about the Model Context Protocol (MCP)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8579e8b825ec843ba604a_Blog%20Header%20Brand%20Refresh%20(4).png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Anthropic's recently-released Model Context Protocol (MCP) reaffirms that large language models (LLMs) need customer data to provide reliable, personalized, and useful outputs.

The protocol will likely play an invaluable role in helping AI models and 3rd-party applications integrate with one another. There are just a few things to consider when building and maintaining connections with this protocol.

You can read on to learn how MCP works, the benefits it provides, and how unified API solutions can complement it.

What you need to know about the Model Context Protocol (MCP) - YouTube

Merge

202 subscribers

[What you need to know about the Model Context Protocol (MCP)](https://www.youtube.com/watch?v=NdYgmWJsCuY)

Merge

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

[Watch on YouTube](https://www.youtube.com/watch?v=NdYgmWJsCuY "Watch on YouTube")

## **What is the Model Context Protocol?**

MCP is an open standard protocol released by Anthropic. It allows AI models to connect directly with external data sources so that the models can read data from and write data to the connected applications.

More specifically, MCP includes:

- **An MCP client:** a component that’s integrated within LLMs and facilitates interactions with external data sources

- **An MCP server:** a lightweight program that exposes data and functionality from external systems. These systems can come from local data sources, like files and databases, or remote services, such as APIs from applications like Salesforce and Box

- **Tools:** allow LLMs to access specific data and execute functionality exposed by the [MCP server](https://www.merge.dev/blog/how-to-build-mcp-server) in response to user prompts

[![How MCP works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67edbfbdb0b6658e4ce302e9_MCP%20in-line%20blog%20graphic%20(1).png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67edbfbdb0b6658e4ce302e9_MCP%20in-line%20blog%20graphic%20(1).png)

_Related:_ [_How MCP compares to APIs_](https://www.merge.dev/blog/api-vs-mcp)

## **Examples of using MCP**

Here are just a few ways to leverage MCP.

### **Power a customer-facing support chatbot**

Say you offer a [customer-facing AI chatbot](https://www.merge.dev/blog/how-to-build-ai-chatbot) that can use several LLMs (e.g., GPT-4o, Claude 3.5, etc.), depending on the support task it’s performing.

To help all of the AI chatbot’s underlying LLMs get the context needed to understand tasks and perform them, you can integrate the LLMs with the relevant support applications via the MCP protocol and give the LLMs access to read and write capabilities across these connected systems.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e2ccc609757ac42d330ee7_AD_4nXcBfuSNL13ubSxMs19lZ0wRI7Hg654jhp_iQNfEVtV3LGqRNqQPyILVjzND3E6wDomH6Tp8M0n_pdpj1SAOUvThAPicaktxSRlzpJE3XYbgo1VBHIrP32_qMK1mZkJVzc-YypvxmQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e2ccc609757ac42d330ee7_AD_4nXcBfuSNL13ubSxMs19lZ0wRI7Hg654jhp_iQNfEVtV3LGqRNqQPyILVjzND3E6wDomH6Tp8M0n_pdpj1SAOUvThAPicaktxSRlzpJE3XYbgo1VBHIrP32_qMK1mZkJVzc-YypvxmQ.png)

_Using the MCP protocol, you can build integrations that allow LLMs to access and use customers’ ticketing data_

### **Support enterprise AI search**

Imagine that you offer an AI assistant that can help customers’ employees ask a wide range of questions and receive answers in plain text (using NLP).

To ensure the AI assistant can answer a broad range of questions, you can integrate its underlying LLM with the clients’ file storage systems via MCP. The LLM can then ingest the contents from the documents and not only use these contents to generate outputs but also link out to the documents themselves.

[![A screenshot of DoraAI, an AI chatbot for employees](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb73725d2e6ef86ee3_AD_4nXeBT8FW80EQYeAYYkT1ujKszVdRnMzLvxbVZJ2eSJGyVk5vaD6Boj4Fs9sDtTXhI_xOl5nIU2eTpvNql46BI7u4AxCsamwlaZfzBD19DxImlH9Hk91L5-WHbPksD2cRCs248_O_gQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb73725d2e6ef86ee3_AD_4nXeBT8FW80EQYeAYYkT1ujKszVdRnMzLvxbVZJ2eSJGyVk5vaD6Boj4Fs9sDtTXhI_xOl5nIU2eTpvNql46BI7u4AxCsamwlaZfzBD19DxImlH9Hk91L5-WHbPksD2cRCs248_O_gQ.png)

_AI assistant providers—like_ [_Assembly’s DoraAI_](https://www.joinassembly.com/solutions/ai-workplace-assistant) _—can connect their LLM to customers’ file storage systems to answer employees’ questions in plain text_

_Related:_ [_Enterprise AI search use cases_](https://www.merge.dev/blog/ai-enterprise-search)

### **Enable AI agents to act as recruiting coordinators**

Now say you want to power AI agents that help customers manage interviews.

More specifically, you want the AI agent to not only remind interviewers about an upcoming interview but also provide context on candidates to help these interviewers prepare quickly, easily, and effectively.

To power this, you can integrate your AI agent’s LLM with your customers’ applicant tracking systems (ATSs) through MCP.

The AI agent can then ingest the information provided in the applications—from resumes to cover letters to Linkedin profiles—allowing it to generate summaries on candidates in a place that’s convenient for interviewers (e.g., Slack).

[![A screenshot from a Nova agent that helps an interviewer prep for their upcoming calls](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67dd74fb92a993fb885b25ba_AD_4nXfV6tzHjdH9QY9ahoDce_zszPHh6P6papU_QI3SrvGXUgOK3HPSFku9jzjOf216RBSP97QneFW1xcZNgpFcvQmiAbBJYBzZRwbWK8nVRJAx52PsHF1juXIsDLwqcMdehqp8Xl3EBA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67dd74fb92a993fb885b25ba_AD_4nXfV6tzHjdH9QY9ahoDce_zszPHh6P6papU_QI3SrvGXUgOK3HPSFku9jzjOf216RBSP97QneFW1xcZNgpFcvQmiAbBJYBzZRwbWK8nVRJAx52PsHF1juXIsDLwqcMdehqp8Xl3EBA.png)

_Recruiting coordinator AI agents—like_ [_Peoplelogic’s “Noah” agent_](https://nova.peoplelogic.ai/) _—can use customers’ ATS data to generate summaries on candidates_

## **Benefits of using MCP**

The Model Context Protocol offers several benefits that'll help support widespread adoption:

- **Simplifies the build process:** By providing a single, standard protocol, LLM providers and SaaS applications have a clearer and easier path to integrating with one another

- **Supports workflow definitions:** It provides a structured way for LLMs to retain, update, and get context, which allows the LLMs to manage and progress workflows  autonomously

- **Enhances LLM efficiency**: By standardizing context management, MCP minimizes unnecessary processing for LLMs

- **Strengthens security and compliance:** It offers standardized governance over how context is stored, shared, and updated across different environments

_Related:_ [_Tips for using MCP_](https://www.merge.dev/blog/mcp-best-practices)

## **What MCP doesn’t address at the moment**

Here are a few areas it doesn’t cover:

- **Managing rate limits optimally**: MCP doesn’t optimize data syncing within an integration provider’s rate limits, requiring you to [implement throttling strategies](https://www.merge.dev/blog/api-throttling-best-practices)

- **Authenticating to an endpoint**: MCP doesn’t handle authentication or specify how it should be implemented, leaving that decision to the integration provider

- **Handling errors**: MCP doesn’t enforce a standardized error-handling framework or [response status codes](https://www.merge.dev/blog/api-response-codes)—these are defined by each API provider. That said, MCP allows you to use error messages in JSON RPC 2.0, which includes code, message, and data fields. Learn more [here](https://modelcontextprotocol.io/docs/concepts/transports#message-format)

- **Supporting webhooks**: The protocol doesn’t include webhooks or event-driven architecture for instant data updates (although they do support real-time syncs via [server-sent events](https://modelcontextprotocol.io/docs/concepts/transports#server-sent-events-sse))

## **How unified APIs relate to MCP**

[Unified API solutions](https://www.merge.dev/blog/what-is-a-unified-api), which let you add hundreds of integrations to your product through a single, aggregated API, complement MCP for any integration, whether that’s managing authentication, data normalization, security, or sync speeds.

### **Data normalization**

A unified API solution normalizes all of the integrated customer data, or converts that data to a predefined data model. This ultimately allows an LLM to handle prompts with more precision.

[![How normalized data leads to better outputs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d1d3ebac67fee09104d3db_AD_4nXdkdvuZMmAFYoaDL5KbiMXc-Itjiyw-OTZ594yNYeExZtOBGGzYksDg0x6Zr4ZloXMNV0I_Tf9ETfPfL3KmiS3kXlDIbltSV7aRObKExK65RqYhoevH1LJfcFH8iA2Dgzf-K5MfDg.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d1d3ebac67fee09104d3db_AD_4nXdkdvuZMmAFYoaDL5KbiMXc-Itjiyw-OTZ594yNYeExZtOBGGzYksDg0x6Zr4ZloXMNV0I_Tf9ETfPfL3KmiS3kXlDIbltSV7aRObKExK65RqYhoevH1LJfcFH8iA2Dgzf-K5MfDg.png)

_An LLM can use normalized data to answer prompts—like “Give me the marketing team’s first names and email addresses”—successfully_

### **Security**

Unified API solutions can secure your integrations by giving you full control of the customer data you can access and who on your team can access it.

For example, a unified API solution can offer scopes—or the ability for either you or your customers to toggle off the specific fields that customers don’t want you to access and sync.

_Related:_ [_The risks of using MCP token management_](https://www.merge.dev/blog/mcp-token-management)

### **Observability**

Unified API solutions can offer a full suite of integration observability features to help your customer-facing team manage any of your MCP-based integrations. This includes everything from automated issue detection to fully-searchable logs.

### **Performance**

Finally, unified API solutions can support integrations with fast sync speeds. And many support webhooks to sync data in real-time—allowing an LLM to use the latest data for each customer.

## Enable your LLM to access all of your customers' data via Merge MCP

We've just released our own MCP server— [Merge MCP](https://www.merge.dev/features/mcp)—to help you access all 220+ of our customer-facing integrations!

You’ll still get access to the rest of our features and capabilities, from our integration maintenance support to our features that let your customer-facing teams manage integrations independently.

You can even implement Merge MCP with a few lines code:

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

#### Want to learn more about Merge MCP?

Learn more about Merge MCP and how it can power your AI product by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmodel-context-protocol)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

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

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2d914c87-46d7-427d-8a88-4c3197be6e57&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=25a4fe3f-34fa-4a86-a92f-5a98ef885c5a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2d914c87-46d7-427d-8a88-4c3197be6e57&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=25a4fe3f-34fa-4a86-a92f-5a98ef885c5a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=103a09b9-cb1e-4507-9a97-6341cab308a9&bo=2&sid=68cc08303e8c11f0ab89670fb1e8f535&vid=68cc36e03e8c11f0985187a58805a268&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=What%20you%20need%20to%20know%20about%20the%20Model%20Context%20Protocol%20(MCP)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmodel-context-protocol&r=&lt=1334&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=192708)