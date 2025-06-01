---
url: "https://www.merge.dev/blog/guide-to-payroll-api-integrations"
title: "Guide to payroll API integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-payroll-api-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-payroll-api-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-payroll-api-integrations#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-payroll-api-integrations)

##### Just for you

No items found.

# Guide to payroll API integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadbbb5568970b2d91a_8.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 40+ payroll integrations with one_ [_payroll API_](https://merge.dev/categories/hr-payroll-api).

Getting paid: it’s more than important to you — it’s a BIG business to everyone else.

In the past few years, payroll tech has exploded. Concepts such as [embedded payroll](https://www.forbes.com/sites/adeyemiajao/2020/09/10/embedded-apis-automate-27b-payroll-market/?sh=1282131e7133) allow products to add payroll services without building it themselves. [Novel consumer user cases](https://a16z.com/2020/10/20/payroll-apis/), such as credit checks and lending software, are popping up to utilize the rich set of payroll data being made available. And with this growth, B2B software integrations are proliferating as the payroll system expands and innovates.

So — how did this all happen? And how can you get up to date on this growing software trend to benefit your own business?

All of these changes are made possible by one critical piece of tech: payroll APIs that stitch together the entire payments ecosystem.

This guide to Payroll APIs will teach you about:

- **Top APIs** \- Which providers matter most
- **Key concepts** \- How payroll works
- **Data schemas** \- How various providers organize payroll data
- **Use cases** \- Common ways payroll data is used in product integrations
- **How to get started** \- Approaching payroll API integrations within your own product

### Top payroll APIs

The team at [Base 10 VC](https://base10.vc/research/payroll) found more than 70 payroll-related companies that have received over $9B in investment. This includes heavyweight payroll providers raising hundreds of millions of dollars such as Rippling, Gusto, Zenefits, Namely, Payfit, Personio, Deel, Oyster, and DailyPay.

The payroll software market is very fragmented, with a few larger players that make up ~10% of revenue, and a long tail of other companies. If you’re building payroll integrations you’ll want to consider supporting the following payroll software providers.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2656_62f5a7ba844ebd022b7a7f15_Table.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2656_62f5a7ba844ebd022b7a7f15_Table.webp)

Source: IDC Worldwide HCM and Payroll Applications Software Market Shares, 2020 and company 10Ks

#### Integrate with every payroll provider through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of payroll solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-payroll-api-integrations)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Key payroll API concepts for developers

Understanding [payroll APIs](https://www.merge.dev/blog/product/fulfilling-the-promise-of-payroll-apis) begins with understanding payroll. And if you’re unfamiliar with the space, then heads up: it might seem a bit complicated at first. To help you, here are the key concepts you need to know to start interacting with payroll data today.

**Companies and employees**

The fundamental context for all payroll API interactions are **companies** and the **employees** (or contractors) that work there. This forms the basis of how you’ll typically query for data will provide attributes about the employee valuable for additional context (e.g. location).

**Pay periods, payroll runs, and statuses**

Payroll systems are built around the core concept of a ‘Pay Period’ (e.g., monthly, twice monthly) and ‘Payroll Runs’ that occur once every period. Within ‘Payroll Runs’, there are both ‘Regular’ runs as well as one-time ‘Off-Cycle’ runs that can occur to fix a mistake or pay someone immediately upon termination. Each ‘Payroll Run’ has a status that it goes through, from ‘unprocessed’ through to ‘paid.’ You’ll almost always be interacting with data specific to a payroll run with a defined pay period (e.g. deductions related to the last completed payroll run).

**Jobs and pay rates**

Chances are one of the key attributes you want to know about an employee is how much they earn. Figuring out how much someone earns involves finding their ‘Job’, typically defined as a specific ‘Title’, as well as a ‘Pay Rate’. Each ‘Job’ has either an associated ‘Pay Rate’ or ‘Compensations’. Both can include the cash compensation per unit of time (e.g., $ per hour) and may also include other compensation, such as commissions, bonuses, or one-time payments.

**Tip:** In many payroll and HR systems a ‘Job’ is unique to a specific employee: one employee may have two ‘Jobs’ but two employees won’t have the same ‘Job’.

**Employee pay**

A ‘Pay Rate’ is just the beginning of calculating what an employee will actually receive in their bank account. The ‘Pay Rate’ times the time period worked (e.g. 80 hours over 2 weeks) will generate a ‘Gross Pay’ amount. From that, there are ‘Pre-Tax Deductions’, ‘Tax’, ‘Post-Tax Deductions’, and ‘Reimbursements’.

**Tip:** In a Payroll API such as Merge, you’ll typically find these within the Earnings, Deductions, and Taxes objects.

**Employer cost**

Payments also occur on the employer side. In addition to the ‘Employee Gross’ pay (based on the concepts described above), there is ‘Employer Tax’ (e.g. payroll taxes, social insurance taxes), and ‘Contribution to Benefits’ that employers make on behalf of their employees.

**Tip:** In a payroll API, you’ll find these under the [Benefits](https://merge.dev/docs/hris/benefits/#benefits-object) object.

#### Integrate with every payroll provider through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of payroll solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-payroll-api-integrations)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Payroll API data schemas

Each Payroll API has a schema specific to that platform. A typical data schema looks like the one below, modeled off of Merge’s [Payroll Unified API](https://merge.dev/docs/hris/overview/).

[**Employees**](https://merge.dev/docs/hris/employees) typically include all full-time workers, part-time workers, and contractors. Demographic information (birthdates, government IDs) and addresses are available from the employee object. Addresses are often stored as an array of ‘Locations’ objects. Employees are associated with their [**Bank Info**](https://merge.dev/docs/hris/bank-info) for direct deposit.

Each employee has one or many [**Employments**](https://merge.dev/docs/hris/employments) that define their current roles and compensation. This includes job title, pay rate and frequency, and the [**Pay Groups**](https://merge.dev/docs/hris/pay-groups) they belong to.

Employees are also associated with [**Benefits**](https://merge.dev/docs/hris/benefits) that they enroll in. The Benefit object includes information about how much the employee and the employer contribute each pay period.

To determine how much someone was paid or will be paid, it’s important to use the [**Employee Payroll Runs**](https://merge.dev/docs/hris/employee-payroll-runs) object. For each employee, you’ll be able to access the gross pay, net pay, earnings, deductions, and taxes for each pay period. This is also the object you’ll want to use to post new line items to the payroll. You can find the appropriate run by using the [**Payroll Runs**](https://merge.dev/docs/hris/payroll-runs) object and filtering on the date or run type.

Each Employee Payroll Run has **Deductions** paid by either the employee or the company. These deductions represent one-time debits for a specific employee. While some Payroll APIs support the concepts of recurring deductions or company-wide deductions, these concepts aren’t common among most APIs. Note that for most Payroll APIs, benefits such as health insurance may or may not be mapped to deductions.

### Relevant HRIS API data schemas

In addition to core payroll information, you’ll also find related HR information to be valuable in your product integration. These objects include [**Teams**](https://merge.dev/docs/hris/teams), which define employees in hierarchical or local groups. You may also want to access information about [**Time Off**](https://merge.dev/docs/hris/time-off) to map back to the payroll line items of a given employee.

### Top payroll API use cases

Payroll data is used in a wide variety of B2B and B2C products. Here are the most common examples of payroll data integrations.

**Employee onboarding**

When full-time or part-time users are onboarded to a new company they need to set up payroll, bank account, tax status, and deduction information so that they can get paid.

Examples: Sapling, Zavvy

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2659_62f5a7f0ea0370ac9f5669fd_EmployeeOnboarding_Example.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2659_62f5a7f0ea0370ac9f5669fd_EmployeeOnboarding_Example.webp)

_See: The Sapling pre-onboarding flow sends new hire payroll and tax data to ADP._

**Employee reimbursements**

Workers spend money out-of-pocket (travel, mileage, per-diems) that they want to be reimbursed by their employer. Payroll data can provide bank account information and tax tracking necessary to make reimbursements seamless.

Examples: Ramp, Brex, Navan, Mesh Payments, Airbase, Expensify

**Benefit administration and deductions**

Employers offer health, mental health, insurance, fitness, referral bonuses, transport, and other fringe benefits. Payroll data makes it easy to deduct from employee paychecks, company accounts, and to keep track of taxes.

Examples: Forma, Origin, Paytient, Benepass, Bonusly, Assembly

**Global employment and tax management**

Hiring and managing teams in multiple countries lead to increased payroll complexity. Integrating with payroll data allows you to create streamlined compliance workflows by using data such as employee address, earnings, and tax payment info.

Examples: Remote, Oyster, Deel

**Compensation management**

Employers need to ensure salary and equity pay are competitive and equitable. Payroll and HR data makes it easy to view and compare compensation across locations, titles/roles, and demographic data.

Examples: Pave, Pequity, Assemble, Carta Total Comp, Barley, Complete, Compete

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c265c_62f5a8157ff2dd53f50db660_Compensation_Management.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c265c_62f5a8157ff2dd53f50db660_Compensation_Management.webp)

_See: Carta’s Total Compensation integration with Gusto for leveling and benchmarking._

**Accounting, financial planning, and analytics**

Employers want to reduce manual labor by syncing payroll to accounting systems and performing financial analysis by teams or departments. Payroll data integrations make it possible to read data from and write data to financial systems.

Example: Mosaic, Causal, Jirav, Quickbooks

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2660_62f5a882bbbfc113656b343e_Quickbooks_Online_Eaxmple.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2660_62f5a882bbbfc113656b343e_Quickbooks_Online_Eaxmple.webp)

_See: Quickbooks integration in Gusto mapping payroll line items with general ledger accounts._

**Time management**

Employers use time tracking software to calculate payroll, sometimes as part of their payroll system and sometimes from external products. Integrating time management and payroll systems makes it easy to sync hours worked, tips accrued, and payroll paid.

Examples: Factorial, Deputy, Homebase, QuickBooks Time, When I Work

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2668_62f5a89fea32fe190678459f_Time_Management_Example.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2668_62f5a89fea32fe190678459f_Time_Management_Example.webp)

_See: Homebase integrates with ADP to export timecards for payroll processing._

**Consumer banking and lending**

Consumers can benefit from increased access to banking, lending, and credit products by connecting accounts to their work payroll provider. Payroll data enables income verification, employment verification, and garnishment for debt collection.

Examples: DailyPay, Branch

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2664_62f5a8b78499d80742cf9ecb_DailyPay_Example.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a7c4338c498d6b0c3c2664_62f5a8b78499d80742cf9ecb_DailyPay_Example.webp)

_See: DailyPay payroll advance powered by integration with ADP._

### Getting started with payroll APIs

Once you’re ready to kick the tires on integrating with a payroll provider, you’ll want to keep in mind a few additional topics:

- API format - REST, SOAP, etc.
- Authentication
- Pagination
- [Rate Limits](https://www.merge.dev/blog/what-is-api-rate-limiting)
- Test Accounts

We’ve built Merge to help make integrating with multiple payroll providers as easy as possible. Our [HR, Payroll, and Directory Unified API](https://www.merge.dev/categories-old/hr-payroll-api) is REST-based, and uses a standard approach to authentication, pagination, and rate limiting to make your development simple. Hundreds of companies use Merge to plug into payroll APIs, including the team at [Ramp](https://merge.dev/case-studies/) for compensation management.

If you're curious about learning more, reach out to our team for a [demo](https://merge.dev/get-in-touch/?utm_btn=dr-page-blog%2Fguide-to-payroll-api-integrations), or sign up and [get API access for free](https://app.merge.dev/signup), today.!

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1afbe4e2-adf0-42fa-bfbb-4d5c9cc8a386&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d67afb11-3bbf-44ef-a262-a4c461c3b7e9&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-payroll-api-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1afbe4e2-adf0-42fa-bfbb-4d5c9cc8a386&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d67afb11-3bbf-44ef-a262-a4c461c3b7e9&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-payroll-api-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=144d40ae-cc19-4790-b295-a9c56800334f&bo=2&sid=c3dc9d303e8d11f084a673f96caa2ed0&vid=c3dd07003e8d11f098605b4845ecfb6c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20payroll%20API%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-payroll-api-integrations&r=&lt=448&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=872587)