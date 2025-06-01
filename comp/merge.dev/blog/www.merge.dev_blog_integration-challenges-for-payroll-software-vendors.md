---
url: "https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors"
title: "3 challenges that HR software vendors face in building and maintaining customer-facing accounting integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#)

Table of contents

[Configuring journal entry data at scale](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#configuring-journal-entry-data-at-scale)

[POSTing to inactive accounts or creating duplicate data](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#posting-to-inactive-accounts-or-creating-duplicate-data)

[Accounting for API providers’ unique build requirements](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#accounting-for-api-providers-unique-build-requirements)

[Add several accounting integrations to your product with ease through Merge](https://www.merge.dev/blog/integration-challenges-for-payroll-software-vendors#add-several-accounting-integrations-to-your-product-with-ease-through-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-challenges-for-payroll-software-vendors)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Why HR software needs cross-category integrations to survive**](https://www.merge.dev/blog/hr-and-payroll-software-needs-cross-category-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How 3 HR software solutions use integration data to build cutting-edge AI features**](https://www.merge.dev/blog/how-hr-and-recruiting-software-power-ai-features)

# 3 challenges that HR software vendors face in building and maintaining customer-facing accounting integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb1e10d897b1194792e1de_Anuj%20Jhunjhunwala%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ba8b5339e4c1931fb22629_anuj-headshot-2-min.webp)

Anuj Jhunjhunwala

Director of Product Management

@Merge

HR software solutions often need accounting integrations to help customers perform key financial activities in their ERP systems, whether that’s reconciling payroll journal entries, accounting for approved expenses, or building comprehensive financial reports.

The process of building and maintaining these integrations, however, is far from easy.

Each accounting integration requires significant developer resources at every phase, including ongoing maintenance.

To help streamline your team’s process of building and maintaining each accounting integration, we’ll break down the challenges associated with the API request you’ll need to make— _POSTing payroll journal entries to customers’ ERP solutions_—and how a unified API solution can address them.

## **Configuring journal entry data at scale**

The most difficult part about building an integration between your HR and payroll software and an ERP is the work you need to perform before POSTing a journal entry: configuring the journal entry data.

For each customer, you’ll need to research and discover the general ledger account you should POST the journal entry against. You’ll also need to figure out whether to POST different line items per department, location, or employee.

To address this at scale, you can equip customers with a custom mapping UI that lets them configure the journal entry sync.

Using the UI, your customers should be able to select and map relevant dimensions to categorize their journal entries, such as departments, classes, and locations. The UI could also include a way to map benefit and deduction codes to the general ledger accounts in the ERP.

For example, Gusto, a widely-used payroll and HR solution, lets customers map data between their software and different ERP solutions:

How to Integrate QuickBooks Online with Gusto - YouTube

Gusto

13.9K subscribers

[How to Integrate QuickBooks Online with Gusto](https://www.youtube.com/watch?v=DuWsqIIsDKQ)

Gusto

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

[Watch on YouTube](https://www.youtube.com/watch?v=DuWsqIIsDKQ "Watch on YouTube")

## **POSTing to inactive accounts or creating duplicate data**

For any integration that involves POSTing data, you’ll need to think through next steps when a sync fails.

This is even more important when an integration POSTs journal entries to a customer’s general ledger. If this data isn’t 100% accurate, it’ll adversely impact your customer's end-of-period reconciliation process—or worse.

To minimize the impact of any syncing issues, your integration will need to handle errors from the ERP and surface them to your customer.

For example, say your customer voids a GL account that they’ve already mapped to your application. If you were to then POST a journal entry, you’ll receive an error that tells you the account is no longer active; you should pass that to your customer as soon as possible so they can correct the mapping.

Equally important, you’ll need to avoid creating duplicate data.

You can use idempotency keys to prevent creating duplicate data, especially since many ERPs offer them out of the box.

QuickBooks Online, as an example, lets you use their idempotency key as follows:

```python

curl -X POST \
  https://quickbooks.api.intuit.com/v3/company//journalentry \
  -H "Authorization: Bearer " \
  -H "Accept: application/json" \
  -H "Content-Type: application/json" \
  -H "Request-Id: " \
  -d '{
        "Line": [\
          {\
            "Description": "Debit line for Journal Entry",\
            "Amount": 500.00,\
            "DetailType": "JournalEntryLineDetail",\
            "JournalEntryLineDetail": {\
              "PostingType": "Debit",\
              "AccountRef": {\
                "value": "42"\
              }\
            }\
          },\
          {\
            "Description": "Credit line for Journal Entry",\
            "Amount": 500.00,\
            "DetailType": "JournalEntryLineDetail",\
            "JournalEntryLineDetail": {\
              "PostingType": "Credit",\
              "AccountRef": {\
                "value": "50"\
              }\
            }\
          }\
        ],
        "TxnDate": "2024-12-16",
        "PrivateNote": "A Payroll Journal Entry"
      }'

```

## **Accounting for API providers’ unique build requirements**

As you comb through accounting providers’ API documentation, you’ll notice that their journal entries’ endpoints differ in meaningful ways.

This can be anything from the rate limits you’ll need to follow to the data you can post to the authentication methods you should use.

For example, Sage Intacct offers a specific set of parameters you can include in your POST requests:

[![Journal Entry parameters for Sage Intacct](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/677bf751c100d13543d28636_AD_4nXeyeWyb97t9e46fIzDfSXzyZneJhcO8zzGz0FRRj0fnICXZ0YQdwhxqCt_3if85tfIqUDZQFSBTS-vCNZkCcm5qKhIwZSUU1BIEFYcjnDGGkVX3lNz8VTWESUuuk3ceVmIInPWAeg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/677bf751c100d13543d28636_AD_4nXeyeWyb97t9e46fIzDfSXzyZneJhcO8zzGz0FRRj0fnICXZ0YQdwhxqCt_3if85tfIqUDZQFSBTS-vCNZkCcm5qKhIwZSUU1BIEFYcjnDGGkVX3lNz8VTWESUuuk3ceVmIInPWAeg.webp)

_A snapshot of the parameters you can include when_ [_POSTing journal entries to Sage Intacct_](https://developer.intacct.com/api/general-ledger/journal-entries/)

These parameters differ almost entirely from what Zoho Books offers, both in their structure and in the type of data that can be passed through.

[![Journal entry parameters for Zoho Books](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/677bf75578ac2a90cc9cb0c3_AD_4nXfOboatVwAXr0UOzXsrBbKPNoTt-F3qsxyDYCDQXN09hq6H2Jm9ovNvSkE2o14YYL5NdAWt3-geKON4g1Dk3kCvTdWubsmlcTPZsEZ5lm2p3otBqQI9Ij8hlx-KllxrJN_7vEZF.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/677bf75578ac2a90cc9cb0c3_AD_4nXfOboatVwAXr0UOzXsrBbKPNoTt-F3qsxyDYCDQXN09hq6H2Jm9ovNvSkE2o14YYL5NdAWt3-geKON4g1Dk3kCvTdWubsmlcTPZsEZ5lm2p3otBqQI9Ij8hlx-KllxrJN_7vEZF.webp)

_A snapshot of the “arguments,” or parameters, you can include when_ [_POSTing journal entries to Zoho Books_](https://www.zoho.com/books/api/v3/journals/#create-a-journal)

‍

Addressing each application’s unique POST journal entries build can be time consuming for your engineers and lead to errors along the way (e.g., including the wrong parameters in an API request).

_Related:_ [_What is a payroll integration?_](https://www.merge.dev/blog/payroll-integrations)

## **Add several accounting integrations to your product with ease through Merge**

Merge, the leading unified API solution, lets you add more than a dozen accounting integrations through a single build.

[![Accounting integrations Merge supports](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6759bddca329294ca1d6c2b4_AD_4nXc9ItrFILAzsqaurff3dWPBaSf8GM87FPKfuExY6vStMgTiEHtN_Ohd3yLMOuUbDLh0eZlFmuH-qEX5d-SGhToxEshpDCJzGZDpZ6w5KQLYWNQ8EUcHcbZmSF2lAdjmjpZ5MXtH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6759bddca329294ca1d6c2b4_AD_4nXc9ItrFILAzsqaurff3dWPBaSf8GM87FPKfuExY6vStMgTiEHtN_Ohd3yLMOuUbDLh0eZlFmuH-qEX5d-SGhToxEshpDCJzGZDpZ6w5KQLYWNQ8EUcHcbZmSF2lAdjmjpZ5MXtH.webp)

_A snapshot of_ [_the accounting integrations Merge supports_](https://www.merge.dev/categories/accounting-api)

Merge also neatly addresses the challenges above by:

- Consolidating different categorization concepts into one [Tracking Categories endpoint](https://docs.merge.dev/accounting/tracking-categories/). This helps reduce the complexity in the mapping process

- Returning errors in the same format as well as allowing you to pass an idempotency across all integrations—even if the third party ERP doesn’t support it

- Letting you build to only one journal entry endpoint

Learn more about why leading HR and payroll software providers like Remote and BambooHR trust Merge to power their accounting integrations by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-challenges-for-payroll-software-vendors).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb1e10d897b1194792e1de_Anuj%20Jhunjhunwala%20-%20Merge.png)

Anuj Jhunjhunwala

Director of Product Management

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a8283c32-6ec4-46bc-9aee-136b6f1246b3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=52857278-3304-4a3f-98ce-1b202935b9b1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-challenges-for-payroll-software-vendors&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a8283c32-6ec4-46bc-9aee-136b6f1246b3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=52857278-3304-4a3f-98ce-1b202935b9b1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-challenges-for-payroll-software-vendors&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=be6d6dae-c304-4bcf-bb47-c6bd423a3d3d&bo=2&sid=096261a03e8c11f0a6a929b59d548f58&vid=0962a7a03e8c11f0b65d57e2c94007fb&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=3%20challenges%20that%20HR%20software%20vendors%20face%20in%20building%20and%20maintaining%20customer-facing%20accounting%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-challenges-for-payroll-software-vendors&r=&lt=986&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=719826)