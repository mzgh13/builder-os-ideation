---
url: "https://www.merge.dev/blog/bank-feed-api"
title: "A guide to using bank feed APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/bank-feed-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/bank-feed-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/bank-feed-api#)

Table of contents

[What is a bank feed API?](https://www.merge.dev/blog/bank-feed-api#what-is-a-bank-feed-api)

[How to use bank feed APIs](https://www.merge.dev/blog/bank-feed-api#how-to-use-bank-feed-apis)

[Bank feed API examples](https://www.merge.dev/blog/bank-feed-api#bank-feed-api-examples)

[Benefits of using a bank feed API](https://www.merge.dev/blog/bank-feed-api#benefits-of-using-a-bank-feed-api)

[Sync bank feed data across ERP solutions with ease via Merge](https://www.merge.dev/blog/bank-feed-api#sync-bank-feed-data-across-erp-solutions-with-ease-via-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbank-feed-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**3 challenges that FinServ companies face in building and maintaining customer-facing ERP integrations**](https://www.merge.dev/blog/finserv-challenges-erp-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c708a90c28c8112d7f0_Fintech_header_image.webp)**How 3 fintech companies use integration data to power cutting-edge AI features**](https://www.merge.dev/blog/how-fintechs-power-ai-features)

# A guide to using bank feed APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Bank feed endpoints play a critical role in supporting FinServ companies and their customers.

To break down the impact of using bank feed APIs, we’ll highlight several use cases and share a few real-world examples of these endpoints.

But to start, let’s align on the definition of a bank feed API.

## **What is a bank feed API?**

It’s an endpoint that lets you access data from a particular bank account. This can include data related to account balances, account names, currencies, and more.

Also, depending on the API provider, you may be able to perform multiple operations on the bank feed data, such as GET and POST requests.

[Related](https://www.merge.dev/blog/financial-statement-api?blog-related=image)

#### [How to use financial statement APIs successfully](https://www.merge.dev/blog/financial-statement-api?blog-related=image)

[![How to use financial statement APIs successfully](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7aa6e16bf864755f32e_Financial_statements_API.webp)](https://www.merge.dev/blog/financial-statement-api?blog-related=image)

## **How to use bank feed APIs**

Here are just a few of the use cases they support.

### **POST bank feed transactions to ERP systems**

To help customers reconcile their transactions on your FinServ platform quickly and easily, you can POST bank transactions to their ERP systems on a recurring cadence (e.g., every 24 hours).

[![POSTing bank feed transaction workflow](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e4_679166a4b37e69d9148d3e71_POST%2520bank%2520feeds%2520(4).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e4_679166a4b37e69d9148d3e71_POST%2520bank%2520feeds%2520(4).webp)

### **GET bank feed transaction data from customers**

Say you offer a financial planning & analysis (FP&A) platform that helps users access comprehensive and actionable financial models.

To ensure your models are consistently up to date and valuable for users, you can make GET requests to customers’ ERP systems’ bank feed endpoints every day to fetch and continually re-sync bank transaction data.

[![Fetching bank feed transactions for FP&A product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e7_67916889aa5d639817d51455_GET%2520bank%2520feeds%2520(3).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e7_67916889aa5d639817d51455_GET%2520bank%2520feeds%2520(3).webp)

### **GET bank feed accounts from potential borrowers**

Imaging you’re a business lender and need to determine credit worthiness across potential borrowers to effectively pinpoint the best candidates.

To help you evaluate candidates, you can access their bank feed accounts (with their consent) from their ERP systems and review their current and historical balances across active accounts.

[![Bank feed accounts workflow for lending products](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e1_67916840d04e79ef70832442_GET%2520bank%2520feed%2520accounts%2520(2).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679168ba98117893894451e1_67916840d04e79ef70832442_GET%2520bank%2520feed%2520accounts%2520(2).webp)

## **Bank feed API examples**

Let’s break down a few bank feed APIs you can use.

### **Xero**

Xero has two types of endpoints that are part of their bank feeds API.

- **Statements endpoint:** It lets you fetch or create bank statements. For the latter, you’ll need to provide certain information in your API requests, including the connection feed ID, the start and end dates, and the start and end balances

- **Feed Connections endpoint:** It lets you either create feed connections in or retrieve feed connections from Xero. Like the Statements endpoint, POSTing requires  certain types of data, such as the account ID, number, and name

It’s worth noting that you’ll need to be certified by Xero before you can start building to the endpoint, which can take several months.

There’s also no guarantee you’ll get certified. Many FinServ companies need additional permissions to apply and may ultimately fail to gain approval.

[![Steps to becoming a Xero partner](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6791661df859c229108a197b_AD_4nXeCSTKzY8qsYt8JjkNzOQhL7ZNRpRQr0ZOd1JeAPMCzvO7DQm1tOfgxvqrY2LO_OoYuGO63PkG0sfI_hcv2zfINI6WgaPs5yUTwmch7l7p5RYerqCo1AvjI0CAb3n2IFqQfkjUpdA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6791661df859c229108a197b_AD_4nXeCSTKzY8qsYt8JjkNzOQhL7ZNRpRQr0ZOd1JeAPMCzvO7DQm1tOfgxvqrY2LO_OoYuGO63PkG0sfI_hcv2zfINI6WgaPs5yUTwmch7l7p5RYerqCo1AvjI0CAb3n2IFqQfkjUpdA.webp)

[_Xero_](https://developer.xero.com/documentation/xero-app-store/app-partner-guides/app-partner-steps/) _requires many types of FinServ companies to get prior approval before beginning the application process_

‍

[Related](https://www.merge.dev/blog/xero-api?blog-related=image)

#### [Xero API integration: everything you need to know](https://www.merge.dev/blog/xero-api?blog-related=image)

[![Xero API integration: everything you need to know](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c709309b17fd57b0d4f_Xero_Guide_%252525281%25252529.webp)](https://www.merge.dev/blog/xero-api?blog-related=image)

### **Merge**

The leading [API aggregator for B2B SaaS companies](https://www.merge.dev/blog/api-aggregator) offers two Common Models, or normalized data models, for bank feeds.

- **Bank Feed Accounts:** You can get or add bank feed accounts and their associated data, such as account numbers, currencies used, and balance information

For example, here’s how it can look to POST Bank Feed Accounts through Merge:

```python

{
 "next": "cD0yMDIxLTAxLTA2KzAzJTNBMjQlM0E1My40MzQzMjYlMkIwMCUzQTAw",
 "previous": "cj1sZXdwd2VycWVtY29zZnNkc2NzUWxNMEUxTXk0ME16UXpNallsTWtJ",
 "results": [\
   {\
     "id": "b26fd49a-cbae-470a-a8f8-bcbc119e0390",\
     "remote_id": "987300",\
     "created_at": "2021-09-15T00:00:00Z",\
     "modified_at": "2021-10-16T00:00:00Z",\
     "bank_feed_account": "49cd5a42-b311-4750-9361-52e2ed1d4653",\
     "transaction_date": "2024-02-02T00:00:00.000Z",\
     "posted_date": "2024-02-03T00:00:00.000Z",\
     "amount": 100.1,\
     "description": "Lunch expense",\
     "transaction_type": "payment",\
     "payee": "Elmo's diner",\
     "credit_or_debit": "CREDIT",\
     "source_transaction_id": "124569",\
   }\
 ]
}

```

‍

- **Bank Feed Transactions:** You can fetch or create bank feed transactions, including the transactions’ dates, amounts, descriptions, and whether they fall under credits or debits

Here’s how the response can look for a GET request:

```python

{
 "next": "cD0yMDIxLTAxLTA2KzAzJTNBMjQlM0E1My40MzQzMjYlMkIwMCUzQTAw",
 "previous": "cj1sZXdwd2VycWVtY29zZnNkc2NzUWxNMEUxTXk0ME16UXpNallsTWtJ",
 "results": [\
   {\
     "id": "b26fd49a-cbae-470a-a8f8-bcbc119e0390",\
     "remote_id": "987300",\
     "created_at": "2021-09-15T00:00:00Z",\
     "modified_at": "2021-10-16T00:00:00Z",\
     "bank_feed_account": "49cd5a42-b311-4750-9361-52e2ed1d4653",\
     "transaction_date": "2024-02-02T00:00:00.000Z",\
     "posted_date": "2024-02-03T00:00:00.000Z",\
     "amount": 100.1,\
     "description": "Lunch expense",\
     "transaction_type": "payment",\
     "payee": "Elmo's diner",\
     "credit_or_debit": "CREDIT",\
     "source_transaction_id": "124569",\
   }\
 ]
}

```

‍

_Learn more about our bank feed endpoints by visiting_ [_our docs_](https://docs.merge.dev/accounting/overview/) _._

## **Benefits of using a bank feed API**

APIs offer several benefits over scripts and files when it comes to syncing bank feed data.

- **Fast sync frequencies:** Depending on the provider and the specific endpoint, you may be able to sync bank feed data every day, every few hours, or even more often

- **High data accuracy:** API-based syncs let you and your customers avoid any manual intervention, which helps prevent costly human errors (e.g., assigning the wrong figure to a transaction amount)

- **Secure connections:** API providers typically require clients to follow strict policies to access their endpoints, such as using specific authentication protocols (e.g., OAuth) and adhering to encryption standards like TLS for secure data transmission

- **Wide availability:** Most ERP providers offer bank feed APIs and a wide range of [integration solutions](https://www.merge.dev/blog/api-integration-tools) are available to help you build to them quickly

## **Sync bank feed data across ERP solutions with ease via Merge**

Merge lets you access bank feed endpoints at scale, quickly, as you only have to build to [Merge’s Accounting Unified API](https://www.merge.dev/categories/accounting-api) to access bank feed endpoints across ERP solutions.

In addition, Merge offers multiple unified data models— [bank feed accounts](https://docs.merge.dev/accounting/bank-feed-accounts/) and [bank feed transactions](https://docs.merge.dev/accounting/bank-feed-transactions/)—to help you access all the bank feed data you need across your customer base.

Learn more about Merge’s Bank Feeds Common Models and how you can use them by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbank-feed-api).

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=bd29b6d2-6149-4ea9-bcba-03c1af703945&bo=2&sid=cea6d6003e8b11f09c48ada39ee4e868&vid=cea74e603e8b11f08587d7c96a8034a2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20using%20bank%20feed%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbank-feed-api&r=&lt=388&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=868477)