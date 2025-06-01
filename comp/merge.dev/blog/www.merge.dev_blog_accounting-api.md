---
url: "https://www.merge.dev/blog/accounting-api"
title: "7 accounting APIs to integrate with in 2025"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/accounting-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/accounting-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/accounting-api#)

Table of contents

[Top accounting API platforms](https://www.merge.dev/blog/accounting-api#top-accounting-api-platforms)

[Integrate with accounting APIs at scale through Merge](https://www.merge.dev/blog/accounting-api#integrate-with-accounting-apis-at-scale-through-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Financial API integration: what it is, examples, and tips**](https://www.merge.dev/blog/financial-api-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is an invoicing API? Here’s what you need to know**](https://www.merge.dev/blog/invoicing-api)

# 7 accounting APIs to integrate with in 2025

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

Integrating with clients' accounting APIs can make your product more valuable in a variety of ways, whether that's improving your platform's analytics, keeping your customer or supplier data up-to-date, creating invoices automatically, and so on.

Since accounting APIs are different in various ways, however, integrating with each system presents unique challenges.

We'll help you discern the key differences across popular accounting systems so that you can build to each more easily.

## **Top accounting API platforms**

**‍** As we cover each accounting solution, we’ll highlight key information about each platform and their API:

- **Market share:** How much of the market the platform currently "owns"
- **API type:** Whether the API is in SOAP or REST
- **Documentation:** A link to the platform’s documentation
- **Sandbox availability:** Whether the platform offers a sandbox to test the integration ahead of time
- **Rate limit:** The general [rate limit for the API](https://www.merge.dev/blog/how-to-stop-being-rate-limited-best-practices-for-making-api-calls-at-scale).
- **Pagination:** The method an [API uses for returning data](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations)
- **Authentication:** Whether it's OAuth or Basic Authentication
- **Key data models:** The popular data objects each API can access

_Related:_ [_Common financial statement API use cases_](https://www.merge.dev/blog/financial-statement-api)

### **QuickBooks Online (QBO)**

QuickBooks, first introduced in 1992 as a DOS package for Mac and PC, predates many of its ERP counterparts.

Unlike a traditional ERP system, it focuses on ease of use for individuals with little-to-no formal accounting training at small and medium businesses.

- QuickBooks Market Share is a whopping [85%](https://6sense.com/tech/small-business-accounting/quickbooks-market-share) in the small business accounting category
- They offer a REST API that leverages OAuth 1.0, which you can learn more about in [their API docs](https://developer.intuit.com/app/developer/qbo/docs/develop)
- Sandboxes [are available](https://developer.intuit.com/app/developer/qbo/docs/develop/sandboxes) for free
- Their rate limit is set at 500 requests per minute, per realm ID
- Their API uses a form of offset pagination, which involves specifying a starting point (the offset) and the number of records to retrieve (the limit). For example, offset=10&limit=10 would skip the first 10 records and return the next 10
- They provide SDKS in nodeJS, Ruby, and Python languages; you can learn more about them [here](https://developer.intuit.com/app/developer/qbo/docs/develop/sdks-and-samples)
- Useful data models include purchase orders, accounts, and cash flows

_Related:_ [_Everything you need to know to integrate with QuickBook Online_](https://www.merge.dev/blog/quickbooks-api)

### **Xero**

Founded in New Zealand in 2006, Xero is [a newer entrant in the established accounting software market](https://www.businessinsider.com/the-untold-story-how-xero-took-a-band-name-and-changed-accounting-for-a-million-companies-2017-9). Similar to QuickBooks, it targets the small business accounting sector and has gained significant popularity globally, especially in the APAC region.

- Their Market share is [6.85%](https://6sense.com/tech/financial-reporting/xero-market-share) (in the financial reporting category), and they primarily serve SMBs
- They utilize a REST API with OAuth 2.0 Authentication; you can learn more about their API by visiting [their docs](https://developer.xero.com/documentation/api/accounting/overview)
- Their sandbox is free to use if you have an account
- [Their rate limits](https://developer.xero.com/documentation/guides/oauth2/limits/) work as follows: their concurrent limit is 5 calls in progress at one time; their limit by minute is 60 calls; and their daily limit is 5000 calls
- They use page-based/numbers-based pagination. You can [see their query parameter docs](https://developer.intuit.com/app/developer/qbo/docs/learn/explore-the-quickbooks-online-api/data-queries) for more information
- They provide SDKS in C#, Java, and Node languages; you can learn more about them [here](https://developer.xero.com/documentation/sdks-and-tools/libraries/overview/) ‍
- Popular data models include invoices, bank transactions, purchase orders, and journals

### **Freshbooks**

Founded in Toronto, Canada, in 2003, FreshBooks emerged as a SaaS software targeting small and medium businesses after the dot-com boom. Initially bootstrapped through its first four years, the company is now recognized for its simplicity and user experience, making it ideal for freelancers, solopreneurs, and small companies.

- They have a Market Share of [0.27%](https://6sense.com/tech/financial-reporting/freshbooks-market-share) (in the financial reporting category), and they primarily serve SMBs
- Like other SMB software covered, their API is REST-based with OAuth 2.0. You can learn more about both of these items [here](https://www.freshbooks.com/api/start) ‍
- There's no set limit on requests to Freshbooks, however [they may enforce them if there are too many requests in a given period of time](https://www.freshbooks.com/api/limits)
- They use page-based and limit-based pagination. The latter lets you set the number of rows that are returned via an API. You can [learn more about both of these methods in their docs](https://www.freshbooks.com/api/parameters) ‍
- Their popular data models include bill vendors, bills, credit notes

### **Microsoft Dynamics 365**

Microsoft Dynamics 365, a cloud ERP solution from Microsoft, has the longest history among current ERP platforms. Today, Dynamics 365 ERP is utilized by major [automotive companies, financial institutions, and government offices](https://dynamics.microsoft.com/en-us/customer-stories/).

- Dynamics 365 has an outsized Market Share of [26.54%](https://6sense.com/tech/erp/microsoft-dynamics-market-share) (in the ERP category), and they focus on enterprises and large businesses (as an ERP)
- Their API is REST based and uses OAuth 2.0; you learn more about its API by visiting [their docs](https://learn.microsoft.com/en-us/rest/dynamics365/)
- Their sandbox is free
- Their API has a rate limit of 600 requests per minute
- Dynamics has unique names for their pagination: Position-based paging (form of offset) and value-based pagination (form of keyset, which lets you X). You can [visit this page to learn more about both methods](https://learn.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/paging-and-query-service-results) **‍**
- They provide SDKS for Microsoft Visual Studio and related languages [here](https://www.microsoft.com/en-us/download/details.aspx?id=50032) ‍
- Their popular data models include vendors, items, dimensions, credit notes

### **Oracle NetSuite**

NetSuite, initially named NetLedger, was founded in 1998 and was later acquired by Oracle in [2016 for $9.3 billion](https://www.oracle.com/corporate/pressrelease/oracle-buys-netsuite-072816.html).

- NetSuite has a market share of [9.27%](https://6sense.com/tech/accounts-payable/netsuite-market-share) (in the accounts payable category) and serves enterprises in various verticals
- They have both an older SOAP and newer REST API, and you can access information on either by visiting [their docs](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_157373386674.html#The-REST-API-Browser)
- They use OAuth 1.0
- Sandboxes are not freely available for NetSuite. You need to contact a representative from NetSuite to request one
- NetSuite is rate limited to 4 concurrent requests at a time
- They paginate with limit-based and offset pagination. Visit [this page](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_156414087576.html) to learn more.
- They provide SDKS for Java, Node.js, Visual Studio Code, among a few other languages. You can learn more about them [here](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1558730192.html#SuiteCloud-SDK) ‍
- Their key data models include purchase orders and vendors

### **Sage Intacct**

Intacct was co-founded in 1999, and was one of the first cloud-based accounting platforms at the time of its inception. The company was eventually [acquired by UK-based Sage Group in 2017](https://techcrunch.com/2017/07/25/sage-group-buys-intacct-accounting-software-for-850m/), leading the company to be rebranded to Sage Intacct.

- Sage Intacct has a sizable market share of [6.1%](https://6sense.com/tech/fund-accounting/sage-intacct-market-share) (in the fund cacounting category)
- Their API is notable in that it uses SOAP with a basic authentication method (with token exchange). You can find their documentation [here](https://developer.intacct.com/api/)
- Their sandbox is available with a developer account
- They use limit-based and page-based pagination; you can [visit this docs page](https://developer.sage.com/accounting/guides/efficiencies/pagination/) to learn more
- They provide SDKS for .NET, Node, and PHP languages; you can learn more about them [here](https://developer.intacct.com/tools/)
- Their key data models include general ledger, accounts payable, and cash management

_Related:_ [_What you need to know about Sage Intacct's API_](https://www.merge.dev/blog/sage-intacct-api)

## Integrate with accounting APIs at scale through Merge

You can offer more than a dozen accounting integrations by building to [Merge's Accounting Unified API](https://www.merge.dev/categories/accounting-api).

Merge also offers the maintenance support and management tooling your team needs to provide reliable, high-performing integrations over time.

To learn more about Merge's Accounting Unified API, and the Merge platform more broadly, you can [schedule a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-api)!

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)

Anthony Lagana

Product Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6ead9bd0-9112-4e49-9b0d-2b63545e574d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d17f5ca6-35f2-4122-99c2-ee49ab8824c8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6ead9bd0-9112-4e49-9b0d-2b63545e574d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d17f5ca6-35f2-4122-99c2-ee49ab8824c8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=5f89f8bd-3f44-45e3-9a4e-6bb9962fd2d9&bo=2&sid=5a07bca03e8c11f0953581051ed81505&vid=5a10a6803e8c11f09e01c3986521fb8b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=7%20accounting%20APIs%20to%20integrate%20with%20in%202025&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-api&r=&lt=967&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=604122)