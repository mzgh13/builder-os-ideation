---
url: "https://www.merge.dev/blog/announcing-single-tenancy-at-merge"
title: "Announcing single tenancy at Merge"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#)

Table of contents

[What is Single Tenancy?](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#what-is-single-tenancy)

[The Data-Sync Problem](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#the-data-sync-problem)

[API-First?](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#api-first)

[SNS & SQS to the rescue](https://www.merge.dev/blog/announcing-single-tenancy-at-merge#sns-and-sqs-to-the-rescue)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fannouncing-single-tenancy-at-merge)

##### Just for you

No items found.

# Announcing single tenancy at Merge

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb2b0b7764b66a5aa8b6b8_Dan%20Rothman%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538316bd609b4c800381_62eff2ae1cef2850ec2d43ad_dan-rothman.webp)

Dan Rothman

Engineering

@Merge

Merge has always followed a security-first model. This [core tenet of ours](https://medium.com/mergeapi/why-we-started-merge-1fd19c18b263) informs the [very nature of our integrations](https://medium.com/mergeapi/integrations-in-3-methods-why-merge-is-api-first-89bd6a256293) and ensures we build a scalable, reliable, and secure product.

**Still, we understand that many enterprise-level users require more than just best-in-class security— they often require industry specific compliance standards or simply corporate peace-of-mind.**

With this enterprise-first focus in mind, we’re excited to announce the launch of our new **single tenant offering.** Think this might be the solution for you? Drop us a line at hello@merge.dev!

## **What is Single Tenancy?**

Single tenancy is like being able to rent your own, private AirBnB as opposed to staying in a hotel. The place is all yours. While this architecture pattern can be more resource-intensive to set up and to maintain, it provides a few critical benefits to an enterprise:

- **Increased flexibility:** Resource allocation can be attuned to the exact needs of the customer.
- **Custom specifications:** Merge single tenancy customers are able to specify database options to comply with industry requirements or internal policies.

From speaking with our customers, it was clear that we would need to offer single tenant architecture to meet these needs. Below are some of the challenges we faced when building single tenancy at Merge.

## **The Data-Sync Problem**

Our Unified API works with two types of data: customer-specific and operational.

Single tenant architectures are inherently designed to segment customer-specific data, but we needed to still find a way to allow operational data to pass through. Consistent operational data— the data that lets our integrations talk to our Unified API— would enable our single tenant customers to receive integration updates as we release them.

Thus, the **data-sync problem** was born: how do you share data models in systems designed to be segmented?

## **API-First?**

We at Merge like to consider ourselves API experts, and our initial approach was to share data the same way our users share theirs: through secure API calls. To the uninitiated this seems simple enough: expose some API on our single tenant that could generically take in our model data, fire off some POST requests whenever our production data changed, and call it a day.

To the initiated this quickly proves insufficient.

We use relational database models built on Postgres, and preserving foreign key relations across our models would require data to be processed and saved in a specific order. Problem: standard POST requests couldn’t guarantee that order. Furthermore, our production server would need to keep track of the URL’s required to sync with each tenant. This pattern was bad enough for scaling purposes, and that was before we started to worry about isolated tenants having downtime and failing to receive messages!

## **SNS & SQS to the rescue**

Fortunately for us, Amazon Web Services offers two services that are perfect for our problem: Simple Notification Service (SNS) and Simple Queue Service (SQS).

SNS is a push-based notification service. Data gets packaged as a “message” and sent to all subscribers of a given “topic.” By using SNS we’d no longer need to manage a list of remote URLs— we could simply blast out the updated data once and let SNS handle the fan-out for us.

SQS, on the other hand, is a message queue. It allows any receiver (in our case, a single tenant) to process messages in an ordered and reliable manner. By simply allocating a queue to each tenant server, and having said queue subscribe to our SNS topic, we could propagate any data changes on our main server to isolated tenants in a reliable and scalable fashion.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d72a011d7a2d85dfddcd04_Single%20Tenant%20Example%20.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d72a011d7a2d85dfddcd04_Single%20Tenant%20Example%20.png)

After data-sync, there were plenty of additional challenges we had to solve. How to best sync large batches of data when a new tenant is spun up? How do we handle data that exceeds SNS/SQS’s 256 kb message size limit? How do we optimally check for and process new messages in our tenants? Countless completed Asana tasks later, we couldn’t be more thrilled with the results.

Solving engineering problems like these are a huge part of what makes it so exciting to be an engineer at Merge. If these seem like interesting problems to you, then great news— Merge is hiring! Why not [apply today?](https://www.merge.dev/careers#opportunities)

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb2b0b7764b66a5aa8b6b8_Dan%20Rothman%20-%20Merge.png)

Dan Rothman

Engineering

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=13afac8f-3fa5-4ea1-ada1-0eb37501fa60&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=14d5d281-cec8-4c6c-9ac6-bfc640e37b0d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fannouncing-single-tenancy-at-merge&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=13afac8f-3fa5-4ea1-ada1-0eb37501fa60&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=14d5d281-cec8-4c6c-9ac6-bfc640e37b0d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fannouncing-single-tenancy-at-merge&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=902b518e-c490-40dc-9b5d-ee8ae5804bde&bo=2&sid=1358ad603e8c11f08e3d456f866a7280&vid=1358d2c03e8c11f0b04a830c9cd9b14f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Announcing%20single%20tenancy%20at%20Merge&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fannouncing-single-tenancy-at-merge&r=&lt=535&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=256503)