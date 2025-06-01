---
url: "https://www.merge.dev/blog/api-polling-examples"
title: "Common examples of API polling"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-polling-examples#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-polling-examples#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-polling-examples#)

Table of contents

[What is API polling?](https://www.merge.dev/blog/api-polling-examples#what-is-api-polling)

[API polling examples](https://www.merge.dev/blog/api-polling-examples#api-polling-examples)

[Poll hundreds of 3rd-party API endpoints with Merge](https://www.merge.dev/blog/api-polling-examples#poll-hundreds-of-3rd-party-api-endpoints-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-polling-examples)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cef5c33a545135e9dde_How_to_get_your_ChatGPT_API_key.webp)**7 API logging best practices worth implementing**](https://www.merge.dev/blog/api-logging-best-practices)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API error handling: definition, example, best practices**](https://www.merge.dev/blog/api-error-handling)

# Common examples of API polling

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c750ee25c62b0a40a3d_Two-way_API_integration.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you build integrations, you’ll likely look to poll certain API endpoints to ensure that specific data is constantly synced between the connected systems.

Deciding on the best frequency to poll these endpoints, however, isn’t always clear.

To help you pick the right polling cadence for your integration use cases, we’ll walk through several scenarios. But before we do, let’s align on the definition of API polling.

## **What is API polling?**

It’s when a client makes repeated API requests to a specific endpoint in order to read a specific resource. These requests are normally repeated on a specific time interval, but they can be randomized as well.

‍

[![A visual illustration of API polling](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e39dc1a73a2a2a1a0f_Gm3CiQvKkm5X6mCayaVmzahlkLFNDsVW5aZpnThSii37Z5xRyGLgllyvDIxxOyTsKFAq0nEnGRdDbd7cm_d07MM4cP0vtqy549S6Mo6HAjoUPyEYvwgAyBYxAedi6K6V3jZjrvL1Xv4UIohExA5BV3g.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e39dc1a73a2a2a1a0f_Gm3CiQvKkm5X6mCayaVmzahlkLFNDsVW5aZpnThSii37Z5xRyGLgllyvDIxxOyTsKFAq0nEnGRdDbd7cm_d07MM4cP0vtqy549S6Mo6HAjoUPyEYvwgAyBYxAedi6K6V3jZjrvL1Xv4UIohExA5BV3g.webp)

_Related:_ [_API polling best practices_](https://www.merge.dev/blog/api-polling-best-practices)

## **API polling examples**

We’ll cover both internal and customer-facing examples.

### **Sync leads between your CRM and marketing automation tool every few minutes**

As your marketing team acquires and nurtures leads, your sales reps need to be notified quickly whenever a prospect becomes a sales qualified lead and is ready to be contacted by a rep. That way, the rep can reach out while the prospect is warm and more likely to take a meeting.

To help sales identify and follow-up with sales qualified leads quickly, you can connect your marketing automation system with your CRM and poll the leads endpoint in your marketing automation tool on a frequent cadence, such as every 5 minutes. This can return any new leads that have been added within the last 5 minutes to your CRM, as well as update various fields—including the leads’ scores.

‍

[![API polling example for syncing leads](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3c2e57acabd4b4fc7_J0emVSzdm6vl2hltQzd0nVus1Cjg4axFh7Cff9-mD8HbxBZM8gNVXFJcxh8jw-c1hURDpKl_nk_ac4xv7ancXxLeoNxkBnJBPd5pO3udy5rOiDOLgMgS0Oe5ypI95zBmIy4Ciq-RSjUwyJHQlYtODr4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3c2e57acabd4b4fc7_J0emVSzdm6vl2hltQzd0nVus1Cjg4axFh7Cff9-mD8HbxBZM8gNVXFJcxh8jw-c1hURDpKl_nk_ac4xv7ancXxLeoNxkBnJBPd5pO3udy5rOiDOLgMgS0Oe5ypI95zBmIy4Ciq-RSjUwyJHQlYtODr4.webp)

### **Sync invoices between your CRM and your ERP system every few hours**

As finance invoices a client, the associated customer success manager (CSM) likely wants to be made aware in case an invoice isn’t paid on time and/or in full.

And while CSMs should be made aware of invoicing issues quickly, alerting them within minutes or even hours might not necessarily influence the desired outcome (i.e., the client pays the invoice in full).

With this in mind, you can integrate the ERP system finance uses to invoice clients with the CRM your CSMs use to manage clients. You can then poll the ERP systems’ invoices endpoint every few hours so that your CRM can retrieve newly-created and updated invoices.

[![API polling example for syncing invoices](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e2a8d7833ec63438bd_13ItYRCeZH_vRpnbvsQgazgppRubyzQtJp7B042KscszBAdaNEY3w2-i4gJ-c5Tc2l8jkoFfwmkhbNmPiIeZ54gqWYbr9z9UNN52tcLxn8NfFVbMe8wNUeJxLUyznAziiSNHtiyr__SrXdLtIfi24K4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e2a8d7833ec63438bd_13ItYRCeZH_vRpnbvsQgazgppRubyzQtJp7B042KscszBAdaNEY3w2-i4gJ-c5Tc2l8jkoFfwmkhbNmPiIeZ54gqWYbr9z9UNN52tcLxn8NfFVbMe8wNUeJxLUyznAziiSNHtiyr__SrXdLtIfi24K4.webp)

_Related:_ [_A guide to choosing between webhooks and polling_](https://www.merge.dev/blog/webhooks-vs-polling)

### **Sync employee data with your product on a daily cadence**

As your clients add and remove employees in their HRIS solutions, you’ll want your product to keep up with the changes effectively. More specifically, once a new hire is added to a client’s HRIS solution, they should be provisioned in your product seamlessly and quickly; and as soon as an employee is taken off of a client’s HRIS solution, they should be removed from your product automatically.

To enable these workflows, you can connect your product with clients’ HRIS solutions and poll the solutions’ employee endpoints on a daily cadence. Based on the changes made in the last 24 hours, you can identify new employees that need to get added, departing/departed employees that need to be removed, and employees who’ve changed roles.

[![API polling example for syncing employees](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3974cac6fe20df7d3_LFf9Auj4H6MfHdMtXuq4T6J8uawW788ezv_HBn9l7uiIzdumSG3e9jGtLwdoYIrR79y6jrsV_UzWa4uauJgYshgpqqS_Kq3j1csL8fnpnGPGZq18glvqmc-G9uvkMSjE7h3KpuJ3wRk5MtERuQwOf2c.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3974cac6fe20df7d3_LFf9Auj4H6MfHdMtXuq4T6J8uawW788ezv_HBn9l7uiIzdumSG3e9jGtLwdoYIrR79y6jrsV_UzWa4uauJgYshgpqqS_Kq3j1csL8fnpnGPGZq18glvqmc-G9uvkMSjE7h3KpuJ3wRk5MtERuQwOf2c.webp)

### **Sync your clients’ files with your product every few minutes**

Say you offer a product that allows users to search for and find valuable information on their employer (i.e. employee intranet). Let’s also assume that your clients value accessing highly recent information, as their files constantly change.

To ensure your product provides users up-to-date, comprehensive information over time, you can integrate your product with clients’ file storage systems and poll the latter system’s files endpoint every 5 minutes. That way, you can not only retrieve documents that have been created and updated every few minutes but also identify files that have just been deleted.

[![API polling example for syncing files](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3170bbf1eb4f8d0a8_SdWLNcBlSlHieTtZAggp7_WNsVYHlvDS7QPIddbCg6YmxdZ7TFdIV9JDHdOMl1iHcGifA_jBPu5E0ksGSPQMl_99VMVr_s2UmmeuG_mSFMURV5aVBH9QriWFDB80Zccd2uGPrsMB5vaVXB7CqbrrosY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65bac4e3170bbf1eb4f8d0a8_SdWLNcBlSlHieTtZAggp7_WNsVYHlvDS7QPIddbCg6YmxdZ7TFdIV9JDHdOMl1iHcGifA_jBPu5E0ksGSPQMl_99VMVr_s2UmmeuG_mSFMURV5aVBH9QriWFDB80Zccd2uGPrsMB5vaVXB7CqbrrosY.webp)

_Related:_ [_A guide to API integration security_](https://www.merge.dev/blog/api-integration-security)

## **Poll hundreds of 3rd-party API endpoints with Merge**

Merge, a single API that lets you add hundreds of integrations to your product, offers flexible sync frequencies, whether that’s near real-time (via 3rd-party webhooks), every few minutes, daily, or monthly—all but ensuring our integrations meet your business’ needs.

We also offer integration observability features to help your CSMs identify, troubleshoot, and resolve integration issues, and we provide maintenance support to keep your integrations running reliably.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-polling-examples).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=59ad3cd8-9005-4b85-beee-4c84976b1286&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d2ff1b7b-d525-47ad-b128-eeb378ea7092&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-examples&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=59ad3cd8-9005-4b85-beee-4c84976b1286&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d2ff1b7b-d525-47ad-b128-eeb378ea7092&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-examples&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=dc7758fa-94d9-4801-a27e-06392e861d41&bo=2&sid=52bd26303e8c11f0babe37d4f384e666&vid=52bdf1103e8c11f08d099f2411f8b0ea&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Common%20examples%20of%20API%20polling&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-polling-examples&r=&lt=510&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=11567)