---
url: "https://www.merge.dev/blog/financial-statement-api"
title: "How to use financial statement APIs successfully"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/financial-statement-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/financial-statement-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/financial-statement-api#)

Table of contents

[What is a financial statement API?](https://www.merge.dev/blog/financial-statement-api#what-is-a-financial-statement-api)

[Examples of financial statement APIs](https://www.merge.dev/blog/financial-statement-api#examples-of-financial-statement-apis)

[Financial statement API use cases](https://www.merge.dev/blog/financial-statement-api#financial-statement-api-use-cases)

[Access all of your customers’ financial data with Merge](https://www.merge.dev/blog/financial-statement-api#access-all-of-your-customers-financial-data-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffinancial-statement-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Financial API integration: what it is, examples, and tips**](https://www.merge.dev/blog/financial-api-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What is an invoicing API? Here’s what you need to know**](https://www.merge.dev/blog/invoicing-api)

# How to use financial statement APIs successfully

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7aa6e16bf864755f32e_Financial_statements_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Financial statements offer invaluable data for your product and internal applications.

To better understand why integrating this data with other applications can prove invaluable and to help you implement any integration yourself, we’ll cover how a few real-world endpoints work and share several impactful integration use cases.

But first, let’s align on the definition of a financial statement API.

## **What is a financial statement API?**

It’s an endpoint that lets you access and interact with data within a financial statement, whether it's a balance sheet, an income statement, a cash flow statement, etc.

_Related:_ [_What is a tax rate API?_](https://www.merge.dev/blog/tax-rate-api)

## **Examples of financial statement APIs**

Many of the largest accounting tools don't offer out-of-the-box endpoint support for income, cashflow, and balance sheets, and require you to build custom logic through different methods to aggregate these reports.

That said, Xero is a great example of an API provider that offers at least some out-of-the-box endpoint support.

The accounting solution lets you access several financial statement endpoints via GET requests. Here are just a few of these endpoints (see the full list [here](https://developer.xero.com/documentation/api/finance/financialstatements)):

- Use `https://api.xero.com/finance.xro/1.0/financialstatements/balancesheet` to fetch balance sheets. You can also use balanceDate as a query parameter to get information on a specific balance sheet report

- Use `https://api.xero.com/finance.xro/1.0/financialstatements/cashflow` to retrieve cash flow statements outside of the U.S. (currently not supported in the U.S.). You can also use startDate and endDate parameters to customize the cash report; if no parameters are used, you’ll get a cash flow statement from the last 12 months

- Use `https://api.xero.com/finance.xro/1.0/financialstatements/profitandloss` to get a detailed profit and loss statement. Like the cashflow endpoint, you can use startDate and endDate query parameters to specify the time frame for your report. Otherwise, it’ll be the last 12 months

_Related:_ [_How to integrate with Xero’s API_](https://www.merge.dev/blog/xero-api)

## **Financial statement API use cases**

Here are a few ways to use financial statement APIs with internal applications and with customers’ accounting systems.

#### **Sync financial statements with your BI tool to uncover key insights**

To help your analysts identify opportunities and risksbased on your financial data, you can integrate your ERP system with your BI solution (e.g., Tableau) and sync a wide range of financial statement data once per day.

[![NetSuite sync with Tableau](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182666c570e513ec67f7e3_AD_4nXcHsoZ5nqsBqXW2n2U15pMoURMwf8h1Zk9WxAAJQLSTrWgYVBensFlSKAEvr3c3z0qmHtfm76-s1j_8-jAr_FToqQfh5zGl6PpoGN_ckWtYxvN-7oIujbCFUqvT9zAEvuTTXjh6F4VVrRz6aDUcjuuMjbE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182666c570e513ec67f7e3_AD_4nXcHsoZ5nqsBqXW2n2U15pMoURMwf8h1Zk9WxAAJQLSTrWgYVBensFlSKAEvr3c3z0qmHtfm76-s1j_8-jAr_FToqQfh5zGl6PpoGN_ckWtYxvN-7oIujbCFUqvT9zAEvuTTXjh6F4VVrRz6aDUcjuuMjbE.webp)

You can also add logic to your integration to allow certain types of data to get added to specific reports automatically.

#### **Build alerts in your business communications platform when financial data crosses a predefined threshold**

To help your finance team become aware of issues on time, you can integrate your accounting system with an app like Slack and build a flow where once a certain type of data is higher or lower than expected (e.g., an operating expense is higher than expected), the finance team gets notified in a specific Slack channel. The notification can also include details on the issue to help finance understand and address it quickly.

[![QuickBooks sync with Slack](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671826650a5ddc44d916b79b_AD_4nXcU6liC49qQBYbFt2pR-8EwKqdp2Ola8-eNOU0purXH1mBbTdDPn-6611Fa1a6IwwnzXOJj6L0AUD3Hm8BelAVmtBHOho37JLHz9_7KqaROzxqHlvxVA11t6DNqYpF0mEqf-wrLvcM9tD8JeNJ-nVdqKPo8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671826650a5ddc44d916b79b_AD_4nXcU6liC49qQBYbFt2pR-8EwKqdp2Ola8-eNOU0purXH1mBbTdDPn-6611Fa1a6IwwnzXOJj6L0AUD3Hm8BelAVmtBHOho37JLHz9_7KqaROzxqHlvxVA11t6DNqYpF0mEqf-wrLvcM9tD8JeNJ-nVdqKPo8.webp)

_Related:_ [_Examples of bank API integrations_](https://www.merge.dev/blog/bank-api-integration)

#### **Power an AI copilot to create actionable financial models**

Say you offer a financial planning tool and want to help customers realize value from your platform quickly and easily.

To remove any friction, you can integrate with customers’ accounting systems, feed their financial statement data to your machine learning model and continually do so on a predefined cadence (e.g., every 24 hours).

Using your ML model, you can then build a product feature that calculates financial metrics from the integrated data—gross profit, runway, burn rate, etc.—and displays this data in fully-customizable models.

[![A screenshot of Causal's AI Wizard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182666c0fdea176bf76ca3_AD_4nXcEYwMNKUwTtzUol1fKnlS4Z7H_OZp7KOcEWTsAgKRd76kB9OgBykV39-DR5_ioFOGAtvxfZYyAninvSyBRc_DLgI-FxFZ47DYFd-QyxgSSoVdJWl9QvdXKlOi9jRczyTvrlCYXsbghfO0UU3HtqN0aO5OT.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182666c0fdea176bf76ca3_AD_4nXcEYwMNKUwTtzUol1fKnlS4Z7H_OZp7KOcEWTsAgKRd76kB9OgBykV39-DR5_ioFOGAtvxfZYyAninvSyBRc_DLgI-FxFZ47DYFd-QyxgSSoVdJWl9QvdXKlOi9jRczyTvrlCYXsbghfO0UU3HtqN0aO5OT.webp)

[_Causal_](https://www.merge.dev/case-studies/how-causal-sped-up-their-self-serve-time-to-value-by-20-with-merge) _, a financial planning tool, built an AI Wizard that works exactly as described above_

#### **Enable customers to analyze different financial scenarios**

Say you offer a financial modeling platform that helps customers review and forecast their cash balance, cashflow, and expenses for any number of scenarios.

To help customers adopt your platform quickly, you can integrate with their accounting systems and sync—and consistently re-sync—the financial statement data from their systems. Your platform can then auto-populate and frequently update its dashboards, all but ensuring customers use the latest data.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a2c710a1acb022f172_AD_4nXfCzn2scffSL50TJtPp8h8-_VS0Z4KV4rjkoyoOyoD2eP_jyykTU4wpAzuwI1ZbhBPaOpfdAILb5KBH73OBomuABYEK8HvSCGEH1dQ1vjhe8DiDewTKlCke2UObHEC2jfaqbLCi58PnImepfH57HtcO2V6E.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a2c710a1acb022f172_AD_4nXfCzn2scffSL50TJtPp8h8-_VS0Z4KV4rjkoyoOyoD2eP_jyykTU4wpAzuwI1ZbhBPaOpfdAILb5KBH73OBomuABYEK8HvSCGEH1dQ1vjhe8DiDewTKlCke2UObHEC2jfaqbLCi58PnImepfH57HtcO2V6E.webp)

[_Parallel_](https://www.merge.dev/case-studies/parallel) _, a financial modeling software, added integrations with QuickBooks Online and Xero to support the use cases described above_

_Related:_ [_What is an accounting integration?_](https://www.merge.dev/blog/accounting-integration)

## **Access all of your customers’ financial data with Merge**

Merge, the leading unified API solution, lets you integrate with more than a dozen accounting systems by simply building to its unified API.

[![The accounting integrations Merge supports](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182665022651eff12c426e_AD_4nXfUXgWhMM0acGFRn3_YNuOj-OKESi0spPT62vnU_XT_MHjrivltd75tuwdpI8uaL0xr-Of1YmQYExt-AwGBfe6BIMI1elj8_bb0c2FILz6q3r9EEcJ-pGWaQC4sTchwrtktevmRkzhxpasCWqhm-2bg6Rou.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67182665022651eff12c426e_AD_4nXfUXgWhMM0acGFRn3_YNuOj-OKESi0spPT62vnU_XT_MHjrivltd75tuwdpI8uaL0xr-Of1YmQYExt-AwGBfe6BIMI1elj8_bb0c2FILz6q3r9EEcJ-pGWaQC4sTchwrtktevmRkzhxpasCWqhm-2bg6Rou.webp)

_A snapshot of the accounting integrations Merge supports_

In addition, Merge lets you sync a comprehensive set of data through its [Cash Flow Statements](https://docs.merge.dev/accounting/cash-flow-statements/), [Balance Sheets](https://docs.merge.dev/accounting/balance-sheets/), and [Income Statements](https://docs.merge.dev/accounting/income-statements/) Common Models. And Merge provides advanced features—Field Mapping, Authenticated Passthrough, and Remote Data—to help you access and sync custom financial statement data from any customer.

#### Ready to sync customers' financial data?

Learn how Merge can help by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffinancial-statement-api)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e8ce58ac-b51f-4f9a-a24c-7cc02198ac28&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d3114c12-4045-4094-b70f-5d024c87a747&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffinancial-statement-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e8ce58ac-b51f-4f9a-a24c-7cc02198ac28&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d3114c12-4045-4094-b70f-5d024c87a747&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffinancial-statement-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)