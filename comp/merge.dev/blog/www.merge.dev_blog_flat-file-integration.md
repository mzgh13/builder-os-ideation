---
url: "https://www.merge.dev/blog/flat-file-integration"
title: "Flat file integration: here’s everything you need to know"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/flat-file-integration#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/flat-file-integration#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/flat-file-integration#)

Table of contents

[What is a flat file?](https://www.merge.dev/blog/flat-file-integration#what-is-a-flat-file)

[What is flat file integration?](https://www.merge.dev/blog/flat-file-integration#what-is-flat-file-integration)

[Examples of flat file integration](https://www.merge.dev/blog/flat-file-integration#examples-of-flat-file-integration)

[Benefits of flat file integration](https://www.merge.dev/blog/flat-file-integration#benefits-of-flat-file-integration)

[Drawbacks of flat file integration](https://www.merge.dev/blog/flat-file-integration#drawbacks-of-flat-file-integration)

[When to integrate with flat files](https://www.merge.dev/blog/flat-file-integration#when-to-integrate-with-flat-files)

[Build secure and performant integrations at scale with Merge](https://www.merge.dev/blog/flat-file-integration#build-secure-and-performant-integrations-at-scale-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fflat-file-integration)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**7 examples of using webhooks**](https://www.merge.dev/blog/webhook-examples)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c76049139dc5bc6bf16_White_label_API_integration.webp)**Integration outsourcing: when and how you should pursue it**](https://www.merge.dev/blog/outsourcing-integration)

# Flat file integration: here’s everything you need to know

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cef5c33a545135e9dde_How_to_get_your_ChatGPT_API_key.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As your organization looks to integrate applications, one of the methods at your disposal includes flat files.

To help you evaluate this integration method for any of the scenarios you’re considering, we’ll break down how it works, its use cases, its pros and cons, and more.

But first, let’s align on what a flat file is.

## **What is a flat file?**

It’s any human-readable file that contains specific records and uses a delimiter (e.g., commas) to separate the records’ fields.

Flat files can take various forms, including comma separated value (CSV) files, text files (TXT), and tab-separated values (TSV) files. They can also store a wide range of records, from customer orders to employee information.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6602ee6c5f8175b056357adf_tX0Qk2QqIC0293udDqGg9MGPkZ6WzTiWN3vElqoQ7PX9xdQBIqN3dN2WD1K_uuU39Wp9otID_D2flNTtKnpOzRG0FNrCK_jzc8TshiFGUmnlaNnc-Sogb5jDCtkutbw_tRQAlNDifBnuReiGtHYgaD8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6602ee6c5f8175b056357adf_tX0Qk2QqIC0293udDqGg9MGPkZ6WzTiWN3vElqoQ7PX9xdQBIqN3dN2WD1K_uuU39Wp9otID_D2flNTtKnpOzRG0FNrCK_jzc8TshiFGUmnlaNnc-Sogb5jDCtkutbw_tRQAlNDifBnuReiGtHYgaD8.webp)

‍

## **What is flat file integration?**

It’s the use of flat files to sync data between applications. This involves exporting a file from one system (“source system”), transforming and validating its data, and then importing it to another system (“destination system”), where the data can be processed and added to the appropriate places.

[![Flat file integration overview](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc7b83f9a01b80be14b_pD1YRG8lXZzyxlKU1kFRGyer84exgkbg3nOorBzS4xlP7RRGliij7v7nKxcQTlvPM3tKef_rwjEbhfqP0d_b6-z6of4zA17PUpD-XLz7XCbdN26kdJy9v8XaJUo4HZmdeQwFomfEr2xOpo-2t_Ma2Ak.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc7b83f9a01b80be14b_pD1YRG8lXZzyxlKU1kFRGyer84exgkbg3nOorBzS4xlP7RRGliij7v7nKxcQTlvPM3tKef_rwjEbhfqP0d_b6-z6of4zA17PUpD-XLz7XCbdN26kdJy9v8XaJUo4HZmdeQwFomfEr2xOpo-2t_Ma2Ak.webp)

### **Flat file integration vs API integration**

It’s easy to confuse file-based integrations with a popular alternative option— [API-based integrations](https://www.merge.dev/blog/api-integration). Their difference is simply in how the applications are connected. The former uses files to connect applications while the latter uses the applications’ underlying APIs.

_Related:_ [_The differences between flat file integration and API integration_](https://www.merge.dev/blog/flat-file-integration-vs-api)

## **Examples of flat file integration**

We’ll cover a few common internal and customer-facing flat file integrations.

### **Add newly-signed customers to your accounting system**

Your accounting team needs to become aware of new clients quickly so that they can begin the work of adding them into their system and invoicing them with little delay.

To help them do just that, you can implement a flat file integration that works as follows:

[![Flat file integration between Salesforce and NetSuite](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc8779e526717c0fbe9_471r6SoUwS245e_Ymg7s4w76k49GlFLHpRV0e7z1ZLswgedoOIn8m3jRH13SuM1zs9QmhrNHFXF_DgHth-fHad_oN9fDzzP8lY_Zrs0WVNmm-LuX3i1OlJX6IsUlrwWVoVxpGT4boOdEmRKXuUOPu1k.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc8779e526717c0fbe9_471r6SoUwS245e_Ymg7s4w76k49GlFLHpRV0e7z1ZLswgedoOIn8m3jRH13SuM1zs9QmhrNHFXF_DgHth-fHad_oN9fDzzP8lY_Zrs0WVNmm-LuX3i1OlJX6IsUlrwWVoVxpGT4boOdEmRKXuUOPu1k.webp)

‍

1\. A flat file is exported from your CRM every 24 hours with all the clients who signed that day. The file also includes specific details on each client, such as the terms of their contracts and their billing information.

2\. The file’s data format is transformed via a script to meet the data model your ERP system accepts.

3\. Once transformed, the flat file is imported into the ERP system, where the clients’ data is processed and used to create new client accounts and corresponding invoices.

### **Keep critical employee records securely stored and easily accessible**

As you add and edit employee data in your HRIS, you can back up their information in your file storage system, where it can also be kept secure and easy to access for the appropriate stakeholders.

To facilitate this use case, you can build the following integration:

[![Flat file integration between Workday and Box](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc712fca32e8b9b3a45_PkRpgathk8tbtnYaOfESugSUXnR3G6kvzfFfAAExQxPAGz6iIgSWvMouxBLspumJ3QxRayd-STvfWedoW95PH6rgYNr7HPs9eNK_lAX5a0ILr9gPIOA1RPGaD-DEagryjx6gKmcQ4G4Mi7PV6VfjC20.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc712fca32e8b9b3a45_PkRpgathk8tbtnYaOfESugSUXnR3G6kvzfFfAAExQxPAGz6iIgSWvMouxBLspumJ3QxRayd-STvfWedoW95PH6rgYNr7HPs9eNK_lAX5a0ILr9gPIOA1RPGaD-DEagryjx6gKmcQ4G4Mi7PV6VfjC20.webp)

1\. A flat file is exported from your HRIS every 24 hours with key information on your employees, from employees’ full names to their social security numbers to their addresses.

2\. The file is imported into your file storage platform, where it’s processed.

3\. If there are new employees, new files get created in the file storage system for them; if an existing employee’s information has changed since the last import, their information is updated in the file storage system; and if there are no changes for an existing employee since the last import, their information is left unchanged in the file storage system.

### **Enable clients to auto provision and deprovision users in your product**

To help clients add and remove users in your product, as well as modify permissions based on changes to a user's role, you can build the following flat-file integration:

[![File integration for auto-provisioning users in your product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc789b54bab92520896_NeS8I5Gt4nCgDdtLLdowMeskc9zPqa9rrhVWMBK7DJ40eIaoQNuLXtb0OjeBXZyBnirTeTdY6GuubzLmAzoD7mfv2J5sPBFInnzMtXXlX4zeQrgPjruXoomdlGHGpI049akgC6mKrGAa8sLtw-POeOc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d4dcc789b54bab92520896_NeS8I5Gt4nCgDdtLLdowMeskc9zPqa9rrhVWMBK7DJ40eIaoQNuLXtb0OjeBXZyBnirTeTdY6GuubzLmAzoD7mfv2J5sPBFInnzMtXXlX4zeQrgPjruXoomdlGHGpI049akgC6mKrGAa8sLtw-POeOc.webp)

1\. Once a day, a client’s file is exported from their HRIS with all the employees in their HRIS.

2\. The file’s data format is transformed via a script to match the data format of users in your product.

3\. The file is imported into your product. New employees in the file are automatically added as users in your product and are assigned the appropriate level of permissions; employees who aren’t included in the file are removed as users in your product; and employees whose information has changed since the last import are updated accordingly in their user profile—which could potentially change their level of permissions.

_Related:_ [_A guide to automated provisioning_](https://www.merge.dev/blog/automated-provisioning)

## **Benefits of flat file integration**

Here are just a few reasons to adopt flat file integrations.

### **Universally accessible**

Most applications, regardless of where they’re hosted or the use cases they support, can export and import flat files. As a result, you'll likely be able to rely on flat file integrations across all the  scenarios you’re interested in.

### **Supports a wide range of data**

Flat files can store and sync nearly every type of data you’re interested in—from employee records to financial information. As a result, it can support a broad range of integration use cases.

### **Syncs data efficiently**

Since files can store a high volume of information, they can integrate data in batches efficiently. In other words, whatever your cadence looks like for integrating data, the files can transfer all the information at once.

## **Drawbacks of flat file integration**

Unfortunately, flat file integrations aren’t without their flaws.

### **Complex to implement and maintain**

Whatever method you use to build and maintain the file integrations—scripts or an integration middleware tool—you’ll need your engineers heavily involved throughout their life cycles. This can prove to be time and resource intensive for them, especially when you need to scale your integrations.

### **Lack of real or near real-time syncs**

In many cases, you’ll need data to move between systems as quickly as possible, whether that’s  routing leads to sales reps, sending escalated tickets to engineering, and so on.

Since flat file integrations can’t sync data faster than a few minutes (at best), it may not support your time-sensitive use cases effectively.

### **Security risks**

While a file gets transferred, it can be vulnerable to data leakage, especially if you aren’t using a measure like Secure File Transfer Protocol (SFTP). Assuming you’re integrating sensitive data, like employees’ or clients’ personal information, your organization can potentially face reputational and financial damage.

_Related:_ [_How API and SFTP integrations compare_](https://www.merge.dev/blog/sftp-vs-api-integrations)

## **When to integrate with flat files**

Given all these pros and cons, you’re likely wondering when it makes sense to [integrate systems](https://www.merge.dev/blog/system-integration) via files.

The answer largely depends on the applications you’re looking to connect and the specific requirements for the integration. Let’s take a closer look at these factors.

### **Endpoint accessibility**

You might find that the applications you want to connect don’t offer APIs; or they might offer APIs but not the specific API endpoints you care about. In either scenario, you’re left with no option but to integrate the applications through other means, such as files.

It’s also worth noting that even if an application supports the endpoints you care about, the quality of their documentation on those endpoints (and on their APIs more broadly) can be insufficient, out of date, or difficult to find. If you find yourself in any of these positions, it can also be worth using flat files instead of APIs.

### **Syncing frequency**

Since flat file integrations can’t sync data frequently, you’ll need to review your processes and prioritize the ones that sync data once every few hours, days, weeks, etc. for flat file integrations.

While it obviously depends on the nature of your business and how, exactly, your team wants certain processes to run, this can take the form of updating employee information in your HRIS, adding data to your business intelligence platform, revising inventory data in your e-commerce solution, etc.

### **Simple data syncs**

If the files you’re syncing don’t require significant data transformations and their records aren’t likely to change much, if at all, over time, then using flat files can make sense.

That said, the scenarios that meet these requirements are few and far between. Most types of data consistently evolve in unpredictable ways, and some level of data transformation is generally needed, as applications often use different data formats and schemas.

## **Build secure and performant integrations at scale with Merge**

Merge allows you to add hundreds of integrations to your product by simply building to a single unified API.

Moreover, using Merge, you can:

- Use webhooks to sync data with your product in real-time
- Enable your customer-facing employees to diagnose, troubleshoot, and resolve clients’ integration issues quickly and independently
- Save your engineers from maintaining your integrations—as Merge maintains them on your behalf

Learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fflat-file-integration).

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

[iframe](https://app.qualified.com/w/1/faa5v4dWtZ1a9fXx/messenger?uuid=9a7ad9a4-6e88-4b5d-8e2b-47d68fefc9d5)

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1e8e3819-47d2-4eaf-9dbf-0a1ef0aabd2c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=9bf62fc6-69ef-4eb0-8de5-7f80b4f8ad7f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fflat-file-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1e8e3819-47d2-4eaf-9dbf-0a1ef0aabd2c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=9bf62fc6-69ef-4eb0-8de5-7f80b4f8ad7f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fflat-file-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743698149&cv=11&fst=1748743698149&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2h1v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fflat-file-integration&_ng=1&hn=www.googleadservices.com&frm=0&tiba=Flat%20file%20integration%3A%20here%E2%80%99s%20everything%20you%20need%20to%20know&npa=0&pscdl=noapi&auid=1295168273.1748743698&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743698296&cv=11&fst=1748743698296&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2h1v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fflat-file-integration&_ng=1&hn=www.googleadservices.com&frm=0&tiba=Flat%20file%20integration%3A%20here%E2%80%99s%20everything%20you%20need%20to%20know&did=dZTQ1Zm&gdid=dZTQ1Zm&npa=0&pscdl=noapi&auid=1295168273.1748743698&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0de739d6-183f-4d45-8b65-c527fc90b92c&bo=2&sid=48dc77303e8d11f0a94635a4c8a1cdf9&vid=48de0d703e8d11f0bc891f2f171b5e50&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Flat%20file%20integration%3A%20here%E2%80%99s%20everything%20you%20need%20to%20know&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fflat-file-integration&r=&lt=518&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=492488)