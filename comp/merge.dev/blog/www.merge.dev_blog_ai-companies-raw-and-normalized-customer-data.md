---
url: "https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data"
title: "Why AI companies need both raw and normalized customer data"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/ai-companies-raw-and-normalized-customer-data#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-companies-raw-and-normalized-customer-data)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**5 challenges of using retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-challenges)

# Why AI companies need both raw and normalized customer data

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67caee40ccdc6ec829d415d3_David%20Dalmaso%20-%20Merge-min.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679bc329176d8ae0120289e6_Group%2037286.webp)

David Dalmaso

Engineer

@Merge

Performing certain transformations on customer data before embedding and adding it to a vector database is essential to powering reliable, personalized, and robust AI capabilities. More specifically, the majority of your customer data needs to be normalized before it’s embedded.

But that might not be the case when critical data is unique to a specific customer.

You can read on to learn more about the role of normalized and raw data for fueling AI products and features.

### **Normalized data helps LLMs generate clean, accurate, and non-sensitive outputs**

Normalization refers to the process of standardizing and transforming data into a consistent format across systems.

[![How data around file created date can be normalized](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed073b506325a7e7809_AD_4nXdzsfgxAmxn6FMMuE5A2_qJR3blk74kgL8SciZBKVP1nBHt9vOwsukTI9GWMLQ0HUX80nYMPbnf5a_LGeOX6y45Ind6BaALlRDpaVv_usFEAEl0wzktV0iVrpwTIbQd5rkPAQVCkA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed073b506325a7e7809_AD_4nXdzsfgxAmxn6FMMuE5A2_qJR3blk74kgL8SciZBKVP1nBHt9vOwsukTI9GWMLQ0HUX80nYMPbnf5a_LGeOX6y45Ind6BaALlRDpaVv_usFEAEl0wzktV0iVrpwTIbQd5rkPAQVCkA.webp)

_Fields related to when a file gets created can be normalized across file storage solutions, or transformed into a common format_

This process offers several advantages during the retrieval portion of a RAG ( [retrieval-augmented generation](https://www.merge.dev/blog/rag-examples)) pipeline.

##### Since normalized data is consistent and doesn’t include extraneous information, an embedding algorithm is more likely to produce semantically-accurate vectors before storing them

This ensures that the most accurate contextual embeddings are retrieved, which in turn allows the LLM to generate more reliable output.

[![How normalized data can improve an LLM's outputs](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3b782630515a644cbe559_RAG.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3b782630515a644cbe559_RAG.webp)

But the value of normalized data doesn’t stop there.

The normalization process can also include removing certain types of sensitive data (e.g., social security numbers). This effectively prevents this data from being returned in your retrieval step.

[![How data related to tax numbers can be removed during the normalization process](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23e9966ead6fcee07e828_AD_4nXcphYE3L-VVwhvxOOfLL_g0XTVZxACR4q7S6knhLYjkAsOBtSKdXx6VKwMvMCG9MgGhziSGcN_L_m-wfK91VCM_HEX_FMHpEIQFpTkCuRGZiVdsTN8IZaRtTkmDcqFxayyFBrsjfw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a23e9966ead6fcee07e828_AD_4nXcphYE3L-VVwhvxOOfLL_g0XTVZxACR4q7S6knhLYjkAsOBtSKdXx6VKwMvMCG9MgGhziSGcN_L_m-wfK91VCM_HEX_FMHpEIQFpTkCuRGZiVdsTN8IZaRtTkmDcqFxayyFBrsjfw.webp)

_The process of normalizing data can include removing certain fields that are sensitive, like organizations’ tax numbers in your customers’ ERP systems_

Finally, part of normalizing data involves removing duplicates automatically. This means that duplicate data won’t go on to get embedded, retrieved, and used by an LLM.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed0ffcb48aaa8b68842_AD_4nXf70o84q68XrpiiNS10iiNm2CTAlKqnbJLXTBQNm8p7E4m1sswSan3S57AYoWj4VfCaSDfbWfYQVc-bslJbpR1MltYmAdsOoOyc-fi5NEQtHpIUDn7w4n_QqIGklrGEYvSEV7MFHg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed0ffcb48aaa8b68842_AD_4nXf70o84q68XrpiiNS10iiNm2CTAlKqnbJLXTBQNm8p7E4m1sswSan3S57AYoWj4VfCaSDfbWfYQVc-bslJbpR1MltYmAdsOoOyc-fi5NEQtHpIUDn7w4n_QqIGklrGEYvSEV7MFHg.webp)

_Normalizing data from customers’ HRISs can include removing duplicate names_

‍

[Related](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

#### [How to build integrations that power enterprise AI search](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

[![How to build integrations that power enterprise AI search](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/ai-enterprise-search?blog-related=image)

‍ **‍**

### **Raw data lets you account for edge cases across your customer base**

Your customers’ applications are often highly customized with unique objects and fields that fit their specific business needs.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3b7ff45c51aae29024a98_Custom%20fields%20(4).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3b7ff45c51aae29024a98_Custom%20fields%20(4).webp)

_Your customers might have custom fields across systems of record that need to be fed to your LLM_

Since this type of data isn’t consistently created and stored across your customers’ systems, it wouldn’t make sense to create strict normalized data models for them.

##### That said, custom data can be an important part of a customer’s use case(s) with your product, making it an essential input for the LLM you use.

For example, say you offer a product intelligence solution that uses an LLM to summarize product feedback based on the transcripts of recorded customer calls. Let’s also assume that a customer has a unique “Customer Health Score” field in their CRM that can—depending on the value—determine how they prioritize product feedback.

By embedding health score data from that customer’s CRM, it can be returned in the retrieval step when the customer uses terminology and data related to a client’s health. Your LLM can then use the additional context to not only summarize customer-specific product feedback but also weigh in on whether and why it should be prioritized.

_Related:_ [_Why your RAG pipelines need normalized data_](https://www.merge.dev/blog/normalized-data-rag)

### **Access normalized and raw data across your integrations with Merge**

Merge, the leading unified API solution, normalizes integrated data using predefined [Common Models](https://www.merge.dev/features/common-models) for the 200+ cross-category integrations it supports.

The platform also lets you access raw data from your customers’ systems through its [Authenticated Passthrough Request feature](https://docs.merge.dev/supplemental-data/passthrough/overview/).

[![Merge Authenticated Passthrough visualization](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed1331df4df7bc9159a_AD_4nXeglOZ7GiiBj0N2sseTxeQuvsSdA81RuDLCAvB2d_RkuUoyGK7SypauakcgLHqopFDUhwRTU-dsvpBJ-MhJL5lEWwRA94-AihC0rDWcA-myALcYUAaKHxQ4LkWSdiF1JbtDDQSHBQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3aed1331df4df7bc9159a_AD_4nXeglOZ7GiiBj0N2sseTxeQuvsSdA81RuDLCAvB2d_RkuUoyGK7SypauakcgLHqopFDUhwRTU-dsvpBJ-MhJL5lEWwRA94-AihC0rDWcA-myALcYUAaKHxQ4LkWSdiF1JbtDDQSHBQ.webp)

_How Merge’s Authenticated Passthrough Request feature works_

Learn how Merge powers cutting-edge AI companies like Guru, Ema, and Telescope, and discover how it can support your organization by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fai-companies-raw-and-normalized-customer-data).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c871b89a-1a42-4105-8172-07bf60c9acd6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=932b64ec-3097-4b73-a4d0-5358943a5b44&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-companies-raw-and-normalized-customer-data&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c871b89a-1a42-4105-8172-07bf60c9acd6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=932b64ec-3097-4b73-a4d0-5358943a5b44&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-companies-raw-and-normalized-customer-data&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=9659105f-e9da-4ac6-9108-074919a80be4&bo=2&sid=ac01f2f03e8c11f099f7fb274c0c961d&vid=ac0307603e8c11f0a8f23f183d73a943&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Why%20AI%20companies%20need%20both%20raw%20and%20normalized%20customer%20data&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fai-companies-raw-and-normalized-customer-data&r=&lt=488&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=313450)