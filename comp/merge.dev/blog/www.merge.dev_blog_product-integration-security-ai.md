---
url: "https://www.merge.dev/blog/product-integration-security-ai"
title: "How AI companies can provide enterprise-grade secure product integrations successfully"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/product-integration-security-ai#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/product-integration-security-ai#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/product-integration-security-ai#)

Table of contents

[Prevent outputs that include sensitive data](https://www.merge.dev/blog/product-integration-security-ai#prevent-outputs-that-include-sensitive-data)

[Provide controls on who can access certain types of data](https://www.merge.dev/blog/product-integration-security-ai#provide-controls-on-who-can-access-certain-types-of-data)

[Perform frequent syncs to avoid unauthorized data access](https://www.merge.dev/blog/product-integration-security-ai#perform-frequent-syncs-to-avoid-unauthorized-data-access)

[Build and sustain customer trust](https://www.merge.dev/blog/product-integration-security-ai#build-and-sustain-customer-trust)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fproduct-integration-security-ai)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**3 RAG use cases—plus tips for implementing them**](https://www.merge.dev/blog/rag-use-cases)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**Why AI companies need both raw and normalized customer data**](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data)

# How AI companies can provide enterprise-grade secure product integrations successfully

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

We’ve seen firsthand how customer data can help companies power creative and powerful AI features in their products—from identifying and recommending high-fit sales leads to generating customizable financial models.

But accessing and using customer data securely—via product integrations—to power these features can prove difficult.

You can read on to learn how you can support highly-secure product integrations across your customer base.

## **Prevent outputs that include sensitive data**

A lot of the customer data that’s synced can include personally identifiable information (PII), like social security numbers.

Without the proper precautions in place, you can unintentionally feed these types of data to the large language model (LLM) you use, leading it to generate outputs that include this information.

For example, if you offer an [enterprise AI search solution](https://www.merge.dev/blog/ai-enterprise-search) and a user asks something like “What’s my colleague Mike’s social security number?”, the LLM can generate an output that includes the number.

[![RAG example for generating Mike's social security number](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9b93ae26a7ab9ddf902_AD_4nXf_fq3kweoQMPUjyCynJBvzpSRNMtLTXKC5TaEr31X3bi81mHD1zsj6XbjW1lIV7LapnMklKClgeIWNsZhRYmCQ1EVSTyBL6xlqAZZa4x7ED-ckkslApIDr0nLSPzSRMZHUyKtDfQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9b93ae26a7ab9ddf902_AD_4nXf_fq3kweoQMPUjyCynJBvzpSRNMtLTXKC5TaEr31X3bi81mHD1zsj6XbjW1lIV7LapnMklKClgeIWNsZhRYmCQ1EVSTyBL6xlqAZZa4x7ED-ckkslApIDr0nLSPzSRMZHUyKtDfQ.webp)

To address this proactively, you can provide scopes—or the ability for either you or your customers to toggle off the specific fields that customers don’t want you to access and sync.

[![How Merge's Common Model Scopes work](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc091e660e3d95688bf8dd_62ed6c4a26ad07d17bb1d94d_Scopes_GIF.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc091e660e3d95688bf8dd_62ed6c4a26ad07d17bb1d94d_Scopes_GIF.gif)

[_Merge’s Common Model Scopes_](https://help.merge.dev/en/articles/5950052-what-are-common-model-scopes) _let you control the customer data that gets synced_

[Related](https://www.merge.dev/blog/ai-connector?blog-related=image)

#### [AI connectors: use cases, benefits, and features](https://www.merge.dev/blog/ai-connector?blog-related=image)

[![AI connectors: use cases, benefits, and features](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/ai-connector?blog-related=image)

## **Provide controls on who can access certain types of data**

In cases where you need your AI feature to generate outputs with sensitive information but you only want that information to be available to certain individuals, you can bake access control lists (ACLs) into your product integrations.

For example, say you have documents related to your company’s financials that you only want executives and members of your finance team to access and work off of.

Using ACLs, the integrations will only feed the data from these documents to the LLM _when_ the user who’s trying to access it in your product has the right set of permissions.

We’ve seen first hand how powerful this security feature can be.

[Ema](https://www.ema.co/), which offers agents that can complete a wide range of tasks on behalf of employees, uses ACLs for the file storage integrations they offer through Merge. Their Head of Operations and Strategy [recently told us](https://www.merge.dev/case-studies/ema) how it’s helped them and their customers:

“Our AI agents only show information to a user based on the documents that user has access to. _This helps us keep our customers’ sensitive information secure over time.”_

‍‍‍‍

_Related:_ [_Best practices for building AI chatbots_](https://www.merge.dev/blog/how-to-build-ai-chatbot)

## **Perform frequent syncs to avoid unauthorized data access**

As your team changes permissions on files, reports, dashboards and more over time, they’ll need to ensure that those changes are enforced effectively over time.

To help facilitate this, you can set your integrations to make frequent GET requests (e.g., daily re-syncs).

The re-synced data will only get shown to employees who actively meet the relevant permission levels in the integrated system; while the employees who no longer meet these permissions won’t have access to the data.

[![Syncing frequency for Merge's integration with Google Drive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9bab7708fee608a9ba8_AD_4nXcDEjSGayTPbljDRz3L49Mmn8lyaKGRPhLANnE3le8fjj9jXT-EEIMx13yu9_REq4OApLmmdNgjri1GLLwm14C2Ke715OcZPH3wpQ47CGqL5V5LnxeNOrcSRnFpeycIjezrNGFp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9bab7708fee608a9ba8_AD_4nXcDEjSGayTPbljDRz3L49Mmn8lyaKGRPhLANnE3le8fjj9jXT-EEIMx13yu9_REq4OApLmmdNgjri1GLLwm14C2Ke715OcZPH3wpQ47CGqL5V5LnxeNOrcSRnFpeycIjezrNGFp.webp)

_Merge’s Permission Common Model for file storage integrations—like Google Drive—can re-sync daily. This allows your users to not only access up-to-date documents but also avoid unauthorized access_

_Related:_ [_A guide to coming up with AI product ideas_](https://www.merge.dev/blog/ai-product-ideas)

## **Build and sustain customer trust**

Your customers may not be fully comfortable with providing sensitive data to whatever LLM you use until they learn about and approve of the level of security provided by the underlying integrations.

To that end, being able to offer product integrations that comply with key data privacy and protection laws and regulations, like GDPR, offer strong encryption protocols (e.g., encrypting data at rest and in transit), store data in secured data centers, and more can go a long way in meeting customers’ expectations.

[![A look at the security measures Merge takes](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9bade605250cb1b9b41_AD_4nXeCVSaxmS9ggrD6wHzo5A6RwKDOefMHnezfLi7f-79FaPCUqguJAB4gIzeAx5W9i1rHyaAzIYNs3C7iXRv7Ak1uNddgDe7yOuKllr_lHNlX4QAuBVBqOqZvAwc_o1ljCUNuWrUXcA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c5e9bade605250cb1b9b41_AD_4nXeCVSaxmS9ggrD6wHzo5A6RwKDOefMHnezfLi7f-79FaPCUqguJAB4gIzeAx5W9i1rHyaAzIYNs3C7iXRv7Ak1uNddgDe7yOuKllr_lHNlX4QAuBVBqOqZvAwc_o1ljCUNuWrUXcA.webp)

_Merge outlines the various security measures it’s put into place on its_ [_security page_](https://www.merge.dev/security) _—giving you and your customers full visibility on how we’ve approached building secure integrations_

#### Ready to add enterprise-grade secure integrations to your product?

Learn how Merge can help you add hundreds of integrations across key software categories in a matter of weeks.

[Schedule a demo](https://www.merge.dev/get-in-touch-v2?utm_btn=dr-page-blog%2Fproduct-integration-security-ai)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=943ef705-ddcf-43e5-a23b-e92a1ef954cc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e1d7cd3e-c04e-4ebd-acfe-90eaede7b496&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-integration-security-ai&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=943ef705-ddcf-43e5-a23b-e92a1ef954cc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e1d7cd3e-c04e-4ebd-acfe-90eaede7b496&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-integration-security-ai&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e242b40b-9f6f-4e27-a70f-0d9168eb2f84&bo=2&sid=45d4ee203e8c11f0a8cd27c0188b1474&vid=45d548503e8c11f089699db5cd1fd4e3&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20AI%20companies%20can%20provide%20enterprise-grade%20secure%20product%20integrations%20successfully&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fproduct-integration-security-ai&r=&lt=590&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=770147)