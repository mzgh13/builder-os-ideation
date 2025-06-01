---
url: "https://www.merge.dev/blog/ai-agent-integrations"
title: "How to build integrations for AI agents"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/ai-agent-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/ai-agent-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/ai-agent-integrations#)

Table of contents

[How integrations support AI agents](https://www.merge.dev/blog/ai-agent-integrations#how-integrations-support-ai-agents)

[Examples of AI agent integrations](https://www.merge.dev/blog/ai-agent-integrations#examples-of-ai-agent-integrations)

[Best practices for building integrations with AI agents](https://www.merge.dev/blog/ai-agent-integrations#best-practices-for-building-integrations-with-ai-agents)

[Integration options for AI agents](https://www.merge.dev/blog/ai-agent-integrations#integration-options-for-ai-agents)

[Access customer data via MCP and a unified API through Merge](https://www.merge.dev/blog/ai-agent-integrations#access-customer-data-via-mcp-and-a-unified-api-through-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-agent-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)**AI product strategy: key steps, examples, and best practices**](https://www.merge.dev/blog/ai-product-strategy)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

# How to build integrations for AI agents

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to build AI agents in your product, you’ll inevitably need to support integrations that can access and interact with your customers’ data.

To help you navigate this successfully, we’ll break down examples of AI agents that use integrations and your options for building and maintaining any integration.

But first, let’s align on why AI agents require integrations.

## **How integrations support AI agents**

It comes down to a few key reasons.

### **Powers RAG pipelines**

Integrations form the foundation of [retrieval-augmented generation (RAG) pipelines](https://www.merge.dev/blog/how-rag-works), enabling AI agents to retrieve the context needed to effectively take actions on behalf of each user.

For example, say you offer a headcount analysis solution and support an AI agent to help users get more value from your platform.

Using RAG, your AI agent can take a question (e.g., “What are the top drivers behind the recent surge in headcount costs?”) and use the customer’s integrated employee and payroll data to provide an answer—along with recommended next steps.

[![RAG pipeline to help an AI agent provide insights on growing headcount costs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d115ea60f46d163cae_AD_4nXcVcTsxMtp0IerDzoFEDiwQw6SmDk8tuCbultN_ORpo_RSkAlPzhloDpOREoZBcfNuazbxr1bi3p5QD3FVGZ7U-G2fhAGt68IhLnq-xGJVJ4OqZbPNIh_pMsaM7J459tDJWUGNQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d115ea60f46d163cae_AD_4nXcVcTsxMtp0IerDzoFEDiwQw6SmDk8tuCbultN_ORpo_RSkAlPzhloDpOREoZBcfNuazbxr1bi3p5QD3FVGZ7U-G2fhAGt68IhLnq-xGJVJ4OqZbPNIh_pMsaM7J459tDJWUGNQ.png)

_How RAG can support an AI agent that answers customers’ questions on employee headcount_

‍

[Related](https://www.merge.dev/blog/agentic-rag?blog-related=image)

#### [Agentic RAG: definition, benefits, and real-world examples](https://www.merge.dev/blog/agentic-rag?blog-related=image)

[![Agentic RAG: definition, benefits, and real-world examples](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)](https://www.merge.dev/blog/agentic-rag?blog-related=image)

### **Offers raw and normalized customer data**

Each type of data can be valuable.

Normalized data, or data that’s transformed to fit a predefined data model, can remove sensitive information, unnecessary details, and duplicate data.

[![Example of normalized file data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d135842d30229887d2_AD_4nXffcxwbGB_zIOA1k26LGCzr_PwQUVuaYDb6kEEDRd9a_D_owVwPTBVGOxYdu8TWocLkxt3l2elbYO6NNHL7D1z26dO15uLp4fOG-MRjBNUJ5G94u0MK1FPdgQxbXqZNrsD86cHNZQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d135842d30229887d2_AD_4nXffcxwbGB_zIOA1k26LGCzr_PwQUVuaYDb6kEEDRd9a_D_owVwPTBVGOxYdu8TWocLkxt3l2elbYO6NNHL7D1z26dO15uLp4fOG-MRjBNUJ5G94u0MK1FPdgQxbXqZNrsD86cHNZQ.png)

_Fields related to a file's creation date can be normalized across file storage solutions_

This clean, consistent data enables embedding algorithms to generate accurate vector representations before storing them in a vector database. This, in turn, lets your AI agent retrieve the most relevant data across supported workflows consistently.

Raw data, or data that isn’t altered from the customer’s application, helps your AI agent support unique workflows for individual customers.

For example, imagine you offer a product intelligence platform with an AI agent that listens to customer conversations. Based on those conversations, the agent generates recurring reports highlighting key themes.

Now say that a specific customer has a custom CRM object they’d like included and populated in these reports—”Use case(s).” Based on the use case(s) that keeps coming up, this customer’s product team could better prioritize which features to build over time.

### **Supports time-sensitive processes**

Your AI agents may need to support time-sensitive workflows, like routing leads, de-provisioning a departing employee’s applications, creating and assigning tickets for a product bug, and more.

Integrations can help facilitate these use cases, among countless others, by supporting real or near real-time syncs with your customers’ systems.

## **Examples of AI agent integrations**

To better understand how AI agents can use integrations, let’s break down a few real-world examples.

### **Proposal Writer uses file storage and CRM integrations to generate personalized offers**

[Ema](https://www.ema.co/), which lets you build and manage AI agents across teams, offers a Proposal Writer agent that takes customers’ prompts (e.g., write a proposal for a customer in X industry that needs Y plan) and uses integrated data, among other context, to generate compelling proposals within seconds.

It does this by leveraging similar proposals in the customer’s file storage system and by evaluating the notes, along with other helpful information, within the prospect’s opportunity page in the CRM.

[![Ema's Proposal Writer AI agent](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d1f8f271b149912e2a_AD_4nXc4Js8PH8P1Oq2XYWkibXOq63FPliMqI87kPuCwILaqHy8hPs9wHvPJw-7-YfTmNAbCYXaTJslK7XKgDSJQdUdH-dkJRVkYbpXtGpV2wL5RJv7mkyYzZr29mPX5h5aLN9Wbh-Lr.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d1f8f271b149912e2a_AD_4nXc4Js8PH8P1Oq2XYWkibXOq63FPliMqI87kPuCwILaqHy8hPs9wHvPJw-7-YfTmNAbCYXaTJslK7XKgDSJQdUdH-dkJRVkYbpXtGpV2wL5RJv7mkyYzZr29mPX5h5aLN9Wbh-Lr.png)

[Related](https://www.merge.dev/blog/rag-vs-ai-agent?blog-related=image)

#### [AI agent vs RAG: how the two differ and where they overlap](https://www.merge.dev/blog/rag-vs-ai-agent?blog-related=image)

[![AI agent vs RAG: how the two differ and where they overlap](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/68263d8a39012af57f47cf95_Blog%20Header%20Brand%20Refresh%20(11).png)](https://www.merge.dev/blog/rag-vs-ai-agent?blog-related=image)

### **Juicebox Agent uses ATS integrations to help surface high-fit candidates**

[Juicebox](https://juicebox.ai/), which lets recruiters find and bring in talent, offers an agent that can surface thousands of high-fit candidates in seconds.

Here’s how it works: A user would click on a role they want candidates for (existing open roles are surfaced in Juicebox via the [integrated applicant tracking system](https://www.merge.dev/blog/guide-to-ats-api-integrations)).

[![How ATS integrations support Juicebox](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/68226082dc1438fc77079d54_AD_4nXfuSPhbnVEyrXgvOFceXSwtg9eF6EKXTtvxjvI_m-zAiICf2T6CI8hvVqa1sP_QxClYk7RuB1424STHO8HI-K5vf1JA19DyBAo0TuhVOmgaqU7t45binfHSx81FuvuiTYMCpENOtw.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/68226082dc1438fc77079d54_AD_4nXfuSPhbnVEyrXgvOFceXSwtg9eF6EKXTtvxjvI_m-zAiICf2T6CI8hvVqa1sP_QxClYk7RuB1424STHO8HI-K5vf1JA19DyBAo0TuhVOmgaqU7t45binfHSx81FuvuiTYMCpENOtw.png)

_Where the open roles appear in Juicebox_

The agent then uses the integrated job description associated with the selected role, along with additional context, to kickoff its search.

### **Nova uses ATS and HRIS integrations to help HR teams manage countless tasks**

[Peoplelogic](https://peoplelogic.ai/), the AI for HR platform, offers Nova, a suite of AI agents that can help HR teams perform specific tasks in Slack.

To help their agents execute tasks on behalf of users successfully, they use integrated candidate and employee data.

For example, a people ops leader can ask a Nova agent (“Shruti”) to remind every interviewer about their upcoming interviews that day on Slack. The people ops leader can also clarify when the messages should be sent and what context can be included.

[![How someone can make a request to Nova in Slack](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d1863efe1715ebd1a4_AD_4nXc16-Lq45T8uf-weZSfkMtolUQy08UJM25un-hH8a2daj7U32oconhF2DTEzX8ugOyBhicvqeXewxgFrnwyPydf4TxqXBRULCExOgVnpaPt3B03fL8MKPoh3QlN_OmWjAAPGPw2.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d1863efe1715ebd1a4_AD_4nXc16-Lq45T8uf-weZSfkMtolUQy08UJM25un-hH8a2daj7U32oconhF2DTEzX8ugOyBhicvqeXewxgFrnwyPydf4TxqXBRULCExOgVnpaPt3B03fL8MKPoh3QlN_OmWjAAPGPw2.png)

Shruti can then determine which agent should take on the task (it would be “Noah”). And the assigned agent can use the integrated candidate data to send the messages on time, along with the appropriate context from their applications.

[![How one of Nova's AI agents can interview notifications](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/68226081910a775191e944cb_AD_4nXeq_AA1Tg99G42XCyIaAWeEXaGuXG2u8I0Yh5jr4zQP8qagL7lmpH5z1DKi3wn7aNKTZDNIrIfgI94pRLkB_ojPAv9XSgDARHe7IBut-Ogv5QUiQsaMajVj_j-eY7PPvTyxwLrtPA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/68226081910a775191e944cb_AD_4nXeq_AA1Tg99G42XCyIaAWeEXaGuXG2u8I0Yh5jr4zQP8qagL7lmpH5z1DKi3wn7aNKTZDNIrIfgI94pRLkB_ojPAv9XSgDARHe7IBut-Ogv5QUiQsaMajVj_j-eY7PPvTyxwLrtPA.png)

[Related](https://www.merge.dev/blog/how-to-build-ai-chatbot?blog-related=image)

#### [Building AI chatbots with RAG: a step-by-step guide](https://www.merge.dev/blog/how-to-build-ai-chatbot?blog-related=image)

[![Building AI chatbots with RAG: a step-by-step guide](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)](https://www.merge.dev/blog/how-to-build-ai-chatbot?blog-related=image)

## **Best practices for building integrations with AI agents**

Before you begin investing resources on integration development, it’s worth considering the following.

### **Navigate the build versus buy decision carefully**

In most cases, tasking your own engineers with implementing these integrations isn’t worth it. It prevents them from developing your AI agents—and working on other core projects—which is likely what they’re uniquely qualified to tackle and what’ll differentiate your AI product long-term.

That said, if your agents need to support highly-custom integration use cases and/or you have resources you can afford to allocate towards integration projects, it can be worth implementing them in-house.

The following section—which breaks down all of your options for building and maintaining integrations for AI agents—can help you decide on the best approach.

### **Implement access control levels (ACLs) across your integrations**

The last thing you want is your AI agents performing actions on behalf of users in integrated applications without respecting the users’ permission levels.

For example, if one of your users requests information about an integrated file they don’t have access to, your AI agent should never reveal any details from that file—regardless of the user’s prompt.

To prevent your AI agents from inadvertently exposing sensitive data, it’s essential to implement access control lists (ACLs) across all integrations you develop.

### **Leverage webhooks to help your AI agents respond to events in real time**

Certain use cases require an immediate response from your AI agent.

For example, if one of your customer’s prospects becomes a marketing qualified lead, your AI agent should perform something like the following in real time:

1\. Use integrated CRM data to identify the assigned sales rep.

2\. Analyze the account’s activity history—stored in the marketing automation platform and/or CRM—to determine the best follow-up steps and messaging for the rep.

3\. Notify the rep via an app like Slack with this information to enable them to follow up quickly and effectively.

To facilitate these time-sensitive, agentic workflows, implement webhooks that send notifications to your AI agents when specific events occur—such as a prospect in one of your customer’s integrated apps reaching marketing qualified lead status.

## **Integration options for AI agents**

Here are your options for building integrations for customer-facing AI agents.

### **Native builds**

This simply involves your developers building and maintaining the integrations themselves.

#### **Pros**

- You have full control over which integrations get prioritized and how they should be built

- You’re entrusting your own development team (who you know and trust) to build integrations—not a separate team you’re less familiar with

- You don’t have to worry about the 3rd-party integration provider going out of business, moving away from certain integrations, or doing anything else that would directly impact your product and your AI agents

#### **Cons**

- Building each integration is incredibly complex and resource intensive. Since your AI agent likely needs to access dozens of systems, [native integrations](https://www.merge.dev/blog/native-integrations) can be the wrong approach

- Building and maintaining product integrations is often high pressure and unpleasant. For instance, when integrations break, your CS and leadership teams will know and will ask your devs to drop what they're working on to resolve it as soon as possible. This stressful and constant distraction can lead to burnout and turnover

- Implementing integration observability tooling, such as issue detection notifications in an app like Datadog, can also take your engineers several weeks, if not months

For example, Will Decker, the Head of Engineering at BrightHire, an interview intelligence platform, shared the insight below in [our case study](https://www.merge.dev/case-studies/brighthire):

##### “Building our own integration observability tooling to manage integrations would take our team at least 3 months.”

### **Embedded iPaaS solution**

An [embedded integration platform as a service](https://www.merge.dev/blog/embedded-ipaas) (iPaaS) lets you build customer-facing integrations and automations through a workflow builder interface.

[![Embedded iPaaS visualization](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d128bfb35f83b558d9_AD_4nXekRNU5goMZ39JGFfxJmtopdsSGfW_y0NXZDd3yGvZriHf4Ws6Hk3ipQBqkbW9I3v6e0Rt6vLOv5PMrueANXIEF-Nzsx4PPEsuJFHJAPhbxI3jjRXYQHUVLvnFcRHkRtXh0XybUeQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d128bfb35f83b558d9_AD_4nXekRNU5goMZ39JGFfxJmtopdsSGfW_y0NXZDd3yGvZriHf4Ws6Hk3ipQBqkbW9I3v6e0Rt6vLOv5PMrueANXIEF-Nzsx4PPEsuJFHJAPhbxI3jjRXYQHUVLvnFcRHkRtXh0XybUeQ.png)

#### **Pros**

- Helps accelerate integration and automate development by providing pre-built connectors and automation templates

- Many providers also offer complementary solutions, like an [embeddable marketplace for your app](https://www.merge.dev/blog/integration-marketplace)

- Lets you choose between implementing all the integrations and automations yourself and allowing customers to build and maintain the integrations (or a combination of both)

#### **Cons**

- Forces you to become familiar with their UX and implement each individual integration, which can prove time and resource intensive for your team

- Fails to provide robust integration management capabilities, like diagnosing specific integration issues

- Don’t normalize data—you’ll have to do this work yourself

The CEO and co-founder of Peoplelogic, elaborates on that last point in [our case study](https://www.merge.dev/case-studies/peoplelogic):

##### “Embedded iPaaS solutions can’t normalize our customers’ data, preventing our agents from providing accurate outputs, consistently.”

### **Model context protocol**

Anthropic’s [Model Context Protocol](https://www.merge.dev/blog/model-context-protocol) (MCP) lets AI agents interact with customers’ data via tools, or specific functionality and data exposed in an MCP server.

[![MCP overview visual](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d110bbe918e01080dc_AD_4nXcmmhF79vHyLRNyyb9HveNxkHcOYsHBZrmJLIGLmxM5EmNISkRf4EbP7twbaQZjBF0hWVzkD7QdKO1oIk-jv3uOFBo6sf0pTtlH01fq9S_oHe5p3mbzI2QoaRUy5F1xDk4oEphr.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e29d110bbe918e01080dc_AD_4nXcmmhF79vHyLRNyyb9HveNxkHcOYsHBZrmJLIGLmxM5EmNISkRf4EbP7twbaQZjBF0hWVzkD7QdKO1oIk-jv3uOFBo6sf0pTtlH01fq9S_oHe5p3mbzI2QoaRUy5F1xDk4oEphr.png)

#### **Pros**

- Lets AI agents act autonomously, as they can decide which tools to use based on users’ prompts

- Most SaaS solutions have (or will) spun up MCP servers, making this approach usable for nearly any use case

- Relatively easy to implement, as it offers a single, standard protocol for LLMs and SaaS providers to follow

#### **Cons**

- MCP providers can be easily manipulated into sharing sensitive information with unauthorized users (e.g., [tokens stored in an MCP server](https://www.merge.dev/blog/mcp-token-management))

- Many fraudulent MCP servers (“Shadow servers”) are cropping up, and it can be hard to differentiate them from legitimate ones

- The protocol is still in its infancy. It can change in negative ways or receive less support from data providers over time, making it unsuitable for your AI agents

### **Unified API platform**

A unified API solution lets you add hundreds of cross-category integrations through a single integration build.

[![Unified API visual](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6823cbb37d8dd54049fc4c28_AD_4nXfdJBS3MuAcYKceDCmdEBYQdGlEfO4eI8kdpiUc2hun-Lf-1L8qp_g3c5ZwDYMHNQDhpRkTDHm7AG8PqNoZFPaGK7j4w8K5ZT90m5aTD93SRTmXjIluMZZ9LAb3iB3UUz9Se-M-.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6823cbb37d8dd54049fc4c28_AD_4nXfdJBS3MuAcYKceDCmdEBYQdGlEfO4eI8kdpiUc2hun-Lf-1L8qp_g3c5ZwDYMHNQDhpRkTDHm7AG8PqNoZFPaGK7j4w8K5ZT90m5aTD93SRTmXjIluMZZ9LAb3iB3UUz9Se-M-.png)

#### **Pros**

- Lets you support all the integrations your AI agent needs, quickly and easily

- Some providers (like Merge) normalize all of the integrated data before syncing it with your product

- Offer a seamless process for authenticating with an application (typically via a UI component that’s embedded in your product)

#### **Cons**

- Most providers support limited types of data and/or integrations, making them a bad long-term fit

- Some providers are relatively new (founded within the last two years), and their long-term viability is questionable

- A few providers offer insecure integration methods when providers don’t support the relevant endpoints (e.g., “ [Assisted Integrations](https://www.merge.dev/blog/automated-vs-assisted-integrations)”)

Given all the integration methods to choose from, it can be hard to pinpoint the best option for your AI agent’s use cases.

You can follow the principle below as a general rule of thumb:

##### If your AI agent’s use case involves dynamic decision-making, opt for MCP; if the use case is static (i.e., follows a predefined workflow), use a unified API solution.

So, going back to our examples, Juicebox can use the unified API approach since their agent follows the same process every time when using integrated ATS data. On the other hand, Peoplelogic may want to leverage MCP because their agents’ workflows for executing tasks are less defined.

## **Access customer data via MCP and a unified API through Merge**

Merge, the leading unified API solution, offers 220+ cross-category integrations, a full suite of integration observability features, advanced syncing features to access and interact with any data, and enterprise-grade security features to keep customer data secure.

Merge also provides [Merge MCP](https://www.merge.dev/features/mcp)—a server that lets your AI agent access all of Merge’s supported integrations and endpoints.

[![Visual of Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e2c40616be04d419aad4a_AD_4nXdSNYlK-ct75PUX68irMAWPXu7p3-wreSVRcMoJiqU8-c56y7i_Dr5o582GISeNv529ErXEjcweBGlYmCpuR78G-_NkasgZViYwsbqxpZlNzQIdlysbUfnB1_D81jMDVc6vyGoNrA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682e2c40616be04d419aad4a_AD_4nXdSNYlK-ct75PUX68irMAWPXu7p3-wreSVRcMoJiqU8-c56y7i_Dr5o582GISeNv529ErXEjcweBGlYmCpuR78G-_NkasgZViYwsbqxpZlNzQIdlysbUfnB1_D81jMDVc6vyGoNrA.png)

Learn more about using Merge to support your AI agents’ integrations by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-agent-integrations).

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=cfbaecac-c158-4e71-a5df-e3ac9f0ab8a7&bo=2&sid=ffd120703e8c11f08a9d4369e41cfbe8&vid=ffd176503e8c11f0b3b8e18cdef8a62e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20build%20integrations%20for%20AI%20agents&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-agent-integrations&r=&lt=1180&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=743478)