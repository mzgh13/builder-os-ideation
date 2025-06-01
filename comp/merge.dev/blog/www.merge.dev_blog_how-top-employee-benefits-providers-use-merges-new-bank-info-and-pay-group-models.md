---
url: "https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models"
title: "How top employee benefits providers use Merge’s new Bank Info and Pay Group models"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#)

Table of contents

[What even is a Pay Group? How to Use the Pay Groups Endpoint](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#what-even-is-a-pay-group-how-to-use-the-pay-groups-endpoint)

[How To Use the Bank Info Endpoint](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#how-to-use-the-bank-info-endpoint)

[Use Cases For Bank Info Endpoints](https://www.merge.dev/blog/how-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models#use-cases-for-bank-info-endpoints)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models)

##### Just for you

No items found.

# How top employee benefits providers use Merge’s new Bank Info and Pay Group models

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c76e1896d1b5abd82c0_How_to_fetch_Users_from_Okta_with_Merge_HRIS_Unified_API_using_JavaScript.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53853af779c6de1fabd7_62eff9857d098c1325724163_ria.webp)

Ria Garg

Platform

@Merge

Merge Platform is excited to announce the addition of two new common models to our Unified HRIS API: [Pay Group](https://docs.merge.dev/hris/pay-groups/) and [Bank Info](https://www.merge.dev/docs/hris/bank-info#_). After receiving countless customer requests for added support around payroll, these new models will be a welcome addition for any service looking to build in the employee benefits space.

## **What even is a Pay Group? How to Use the Pay Groups Endpoint**

With our additional models, customers now can link employees to a specific Pay Group within any HR or Payroll platform. If an organization groups employees for payroll reasons (contractor vs. salaried, etc.), this field can be used to make that distinction. By offering this label we hope our Pay Groups endpoint will simplify creating payroll runs.

The pay group model returns a single field: pay group name.

_Related:_ [_Common benefits of implementing software integration_](https://www.merge.dev/blog/software-integration)

## **How To Use the Bank Info Endpoint**

If you need to access an employee’s bank account in order to make payments or deposit money on their behalf, then [Bank Info](https://www.merge.dev/docs/hris/bank-info#bank-info-object) can be used to record bank accounts for customers. The bank info object returns the following fields which allow you to access the specifics of a user’s accounts:

- account number
- routing number
- employee id
- bank name
- remote created at

With our Unified API, you can link as many bank accounts per user as necessary!

## Use Cases For Bank Info Endpoints

To help you better understand these two new models, we’ll walk through a quick list of how companies can utilize these new data objects.

**Purchase on Employee's Behalf**

- Use the account information returned in **bank info** to make transactions on an employee's behalf in order to purchase certain benefits or rewards points.

**Reliably Link to Bank Accounts**

- Use **bank info** to manage cash for customers. You can take the fields returned in bank info to link to customer bank accounts directly, allowing you to easily transfer funds on an end-users behalf.

**Regulate Pay Rate**

- If you are a company that manages _how_ an employee gets paid, then you need to manage employees' bank accounts to regulate how they get paid. The **bank info** model tracks employee bank account information regardless of the platform they use.

### **Pay Groups for all**

- You can use the Pay Group endpoint as a flag to group different cohorts of employees. For example, if you have multiple groups of employees that began work on different dates – such as a cohort that began in January versus September – and they need to be paid in different intervals you can usepay group to programmatically group these employees.
- You can group different employment types into Pay groups **:** contractor, interns, salaried employees, or more.

If you have any questions on how to use the added fields, Merge is always here to answer questions. Feel free to reach out over Intercom or email hello@merge.dev.

If you want to test out these common models for yourself: sign up for a [free account today](https://app.merge.dev/signup) and start using Merge. If you’re best served with a hands-on demo, then we’re happy to chat [here](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models)!

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7f86b5b2-a6fe-4aaf-997f-1792c24d2023&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ab4fce35-40a4-4c9e-8683-045daa47d292&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7f86b5b2-a6fe-4aaf-997f-1792c24d2023&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ab4fce35-40a4-4c9e-8683-045daa47d292&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=fbc941a8-c0b2-41e1-b878-5ad1a17ce8af&bo=2&sid=143bfc103e8d11f0970a978cb76e3573&vid=143c2b903e8d11f0b094a7d520139d0b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20top%20employee%20benefits%20providers%20use%20Merge%E2%80%99s%20new%20Bank%20Info%20and%20Pay%20Group%20models&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-top-employee-benefits-providers-use-merges-new-bank-info-and-pay-group-models&r=&lt=586&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=389028)