---
url: "https://www.merge.dev/blog/finserv-challenges-erp-integrations"
title: "3 challenges that FinServ companies face in building and maintaining customer-facing ERP integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/finserv-challenges-erp-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/finserv-challenges-erp-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/finserv-challenges-erp-integrations#)

Table of contents

[Accessing ERP providers’ bank feed endpoints](https://www.merge.dev/blog/finserv-challenges-erp-integrations#accessing-erp-providers-bank-feed-endpoints)

[Accounting for providers’ unique build requirements](https://www.merge.dev/blog/finserv-challenges-erp-integrations#accounting-for-providers-unique-build-requirements)

[Handling different data models](https://www.merge.dev/blog/finserv-challenges-erp-integrations#handling-different-data-models)

[Add accounting integrations that let you POST to customers’ ERP systems with ease via Merge](https://www.merge.dev/blog/finserv-challenges-erp-integrations#add-accounting-integrations-that-let-you-post-to-customers-erp-systems-with-ease-via-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffinserv-challenges-erp-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How to integrate with NetSuite's API in 2025**](https://www.merge.dev/blog/netsuite-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Accounting integrations: examples, benefits, and tools**](https://www.merge.dev/blog/accounting-integration)

# 3 challenges that FinServ companies face in building and maintaining customer-facing ERP integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Most financial services (FinServ) companies need to support customer-facing accounting integrations to grow over time.

Case in point: We surveyed 260 leaders at FinServ companies with at least 100 employees through [Centiment](https://www.centiment.co/), a leading market research platform, and learned that most FinServ companies can close more sales, retain customers, expand to new markets, and more by offering customer-facing ERP integrations.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67900c8e220c5ac0b47b59e9_AD_4nXe399KSp67h_va5RQfWp429fMKhvqGJmcOuZGg1feGs5Z_CH8XLjYfzW_Xt5JXN8ugpidqGp0mgmdZzxeHRmQiY6E12LQQOuXjqqefjtsKVpwW1hlHgFQAj1_MF48n1RajvXGOskg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67900c8e220c5ac0b47b59e9_AD_4nXe399KSp67h_va5RQfWp429fMKhvqGJmcOuZGg1feGs5Z_CH8XLjYfzW_Xt5JXN8ugpidqGp0mgmdZzxeHRmQiY6E12LQQOuXjqqefjtsKVpwW1hlHgFQAj1_MF48n1RajvXGOskg.webp)

Unfortunately, the process of building and maintaining ERP integrations is far from easy. Each requires significant developer resources at every phase, including ongoing maintenance.

To help streamline your team’s process of building and maintaining every accounting integration, we’ll break down the challenges associated with the API request your FinServ company likely needs to make—POSTing bank feeds to customers’ ERP solutions—and how Merge can address them.

## **Accessing ERP providers’ bank feed endpoints**

Widely-used ERP solutions, like Xero and Quickbooks Online, typically restrict access to their bank feed functionality to partners.

The process of securing a partnership with one of these providers can be time intensive (it can take months, if not years) and expensive (it can cost tens of thousands of dollars per year). Also, some FinServ companies may not even qualify to be a partner, preventing them from accessing the ERP vendors’ bank feed endpoints altogether.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679011ec3262309c9c1b1983_679011d32122e9ffe974f56e_Screenshot%25202025-01-21%2520at%25204.29.06%25E2%2580%25AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679011ec3262309c9c1b1983_679011d32122e9ffe974f56e_Screenshot%25202025-01-21%2520at%25204.29.06%25E2%2580%25AFPM.webp)

[_Xero_](https://developer.xero.com/documentation/xero-app-store/app-partner-guides/app-partner-steps/) _requires many types of FinServ companies to get prior approval before beginning the application process_

[Related](https://www.merge.dev/blog/tax-rate-api?blog-related=image)

#### [Tax rate API: what to know about using the endpoint](https://www.merge.dev/blog/tax-rate-api?blog-related=image)

[![Tax rate API: what to know about using the endpoint](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7aa9ea70cac8836b743_Tax_rate_api.webp)](https://www.merge.dev/blog/tax-rate-api?blog-related=image)

## **Accounting for providers’ unique build requirements**

Each platform has a fundamentally different way of building into their bank feed APIs. For example, while Xero has a relatively straightforward REST API, NetSuite’s requires a custom SuiteApp build to enable bank feed functionality.

[![Banking SuiteApps screenshot](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67900e4b98cb4d55c4a6313d_67900e06f3bcdefbd2a48ee3_Screenshot%25202025-01-21%2520at%25204.13.09%25E2%2580%25AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67900e4b98cb4d55c4a6313d_67900e06f3bcdefbd2a48ee3_Screenshot%25202025-01-21%2520at%25204.13.09%25E2%2580%25AFPM.webp)

_To build to_ [_NetSuite’s bank feeds endpoint_](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/chapter_N3409913.html#subsect_158563698539) _, you’ll need to install their SuiteApp Marketplace and use their “Bank Feeds” SuiteApp_

Given the differences across providers, your engineers will have to take the same steps for each integration they need to add—from scoping the requirements to constructing the build to thoroughly testing the connection. This takes your engineers away from the core development initiatives they’re uniquely equipped to tackle, which can degrade your product over time.

## **Handling different data models**

Each platform uses a different data model for its bank feeds functionality, and bridging these differences when you’re trying to build bank feeds functionality across providers can prove difficult.

For example, Sage Intacct uses the following data model:

```python

{
  "BANKACCTTXNFEED": {
    "FINANCIALENTITY": "BOV",
    "FEEDDATE": "2020-05-15",
    "FEEDTYPE": "xml",
    "BANKACCTTXNRECORDS": [\
      {\
        "POSTINGDATE": "2020-04-09",\
        "TRANSACTIONTYPE": "withdrawal",\
        "DOCTYPE": "Check",\
        "DOCNO": "198",\
        "AMOUNT": -184.00,\
        "DESCRIPTION": "Office supplies"\
      },\
      {\
        "POSTINGDATE": "2020-04-09",\
        "TRANSACTIONTYPE": "withdrawal",\
        "DOCTYPE": "Check",\
        "DOCNO": "222",\
        "AMOUNT": -211.14,\
        "DESCRIPTION": "Computer service call"\
      },\
      {\
        "POSTINGDATE": "2020-04-17",\
        "TRANSACTIONTYPE": "deposit",\
        "DOCTYPE": "Check",\
        "DOCNO": "220",\
        "AMOUNT": 2000.00,\
        "DESCRIPTION": "From account CH to account BOV"\
      }\
    ]
  }
}

```

Xero, on the other hand, requires you to format bank transactions in a REST format:

```python

{
  "pagination": {
    "page": 1,
    "pageCount": 1,
    "pageSize": 50,
    "itemCount": 3
  },
  "items": [\
    {\
      "id": "ba4f3127-5e46-427d-80ea-dea2fcd26afe",\
      "feedConnectionId": "87cb0dc8-fa32-409c-b622-19f8de8dcc83",\
      "status": "PENDING",\
      "startDate": "2018-07-27",\
      "endDate": "2018-07-27",\
      "startBalance": {\
        "amount": "9.0000",\
        "creditDebitIndicator": "DEBIT"\
      },\
      "endBalance": {\
        "amount": "10.1340",\
        "creditDebitIndicator": "DEBIT"\
      },\
      "statementLineCount": "1"\
    },\
    {\
      "id": "6f04e5be-dc4c-46e7-be93-560e306d613e",\
      "feedConnectionId": "c2abe0f1-179c-456e-aae0-cdc49ecc936a",\
      "status": "REJECTED",\
      "startDate": "2018-07-28",\
      "endDate": "2018-07-27",\
      "startBalance": {\
        "amount": "13.00",\
        "creditDebitIndicator": "CREDIT"\
      },\
      "endBalance": {\
        "amount": "15.50",\
        "creditDebitIndicator": "CREDIT"\
      },\
      "statementLineCount": "1",\
      "errors": [\
        {\
          "type": "invalid-start-and-end-date",\
          "title": "Invalid Start and End Date",\
          "status": 422,\
          "detail": "The end date 2018-07-28 must be later than the start date 2018-07-27."\
        }\
      ]\
    }\
  ]
}

```

[Related](https://www.merge.dev/blog/quickbooks-api?blog-related=image)

#### [QuickBooks Online API integration: what you should know](https://www.merge.dev/blog/quickbooks-api?blog-related=image)

[![QuickBooks Online API integration: what you should know](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c729066afe2f4a608b6_Quickbooks_Guide_%252525282%25252529.webp)](https://www.merge.dev/blog/quickbooks-api?blog-related=image)

## **Add accounting integrations that let you POST to customers’ ERP systems with ease via Merge**

Merge, the leading unified API platform, neatly addresses the challenges above by:

- **Enabling you to avoid costly partnerships:** By building to Merge, you don’t need to form partnerships with enterprise ERPs, like NetSuite

- **Helping you access bank feed endpoints at scale, quickly:** You only have to build to [Merge’s Accounting Unified API](https://www.merge.dev/categories/accounting-api) to access bank feed endpoints across ERP solutions

- **Offering multiple unified data models:** You can access two unified data models— [bank feed accounts](https://docs.merge.dev/accounting/bank-feed-accounts/) and [bank feed transactions](https://docs.merge.dev/accounting/bank-feed-transactions/)

Learn more about Merge’s Bank Feeds Common Models and how you can use them by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffinserv-challenges-erp-integrations).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8ab2788a-c300-40c0-ad13-0dad6e859d11&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=370cc090-51d0-4103-a98c-8ab161ddba5a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffinserv-challenges-erp-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8ab2788a-c300-40c0-ad13-0dad6e859d11&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=370cc090-51d0-4103-a98c-8ab161ddba5a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffinserv-challenges-erp-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=54db591e-6b95-4d0c-aa3c-3b7dc86077bd&bo=2&sid=f72dd1803e8c11f0b9dd9b71a0803b39&vid=f72e8c503e8c11f0838ad52618898bb0&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=3%20challenges%20that%20FinServ%20companies%20face%20in%20building%20and%20maintaining%20customer-facing%20ERP%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffinserv-challenges-erp-integrations&r=&lt=977&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=84492)