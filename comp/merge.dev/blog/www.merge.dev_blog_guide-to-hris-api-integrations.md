---
url: "https://www.merge.dev/blog/guide-to-hris-api-integrations"
title: "Guide to HRIS integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-hris-api-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-hris-api-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-hris-api-integrations#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-hris-api-integrations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c70df1981ff41ecb808_HR_API.webp)**HR API: what you should know about using any**](https://www.merge.dev/blog/hr-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**‍A guide to integrating with Workday’s API**](https://www.merge.dev/blog/workday-api-integration)

# Guide to HRIS integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadc1bfb5f5db30164e_Guide_to_HRIS_APIs.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

HR systems, also known as HRIS (Human Resources Information Systems) or HCM (Human Capital Management) systems, are common in every size of business, from just a few employees to hundreds of thousands. Whenever a company hires a person, it needs to onboard them into the organization, provision them with access to software (and possibly hardware), and set them up with payroll—among many other HR functions. Whenever a company separates with a person, it needs to deprovision software and hardware, track benefits, and possibly process severance.

The key to making all of this magic happen involves HR automation and HR _integrations_. As a key system of record in any company, HR systems are a common integration point for other software and business processes. This guide provides insights into HR systems, how their data and APIs are structured, and common integration use cases. For in depth information on Payroll APIs and integrations, see our [Guide to Payroll APIs](https://www.merge.dev/blog/guide-to-payroll-api-integrations).

Read on for a guide to HR APIs to learn about:

- **HRIS integration overview -** What the definition is
- **Top HR APIs** \- Which providers matter most
- **Key concepts** \- How HR systems work
- **Data schemas** \- How various providers organize HR data
- **Use cases** \- Common ways HR data is used in product integrations
- **Benefits -** Top benefits of HRIS integration
- **How to get started** \- Approaching HR API integrations within your own product

### **What is an HRIS integration?**

It’s the process of scoping, building, and/or maintaining integrations between your HRIS and another application. The integrations can either be customer-facing, meaning that you connect your product to 3rd-party HRIS providers; or they can be for internal use cases, where you connect your HRIS solution with another one of your applications.

‍

[![The applications of HRIS integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65403c8338668fafce913964_-ebuRvoVjaQjVsm0CQzcadInvP4GBXKOU3-bukLt2iKiNOmW0mqK3VrI1_GdfBT8Dsn6gQ614yZa3Y7_oICjRXsDa5-Hp_yUKuQP4g_jZniu3C6MvzhV125sM9UQQtNlPhBk1BHePEwrelIQd13CUzQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65403c8338668fafce913964_-ebuRvoVjaQjVsm0CQzcadInvP4GBXKOU3-bukLt2iKiNOmW0mqK3VrI1_GdfBT8Dsn6gQ614yZa3Y7_oICjRXsDa5-Hp_yUKuQP4g_jZniu3C6MvzhV125sM9UQQtNlPhBk1BHePEwrelIQd13CUzQ.webp)

_HRIS integration can apply to one of two scenarios: connecting HRIS applications with your product or connecting an HRIS application with another one of the applications you use internally._

#### Integrate with every HRIS through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of HRIS solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-hris-api-integrations)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Top HRIS APIs

HR systems vary widely in their functionality and target markets, making comparison of the biggest HR systems challenging. Functionality differs in that some platforms focus on just HRIS/HCM, while others include some combination of payroll, benefits, PEO (professional employer organization), and recruiting capabilities. In particular, products that focus on payroll and PEO for SMBs (e.g. Trinet, Gusto) have much larger customer counts than enterprise-focused HCMs (e.g. Workday, SAP SuccessFactors).

Now that you have a sense of the boundaries of each domain, let’s dive into which actual HRIS and directory software you’ll want to build integrations with.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e300fcb7026ba378735474_6467c1a3eccdcd7a25fe5eb5_Top%2520HRIS%2520Providers%2520by%2520Customers.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e300fcb7026ba378735474_6467c1a3eccdcd7a25fe5eb5_Top%2520HRIS%2520Providers%2520by%2520Customers.webp)

Source: Company websites and annual filings

_Related:_ [_A guide to HR integrations_](https://www.merge.dev/blog/hr-integration)

### HRIS API key concepts and data schemas

If you're looking to integrate with an HR system, the first record you'll usually want is Employees. [Employees](https://merge.dev/docs/hris/employees) typically include all full-time workers, part-time workers, and contractors. Demographic information (birthdates, government IDs), manager, employment status, start date, and termination date are commonly referenced fields on the employee object. Addresses are often stored as an array of ‘Locations’ objects.

[Groups](https://docs.merge.dev/hris/groups/) represent any subset of employees, such as pay groups, teams, departments, and cost centers. Employees can be in multiple Groups, so you'll want to sort by group type depending on your use cases.

Each employee has one or many [Employments](https://merge.dev/docs/hris/employments) that define their current roles and compensation. This includes job title, pay rate and frequency.

[Time Off](https://docs.merge.dev/hris/time-off/) represents all employees' Time Off entries. [Time Off Balances](https://docs.merge.dev/hris/time-off-balances/) represent current balances for an employee's Time Off plan.

Additional payroll-specific information is also available. Check out our [Guide to Payroll APIs](https://www.merge.dev/blog/guide-to-payroll-api-integrations) for more.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e300fdb7026ba37873547f_6467c61ff96be0f42c23e9db_Table%2520-%2520HRIS%2520by%2520Data%2520Schema.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e300fdb7026ba37873547f_6467c61ff96be0f42c23e9db_Table%2520-%2520HRIS%2520by%2520Data%2520Schema.webp)

### Top HRIS API use cases

**Hiring new employees**

Applicant tracking systems and background check systems are often integrated with HR systems to add new employees upon hiring.

Examples: Checkr, Greenhouse, Lever

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b159c99ecf0abfbaccdf_657375a3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b159c99ecf0abfbaccdf_657375a3.webp)

Greenhouse integrates with Zenefits to export new hire information directly into the HR system.

**Employee onboarding and offboarding**

When full-time or part-time users are onboarded to a new company they need to set up payroll, bank account, tax status, and deduction information so that they can get paid. When they are offboarded, most of these services need to be terminated.

Examples: Deel, Navan, Paylocity, Sapling, Zavvy

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b7e52e72090ed73d6769_7f29c330.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b7e52e72090ed73d6769_7f29c330.webp)

Navan (Tripactions) keeps their user list up-to-date with HR provisioning and deprovisioning.

‍

**User provisioning and deprovisioning**

Systems such as identity management, compliance management, rewards and recognition software, travel management, and expense management need to have up-to-date records of employees. Integrations with HR systems make it possible to track which employees are active and should be tracked in these other services.

Examples: Bonusly, Culture Amp, Drata, Expensify, Gifted, Google, Jumpcloud, Kudos, Microsoft, Navan, Okta, Secureframe, Vanta

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1814fc5505753b01fee_2a8e20b8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1814fc5505753b01fee_2a8e20b8.webp)

Bonusly integrates with Gusto to maintain an up-to-date employee roster.

_Related:_ [_Everything you need to know about auto-provisioning_](https://www.merge.dev/blog/automated-provisioning)

**Org structures, teams, and managers**

Performance and learning management software integrates with HR systems to keep employee records, org structures, and manager relationship data up to date.

Examples: 15five, Assembly, Lattice, Northpass, Small Improvements, TalentLMS

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1a2aba1530ac52c1b1a_c9ff39b7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1a2aba1530ac52c1b1a_c9ff39b7.webp)

Gusto integrates with Lattice to sync employee records continuously.

**Staffing, time, and time off management**

Time tracking software commonly integrates with HR systems to maintain an updated employee roster and to sync hours worked, shift schedules, and time off information.

Examples: Factorial, Deputy, Homebase, QuickBooks Time, When I Work

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1bf7ae0105bb4cbe104_ed4c77d5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6467b1bf7ae0105bb4cbe104_ed4c77d5.webp)

Deputy integrates with BambooHR to sync time off data and employee records.

_Related:_ [_Examples of recruiting integrations_](https://www.merge.dev/blog/recruiting-integration)

### **HRIS integration benefits**

Here are some of the benefits of HRIS integrations:

#### **Prevents human errors**

Forcing your employees or clients to copy and paste information to and from an HRIS solution manually can introduce a host of costly errors.

This can be provisioning employees with the wrong level of access to an application, which, in turn, allows them to access data and actions in that app that’s not meant for them; it can be marking an employee as part-time when they’re actually full-time, which prevents them from receiving emails about their benefits, stock options, etc.; or it can be putting the wrong home address for an employee, which can lead to equipment being shipped out to the wrong location and getting lost—and the list goes on.

Since HRIS integration streamlines data entry, your employees or clients don’t have to worry about any of the negative outcomes described above.

#### **Provides a great customer experience**

By allowing clients to automatically sync employee data with your product, you can provision new users on time and without any friction; ensure that every user has the correct set of permissions in your product; set off the appropriate workflows for each user; remove users or adjust their access to your product based on the corresponding changes in the client’s HRIS, etc.

All of this translates to happier clients that are more engaged in your product and are more likely to renew and spend more on you.

#### **Delivers an improved employee experience**

Enabling employees to avoid copying and pasting data between applications not only prevents them from carrying out tedious, mundane work but also lets them focus on tasks they enjoy and are uniquely positioned to tackle. And by letting employees focus on more interesting, strategic work, they can be happier at your organization—making them [more productive](https://www.ox.ac.uk/news/2019-10-24-happy-workers-are-13-more-productive).

#### **Offers scalability**

From using a [unified API](https://www.merge.dev/blog/universal-api), you can simply build to a single API to offer dozens of customer-facing HRIS integrations. This limits the time your developers have to spend on building your integrations and it ensures you’re able to offer all the integrations your clients and prospects need.

[![A visual of how universal APIs work](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ca89b1e6bb722305f6c535_IvIinQ4nKOc_1L7fJBA5ZGmshyjB5ZS-Y7dLfMhI3dSOYGfxXzPa6aKR4PJfnC590aN7vkkv4Tr5h4BZo9OcGrgvd6sHje7phP8sg9hYhEc80RNG-RE7fI3OfVvIuxVjQYNQiPQcgq-JR9v8Zg4WP1ISQQ%3Dnw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ca89b1e6bb722305f6c535_IvIinQ4nKOc_1L7fJBA5ZGmshyjB5ZS-Y7dLfMhI3dSOYGfxXzPa6aKR4PJfnC590aN7vkkv4Tr5h4BZo9OcGrgvd6sHje7phP8sg9hYhEc80RNG-RE7fI3OfVvIuxVjQYNQiPQcgq-JR9v8Zg4WP1ISQQ%3Dnw.webp)

_Using Merge’s_ [_HRIS Unified API_](https://www.merge.dev/categories/hr-payroll-api) _, you can access 50+ HRIS integrations_

In addition, the [unified API solution](https://www.merge.dev/what-is-a-unified-api) can make the process of managing and performing maintenance on these integrations easy by offering fully-searchable logs and features like automatic issue detection.

[![A screenshot of a bad API key error message from Merge's Dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)

_You can automatically identify specific integration issues and uncover the steps to remediate them in Merge’s Dashboard_

### Getting started with HRIS APIs

When you're planning out your HR integrations, keep in mind the following considerations:

- API format - Which standards do the underlying APIs support (REST, SOAP, etc.)
- Authentication - Which auth methods each API uses (e.g. OAuth, basic auth, etc.)
- Pagination and rate limits - How large responses are accessed in each API
- Test Accounts - How to access sandboxes for each API

We’ve built Merge to help make integrating with multiple HR providers as easy as possible. Our [Unified HR & Payroll API](https://www.merge.dev/categories/hr-payroll-api) is all REST-based, with one type of authentication, pagination, rate limiting, and automated issue detection to make development simple. Hundreds of companies use Merge to plug into HR APIs, including [Ramp](https://www.merge.dev/case-studies/ramp) and [Drata](https://merge.dev/case-studies/how-drata-helps-thousands-of-companies-streamline-their-soc2-compliance-with-merge).

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