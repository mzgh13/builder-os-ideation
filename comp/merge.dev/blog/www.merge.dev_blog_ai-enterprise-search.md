---
url: "https://www.merge.dev/blog/ai-enterprise-search"
title: "How to build integrations that power enterprise AI search"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/ai-enterprise-search#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/ai-enterprise-search#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/ai-enterprise-search#)

Table of contents

[What is enterprise AI search?](https://www.merge.dev/blog/ai-enterprise-search#what-is-enterprise-ai-search)

[How enterprise AI search works](https://www.merge.dev/blog/ai-enterprise-search#how-enterprise-ai-search-works)

[Examples of enterprise AI search](https://www.merge.dev/blog/ai-enterprise-search#examples-of-enterprise-ai-search)

[How to build enterprise AI search functionality](https://www.merge.dev/blog/ai-enterprise-search#how-to-build-enterprise-ai-search-functionality)

[Build all the integrations your enterprise AI search needs with Merge](https://www.merge.dev/blog/ai-enterprise-search#build-all-the-integrations-your-enterprise-ai-search-needs-with-merge)

[Enterprise AI search FAQ](https://www.merge.dev/blog/ai-enterprise-search#enterprise-ai-search-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-enterprise-search)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**10 AI product ideas worth building in 2025**](https://www.merge.dev/blog/ai-product-ideas)

# How to build integrations that power enterprise AI search

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Every employee has questions that require a quick and concise response, whether the questions are specific to their role or not.

For example, an account executive might have questions about the latest sales commission model; at the same time, they may have questions about the company’s PTO policy.

Enterprise AI search can help the rep (and any employee) in either type of scenario.

We’ll go deeper on how enterprise AI search can work by reviewing several real-world examples. We’ll also break down how integration data can power enterprise AI search functionality.

But to get started, let’s align on what, exactly, enterprise AI search means.

#### Ready to supercharge your enterprise AI search?

Learn how Guru, Assembly, and other innovative companies use Merge’s integrations to fuel their enterprise AI search.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-enterprise-search)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **What is enterprise AI search?**

It's any search functionality in an application that allows employees to ask questions and receive answers. In addition, the search functionality uses a machine learning model that can understand the query’s intent and use integrated customer data to generate relevant output.

This output can be displayed using both plain text and links with additional context on the answer.

[![Screenshot of Assembly's AI feature, "Dora AI"](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6615ca99a389a894d2ac2634_qkRIonxqIUB103TXsxpiR6ILolf1HM9rjt7QdpfkRz0iFZ-T8HCuOf7zdRcoKrZHTp0d2vheCj_FzxNUjqym8Gzxwcnkus6ZwaAAXV7mDR48Iw4MZHBdy0uLKYGTJn6tTHg6BQkvf4m4Hd1Uhusx9Gc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6615ca99a389a894d2ac2634_qkRIonxqIUB103TXsxpiR6ILolf1HM9rjt7QdpfkRz0iFZ-T8HCuOf7zdRcoKrZHTp0d2vheCj_FzxNUjqym8Gzxwcnkus6ZwaAAXV7mDR48Iw4MZHBdy0uLKYGTJn6tTHg6BQkvf4m4Hd1Uhusx9Gc.webp)

_Assembly, an HR platform, offers an enterprise AI search that generates output with plain text and a link(s). The latter allows searchers to dig deeper on the answer with ease_

_Related:_ [_What is RAG? Here's how it works and how you can apply it_](https://www.merge.dev/blog/rag-use-cases)

## **How enterprise AI search works**

While enterprise AI search’s functionality can vary across providers, it typically works as follows under the hood:

1\. A user submits a query in your enterprise search bar.

2\. That query gets embedded—or turned into a vector. In other words, the query gets transformed from plain text into a string of numbers.

3\. The embedded query is compared to existing vectors in the database via similarity metrics (e.g., cosine similarity) to find the closest matches. The relevant documents and/or data identified from the database are then retrieved.

4\. The LLM collects both the embedded query and the relevant context (i.e., the documents and/or data retrieved).

5\. The LLM then generates an output for the user via the embedded query and context.

[![How enterprise AI search works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e030a22b2b407de214a9_AD_4nXcb08oaCJ2RN8G0Egf0jgRcWIiLy1hedUEj71vv-cHkvZ279kdSeOK2L-KXmeoy3KK53DtIcZgZhQA3gcZvUlp2opxyYMxJMB5xNRJXp20o6h0NOjzAgD1bN-H72gDxJ-GHiHJqIg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e030a22b2b407de214a9_AD_4nXcb08oaCJ2RN8G0Egf0jgRcWIiLy1hedUEj71vv-cHkvZ279kdSeOK2L-KXmeoy3KK53DtIcZgZhQA3gcZvUlp2opxyYMxJMB5xNRJXp20o6h0NOjzAgD1bN-H72gDxJ-GHiHJqIg.webp)

Note: The workflow above uses a technique commonly referred to as retrieval augmented generation (RAG).

## **Examples of enterprise AI search**

To help make enterprise AI search more tangible, let’s break down a few real-world examples.

### **Notion**

The productivity app helps users build internal wikis, organize and track projects, and—using its enterprise AI search—find the answers they need to execute on their work.

Since the platform collects a comprehensive set of data within an organization and can integrate with customers’ file storage systems and ingest the files’ contents, its enterprise AI search (dubbed Notion AI) can answer nearly any question your employees have. This can be anything from the content marketing team’s strategy in 2025 to the company’s current office locations to the product roadmap plans in the coming quarter.

Moreover, within the output’s plain text, Notion AI uses citations to help readers learn more and to give them confidence in the answer’s accuracy.

[![Screenshot of Notoin AI's output](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0306bfc7253946a8cba_AD_4nXdcytZDwUiuCd8dHf0Hp47_XB8FJu45pH_tRNgRCeDFc4pDrPZ1lStL1qtQEHjpxicALXLYs0IzaUBbUYFdy0IM_EUmuNv33G-W8THJJf8g5dcGyxNO7-u3U0scTO3X3iF5vE91.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0306bfc7253946a8cba_AD_4nXdcytZDwUiuCd8dHf0Hp47_XB8FJu45pH_tRNgRCeDFc4pDrPZ1lStL1qtQEHjpxicALXLYs0IzaUBbUYFdy0IM_EUmuNv33G-W8THJJf8g5dcGyxNO7-u3U0scTO3X3iF5vE91.webp)

_Notion AI users can hover over the accompanying numbers to find Notion docs that support its claims. Users can also find relevant files below the plain text_

[Related](https://www.merge.dev/blog/rag-examples?blog-related=image)

#### [9 powerful examples of retrieval-augmented generation (RAG)](https://www.merge.dev/blog/rag-examples?blog-related=image)

[![9 powerful examples of retrieval-augmented generation (RAG)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/rag-examples?blog-related=image)

### **Guru**

Guru’s enterprise AI search—which is the company’s core offering—relies on more integrated data than the contents stored within the app.

Guru integrates with customers’ file storage systems, CRMs, ticketing platforms, and HRIS solutions. Once connected, they can feed the data from all of these systems to the machine learning (ML) they use, allowing the model to perform RAG for all kinds of queries across their customers' user base.

For example, it can still answer questions that may be documented within Guru, like the location of a team onsite.

[![Screenshot of Gurus' enterprise AI search](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0311386faac76ed57d9_AD_4nXc8OZmsvQ7Ay3m2sRsjaNWRxHFMUzZZApKHd6KekBsDvz5Dr8d0TZkzyWFCelg4eZxxOcaZAvcTWTvWekrDq1q74UeeHlwBNL5Mo_raFtg8jf4robDoyQfDd1x9ip5l0zHspswW.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0311386faac76ed57d9_AD_4nXc8OZmsvQ7Ay3m2sRsjaNWRxHFMUzZZApKHd6KekBsDvz5Dr8d0TZkzyWFCelg4eZxxOcaZAvcTWTvWekrDq1q74UeeHlwBNL5Mo_raFtg8jf4robDoyQfDd1x9ip5l0zHspswW.webp)

But queries that require information in other systems—e.g., figuring out how to resolve a particular type of issue for a customer—will lead Guru to rely on the customers' integrated systems of record.

[![Screenshot of Gurus' enterprise AI search](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e031d6338d7d513e601c_AD_4nXfRhLTHR6tryuodv0kst_MaURl7gnClpkPiTWl2mWOntXbThFJHJbvzIozG0SX9VjYnMeD6EGzmSbtaxylZW0DswLm7o432nWHEsLupiWuiwAwlTzrjSr4-f86-xVr6IvUQ0U8s1Q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e031d6338d7d513e601c_AD_4nXfRhLTHR6tryuodv0kst_MaURl7gnClpkPiTWl2mWOntXbThFJHJbvzIozG0SX9VjYnMeD6EGzmSbtaxylZW0DswLm7o432nWHEsLupiWuiwAwlTzrjSr4-f86-xVr6IvUQ0U8s1Q.webp)

## **How to build enterprise AI search functionality**

As our examples show, every enterprise AI search needs [customer-facing integrations](https://www.merge.dev/blog/product-integrations) (i.e., product integrations) to power its outputs.

Otherwise, you risk limiting the search to information stored natively within the app. And, assuming your platform isn’t the system of record across teams and processes, this would curb the search’s value.

With this in mind, here’s how you can build the appropriate set of product integrations for your enterprise AI search:

### **1\. Identify current and potential queries**

If your enterprise AI search functionality is already built and in use, this exercise is easy: Analyze the searches currently taking place.

More likely, you’re still building your enterprise AI search and/or want to expand its value across teams. If you fall into this bucket, you’ll need to spend the time necessary to pinpoint the most relevant queries, such as talking to your ideal customer profiles (both internally and with customer and prospect accounts) on how they’d use the enterprise search day to day.

### **2\. Map the current and/or forecasted queries to the apps that store the relevant data**

Once you know the types of searches your users will make, you can pinpoint the applications you’ll need to integrate with.

Here’s how this can work:

- If your users need to access data on sales opportunities, you’ll need integrate with customers’ CRMs
- If your users need to access data related to customer issues, you'll need to integrate with customers’ ticketing systems
- If your users need to access data on their employer’s policies and procedures, you’ll need to integrate with HRIS solutions
- And if your users need to access any of the above (and more), you’ll need to integrate with file storage solutions as the documents and files stored in these solutions offer a wide range of information.

### **3\. Build integrations with those applications**

Once you know the applications you need to integrate with your enterprise AI search, you’ll need to decide how to build those integrations.

This essentially leaves you with 3 options:

1\. An [embedded iPaaS solution](https://www.merge.dev/blog/embedded-ipaas), which lets you build one integration at a time with your product as well as implemented workflow automations that work across these systems.

[![Embedded iPaaS vendors](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0306b4bee712d69b3a9_AD_4nXcwN7F-55256zo6P2FSsHxw4tjwdmwO3-bO-l-OUHFTJxjm0aDep9VmuHIYZoT490YotyscsPOh-pac016K7kZBlEAe4IzmfClWWJ2pfEiml0YGWLXQq6bTMVpKCWut1UZJljwL.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e0306b4bee712d69b3a9_AD_4nXcwN7F-55256zo6P2FSsHxw4tjwdmwO3-bO-l-OUHFTJxjm0aDep9VmuHIYZoT490YotyscsPOh-pac016K7kZBlEAe4IzmfClWWJ2pfEiml0YGWLXQq6bTMVpKCWut1UZJljwL.webp)

_A snapshot of the embedded iPaaS solutions you can evaluate and choose from_

2\. [A unified API solution](https://www.merge.dev/blog/what-is-a-unified-api), which lets you add hundreds of integrations to your product through a single integration build. These integrations can also span several categories, from HRISs to file storage platforms to CRMs.

[![Unified API vendors](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e03069b45c42ebd923a3_AD_4nXcUHODYKyrCLV1Plg9kgfbfbSdqFbr0Ttch-lJEW-ux_s-9VI8cAAejZFBPY7dXQDU9OUk19H_RU3m5FiPV1o4PxNgMKHoIAbicgtCODzwx3CdhBwgSUat-lgpjnfwaLwz_lvaF2Q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6797e03069b45c42ebd923a3_AD_4nXcUHODYKyrCLV1Plg9kgfbfbSdqFbr0Ttch-lJEW-ux_s-9VI8cAAejZFBPY7dXQDU9OUk19H_RU3m5FiPV1o4PxNgMKHoIAbicgtCODzwx3CdhBwgSUat-lgpjnfwaLwz_lvaF2Q.webp)

_A snapshot of the unified API solutions you can evaluate and choose from_

3\. [Native integrations](https://www.merge.dev/blog/native-integrations), or simply tasking your engineers with both building and maintaining your product integrations over time.

[Related](https://www.merge.dev/blog/embedded-ipaas-vs-unified-api?blog-related=image)

#### [Unified API vs embedded iPaaS: a look at their key differences](https://www.merge.dev/blog/embedded-ipaas-vs-unified-api?blog-related=image)

[![Unified API vs embedded iPaaS: a look at their key differences](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7e97dbabfb2ed0eb210_Accounting_integration.webp)](https://www.merge.dev/blog/embedded-ipaas-vs-unified-api?blog-related=image)

## **Build all the integrations your enterprise AI search needs with Merge**

Merge, the leading unified API platform, is uniquely positioned to support your enterprise AI search for a number of reasons:

- **Integration coverage:** Merge offers 200+ integrations across several categories—including file storage, CRM, HRIS, accounting, ATS, and ticketing—allowing you to integrate all the systems your customers need

- **Data normalization:** Merge normalizes all of your customers’ data into its Common Models, or its normalized data models, before adding it to your vector database. This gives the LLM clear and consistent inputs, which allow it to generate more reliable outputs

- ‍ **Advanced syncing features:** Merge offers several features that let you access data beyond its Common Models (e.g., [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/)), which let you feed additional data to your vector database. The LLM you use can then leverage an increased level of context to answer more queries and/or provide more specificity in its outputs

- **Access control lists (ACLs):** Merge uses ACLs across integrations to ensure that the AI enterprise search only generates outputs that fall under the searchers'  levels of permissions. For example, if a user asks what a colleague’s salary is and the user doesn’t have admin-level access to the [integrated HRIS](https://www.merge.dev/blog/guide-to-hris-api-integrations), they’d receive a message that says they don’t have access to that information

- **Enterprise-grade data security:** Merge has not only built enterprise-grade features and functionality to keep your customers’ documents and data safe—like ACL, [Scopes](https://help.merge.dev/en/articles/5950052-what-are-common-model-scopes), and bring your own key—but also complies with GDPR, SOC 2 Type 2, ISO 27001, and other security measures and regulations

#### Ready to supercharge your enterprise AI search?

Learn how Guru, Assembly, and other innovative companies use Merge’s integrations to fuel their enterprise AI search.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-enterprise-search)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Enterprise AI search FAQ**

In case you have more questions on enterprise AI search, we’ve addressed several common ones below:

### **What are some popular enterprise AI search platforms?**

Widely-used solutions include Guru, Simpplr, Glean, and Aisera.

Before choosing any, you should review the integrations they offer, the large language model(s) they use, and their search's' level of interactivity. For example, some may only let you retrieve information, while others can let you make requests and have the LLM perform actions on your behalf (i.e., it’s agentic).

### **What capabilities should enterprise AI search offer?**

Enterprise AI search should support the following functionality:

- **Concise outputs with links to sources:** It leverages natural language processing (NLP) to understand user intent and interpret semantic relationships between words. This, paired with a large language model(s), allows the enterprise AI search to generate clear and concise summaries—often just a few sentences long—that include links to sources in case the searcher wants to learn more

- **Comprehensive integration coverage:** They should let customers integrate with a wide range of solutions within and across popular categories—from file storage to ticketing to CRM to HRIS. This broad coverage helps the LLM retrieve the latest information for any potential query

- **Access level control (ACL):** The enterprise AI search should only share information that falls within the users’ levels of permissions. For example, an entry-level sales rep shouldn’t be able to retrieve information from a board deck, as they don’t have the permissions to access it in the integrated file storage solution

- **Personalized outputs:** The enterprise AI search can also have context on the user making the query, which can help the LLM generate more relevant and helpful outputs

### **What are the benefits of using enterprise AI search?**

Some of the benefits include:

- **Time savings:** Employees don’t have to sift through several applications to find information. They can simply make a search and get the information they need

- **Employee experience:** Allowing employees to spend less time looking for information lets them focus more on the work they enjoy and can help them work fewer hours

- **Productivity gains:** In addition to answering basic questions, enterprise AI search can complete tedious and complex tasks (e.g., putting together an analysis of the top customer issues from last quarter). This can help employees make more informed business decisions, faster

- **Cross-functional alignment:** By providing a single-source of truth for company information, employees can more easily align on critical areas, such as the current budget for a specific company initiative

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8fb234be-44f6-4a1e-ad44-c257f6e08c82&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b8316f0e-a402-4da0-a711-a3206546082a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-enterprise-search&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8fb234be-44f6-4a1e-ad44-c257f6e08c82&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b8316f0e-a402-4da0-a711-a3206546082a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-enterprise-search&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=7c1958e2-c7ff-4a7a-97f6-168264406135&bo=2&sid=40c001703e8d11f0ac07ff3998f640ff&vid=40c0a3603e8d11f08c61851afcaeec24&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20build%20integrations%20that%20power%20enterprise%20AI%20search&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-enterprise-search&r=&lt=472&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=359180)