---
url: "https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features"
title: "Why embedded iPaaS solutions fail to support AI-powered product features"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#)

Table of contents

[Your RAG pipelines wouldn’t scale across your customer base](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#your-rag-pipelines-wouldnt-scale-across-your-customer-base)

[Your integrated data could lead to inaccurate outputs](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#your-integrated-data-could-lead-to-inaccurate-outputs)

[Your observability tooling may limit your AI feature’s performance](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#your-observability-tooling-may-limit-your-ai-features-performance)

[Power best-in-class AI features by using Merge](https://www.merge.dev/blog/embedded-ipaas-fails-to-support-ai-features#power-best-in-class-ai-features-by-using-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fembedded-ipaas-fails-to-support-ai-features)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**9 powerful examples of retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-examples)

# Why embedded iPaaS solutions fail to support AI-powered product features

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb1e10d897b1194792e1de_Anuj%20Jhunjhunwala%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ba8b5339e4c1931fb22629_anuj-headshot-2-min.webp)

Anuj Jhunjhunwala

Director of Product Management

@Merge

Customer data can play an essential role in the retrieval part of the retrieval-augmented generation (RAG) pipelines that power your product.

Using this type of data effectively, however, requires connecting to all the relevant systems across your customer base, standardizing the data that’s synced from these systems into a common format, and diagnosing and resolving any integration issues quickly.

[Embedded integration platform as a service](https://www.merge.dev/blog/embedded-ipaas) (iPaaS) solutions, which is a common type of product integration software, by and large fail to meet these requirements.

You can read on to learn why.

## **Your RAG pipelines wouldn’t scale across your customer base**

Powering widely-available RAG features means building the integrations your RAG pipelines depend on for _all of your customers_.

Embedded iPaaS solutions are inherently bad at facilitating this.

The solution forces you and/or your customers to build one integration at a time through the platform’s “low-code” workflow builder.

As we’ve learned through numerous customer conversations, these workflow builders still require deep technical expertise—which forces your engineers to use them.

In addition, your engineers will need to spend several hours configuring _each integration_ for _every customer_.

[![How long it takes to build file storage integrations with an embedded iPaaS](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b4d1103489c3e646e494d3_AD_4nXcHWAesbzUc4rw7i-elLNZv2LN5z4uL0kSGKf67C9gG3OWzQISqP6W6bqlxv0eKvR61uiJL5GT3RCJHRsR9QsvY0B3KzNeb1twq8wvIqm6-ZBZRpug3XO1hhuel6ziWqEhqo7n1iQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b4d1103489c3e646e494d3_AD_4nXcHWAesbzUc4rw7i-elLNZv2LN5z4uL0kSGKf67C9gG3OWzQISqP6W6bqlxv0eKvR61uiJL5GT3RCJHRsR9QsvY0B3KzNeb1twq8wvIqm6-ZBZRpug3XO1hhuel6ziWqEhqo7n1iQ.webp)

_Each file storage integration build can take your engineers several hours to implement with an embedded iPaaS_

Since you’ll likely need to support hundreds of integrations over time across countless customers, your engineers won’t be able to keep pace with demand. And even if they try, it’ll come at the expense of them spending time on building and improving your core product features and capabilities.

[Related](https://www.merge.dev/blog/rag-use-cases?blog-related=image)

#### [3 RAG use cases—plus tips for implementing them](https://www.merge.dev/blog/rag-use-cases?blog-related=image)

[![3 RAG use cases—plus tips for implementing them](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/rag-use-cases?blog-related=image)

## **Your integrated data could lead to inaccurate outputs**

Normalized data, which is consistent and doesn’t include unnecessary details, is easier for an embedding algorithm to understand.

[![How file creation date fields can be normalized](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b5127f995c684a32b92507_Group%205%20(1).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b5127f995c684a32b92507_Group%205%20(1).webp)

_Fields related to a file's creation date can be normalized across file storage solutions_

As a result, normalized data can be embedded (or converted into a vector) more accurately before it’s added to a vector database.

Embedded queries can then be closest to the most relevant embeddings in the vector space.

Both the embedded query and the nearest embeddings would go on to be fed to an LLM—enabling the LLM to generate precise outputs.

[![How normalized data leads to higher-quality outputs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b4d1104fa5818eced1b8c5_AD_4nXcVNQj7iJbXBPBBUrGvGmawuaH1cbSx6TOq2UdUqCmAiKTQoNhiCqgJGUktbw8LVWxDAGDlT-YGXJLJiKq7qfDOI0kkoBZhQS2ZjQYAdKO6Ywe2huCJzzq4IWSUUeodK0Cao7k8DQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67b4d1104fa5818eced1b8c5_AD_4nXcVNQj7iJbXBPBBUrGvGmawuaH1cbSx6TOq2UdUqCmAiKTQoNhiCqgJGUktbw8LVWxDAGDlT-YGXJLJiKq7qfDOI0kkoBZhQS2ZjQYAdKO6Ywe2huCJzzq4IWSUUeodK0Cao7k8DQ.webp)

_By normalizing an embedded query like “Who reports to John?”, relevant context can be identified successfully and fed to the LLM, which helps it generate an accurate response_

Unfortunately, embedded iPaaS solutions don’t normalize the data on your behalf.

##### Embedding the integrated data from embedded iPaaS solutions can, as a result, yield inconsistent vectors that lead to incorrect outputs.

And while your team can perform the normalization step for the integrated data, this requires them to define the data model for each integration category and build out and maintain the data transformation logic for normalizing each integrated application’s data—all of which can be incredibly time and resource intensive to perform.

## **Your observability tooling may limit your AI feature’s performance**

Embedded iPaaS solutions fail to provide the integration observability features you need to diagnose, troubleshoot, and resolve integration issues quickly.

This causes integration issues to persist, which prevents fresh data from being embedded and available to the LLM.

The LLM you’re using would then generate low quality outputs, which quickly degrades your UX.

Take [Telescope](https://trytelescope.io/), a sales automation platform, for example.

To consistently recommend high-fit leads for customers, their RAG pipeline needs to constantly collect fresh data on leads from customers’ integrated CRMs.

Otherwise, the LLM they use can disproportionately rely on characteristics that are no longer a strong indicator of a promising lead. For instance, one of Telescope’s customers may have closed many companies in a certain industry several months ago—but those companies are no longer a strong fit for the company.

[![A snapshot of how lead recommendations appear in Telescope](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6615ca99676de98c1f22bce0_tiPrKfUxbkonLl2foIa16Q_JySczqWrKL04yJArcXvAElgkRiv9eIdTryk6BaM6OhmNgV7YGaLt-lkMfIlPXasjTrf1yZIh7jksP502DMuxpvKEvMrbmGpjVAVG5c808Ljsit2-sLIvg4eaNwcEn0hM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6615ca99676de98c1f22bce0_tiPrKfUxbkonLl2foIa16Q_JySczqWrKL04yJArcXvAElgkRiv9eIdTryk6BaM6OhmNgV7YGaLt-lkMfIlPXasjTrf1yZIh7jksP502DMuxpvKEvMrbmGpjVAVG5c808Ljsit2-sLIvg4eaNwcEn0hM.webp)

_Without having up-to-date lead data from customers’ integrated CRMs, Telescope couldn’t recommend best-fit leads_

[Related](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

#### [How to build integrations that power enterprise AI search](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

[![How to build integrations that power enterprise AI search](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

## **Power best-in-class AI features by using Merge**

Merge, the leading unified API solution, addresses all the challenges above by:

- Allowing you to add [hundreds of cross–category integrations](https://www.merge.dev/integrations) to your product through a single build

- Normalizing all the integrated data according to defined [Common Models](https://www.merge.dev/features/common-models) and allowing you to access and sync additional custom data through advanced features, like [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/)

- Fully owning the maintenance of the integrations (through their team of partner engineers)

- Providing robust [Integration Observability features](https://www.merge.dev/features/integration-observability), like fully-searchable logs, automated issue detection, and a comprehensive dashboard overview

[![A screenshot of Merge's Automated Issue Detection functionality](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)

_Merge lets you not only diagnose issues but also uncover specific steps for resolving them_

Learn more about using Merge to support your AI features by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fembedded-ipaas-fails-to-support-ai-features).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb1e10d897b1194792e1de_Anuj%20Jhunjhunwala%20-%20Merge.png)

Anuj Jhunjhunwala

Director of Product Management

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