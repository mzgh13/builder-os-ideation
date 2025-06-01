---
url: "https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide"
title: "Accounting concepts: the developer's essential guide"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#)

Table of contents

[Understanding the Basics of Accounting APIs](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#understanding-the-basics-of-accounting-apis)

[Reference Objects](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#reference-objects)

[Transactions](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#transactions)

[Reports](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#reports)

[Remote Fields](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#remote-fields)

[Additional Objects](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#additional-objects)

[Getting Started with an Accounting Unified API](https://www.merge.dev/blog/accounting-concepts-the-developers-essential-guide#getting-started-with-an-accounting-unified-api)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-concepts-the-developers-essential-guide)

##### Just for you

No items found.

# Accounting concepts: the developer's essential guide

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Kritika Yerrapotu

Marketing

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53853af779c6de1fabd7_62eff9857d098c1325724163_ria.webp)

Ria Garg

Platform

@Merge

You have a technical background. Unfortunately, it’s time to get a financial one.

As a developer, being able to understand accounting terminology is critical to building out integrations within your product. But we’ll be frank: accounting as a field is confusing as is. Add in different accounting providers and APIs that use varying objects and fields, and you have a recipe for headache.

Welcome, then, to the common reference that helps you navigate the world of Accounting APIs.

The guide below does more than clarify key accounting terminology: it provides context on the data models that represent these terms. Using Merge’s [Accounting Unified API](https://merge.dev/category/accounting-api/) as a standard, we’ll elaborate on definitions of each object and relevant fields.

## **Understanding the Basics of Accounting APIs**

Accounting terms connect in related systems through three interrelated data models: Reference Objects, Transaction Objects, and Report Objects.

Together, References, Transactions, and Reports create an accounting system that can efficiently and effectively track a company’s finances.

- **References** classify the parties and goods involved in a transaction such as accounts, contacts, or items by indicating who is selling or buying a product and what the product is.
- **Transactions** record money movement, such as journal entries or invoices and often include data fields for References to show the major parties involved in the transaction.
- **Report objects**, such as a balance sheet, examine all the transactions of a company, classify those transactions into relevant categories, such as assets or liabilities, and can be used to draw conclusions about the company’s financial health.

_Related:_ [_Examples of accounting APIs_](https://www.merge.dev/blog/accounting-api)

## **Reference Objects**

**Accounts**

Accounts refer to what companies use to track transactions. They can be both bank accounts or a ledger (also called a chart of accounts). Across accounting APIs, the term “account” is standard: what differs are the fields included within the object.

_Key Fields:_

- classification: the account’s broadest grouping. This can be either ASSET, EQUITY, EXPENSE, LIABILITY, or REVENUE. In cases where class type is not listed, the original value from the source API will be passed through.
- type: the account’s type is a narrower and more specific group within the account’s classification. For example, an account may be classified as a LIABILITY, but have the “current liability” type of CURRLIAB.
- status: the state of the account, which can be ACTIVE, PENDING, or INACTIVE. For example, an account with frequent transactions would be ACTIVE, or an account that recently had a transaction would immediately be listed as PENDING. If the status is not listed, the original value from the source API will be passed through.

_See our official accounting documentation for accounts_ [_here_](https://docs.merge.dev/accounting/accounts/) _._

**Contacts**

The contact object refers to either a supplier or a customer. Among different Accounting APIs, “contacts” can be called “entities”.

_Key Fields:_

- is\_customer: the boolean value to signify that the contact is or is not a customer (the contact purchasing the item).
- is\_supplier: the boolean value to signify that the contact is or is not a supplier (the contact offering the item). A supplier can also be known as a “vendor.”
- status: the state of the contact, which can be ACTIVE, ARCHIVED, or the original value from the source API.

_See our official accounting documentation for contacts_ [_here_](https://docs.merge.dev/accounting/contacts/) _._

**Items**

Items are the goods involved in a transaction. The item object details what the product or service is, its price, and the buyer’s and seller’s account.

_Key Fields:_

- purchase\_account: references a general ledger account used to record the purchases made by the account holder.
- purchase\_price: the price the item will be purchased at from the buyer.
- sales\_account: references a general ledger account used to record the sales made by the account holder.

_See our official accounting documentation for items_ [_here_](https://docs.merge.dev/accounting/items/) _._

**Payment**

The payment object represents general payments made towards a specific transaction. A transaction object can include payment objects as part of the transaction.

- contact: the supplier involved in the payment.
- account: the customer’s account in which the payment is made.
- total\_amount: the total amount of money being paid to the supplier after taxes.

_See our official accounting documentation for payments_ [_here_](https://docs.merge.dev/accounting/payments/) _._

_Related:_ [_Examples of ERP API integrations_](https://merge.dev/blog/erp-api-integration)

## **Transactions**

Transactions are any record of money movement that directly affect the financial status or statements of a business.

**Transactions** fall into one of two categories: **Accounts Receivable** and **Accounts Payable**.

- Accounts receivable indicate that the holder (to whom the account belongs) is **owed** something.
- Accounts payable indicate that the holder (to whom the account belongs) **owes** something.

Account receivables and account payables are accounts on a company’s general ledger. A general ledger is a set of numbered accounts used to keep track of transactions. The numbering scheme for general ledger (“G/L”) is illustrated below.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d6dbe886acf8c55ea5aef4_62f5df1c7a4039c64fbf729e_Group_41.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d6dbe886acf8c55ea5aef4_62f5df1c7a4039c64fbf729e_Group_41.png)

The following are common fields used in several of the transactions objects:

- contact: the contact to whom the transaction belongs to.
- total\_amount: the total amount being paid after taxes.
- memo: an internal note used by the business to clarify the purpose of the transaction.
- transaction\_date: the date the transaction was made.
- number: the transaction’s number used for identifying purposes.

**Invoice**

An invoice is a request for payment. It is an accounts receivable transaction that exists on the vendor's side as a record of a transaction between a buyer and seller. An invoice can outline the terms of a transaction, including payments, the customers involved, the service or goods, and the price. An invoice’s type is accounts\_receivable.

**Bill**

A bill is a request for payment that exists _on the customer side_. It carries the same information as the invoice object, but customers use the term “bill” for when they owe money to a business. Bills are an accounts payable transaction, because the holder owes money to a business. In an Accounting Unified API, a bill is an invoice with its type set to accounts\_payable.

- InvoiceLineItem object
- ~line\_items: a single entry within an invoice or bill dedicated to one item that is purchased. An invoice or bill can have multiple line items for each item being purchased.
- payments: an array of Payment object IDs.
- sub\_total: the total amount being paid before taxes.
- total\_discount: the total discounts applied to the total cost
- total\_tax\_amount: the total amount being paid in taxes.
- type: whether the invoice is an accounts receivable or accounts payable. If it is accounts\_payable, then it is a bill.

_See our official accounting documentation for invoices and bills_ [_here_](https://docs.merge.dev/accounting/invoices/) _._

**Journal Entries**

Journal entries are records of business transactions kept for bookkeeping purposes. A journal entry includes the amount of money moved, where the money went, and where it is from. Each row (referred to as a “line”) in an entry is classified as either debit or credit. Together, the debit and credit of each entry must sum to zero.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5df33a296b08290bc94ba_Table.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5df33a296b08290bc94ba_Table.webp)

_Key Fields:_

- JournalLine\[\] Object
- ~lines: a single entry within a journal entry detailing cash flowing into (“debit”) or out of (“credit”) a business. A journal entry can have multiple lines for each instance of cash flow.
- net\_amount: the value of the line item including taxes and other fees.
- payments: an array of payment object IDs.

_See our official accounting documentation for journal entries_ [_here_](https://docs.merge.dev/accounting/journal-entries/) _._

**Purchase Order**

A purchase order is a formal record of request for a product or service between a buyer and a seller. This is typically used in cases of a bulk order. A purchase order includes information about the item being purchased, the customer and vendor, and in some cases, delivery information.

As an example, the customer would issue a purchase order to the vendor indicating the item, amount needed, and price they intend to pay. The vendor would then send an invoice to the customer to complete the purchase.

_Key Fields:_

- customer: the party making the purchase order.
- PurchaseOrderLineItem\[\] object
- ~line\_item: a single entry in a purchase order dedicated to a specific item purchased.
- ~description: a description of the item purchased.
- status: the state of the purchase order. Can be one of the following: DRAFT, SUBMITTED, AUTHORIZED, BILLED, DELETE.
- vendor: the party fulfilling the purchase order.

_See our official accounting documentation for purchase orders_ [_here_](https://docs.merge.dev/accounting/purchase-orders/) _._

**Credit Notes**

Credit notes are an accounts payable transaction used when a vendor offers a gift or refund to a customer. This record exists on the vendor side, and outlines how the customer is owed credit. A credit note will contain information on the amount of credit owed, the customer, and the account.

_Key Fields:_

- CreditNoteLineItem\[\] object
- ~line\_items: a single entry in a credit note dedicated to a specific item that is owed to the customer.
- ~description: the description of the item that is owed.
- payments: an array of payment object IDs.
- remaining\_credit: the amount of value remaining in the credit note that the customer can use.
- status: the state of the credit note, which can be SUBMITTED, AUTHORIZED, PAID. In cases where there is no clear mapping, the original value is passed through.

_See our official accounting documentation for credit notes_ [_here_](https://docs.merge.dev/accounting/credit-notes/).

**Vendor Credit**

Vendor credit is an accounts receivable transaction used to show that a customer is owed a gift or refund. It holds the same information as a credit note, but is held by the customer rather than the vendor. This record exists on the customer side, and outlines the amount of credit owed to the customer, the vendor that owes credit, and the account.

_Key Field:_

- VendorCreditLine\[\] object
- ~lines: a single entry in a vendor credit dedicated to a specific type of credit owed to the customer, such as a refund or gifted credit. A vendor credit object can have multiple lines for each type of credit owed to the customer.
- ~description: the description of the credit that is owed.
- net\_amount: the full value of the credit.
- vendor: the vendor that owes the gift or refund to the customer.

_See our official accounting documentation for vendor credit_ [_here_](https://docs.merge.dev/accounting/vendor-credits/).

**Expenses:**

These represent a purchase made from a vendor which can be made with a check, credit card, or cash. Each expense object is dedicated to a grouping of expenses, with each expense recorded in an ExpenseLine object. For example, an expense object can be for “new employee supplies” with an ExpenseLine object for a “MacBook Pro”.

_Key Fields:_

- ExpenseLine\[\] object
- ~lines: a single entry in the expense object dedicated to a specific expense the company made. The expense object can have multiple lines for each item that was purchased.
- ~description: the description of the item that was purchased by the company.

_See our official accounting documentation for expenses_ [_here_](https://docs.merge.dev/accounting/expenses/) _._

**Transactions (Object)**

Since there are several different types of transactions covered across various accounting APIs, an Accounting Unified API uses a general transaction object to cover any transaction type that does not already have a dedicated object. The transaction object does not cover expenses, credit notes, vendor credit, invoices, purchase orders, and journal entries. The type of transaction is determined by the transaction\_type field.

This object can be used with the Netsuite, Quickbooks, and Xero APIs, which all support a variety of transaction types.

_Key Fields:_

- GeneralTransactionLineItem\[\] object
- ~LineItems: a single entry dedicated to the specific item in the transaction. A transaction object can have multiple LineItems for each item involved in the transaction.
- transaction\_type: the type of transaction, which can be any transaction object that is not already included in Merge’s common model.

_See our official accounting documentation for transactions_ [_here_](https://docs.merge.dev/accounting/transactions/) _._

## **Reports**

Reports are a way to measure the financial health of a company by tracking cash inflow and outflow along with account statuses over time. The three main types of reports are Balance Sheets, Profit and Loss (P&L, or Income Statements) and Cash Flow statements. Quickbooks and Xero support these reports within their APIs, however Netsuite only supports these reports in its UI. You cannot pull reports from the Netsuite API programmatically.

**Balance Sheet**

A balance sheet shows a company’s assets, liabilities, and equity. Assets should be equal to liabilities and equity combined. Balance sheets are pulled at the end of every quarter, month, and year. They show the company’s financial health at a specific point in time.

- date: the date the balance sheet was created
- assets:
- ~ReportItem Object
- ~~value: the dollar value of the asset.
- ~~sub\_items: ReportItem objects within the asset’s main ReportItem Object, to further organize the company’s assets.
- liabilities:
- ~ReportItem Object
- ~~value: the dollar value of the liability.
- ~~sub\_items: ReportItem objects within the liability’s main ReportItem Object, to further organize the company’s liabilities.
- equity:
- ~ReportItem Object
- ~~value: the dollar value of the equity.
- ~~sub\_items: ReportItem objects within the equity’s main ReportItem Object, to further organize the company’s equity.

_See our official accounting documentation for balance sheets_ [_here_](https://docs.merge.dev/accounting/balance-sheets/) _._

**Income Statement (also known as Profit and Loss):**

In our common model, Profit and Loss or Income Statements are found in the income statement object. This report shows a company’s income, the cost of sales, operating expenses, and non-operating expenses. Other important values included are gross profit, gross operating profit, and net income. Income statements represent a period of time, such as a quarter or month.

_Key Fields:_

- gross\_profit: the income minus the cost of sales.
- net\_income: the gross profit minus the total expenses.
- net\_operating\_income: the income minus the operating expenses.
- income:
- ~ReportItem object
- ~~value: the dollar value of the income.
- ~~sub\_items: ReportItem objects within the income’s main ReportItem Object, to further organize the company’s income.
- cost\_of\_sales:
- ~ReportItem object
- ~~value: the dollar value of the cost of sales.
- ~~sub\_items: ReportItem objects within the cost of sales’ main ReportItem Object, to further organize the company’s cost of sales.
- operating\_expenses:
- ~ReportItem object
- ~~value: the dollar value of the operating expenses.
- ~~sub\_items: ReportItem objects within the operating expenses’ main ReportItem Object, to further organize the company’s operating expenses.
- non\_operating\_expenses:
- ~ReportItem object
- ~~value: the dollar value of the non-operating expenses.
- ~~sub\_items: ReportItem objects within the non-operating expenses’ main ReportItem Object, to further organize the company’s non-operating expenses.

_See our official accounting documentation for income statements_ [_here_](https://docs.merge.dev/accounting/income-statements/) _._

**Cash Flow Statement:**

A cash flow statement shows three types of activities:

- Operating activities: cash generated from a company’s product or service.
- Investing activities: cash from company’s investments, including the purchasing or selling of assets and loans made to vendors.
- Financing activities: costs that include debt, equity, and dividends with shareholders and investors.

A cash flow statement also includes the value of cash at the beginning of the period and end of the period. These reports are typically pulled monthly, quarterly, and annually.

_Key Fields:_

- operating\_activities:
- ~ReportItem object
- ~~value: the dollar value of the operating activities.
- ~~sub\_items: ReportItem objects within the operating activities’ main ReportItem Object, to further organize the company’s operating activities.
- investing\_activities:
- ~ReportItem object
- ~~value: the dollar value of the investing activities.
- ~~sub\_items: ReportItem objects within the investing activities’ main ReportItem Object, to further organize the company’s investing activities.
- financing\_activities:
- ~ReportItem object
- ~~value: the dollar value of the financing activities.
- ~~sub\_items: ReportItem objects within the financing activities’ main ReportItem Object, to further organize the company’s financing activities.

_See our official accounting documentation for cash flow statements_ [_here_](https://docs.merge.dev/accounting/cash-flow-statements/) _._

## **Remote Fields**

remote\_data: To offer the most comprehensive yet transferable model, an Account Unified API maps the most common and widely-used fields. For some fields that are unique to certain APIs, our common model includes remote\_data which copies the object’s fields and data exactly as it appears in the API it is called from. Essentially, you can access any endpoint in any source API through remote\_data. Learn more about how to use remote\_data [here](https://docs.merge.dev/supplemental-data/remote-data/).

remote\_created\_at: when this object was created by the third party

remote\_updated\_at: when the third party updated this object’s information.

remote\_was\_deleted: Indicates whether or not this object has been deleted by third party webhooks.

remote\_id: The third-party API ID for the matching object.

## **Additional Objects**

CompanyInfo: This object represents general company information. This includes tax numbers, company website URLs, addresses, phone numbers, and fiscal year start and end dates.

Address: This object represents the address of a contact, including the city, country, state, street, and zip code.

AccountingPhoneNumber: This object represents the phone number of a contact.

## **Getting Started with an Accounting Unified API**

Having a thorough understanding of accounting terminology can help you discern what information and which integrations you may need for your product.

If you’re still on the fence about how an Accounting Unified API can help you, read about the benefits of an Accounting Unified API [here](https://www.merge.dev/blog/marketing/why-you-need-a-unified-accounting-api/).

To scope your use case with the information you have learned here, head to our accounting [documentation](https://docs.merge.dev/accounting/overview/).

And finally, for special inquiries or to see our API in action, talk to a sales representative [here](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Faccounting-concepts-the-developers-essential-guide).

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Kritika Yerrapotu

Marketing

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Ria Garg

Platform

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=4083968d-a77a-444d-91d6-749c43cf088c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1add83c5-07cd-425c-aa66-bd3ad4ca9816&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-concepts-the-developers-essential-guide&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=4083968d-a77a-444d-91d6-749c43cf088c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1add83c5-07cd-425c-aa66-bd3ad4ca9816&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-concepts-the-developers-essential-guide&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=3a2b1a64-a8a6-4ae1-a42b-91b352026c00&bo=2&sid=953da0d03e8c11f0a650330f216d21ba&vid=953e53903e8c11f08c991b9beaf1351e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Accounting%20concepts%3A%20the%20developer%27s%20essential%20guide&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Faccounting-concepts-the-developers-essential-guide&r=&lt=1506&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=853173)