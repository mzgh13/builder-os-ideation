---
url: "https://www.merge.dev/blog/introducing-the-ignore-objects-function"
title: "Introducing the ignore objects function"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/introducing-the-ignore-objects-function#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/introducing-the-ignore-objects-function#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/introducing-the-ignore-objects-function#)

Table of contents

[Why ‘Ignore’ and Not Something Permanent like ‘Delete’?](https://www.merge.dev/blog/introducing-the-ignore-objects-function#why-ignore-and-not-something-permanent-like-delete)

[Use Cases - When You’d Use the Ignore Objects Feature](https://www.merge.dev/blog/introducing-the-ignore-objects-function#use-cases-when-youd-use-the-ignore-objects-feature)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintroducing-the-ignore-objects-function)

##### Just for you

No items found.

# Introducing the ignore objects function

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae748c10442b0eba79_653701f158e63264e2e77528_How_to_get_employees_from_any_HRIS_with_Merge.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387ca3e2516664e369a_62eff9710897772d5f67ff9d_lee.webp)

Lee Wang

Software Engineer

@Merge

Merge customers can now specify what end-user data is stored in Merge’s servers with the ‘ignore’ object request for any HR and payroll or ATS object.

In this post, we'll walk through our product decision to use 'ignore,' and walk you through some use cases for when to use this feature.

## Why ‘Ignore’ and Not Something Permanent like ‘Delete’?

Merge is not the source of truth for our customer’s data. Part of the function of a Unified API is to [poll and normalize data](https://medium.com/mergeapi/what-is-a-unified-api-9c41403c584d) from various vendors in the HR and payroll, recruiting, and accounting spaces and store it on our customer’s behalf.

Because Merge pulls data regularly, if we were to delete an Employee's data in our database at 1 pm we'd end up pulling the deleted Employee's data again at 4 pm. When thinking about how we want to account for these issues and best allow our customers to comply with security or data storage concerns, the idea of simple 'deleting' data doesn't make sense.

By using ‘ignore,’ we set the ignored model and any related models to a ‘null’ value in our servers. This means that even if the data is _sent_ from a third-party application to Merge,  Merge’s servers know to not bother with the ignored model and so won’t save that data. This ensures you remain compliant with whatever boundaries your users have set.

More importantly, ‘ignore’ scales as we add new models and features – meaning that you can trust Merge to help you stay in compliance for the long run.

## Use Cases - When You’d Use the Ignore Objects Feature

Let’s run through some examples of when you’d use the ignore feature. Don’t see your use case below? Our team is always happy to chat on Intercom and answer your question!

**Problem:** For privacy reasons,a recruiting candidate doesn’t want their data stored by your system.

**Solution with Merge:** Send a POST request to Merge for /candidates/ignore/{model\_id} where {model\_id} is equal to the specific candidate’s id. On every subsequent pull of data between Merge and the ATS that the candidate is stored in, Merge will ignore the specified candidate's data and all subsequent fields relating to the candidate.

- Models Used: [Merge’s Candidate object](https://www.merge.dev/docs/ats/candidates#candidates-object)
- Requests Used: [POST /candidates/ignore/{model\_id}](https://www.merge.dev/docs/ats/candidates#candidates_ignore_create)

**Problem:** For the HR tasks your platform accomplishes, it’s unnecessary to store information on consultants or executives employed at a customer’s company.

**Solution with Merge:** Send one POST request to /employees/ignore/{model\_id} per employee, where model\_id is equal to the id of an employee belonging to a “team” object that represents “consultant” or “executive” in your system.

- Models Used: [Merge’s Team object](https://www.merge.dev/docs/hris/teams#teams-object)
- Requests Used: [POST /employees/ignore/{model\_id}](https://www.merge.dev/docs/hris/employees#employees_ignore_create)

**Problem:** One of your customers no longer wants _any_ of their data stored by Merge, and doesn’t want to be connected through your service.

**Solution with Merge:** Here we would use the POST /delete-account function, which deletes an entire linked account. Even though we’re deleting data, we don’t have to worry about subsequent data being stored through polling: Merge won’t even consider the (now deleted) Linked Account as something poll-able.

- Requests Used: [POST/delete-account](https://www.merge.dev/docs/hris/delete-account#delete_account_create)

**Problem:** Because of a rise in popularity, let’s say Merge adds a new field called “favorite\_food” to our common Candidate data object. You’ve previously asked Merge to ‘ignore’ several Candidates, but because the “favorite\_food” field wasn’t present in your initial request, you’re worried Merge will _ignore your ignore_ and pull the “favorite\_food” field for these Candidates! Do you need to submit _another_‘ignore’ request to prevent this from happening?

**Solution with Merge:** Nope! This is not a problem. Our code is smart enough to see that the candidate was ignored and know that all future related objects to that candidate are ignored. We know that having to write repeated requests on your own takes time and engineering resources that can be better spent writing features you care about!

If you’ve been having difficulty managing customer privacy through integrations, or want to explore more options to remain compliant with user requests, then we’d love to chat!

Schedule a [demo today](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintroducing-the-ignore-objects-function) or [sign up for free](https://www.app.merge.dev/signup) and start experimenting with Merge today!

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)

Anthony Lagana

Product Marketing

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lee Wang

Software Engineer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=db8b91d5-0771-4bc8-928b-7f2443cb7de3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ba06a309-47f2-4900-93de-c7a847ccf4e0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintroducing-the-ignore-objects-function&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=db8b91d5-0771-4bc8-928b-7f2443cb7de3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ba06a309-47f2-4900-93de-c7a847ccf4e0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintroducing-the-ignore-objects-function&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e8aff989-51da-44a5-83d0-bd1cbba9fcac&bo=2&sid=b466b1703e8d11f0a7ac8b5cb4316949&vid=b46720703e8d11f08de1cb9ce3701134&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Introducing%20the%20ignore%20objects%20function&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintroducing-the-ignore-objects-function&r=&lt=638&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=305238)