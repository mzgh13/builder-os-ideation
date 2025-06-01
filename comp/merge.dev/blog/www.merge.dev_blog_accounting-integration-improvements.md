---
url: "https://www.merge.dev/blog/accounting-integration-improvements"
title: "6 ways we’ve elevated our accounting integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/accounting-integration-improvements#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/accounting-integration-improvements#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/accounting-integration-improvements#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-integration-improvements)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7aa6e16bf864755f32e_Financial_statements_API.webp)**How to use financial statement APIs successfully**](https://www.merge.dev/blog/financial-statement-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Accounting integrations: examples, benefits, and tools**](https://www.merge.dev/blog/accounting-integration)

# 6 ways we’ve elevated our accounting integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26ba0966dc16ec12d14a_Irene%20Hu%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f082f3162f9f1c94ba54a_irene-hu_min.webp)

Irene Hu

Marketing

@Merge

Our team has been hard at work rolling out new features, capabilities, and general improvements for [our Accounting Unified API](https://www.merge.dev/categories/accounting-api).

With a focus on enhancing critical accounting use cases and expanding our capabilities, we’re excited to introduce six powerful new features.

Read on to discover what’s new and how you can start using each feature.

### **Leverage Idempotency when writing large amounts of accounting data**

We now support [idempotency](https://docs.merge.dev/basics/idempotency/) for all POST accounting endpoints to prevent duplicate entries (and all the unnecessary headaches they create).

We recommend using idempotency for bigger tasks—like writing transaction or journal entry data—to prevent duplicate entries.

To perform an idempotent request, simply include an idempotency key in each POST request.

Note: Idempotency is available to all customers and is currently available in beta. **‍**

### **Use Selective Sync to optimize sync times when pulling invoices and/or payments**

For many of our customers, accessing accounts receivable (AR) and accounts payable (AP) data in one model is beneficial, as it reduces the number of API calls they need to make.

However, this approach isn’t useful for customers who only need data from either AR or AP, as it can lead to longer sync times and unnecessary data being pulled.

To address this, we've introduced a [new selective sync filter](https://help.merge.dev/en/articles/9113654-selective-sync).  It lets you pick and choose the AR and/or AP transactions you want to sync in a matter of clicks within the Merge Dashboard.

[![Selective Sync UI](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67857271693d8db0105be784_AD_4nXdz9-NYIjcYeTpcLE1Q9FclTj5ndtu_kyz96JEXDFooB54D1jA6WFpYzm8_w2AiAaIQkwhw63TZL91Q9IDfj2gvqfeprCsciYVSakaPpNwa_wA94Crlc_onO29RJyFNAoIztRDP.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67857271693d8db0105be784_AD_4nXdz9-NYIjcYeTpcLE1Q9FclTj5ndtu_kyz96JEXDFooB54D1jA6WFpYzm8_w2AiAaIQkwhw63TZL91Q9IDfj2gvqfeprCsciYVSakaPpNwa_wA94Crlc_onO29RJyFNAoIztRDP.webp)

_You can use Select Sync to only access payment and invoice data for accounts payable_

### **Sync general ledger transactions with your product exponentially faster**

Our teams aren’t just focused on introducing new capabilities; we’re also committed to continuously improving existing ones.

The [General Ledger Transactions](https://docs.merge.dev/accounting/general-ledger-transactions/) endpoint enables FP&A teams to pull all transactions posted to your customers’ general ledger through a single endpoint.

But given the sheer volume of transaction data in your customers’ general ledgers (think millions of rows of data!), it can be difficult to continuously fetch it quickly.

Despite this challenge, we’ve improved the sync speeds for the endpoints across our accounting integrations. For example, the sync speed for QuickBooks Online has improved by **50x,** while our NetSuite integration can now sync general transactions as much as **20x faster**.

[Related](https://www.merge.dev/blog/netsuite-api?blog-related=image)

#### [How to integrate with NetSuite's API in 2025](https://www.merge.dev/blog/netsuite-api?blog-related=image)

[![How to integrate with NetSuite's API in 2025](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)](https://www.merge.dev/blog/netsuite-api?blog-related=image)

### **Use Remote Fields to access any custom data**

[Remote fields](https://docs.merge.dev/supplemental-data/remote-fields/overview/) let you read and write non-mapped fields to your customers' accounting platform. This feature is already supported for select ticketing and CRM integrations, and we’ve now expanded support to include NetSuite and Sage Intacct across key Common Models, including Journal Entry, Invoice, Payment, Contact, and more.

Some examples of how to use Remote Fields are:

- Creating invoices with custom fields defined in your customers’ Netsuite instance
- Creating a contact with additional information outside of our common model
- Train your models with additional data to power more robust and personalized AI features

### **Apply vendor credits and/or credit notes with ease**

We’ve expanded our AR and AP use case functionality by supporting [POST/ vendor credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_create) and [credit notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_create) for NetSuite, Sage Intacct, Xero, and QuickBooks Online. These credits, often issued for returns, overpayments, or discounts, can now be linked directly to invoices. This streamlines your invoicing workflows and processes and improves tracking and reporting.

[![Code snippet for an invoice's credit note](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67857272f9eda8a2d413e65d_AD_4nXdmXS_cJ_aCEuBEoDQGLqFyzkexsP-8x_FwPHlRJEGq7DfDfpZ0yBlsNEqxp2H5T7zJhF8T4LXDbQS_pve2TVHm8eL5Y0ROxIs-dKiwPgLWapmV9SwUIaMyFZydvrBUc_MaC-EZsA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67857272f9eda8a2d413e65d_AD_4nXdmXS_cJ_aCEuBEoDQGLqFyzkexsP-8x_FwPHlRJEGq7DfDfpZ0yBlsNEqxp2H5T7zJhF8T4LXDbQS_pve2TVHm8eL5Y0ROxIs-dKiwPgLWapmV9SwUIaMyFZydvrBUc_MaC-EZsA.webp)

_New sub-model that associates the invoice a credit note was applied to_

With this data, you can capture specific details like the credit amount, date, and the invoices the credit is applied to.

[![Bill credit in NetSuite](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6785727220693d111051b328_AD_4nXfN3g-x29FSvNaron835BD8a1aO_12JexjSkWr29wIxZH1SrbA5uLo3UrEAY4LL4LyiTuFRg2H3MTlV3ghoGFVJqUu1okHLz6K1IzNAcQcji1PvK6Ej8ybvfi94Jr1MCyAcZdFOjg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6785727220693d111051b328_AD_4nXfN3g-x29FSvNaron835BD8a1aO_12JexjSkWr29wIxZH1SrbA5uLo3UrEAY4LL4LyiTuFRg2H3MTlV3ghoGFVJqUu1okHLz6K1IzNAcQcji1PvK6Ej8ybvfi94Jr1MCyAcZdFOjg.webp)

_Example of a bill credit in NetSuite_

### **Reconcile transactions more smoothly with bank feeds**

Last but not least, we’ve added two new common models to support Bank Feeds functionality: [Bank Feed Accounts](https://docs.merge.dev/accounting/bank-feed-accounts/) and [Bank Feed Transactions](https://docs.merge.dev/accounting/bank-feed-transactions/).

Using these endpoints, your customers can _automatically_ sync the transactions from your banking product with customers’ ERP systems. This helps account for the latest transactions more easily, and it both improves the customer experience and reduces human errors—as your customers no longer have to manually add the transaction data or use CSV uploads.

Common [use cases for Bank Feeds](https://www.merge.dev/blog/bank-feed-api) include:

- Allowing your customer to reconcile card transactions in their ERP
- Enabling your banking product(s) to send cash information to your customer's ERP for regular reconciliation
- Creating records bills and payments for your customers in their ERP based off invoices and facilitate payments with their bank

We currently support Bank Feeds for NetSuite and Xero and will continue to roll this out for additional integrations.

Note: Bank Feeds is currently in beta for NetSuite and Xero. You can reach out to your dedicated customer success manager if you’d like to get early access.

[Related](https://www.merge.dev/blog/xero-api?blog-related=image)

#### [Xero API integration: everything you need to know](https://www.merge.dev/blog/xero-api?blog-related=image)

[![Xero API integration: everything you need to know](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c709309b17fd57b0d4f_Xero_Guide_%252525281%25252529.webp)](https://www.merge.dev/blog/xero-api?blog-related=image)

### **Final thoughts**

We’re thrilled to bring these powerful new features to our Accounting Unified API.

Whether you're optimizing sync times, improving the accuracy of your financial data, or unlocking new functionality, these features offer the flexibility and performance your accounting integrations need.

#### Ready to scale your customer-facing accounting integrations?

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-integration-improvements)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26ba0966dc16ec12d14a_Irene%20Hu%20-%20Merge.png)

Irene Hu

Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=20825539-00ea-413a-9943-fabb97fbb4a6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=fcd833cd-b030-4d2e-bed8-03d8db33149e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-integration-improvements&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=20825539-00ea-413a-9943-fabb97fbb4a6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=fcd833cd-b030-4d2e-bed8-03d8db33149e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-integration-improvements&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=b5385a39-ea63-423c-af2e-e7e873fe4ab4&bo=2&sid=5a5baa703e8d11f096678dfb5a5d550d&vid=5a5baa903e8d11f0a8006b777505be01&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=6%20ways%20we%E2%80%99ve%20elevated%20our%20accounting%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-integration-improvements&r=&lt=449&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=851544)