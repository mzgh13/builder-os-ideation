---
url: "https://www.merge.dev/blog/normalized-data-rag"
title: "Why normalized data is critical for best-in-class retrieval-augmented generation (RAG)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/normalized-data-rag#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/normalized-data-rag#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/normalized-data-rag#)

Table of contents

[Generate more accurate outputs](https://www.merge.dev/blog/normalized-data-rag#generate-more-accurate-outputs)

[Prevent sensitive data from being retrieved](https://www.merge.dev/blog/normalized-data-rag#prevent-sensitive-data-from-being-retrieved)

[Avoid duplicate data in outputs](https://www.merge.dev/blog/normalized-data-rag#avoid-duplicate-data-in-outputs)

[Leverage normalized data across your RAG use cases by using Merge](https://www.merge.dev/blog/normalized-data-rag#leverage-normalized-data-across-your-rag-use-cases-by-using-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fnormalized-data-rag)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**3 best practices for using retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-best-practices)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**5 benefits of retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-benefits)

# Why normalized data is critical for best-in-class retrieval-augmented generation (RAG)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67caee40ccdc6ec829d415d3_David%20Dalmaso%20-%20Merge-min.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679bc329176d8ae0120289e6_Group%2037286.webp)

David Dalmaso

Engineer

@Merge

Customer data is essential to supporting most retrieval-augmented generation (RAG) use cases.

It allows SaaS products to power [enterprise AI search](https://www.merge.dev/blog/ai-enterprise-search), provide targeted lead recommendations, surface high-fit candidates, and more.

But customer data, in and of itself, isn’t enough to power your product’s [RAG use case(s)](https://www.merge.dev/blog/rag-examples) effectively. This data also needs to be normalized, or standardized and transformed into a consistent format across multiple systems or platforms.

[![How file creation date fields can be normalized](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23ffb4c071a922fe73187_Group%205.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23ffb4c071a922fe73187_Group%205.webp)

_Fields related to a file's creation date can be normalized across file storage solutions, or transformed into a common format_

You can read on to learn why normalized data is pivotal for RAG.

_Related:_ [_A guide to the Model Context Protocol (MCP)_](https://www.merge.dev/blog/model-context-protocol)

## Generate more accurate outputs

When customer data is normalized, the data is presented in a consistent format and only includes the necessary information. As a result, the embedding algorithm can easily understand the semantic similarities (and differences) between different types of data.

All of the data that’s semantically similar has embeddings (i.e., vectors) that are close to one another in the vector database, while non-normalized data can lead to embeddings that are more spread out in the database.

For example, say all of your employee objects and fields are normalized, including the “Manager” field. Here’s how this normalized data can support the retrieval portion of your RAG pipeline:

1\. A user makes a query in, say, your enterprise AI search, like “Who reports to John?”

2\. The embedding algorithm would then transform the query’s plain text into a vector, or a numerical representation of the text’s meaning.

3\. The embedded query would be compared to embeddings in the vector space, and all of the embeddings that are close to the embedded query (i.e., all of the employees who report to John) would be fetched.

[![An examples of how normalized data is close in proximity in a vector database](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a26674eaf3c01cc80ccb7b_Screenshot%202025-02-04%20at%202.09.03%E2%80%AFPM%201.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a26674eaf3c01cc80ccb7b_Screenshot%202025-02-04%20at%202.09.03%E2%80%AFPM%201.webp)

4\. Both the embeddings that are fetched and the embedded query get fed to the LLM you use.

5\. The LLM can then generate an accurate response.

[Related](https://www.merge.dev/blog/ai-connector?blog-related=image)

#### [AI connectors: use cases, benefits, and features](https://www.merge.dev/blog/ai-connector?blog-related=image)

[![AI connectors: use cases, benefits, and features](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/ai-connector?blog-related=image)

## **Prevent sensitive data from being retrieved**

The process of normalizing data also gives you the opportunity to remove certain types of data. This gives you more control over the information that’s retrieved and used by the LLM.

As a result, you can _avoid scenarios where the LLM would generate outputs with sensitive information_ on your business, employees, candidates, etc.

For example, say you’re normalizing customers’ accounting data and you don’t want the LLM you use to retrieve personally identifiable information (PII).

You can normalize the accounting data such that all PII fields, like tax numbers associated with companies, are removed before the data gets embedded and added to the vector database.

[![How normalization can remove sensitive data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23e9966ead6fcee07e828_AD_4nXcphYE3L-VVwhvxOOfLL_g0XTVZxACR4q7S6knhLYjkAsOBtSKdXx6VKwMvMCG9MgGhziSGcN_L_m-wfK91VCM_HEX_FMHpEIQFpTkCuRGZiVdsTN8IZaRtTkmDcqFxayyFBrsjfw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23e9966ead6fcee07e828_AD_4nXcphYE3L-VVwhvxOOfLL_g0XTVZxACR4q7S6knhLYjkAsOBtSKdXx6VKwMvMCG9MgGhziSGcN_L_m-wfK91VCM_HEX_FMHpEIQFpTkCuRGZiVdsTN8IZaRtTkmDcqFxayyFBrsjfw.webp)

_The process of normalizing data can include removing certain fields that are sensitive, like organizations’ tax numbers in your customers’ ERP systems_

[Related](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data?blog-related=image)

#### [Why AI companies need both raw and normalized customer data](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data?blog-related=image)

[![Why AI companies need both raw and normalized customer data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data?blog-related=image)

## **Avoid duplicate data in outputs**

Similar to the benefit above, the normalization process allows you to deduplicate data.

So, for example, if there are 5 duplicate employee records in a customer’s HRIS, normalizing them could lead 4 to get removed.

[![Screenshot of how data normalization can help deduplicate data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679b9f559625240a8081126d_AD_4nXfHNejse3CGPkBmHM_WZLIkJnf0WHs2ljPwl2MjllxvFeHPg8FyovIGmCYd6cPYXL1xKHxBs0CVNZnLW7-myZTjp7mcAJuL3RD8LwnlWGPAr1h_Lhu-bd9OJ3tjHyfAzvOf8EKofQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679b9f559625240a8081126d_AD_4nXfHNejse3CGPkBmHM_WZLIkJnf0WHs2ljPwl2MjllxvFeHPg8FyovIGmCYd6cPYXL1xKHxBs0CVNZnLW7-myZTjp7mcAJuL3RD8LwnlWGPAr1h_Lhu-bd9OJ3tjHyfAzvOf8EKofQ.webp)

‍

This allows the LLM to retrieve just a single copy of the record and, in turn, only generate a single copy in its outputs.

[Related](https://www.merge.dev/blog/rag-benefits?blog-related=image)

#### [5 benefits of retrieval-augmented generation (RAG)](https://www.merge.dev/blog/rag-benefits?blog-related=image)

[![5 benefits of retrieval-augmented generation (RAG)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/rag-benefits?blog-related=image)

## **Leverage normalized data across your RAG use cases by using Merge**

Merge, the leading unified API solution, lets you add hundreds of integrations through a single build.

Merge also normalizes the data that’s synced from all these integrations according to its Common Models, or predefined data models. This allows you to access normalized data from all of your customers’ ticketing systems, HRISs, ATSs, CRMs, file storage solutions, and accounting systems.

[![An image that shows how Merge normalizes specific ticketing data](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679b9f564d99ae0b82b363c8_AD_4nXcb7T3ickQaxSj6EybB0TFJcz0dfh-rj4zB00S3RRBL1_9TJh8a8xaV3giktZzG31mhtFEkp8PP2VhJAVaexbj50eYxZi-qNYBTq9ZqJeiWet-HZ3erU3yIS6KWn16tjnxGK_Jwsw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679b9f564d99ae0b82b363c8_AD_4nXcb7T3ickQaxSj6EybB0TFJcz0dfh-rj4zB00S3RRBL1_9TJh8a8xaV3giktZzG31mhtFEkp8PP2VhJAVaexbj50eYxZi-qNYBTq9ZqJeiWet-HZ3erU3yIS6KWn16tjnxGK_Jwsw.webp)

_How Merge normalizes the ticket type object and completed status field across your customers’ ticketing systems_

Merge also has advanced features to give you full control over the customer data you can and can’t sync and normalize, such as [Scopes](https://help.merge.dev/en/articles/5950052-what-are-common-model-scopes).

Learn more about how Merge can normalize your data and discover how companies use Merge to power their RAG use cases by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fnormalized-data-rag).

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

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67caee40ccdc6ec829d415d3_David%20Dalmaso%20-%20Merge-min.png)

David Dalmaso

Engineer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=72ed92d7-efd4-4a83-94b4-889b6e832b54&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0e9b8316-2fdc-4de7-aaa8-834ccab3efd0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalized-data-rag&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=72ed92d7-efd4-4a83-94b4-889b6e832b54&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0e9b8316-2fdc-4de7-aaa8-834ccab3efd0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalized-data-rag&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=94d619d8-4e91-408c-b468-b6780eb2651c&bo=2&sid=396fe7603e8d11f0939301459452149e&vid=396fe4303e8d11f0bd3cbfca71e8565b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Why%20normalized%20data%20is%20critical%20for%20best-in-class%20retrieval-augmented%20generation%20(RAG)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnormalized-data-rag&r=&lt=408&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=686890)