---
url: "https://www.merge.dev/blog/meet-unified-writes"
title: "Meet unified writes"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/meet-unified-writes#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/meet-unified-writes#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/meet-unified-writes#)

Table of contents

[Why Are Data Writes Difficult?](https://www.merge.dev/blog/meet-unified-writes#why-are-data-writes-difficult)

[What are the new improvements?](https://www.merge.dev/blog/meet-unified-writes#what-are-the-new-improvements)

[What will you do with Unified Writes?](https://www.merge.dev/blog/meet-unified-writes#what-will-you-do-with-unified-writes)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmeet-unified-writes)

##### Just for you

No items found.

# Meet unified writes

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c73e308c8ec126f3a56_14.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

Is pushing data to your users’ third-party platforms critical for your product? Unified Writes with Merge let you build once to push data anywhere.

With Unified Writes, Merge is a truly Unified API: **no other method or platform accommodates writing data programmatically across all users and integrations.**

In this blog, we’ll cover why we improved our Writes, what changes we made, and a few things Unified Writes allow you to accomplish. **Be sure to dig into the guides we’re linking along the way — they’ll answer more technical questions and are built to ease you into Writes.**

Unified Writes include:

- **The /meta endpoint,** which allows you to programmatically account for variability across any supported integration
- **Data writes to non-standard fields** using Merge’s Unified POST endpoints
- **Debugging tools that work for you,** with rich error messages and a powerful new tool

We’ve also released comprehensive guides for all things Writes. Use the list below as a jumping-off point if you want to start building right away.

Writes

1. [Introduction](https://www.merge.dev/docs/guides/merge-writes/writes)
2. [Related and Nested Writes](https://www.merge.dev/docs/guides/merge-writes/writes/related-and-nested)

Programmatic Writes with /meta

1. [Introduction](https://www.merge.dev/docs/guides/merge-writes/programmatic)
2. [Programmatic Nested Writes with /meta](https://www.merge.dev/docs/guides/merge-writes/programmatic/nested)
3. [Templates and Conditional Fields](https://www.merge.dev/docs/guides/merge-writes/programmatic/templates-conditional)

Troubleshooting Writes

1. [Warnings and Errors](https://www.merge.dev/docs/guides/writes-troubleshooting)
2. [Debug Mode](https://www.merge.dev/docs/guides/writes-troubleshooting#debug-mode)

And while this update is focused on POST requests, don’t worry: PATCH is on the way soon.

## Why Are Data Writes Difficult?

Unified APIs like Merge exist, in large part, because **of variability across different software platforms.**

When you read data from a Unified API, this platform-specific variability is either normalized into a common data model or ignored. (Through a platform like Merge, that ignored data is made accessible through a feature such as Supplemental Data). Because data from a Unified API is presented in a standardized (‘unified’) format you’re able to build once and be confident you’ve anticipated everything.

When you _write_ data through a Unified API this variability cannot be ignored. Different platforms and linked accounts have different fields that are required to make a successful POST request. On the surface, there’s no ‘standardized’ way for a Unified API to account for variability. **But for a truly unified experience, a developer should be able to build once and:**

- Never worry about an edge case, whether across platforms or end-user linked accounts (even if data is outside of a common data model)
- Send requests to a single endpoint, regardless of which fields are required by platforms or linked accounts
- Troubleshoot error messages in a standardized way and not have to rely on translating third-party error messages

Until now, **no Unified or** [**Universal API**](https://merge.dev/blog/universal-api) **anticipated variability across end-users in an integration to make writing data a truly unified experience**.

**Merge anticipates everything with Unified Writes.**

## What are the new improvements?

Here’s what you can now do with Merge’s Unified Writes.

### **The /meta endpoint: anticipate more, work less**

You’re probably wondering “how do I anticipate variability across dozens of integrations and all of my customers?” Easy: /meta.

**The /meta endpoint allows you to account for all variability across integrations and users for any supported Common Model**. If you can POST to an endpoint, you can anticipate anything. That’s the power of /meta.

/meta returns all fields, field types, and specific enum values unique to a given linked account. With that response in hand, you now know what is required and what is optional to POST a Merge Common Model.

Its response looks something like this:

```python
{
  "request_schema": {
    "type": "object",
    "properties": {
      "model": {
        "type": "object",
        "properties": {
          "first_name": {
            "type": "string",
            "description": "The candidate's first name."
          },
          "last_name": {
            "type": "string",
            "description": "The candidate's last name."
          },
          "email_addresses": {
            "type": "array",
            "description": "Array of email_addresses objects on ats.Candidate",
            "items": {
              "type": "object",
              "properties": {
                "value": {
                  "type": "string"
                },
                "email_address_type": {
                  "type": "string"
                }
              },
              "required": ["value"]
            }
          }
        },
        "required": ["first_name", "last_name", "email_addresses"]
      }
    },
    "required": ["model"]
  }
}

```

‍

There’s a lot to learn with /meta and you can go from beginner to power user in no time in our [Introduction to Programmatic Writes with /meta](https://docs.merge.dev/guides/merge-writes/programmatic/).

#### /meta highlight: Nested Writes create even more with less code

Merge has always supported pushing nested data for common use cases (see our guide to [Related and Nested Writes](https://merge.dev/docs/guides/merge-writes/writes/related-and-nested)).

Now, you can chain together /meta with Nested Writes to accommodate powerful new use cases.

Find out what fields are supported with Nested Writes and how to pair them with /meta in our guide to [Programmatic Nested Writes with /meta](https://docs.merge.dev/guides/merge-writes/programmatic/nested/).

#### Never Miss an Edge Case - Write to non-unified fields using Merge’s Unified POST endpoints

A Unified API should never prevent you from POSTing data. If /meta surfaces required fields that fall outside of those in Merge’s Common Models, we’ve built out functionality that allows you to still POST to that endpoint. This way, Merge is never a blocker.

Write to non-unified, required fields through:

- Integration-specific parameters
- Linked Account-specific parameters
- Input-conditional parameters
- Learn more in our guide on [Templates and Conditional Fields](https://www.merge.dev/docs/guides/merge-writes/programmatic/templates-conditional/)

**Together, all three fields allow you to POST to any platform on behalf of any customer.**

If you’re looking for support for integration-specific or Linked Account-specific parameters for a given integration, then reach out to a member of our team on Intercom. We’re always looking to help you get started.

### **The 'Write' Way to Debug: Information-rich troubleshooting**

We’ve streamlined debugging with Merge into two parts to make your life simpler.

First, **we’ve standardized our error and warning messages.** You now only have to know one common set of error messages, regardless of the third-party platform that error is coming from. These error messages show you what, where, and how things went wrong.

Every error message you’ll need to worry about is laid out in our guide to [Writes Warnings and Errors References](https://www.merge.dev/docs/guides/writes-troubleshooting/warnings-errors) [.](https://www.merge.dev/docs/guides/writes-troubleshooting)

**We’ve also added a new Debug Mode to all endpoints.** Debug Mode returns the original error message from a third-party platform, as well as any requests between Merge and that platform. Combined with our updated error and warning capabilities, your troubleshooting will be a breeze.

Here’s an example of this in action:

```python
GET https://api.merge.dev/api/ats/v1/candidates?is_debug_mode=true

```

‍

Read more about [Troubleshooting Writes](https://merge.dev/docs/guides/writes-troubleshooting/) in our Guide.

## **What will you do with Unified Writes?**

Depending on the fields you want to write and the third-party platforms you want to support, you’ll learn everything you need to know - from pushing updates to basic fields to programmatic form generation with /meta - from our Writes guides.

Here are a few use cases of what you can do in your product with these features:

Problem: You want to create a candidate object in an ATS, but need to link the candidate to an existing job opportunity.

Solution: POST a “Candidate” object, and use a related write to include the “Jobs” object.

Problem: You want to generate a form in your product that creates a candidate in your user’s applicant tracking system. You already know you want to get basic information about the candidate, as well as a relevant resume, but need to anticipate the fact that certain jobs have certain required fields to be filled out.

Solution:

1. Use /meta to surface the fields that you want your applicant to fill out. Meta will allow you to account for the variability of required fields across integrations and linked accounts. Follow the /meta guide [here](https://docs.merge.dev/guides/merge-writes/programmatic/)
2. Generate a form based on the fields provided by /meta and your product requirements
3. Form a POST request for your Candidate object, and use a Nested Write to create the related Attachment object in the same POST request. See more in our Nested Writes with Meta guide [here](https://www.merge.dev/docs/guides/merge-writes/programmatic/nested).

Problem: You’re getting an error back from Merge that says “ERROR,” which doesn’t feel very descriptive.

Solution: Use the \`debug\_mode=on\` parameter to receive logs of the exact response returned by the third-party API. You can learn more about Debug Mode [here](https://docs.merge.dev/guides/writes-troubleshooting/).

These use cases are meant to give you just a taste of what’s possible with Merge. Not sure if your use case is possible with Merge? Ping us on Intercom — we’re always happy to help point you in the right direction.

See you in the next update.

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)

Gil Feig

CTO and co-founder

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a7028ee5-d9c9-424a-8ac6-dd15e4598882&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=96669683-d13d-493f-afad-5dd58bcd48cf&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmeet-unified-writes&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a7028ee5-d9c9-424a-8ac6-dd15e4598882&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=96669683-d13d-493f-afad-5dd58bcd48cf&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmeet-unified-writes&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=418cd1a5-d0d2-46d7-b194-b0ee1099770f&bo=2&sid=708f88503e8d11f0be974b2dea80d63a&vid=7090c3603e8d11f0bda7231bcc1b79dc&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Meet%20unified%20writes&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmeet-unified-writes&r=&lt=829&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=647071)