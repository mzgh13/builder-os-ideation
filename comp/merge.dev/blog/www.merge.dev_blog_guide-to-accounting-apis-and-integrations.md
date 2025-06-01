---
url: "https://www.merge.dev/blog/guide-to-accounting-apis-and-integrations"
title: "Guide to accounting APIs and integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-accounting-apis-and-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-accounting-apis-and-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-accounting-apis-and-integrations#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-accounting-apis-and-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What are payroll integrations? Here's what you need to know**](https://www.merge.dev/blog/payroll-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**6 Codat alternatives worth considering in 2025**](https://www.merge.dev/blog/codat-alternatives)

# Guide to accounting APIs and integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 10+ accounting integrations with one_ [_accounting API_](https://merge.dev/categories/accounting-api).

‍

It’s no secret the accounting and fintech landscape is changing. 77% of finance professionals recognize that most of their basic accounting operations can be fully automated, and more and more are looking for ways to make their work more impactful through analytics, data visualization, and better tooling ( [source](https://financesonline.com/accounting-software-trends/)).

In short: SaaS automation is a must-have for the industry, and integrations help make that SaaS automation a reality.

Accounting integrations—the ability for your product to read and write data to the accounting software that your customers use—can drive revenue and cut costs for your business. They can also derail your product roadmap and add more strain on your engineering and customer success teams.

Read on in this Guide to Accounting APIs to learn about:

- **Top accounting APIs** \- Which accounting systems are most popular
- **Key concepts** \- How accounting systems work
- **Data schemas** \- How accounting data is organized
- **Use cases** \- Common ways accounting data is used in product integrations
- **How to get started** \- Approaching accounting API integrations within your own product

_Related:_ [_What ERP API integration?_](https://merge.dev/blog/erp-api-integration)

### Top Accounting APIs

The accounting software market is divided into two worlds: Small and Medium Business (SMB), and Enterprise Resource Planning (ERP).

SMB software, such as QuickBooks, handles core accounting processes for businesses, often small teams to medium operations. ERP software handles core accounting, as well as detailed order tracking, logging, and supply chain data. Examples include Oracle NetSuite and Microsoft Dynamics.

Below are the rankings of the top accounting platforms, by number of customers.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67046d14d006afdecf9b7dab_646c0fcacf828e03c5251be4_Top%2520Accounting%2520Software%2520by%2520Number%2520of%2520Customers.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67046d14d006afdecf9b7dab_646c0fcacf828e03c5251be4_Top%2520Accounting%2520Software%2520by%2520Number%2520of%2520Customers.webp)

‍

_Related:_ [_A look at the top accounting APIs_](https://www.merge.dev/blog/accounting-api)

### Key Accounting API Concepts for Developers

**References** classify the parties and goods involved in a transaction such as accounts, contacts, or items by indicating who is selling or buying a product and what the product is.

**Transactions** record money movement, such as journal entries or invoices, and often include data fields for References to show the major parties involved in the transaction.

**Reports**—such as Balance Sheets, Income Statements, and Cash Flow Statements—examine all the transactions of a company, classify those transactions into relevant categories, such as assets or liabilities, and can be used to draw conclusions about the company’s financial health.

**Multi-Entity** accounting occurs when a corporation has subsidiaries (or works across multiple locations) and has multiple subsidiaries or ‘entities’ that it needs to account for. Accounting platforms recognize this by organizing accounting data into different entities. Entities are usually organized into a hierarchy of parent and child entities, and all accounting data is tied to a specific entity - each account, transaction, contact, tracking category etc. is a part of an entity. This is important because it allows teams to clearly delineate _who_ owns _what_ when it comes to assets, liabilities, and equity of various organizations.

**Consolidation** is the reconciliation process when a company's business spans multiple countries (and currencies) and those currencies must be reconciled into a single currency for bookkeeping. Different accounting providers handle this differently. For example, Sage and NetSuite have multiple objects for currency and consolidation (NetSuite has three; Sage Intacct has five).

If you want a more expansive refresher on accounting terminology, then read through our [Guide to Core Accounting Concepts](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide).

### Accounting API Data Schemas

[Companies](https://docs.merge.dev/accounting/company-info/) are a top level concept for organizing accounting information. Company objects are used to represent the organization to which a set of Accounts belongs. [Contacts](https://docs.merge.dev/accounting/contacts/) represent counterparties such as vendors and customers.

[Accounts](https://docs.merge.dev/accounting/accounts/) are used to track transactions and exist in a hierarchy in the general ledger for a given Company. They may include revenue, expenses, assets, liabilities, or other items.

Several types of reports are available via an accounting API. [Balance Sheets](https://docs.merge.dev/accounting/accounts/) record assets, liabilities, and equity. [Cash Flow Statements](https://docs.merge.dev/accounting/cash-flow-statements/) record operating, investing, and financing activities. [Income Statements](https://docs.merge.dev/accounting/income-statements/) record income, cost of sales, and expenses. These reports are typically organized in tabular fashion, with rows and columns of data.

[Transactions](https://docs.merge.dev/accounting/transactions/) record activities between a Company and Contacts. Specific types of Transactions include [Expenses](https://docs.merge.dev/accounting/expenses/), [Credit Notes](https://docs.merge.dev/accounting/credit-notes/) (accounts payables refunds), [Vendor Credit](https://docs.merge.dev/accounting/vendor-credits/) (accounts receivables refunds), [Invoices](https://docs.merge.dev/accounting/invoices/), [Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/), and [Journal Entries](https://docs.merge.dev/accounting/journal-entries/). Transactions include a date, amount, and one or more Line Items. These Line Items are associated to [Items](https://docs.merge.dev/accounting/items/) that represent specific goods or services that make up a Transaction.

Transactions, Line Items, and Items can have [Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/) that are used to categories which business unit, department, subsidiary, or other organizational structure is related to a record.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67046d15d006afdecf9b7dbc_646c0fdccf828e03c5253340_Table%2520-%2520Accounting%2520and%2520ERP%2520by%2520Data%2520Schema.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67046d15d006afdecf9b7dbc_646c0fdccf828e03c5253340_Table%2520-%2520Accounting%2520and%2520ERP%2520by%2520Data%2520Schema.webp)

‍

### Top Accounting API Use Cases

**Forecast and Analyze Financial Performance**

Financial planning and analysis software leverage integrates with accounting systems to forecast financial metrics, provide financial dashboards, and track historical performance.

Examples: Chart Mogul, Fathom, Finmark, Float, Jirav, Standard Metrics, Syft Analytics

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c084f10e4372a6e9c555c_5a4da0e9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c084f10e4372a6e9c555c_5a4da0e9.webp)

Jirav integrates with Quickbooks Online to pull financial actuals (revenue, expenses, assets, liabilities) and forecast them.

_Related:_ [_Common ways to use financial statement APIs_](https://www.merge.dev/blog/financial-statement-api)

**Track Receivables and Revenue**

Ecommerce and subscription revenue applications integrate with accounting systems to track and update invoices, making it easier to record revenue and manage account receivables.

Examples: BigCommerce, Chargebee, Invoice2Go

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c0865cf828e03c51b1c0e_3ef9e85d.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c0865cf828e03c51b1c0e_3ef9e85d.webp)

Chargebee integrates with Sage Intacct to create and update invoices in Intacct, such as this example where an invoice is overdue.

**Track Payables and Expenses by Category**

Spend and expense management software integrates with accounting systems to track expenses, categorize them, remove manual data entry, and manage account payables.

Examples: Airwallex, Bill.com, Brex, Concur, Expensify, Payhawk, Ramp, Tipalti

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c087baed7f7cc9b9f5de6_12792cfb.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c087baed7f7cc9b9f5de6_12792cfb.webp)

Brex integrates with Xero to categorize expenses from corporate credit cards in the correct general ledger account.

_Related:_ [_Common accounting integration examples_](https://www.merge.dev/blog/accounting-integration)

**Make or Request Payments**

Payment platforms integrate with account systems to set up one-time or recurring payments and match payments to invoices.

Examples: Lightspeed, Paypal, Square, Stripe

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c0896595d73359ee1e431_a19ee6b0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c0896595d73359ee1e431_a19ee6b0.webp)

Xero integrates with Stripe to track invoices, transactions, and payments for fast reconciliation.

**Evaluate Creditworthiness**

A wide variety of banking, lending, trade and inventory finance, and other financial services rely on creditworthiness data from income statements, balance sheets, and cash flow statements.

Examples: Bluevine, Fundbox

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c08ab9326c44489fe62e0_44a969e2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c08ab9326c44489fe62e0_44a969e2.webp)

Fundbox integrates with Quickbooks Online to provide working capital loans and automatically record the advances and repayments within Quickbooks.

**Prepare Taxes and Tax Credits**

Global taxes are complex and ever changing, making tax compliance software a common integration point for accounting systems.

Examples: Avalara, Paddle, Sovos, Vertex

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c08c5e63efa2bde0ed5da_64a530d8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/646c08c5e63efa2bde0ed5da_64a530d8.webp)

Vertex integrates with SAP to calculate tax rates for a wide variety of jurisdictions.

_Related:_ [_A guide to tax rate APIs_](https://www.merge.dev/blog/tax-rate-api)

### Getting Started with Accounting APIs

Once you’re ready to kick the tires integrating with an accounting provider, you’ll want to keep in mind a few additional topics:

- API format - Which standards do the underlying APIs support (REST, SOAP, etc.)
- Authentication - Which auth methods each API uses (e.g. OAuth, basic auth, etc.)
- Pagination and rate limits - How large responses are accessed in each API
- Test Accounts - How to access sandboxes for each API

We’ve built Merge to help developers easily integrate with multiple accounting systems. Our [Unified Accounting API](https://merge.dev/categories/accounting-api) is all REST-based, with one type of authentication, pagination, rate limiting, and automated issue detection to make development simple. Hundreds of companies use Merge to plug into accounting APIs, including [Causal](https://www.merge.dev/case-studies/how-causal-sped-up-their-self-serve-time-to-value-by-20-with-merge).

For all of this info in one comprehensive place, plus more in-depth examples of accounting integrations, download the [Guide to Accounting APIs and Integrations](https://www.merge.dev/learning/guide-to-accounting-api-integrations).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3417b004-942c-4966-81d7-f0b576243f61&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=47b52758-c5ce-43c2-9bf3-9fbb189bef35&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-accounting-apis-and-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3417b004-942c-4966-81d7-f0b576243f61&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=47b52758-c5ce-43c2-9bf3-9fbb189bef35&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-accounting-apis-and-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ffe36b9e-a6e8-4956-be8f-94130edde218&bo=2&sid=125429703e8c11f0a537f3934d51bf5f&vid=1254da703e8c11f095179f4b4c6109da&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20accounting%20APIs%20and%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-accounting-apis-and-integrations&r=&lt=455&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=92301)