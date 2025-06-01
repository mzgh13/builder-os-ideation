---
url: "https://www.merge.dev/blog/how-to-build-ai-chatbot"
title: "Building AI chatbots with RAG: a step-by-step guide"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-build-ai-chatbot#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-build-ai-chatbot#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-build-ai-chatbot#)

Table of contents

[What is an AI chatbot?](https://www.merge.dev/blog/how-to-build-ai-chatbot#what-is-an-ai-chatbot)

[Why businesses need AI chatbots](https://www.merge.dev/blog/how-to-build-ai-chatbot#why-businesses-need-ai-chatbots)

[The step-by-step process of building an AI chatbot](https://www.merge.dev/blog/how-to-build-ai-chatbot#the-step-by-step-process-of-building-an-ai-chatbot)

[Best practices for creating an AI chatbot](https://www.merge.dev/blog/how-to-build-ai-chatbot#best-practices-for-creating-an-ai-chatbot)

[Power best-in-class AI chatbots with Merge](https://www.merge.dev/blog/how-to-build-ai-chatbot#power-best-in-class-ai-chatbots-with-merge)

[AI chatbot FAQ](https://www.merge.dev/blog/how-to-build-ai-chatbot#ai-chatbot-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-ai-chatbot)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**9 powerful examples of retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-examples)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Why normalized data is critical for best-in-class retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/normalized-data-rag)

# Building AI chatbots with RAG: a step-by-step guide

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As large language models (LLMs) continue to improve, organizations see increasing value in incorporating AI chatbots into their products.

AI chatbots can now address customer issues effectively; answer employees’ questions with high precision; help employees build robust analytics dashboards quickly—and much more.

The process of building these chatbots, however, isn’t always straightforward.

To help guide you through the process, we’ll break down several steps you should take. But first, let’s align on what an AI chatbot is and why it’s important.

How to build an AI chatbot in 2025 - YouTube

Merge

202 subscribers

[How to build an AI chatbot in 2025](https://www.youtube.com/watch?v=OQS9-4fJVBA)

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

[Watch on YouTube](https://www.youtube.com/watch?v=OQS9-4fJVBA "Watch on YouTube")

## **What is an AI chatbot?**

It’s a chat interface that leverages RAG to answer users’ questions or take actions on their behalf. It can be used across your product and in immeasurable ways, as long as it can access all of the relevant data.

_Related:_ [_What is an AI product strategy?_](https://www.merge.dev/blog/ai-product-strategy)

## **Why businesses need AI chatbots**

While the reasons depend on the business and their unique requirements, here are some that apply to many companies:

- **Addresses users’ questions quickly:** AI chatbots can address prompts in a matter of seconds (if not faster). This is not only a great customer experience but also allows users to tackle tasks and/or get issues resolved quickly (which helps explain why [chatbots are often used to improve the customer experience](https://www.statista.com/statistics/1490150/ai-customer-experience-adoption/))


- **Increases conversion rates on leads:** By using AI chatbots to surface leads to the right reps, reps can reach out sooner, which— [according to a prominent study](https://hbr.org/2011/03/the-short-life-of-online-sales-leads)—should help them convert leads at a higher rate


- **Improves employee engagement:** AI chatbots can tackle many repetitive tasks that your employees would otherwise have to perform. This allows your employees to save countless time and focus on the work they’re more likely to enjoy


- **Cost savings:** Since AI chatbots can complete a wide gamut of tasks effectively, they can lower headcount both now and in the future, saving companies countless money


- **Competitive differentiation:** Many companies in your space may not have adopted AI chatbots in their product, or at least not in the ways your team is scoping. If you can be the first mover in incorporating AI chatbots for a certain use case, you can earn and maintain a meaningful competitive advantage

## **The step-by-step process of building an AI chatbot**

Here’s a breakdown of each step you’ll need to take.

[![The steps for building an AI chatbot](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67db1bdcc3b6ce206e272fa5_How%20to%20build%20an%20AI%20chatbot.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67db1bdcc3b6ce206e272fa5_How%20to%20build%20an%20AI%20chatbot.png)

### **1\. Define your objective**

Your objective will be key for executing on the rest of the steps, so it’s critical to establish it at the beginning.

It requires several inputs: the core purpose of your chatbot; the KPI(s) you want it to influence; and the audience you want to use it on (at least initially). You’ll also want to incorporate a goal-setting framework—e.g., SMART—so that the goal is actionable.

For example, if you offer an AI chatbot for employees, your goal can be the following: Improve your customers’ average Net Promoter Score® by at least 5 points, on average, within 3 months.

_Related:_ [_A guide to setting product objectives_](https://www.merge.dev/blog/product-objectives)

### **2\. Choose a chatbot platform**

You’ll need to decide between an open-source chatbot framework, such as [Rasa](https://rasa.com/) or [Botpress](https://botpress.com/), and a cloud-based platform, like [Dialogflow](https://cloud.google.com/products/conversational-agents?hl=en), [Ema](https://www.ema.co/), and [AmazonQ](https://aws.amazon.com/q/).

The best choice depends on a few factors:

- **Customizability:** If you have highly custom requirements, you may need to use an open-source chatbot framework, as it offers more flexibility in how it can be integrated with applications, the workflows it can support, and more


- **Scalability:** If you plan to roll out the chatbot to a large audience (or you eventually plan to do so), it may be worth using a cloud-based platform as they handle the infrastructure on your behalf


- **Time to market:** If your team needs to push the chatbot live as soon as possible, the cloud-based platform will likely be a better choice, as its implementation is likely simpler and easier


- **Resources:** The process of building and maintaining chatbots can be fairly technical, and your team either may not have the resources on hand to manage this project or can’t afford to allocate them to it. This would force your team to use a cloud-based platform **‍**

- **Connectivity:** If the chatbot needs to be integrated with several applications, it may be worth using a cloud-based platform. These platforms typically offer [pre-built connections](https://www.merge.dev/blog/api-connector) and may offer additional support for building new connections (e.g., technical teams on their side can add integrations on your behalf).

In short, there’s no one-size-fits-all answer, but you’ll likely want to use a cloud-based platform.

### **3\. Design the conversation flow**

Once you’ve picked the solution, you’ll need to craft the conversation path based on all of the user inputs that can come up. You’ll also need to consider potential edge cases in user inputs and how the chatbot should respond to them.

Fortunately, this step is getting increasingly easier with the help of natural language processing (NLP).

Many tools let you use plain text to describe the workflow you want an AI chatbot to support and the tool can use an LLM to then generate that workflow on your behalf. You can even iterate on it in plain text, helping you land on the most optimal workflow.

[![A screenshot of a chatbot from Ema](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cce980faa1a4ec7528_AD_4nXeAwRIExsC2N1AUGg37mFebnGzy0Qlgn7RrQGtdg88JGW-pfr1aK4yfBY1PkyodGnMX39RNJ6-RIKNXeAyhxG3vasGAqOAhXozUqpCxteKWL9jAffZaMw2ChoTcSF3yrN3wffYoEQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cce980faa1a4ec7528_AD_4nXeAwRIExsC2N1AUGg37mFebnGzy0Qlgn7RrQGtdg88JGW-pfr1aK4yfBY1PkyodGnMX39RNJ6-RIKNXeAyhxG3vasGAqOAhXozUqpCxteKWL9jAffZaMw2ChoTcSF3yrN3wffYoEQ.png)

[_Ema_](https://www.ema.co/) _, a universal AI employee, lets you build AI agents and chatbots through simple descriptions_

### **4\. Train your AI chatbot**

Your AI chatbot ultimately needs to access your customers’ latest data to provide personalized and actionable outputs.

For example, it can’t help a customer support rep tackle a specific client issue if it can’t access and interact with the customer support rep’s ticketing system.

To that end, you’ll need to [build API-based integrations](https://www.merge.dev/blog/rest-api-integration) (as opposed to file-based integrations, which are slower and error prone) with all of the systems that support your chatbot’s use cases.

[![A screenshot of the integrations that Ema offers](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb7cb3e370706b3ea7_AD_4nXcc8dlrBewTqAtPejhhaVeeQVG4qs5DLu7chMgo0YD5LdE55zfIUu86mz7dom6ZxHd96Ms9vrKwHjObdWnSQAobQgRs76b5_IJ0QgaUXNf6LOkdlsU9JW5e0JF5DvhNXl0sdVWl.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb7cb3e370706b3ea7_AD_4nXcc8dlrBewTqAtPejhhaVeeQVG4qs5DLu7chMgo0YD5LdE55zfIUu86mz7dom6ZxHd96Ms9vrKwHjObdWnSQAobQgRs76b5_IJ0QgaUXNf6LOkdlsU9JW5e0JF5DvhNXl0sdVWl.png)

_Since Ema’s AI chatbots and agents can help employees across departments, their platform offers integrations with several software categories—from file storage to ticketing systems to CRMs_

You’ll also need to fine tune the chatbot based on user inputs; so while the chatbot may not perform well at the beginning, it should consistently improve.

_Related:_ [_Ideas for AI products_](https://www.merge.dev/blog/ai-product-ideas)

### **5\. Secure your AI chatbot**

The integrations that support your chatbot should include access control levels (ACLs), which ensure that users only access the data that meets their level of permissions in that integrated application.

For example, if a user is asking your chatbot for sensitive business information, the chatbot can determine that that user doesn’t have access to the file that contains the information—leading your chatbot to not share it.

### **6\. Test and monitor the chatbot**

Before pushing the chatbot to production, your team should test it with a wide range of inputs, including the edge cases. You should also share it with colleagues who are your target user profiles who haven’t spent as much time working on the chatbot. They can approach it with a fresh pair of eyes and see issues you can’t.

Finally, your team should also monitor the chatbot soon after it goes live as small issues can have a long-term impact on how it gets perceived.

## **Best practices for creating an AI chatbot**

As you build your AI chatbot, it’s worth keeping the following in mind:

- **Create a chatbot personality that reflects your brand values.** Your chatbot is often the first line of communication for prospects, and your customers and employees will likely interact with it often. As a result, it’s critical that the chatbot interacts with users in a way that reflects your brand’s core values—whether that’s humility, integrity, kindness, and so on

- **Provide links to the sources used in its outputs.** Whether fair or not, LLMs have gained a reputation for hallucinating, or generating inaccurate outputs.

To give users confidence that your AI chatbot provides accurate information, you can include the sources used in a given output and make it clickable—allowing users to verify the information and learn more.

[![Example of DoraAI linking out to a source](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cbc7792cdfa9eb610b_AD_4nXfuFjmtQZ4iEHeiFaVVZvf_8VqO24sa7oM3gmrVKuRV1FKnLoTt-hGBT8OvsmvdPm5XRl_m64I7FNJHVzCCC7ZMdUJVWj3PkbwMuzArgBcZCqiYZr9kLtC7WZqEs8bA5pVZMT7cJA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cbc7792cdfa9eb610b_AD_4nXfuFjmtQZ4iEHeiFaVVZvf_8VqO24sa7oM3gmrVKuRV1FKnLoTt-hGBT8OvsmvdPm5XRl_m64I7FNJHVzCCC7ZMdUJVWj3PkbwMuzArgBcZCqiYZr9kLtC7WZqEs8bA5pVZMT7cJA.png)

_Your AI chatbot can include sources in every response it generates, allowing users to not only verify information but also access the documents they need, quickly_

- **Offer suggested prompts by default.** Many users may not know what your AI chatbot is capable of. They also might not think of the most valuable ways to use it. To help guide them in the right direction, you can offer suggestions and even provide brief descriptors of what your chatbot can do (this is especially helpful when it’s the user’s first time using your chatbot)

- **Use webhooks when possible.** Webhooks allow your chatbot to access and use real-time data when generating outputs. This can prove critical for several use cases, from sharing warm leads to sales reps to sharing security incidents

- **Revisit your AI chatbot’s performance regularly.** Your chatbot’s level of adoption may drop after a few months or even a few years based on the quality and value of its outputs. Noticing when this happens and being able to diagnose and address the root cause on time is critical to providing a best-in-class chatbot over time

- **Expand your AI chatbot offerings once your first one succeeds.** After you’ve figured out the right process for building AI chatbots, you can explore additional chatbot applications for your product and apply the same process to implement them

- **Report on your chatbot’s performance to the C-suite.** Your C-suite likely feels pressure from the board of directors to invest in all kinds of AI product features and capabilities. Being able to show your C-suite that your AI chatbot not only exists but is also getting adoption and providing value can help them handle these board conversations and allow you to secure buy-in for additional investments **‍**

- **Experiment with different LLMs to optimize performance.** Depending on the chatbot framework, you may be able to pick and choose the LLM(s) that powers your AI chatbot. When that’s the case, it’s worth trying out a few for anticipated use cases and then moving forward with the one that produces the most reliable, personalized, and high quality outputs.


- **Leverage a unified API solution.** [A unified API solution](https://www.merge.dev/blog/what-is-a-unified-api) offers a single, aggregated API to help you add hundreds of integrations. Since your customers’ tech stacks likely vary, and you may need to support different categories of integrations to cover all of your chatbot’s use cases, this can help you take your chatbot to market faster

[![A screenshot of how Merge works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d845260792e526da90ec08_Homepage%20hero%20illustration%20(1).png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d845260792e526da90ec08_Homepage%20hero%20illustration%20(1).png)

_Merge lets you add 220+ product integrations across 6 software categories_

- **Feed normalized data to the LLM that powers your chatbot.** Normalized data, or data that’s transformed to fit a predefined data model, can be embedded more accurately, as it doesn’t include miscellaneous information. This allows it to be identified for relevant prompts consistently, leading it to be fed to the AI chatbot’s LLM and used in outputs

[![How normalized data leads to better outputs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d1d3ebac67fee09104d3db_AD_4nXdkdvuZMmAFYoaDL5KbiMXc-Itjiyw-OTZ594yNYeExZtOBGGzYksDg0x6Zr4ZloXMNV0I_Tf9ETfPfL3KmiS3kXlDIbltSV7aRObKExK65RqYhoevH1LJfcFH8iA2Dgzf-K5MfDg.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d1d3ebac67fee09104d3db_AD_4nXdkdvuZMmAFYoaDL5KbiMXc-Itjiyw-OTZ594yNYeExZtOBGGzYksDg0x6Zr4ZloXMNV0I_Tf9ETfPfL3KmiS3kXlDIbltSV7aRObKExK65RqYhoevH1LJfcFH8iA2Dgzf-K5MfDg.png)

_An AI chatbot can use normalized data to answer prompts—like “Give me the marketing team’s first names and email addresses”—successfully_

_Related:_ [_Best practices for using retrieval-augmented generation_](https://www.merge.dev/blog/rag-best-practices)

## **Power best-in-class AI chatbots with Merge**

Merge, the leading unified API solution, lets you add hundreds of HRIS, ATS, file storage, ERP, ticketing, and CRM integrations through a single build.

Merge also:

- Normalizes all of the integrated data across its integrations according to its Common Models
- Offers Integration Observability features to help your customer-facing teams manage any integration issues
- Supports webhooks to help your chatbot use real-time data

Learn more about how Merge can support your AI chatbots by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-ai-chatbot).

## **AI chatbot FAQ**

In case you have any more questions, we’ve addressed several more below.

### **What is an example of a RAG-powered AI chatbot?**

One example comes from Assembly, a comprehensive HR software platform.

They offer [DoraAI](https://www.joinassembly.com/solutions/ai-workplace-assistant), an AI chatbot that can answer their customers’ employees’ questions in plain text (using natural language processing) based on the files it has access to. DoraAI can also display the source(s) it used in its answer in case the user wants to learn more.

[![A screenshot of DoraAI, an AI chatbot for employees](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb73725d2e6ef86ee3_AD_4nXeBT8FW80EQYeAYYkT1ujKszVdRnMzLvxbVZJ2eSJGyVk5vaD6Boj4Fs9sDtTXhI_xOl5nIU2eTpvNql46BI7u4AxCsamwlaZfzBD19DxImlH9Hk91L5-WHbPksD2cRCs248_O_gQ.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d843cb73725d2e6ef86ee3_AD_4nXeBT8FW80EQYeAYYkT1ujKszVdRnMzLvxbVZJ2eSJGyVk5vaD6Boj4Fs9sDtTXhI_xOl5nIU2eTpvNql46BI7u4AxCsamwlaZfzBD19DxImlH9Hk91L5-WHbPksD2cRCs248_O_gQ.png)

### **How much does it cost to build an AI chatbot?**

The cost varies depending on the chatbot platform you use, the types of data your chatbot needs, the extent to which customers adopt your chatbot, and more.

Given all these factors, the cost can range anywhere from a few thousand dollars to hundreds of thousands of dollars every year.

### **When is it worth investing in an AI chatbot?**

There’s no “best time.” You might move to build one quickly when customers or prospects request it and/or when your competitors start rolling them out, but it likely comes down to how the chatbot would fit into your product strategy and whether it’s worth prioritizing over other net-new features or product improvements.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=09a8b220-d950-49fe-8fb5-8c607bdd1f8a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6a118d66-e87c-432d-99ba-04b45f1cde83&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-build-ai-chatbot&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=09a8b220-d950-49fe-8fb5-8c607bdd1f8a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6a118d66-e87c-432d-99ba-04b45f1cde83&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-build-ai-chatbot&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=2a8d93bd-760a-4a13-b770-3634f6ead65d&bo=2&sid=bd8374403e8d11f0bf3f0f6e60c6724f&vid=bd8399003e8d11f0b0b2f38f7720ef2c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Building%20AI%20chatbots%20with%20RAG%3A%20a%20step-by-step%20guide&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-build-ai-chatbot&r=&lt=425&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=817208)