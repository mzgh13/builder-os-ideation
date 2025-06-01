---
url: "https://www.merge.dev/blog/lead-api"
title: "A guide to using Lead APIs (with examples from Pipedrive)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/lead-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/lead-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/lead-api#)

Table of contents

[What is a lead API?](https://www.merge.dev/blog/lead-api#what-is-a-lead-api)

[Lead API examples](https://www.merge.dev/blog/lead-api#lead-api-examples)

[Sync leads between your product and CRMs at scale with Merge](https://www.merge.dev/blog/lead-api#sync-leads-between-your-product-and-crms-at-scale-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Flead-api)

##### Just for you

No items found.

# A guide to using Lead APIs (with examples from Pipedrive)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cede4e321d978c2aa62_Lead_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

While it depends on the type of product you offer, building API integrations between your product and your clients' CRM solutions often makes both platforms more valuable.

Here are just a few examples: getting accurate, up-to-date leads into your platform can help you create more robust, actionable reports; enriching newly-added leads in the CRM via existing data in your product can help your reps engage prospects more intelligently; and adding leads to your platform when they reach a certain stage in your CRM can ensure your team nurtures them effectively.

To help you sync lead data between your product and CRM solutions, we’ll break down common API calls you can make and reference specific [examples from Pipedrive](https://developers.pipedrive.com/docs/api/v1/Leads#getLeads) to make them more tangible.

But to start, let’s align on the definition of a lead API.

## **What is a lead API?**

It’s any API endpoint that allows you to create, read, update, or delete a lead object—along with predefined fields—in a given application. You can perform these operations on one lead, all of them, and anything in between.

_Related:_ [_What is CRM API integration?_](https://merge.dev/blog/crm-api-integration)

## **Lead API examples**

Here’s how you can work with lead APIs:

### **GET leads**

To add lead data into your product, you can call the API endpoint https://api.pipedrive.com/v1/leads using a GET request. Also, instead of just retrieving all leads at once, you can be intentional about the leads you collect by adding query parameters to your API calls. For instance, you can use owner\_id to retrieve leads that are managed by a specific sales rep(s) or organization\_id to retrieve leads that belong to a specific organization(s).

### **GET lead**

In addition to gathering leads in bulk, you can obtain them individually.

To do so, you would add ID as a parameter, leaving you with the endpoint https://api.pipedrive.com/v1/leads/{id} (where id corresponds to a specific lead’s ID in Pipedrive).

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e405bed2afa0787bbcc_iiHqwMNGh2phXkMUMxHmhbmahJLi7PvsjbKRpZLdgexUEBeBc0J4Wuim7mvyP7ElGhqm1nDHek5aorFTj7tkUr8bnmRDGrdbUQwK6tc1O37XwkvsK3rTvONUHiWyE7pAFq5npGkqoCKCXycCq2-_-Tg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e405bed2afa0787bbcc_iiHqwMNGh2phXkMUMxHmhbmahJLi7PvsjbKRpZLdgexUEBeBc0J4Wuim7mvyP7ElGhqm1nDHek5aorFTj7tkUr8bnmRDGrdbUQwK6tc1O37XwkvsK3rTvONUHiWyE7pAFq5npGkqoCKCXycCq2-_-Tg.webp)

_A snapshot of a potential response from a GET lead API call; it includes the lead’s id, title, among other information._

_Related:_ [_A guide to implementing product integrations_](https://merge.dev/blog/product-integrations)

### **PATCH a lead**

To edit existing leads based on relevant information in your product, you can use the PATCH request method to the same endpoint above (https://api.pipedrive.com/v1/leads/{id}). You can also control what’s patched via the body parameters included in your API call. This can be anything from title (name of the lead) to the expected\_close\_date to the value (which indicates the anticipated dollar value of the lead if closed won).

### **POST a lead**

You can add leads from your product to Pipedrive via a POST method and with the endpoint https://api.pipedrive.com/v1/leads. The title (i.e. the name of the lead) is the only required body parameter. To add more details on the lead, you can use the body parameters owner\_id, organization\_id, expected\_close\_date, among others.

### **DELETE a lead**

Finally, you can delete leads in Pipedrive when any is deleted in your application by using the DELETE method and the endpoint https://api.pipedrive.com/v1/leads/{id}. All of the fields associated with the lead will be deleted.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e3f488fa65d285efc31_Ybo3XV50M3KfAhuOUKb2JCeb007IyoB1HpBr1d5XzKdBBp1xmYILlTE9NR85PgSRM3CNAn3GMv3ohaKnKzIHs1hGc7ZP3LonH2CAWC6jwb3s8o6zaakP0JDlf5D0ebczv4wlCAw2fzSajMm-MBc411M.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e3f488fa65d285efc31_Ybo3XV50M3KfAhuOUKb2JCeb007IyoB1HpBr1d5XzKdBBp1xmYILlTE9NR85PgSRM3CNAn3GMv3ohaKnKzIHs1hGc7ZP3LonH2CAWC6jwb3s8o6zaakP0JDlf5D0ebczv4wlCAw2fzSajMm-MBc411M.webp)

_A snapshot of a potential response from a DELETE lead API call; it only includes the status message and the id of the lead that was deleted._

‍

_Related:_ [_What is a CRM API?_](https://www.merge.dev/blog/crm-api)

## **Sync leads between your product and CRMs at scale with Merge**

The process of building to and maintaining connections with Pipedrive’s lead API endpoints—via custom code—may not be daunting in and of itself. But considering that you likely need to integrate with several other CRMs, your engineers will eventually become overwhelmed.

That’s where Merge, the leading [unified API platform](https://merge.dev/blog/what-is-a-unified-api), can help.

Using Merge, you only need to build to the [CRM Unified API](https://merge.dev/categories/crm-api) once to get access to 20+ CRM platforms.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e3ff77f0dc3410ccb4c_AezVcNuKCXpNQsJ6WDHBATKPVIIR8RjvJfJpxhy2hpyhyFP2NHEYtdIDPKP27drlin9I-dLkUl3-jCYZCD4otOoCZs5w3SRjUFLe1r_e11_Anp6hCyLsINIY0JnjfMu73gtJGAnjwQ-Weupa53_ZrRQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e60e3ff77f0dc3410ccb4c_AezVcNuKCXpNQsJ6WDHBATKPVIIR8RjvJfJpxhy2hpyhyFP2NHEYtdIDPKP27drlin9I-dLkUl3-jCYZCD4otOoCZs5w3SRjUFLe1r_e11_Anp6hCyLsINIY0JnjfMu73gtJGAnjwQ-Weupa53_ZrRQ.webp)

_A look at the CRMs Merge integrates with_

Merge also lets you access a broad range of lead data across your integrations through the [Leads common model](https://docs.merge.dev/crm/leads/); sync additional objects and fields from your CRM, whether it’s opportunities, users, or accounts; oversee integration activities and help clients troubleshoot any issues through our platform’s suite of [Integrations Management features](https://merge.dev/features/integrations-management)—and much, much more.

‍ _Learn more about building CRM integrations with Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Flead-api) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a8c82ada-3b3e-4b8c-8f90-01a2a3226cec&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=01202084-1cbd-40d8-af6d-151ccb9303e1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flead-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a8c82ada-3b3e-4b8c-8f90-01a2a3226cec&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=01202084-1cbd-40d8-af6d-151ccb9303e1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flead-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=831e509e-7930-4cdb-bde9-cd0d8aa2c6ce&bo=2&sid=1a33f7f03e8d11f0a74c6508352d201c&vid=1a33f2c03e8d11f0881d6f2da57c811b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20using%20Lead%20APIs%20(with%20examples%20from%20Pipedrive)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Flead-api&r=&lt=411&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=23224)