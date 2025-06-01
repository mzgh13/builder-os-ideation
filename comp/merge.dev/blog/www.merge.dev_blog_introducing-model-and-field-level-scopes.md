---
url: "https://www.merge.dev/blog/introducing-model-and-field-level-scopes"
title: "Introducing model and field level Scopes"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/introducing-model-and-field-level-scopes#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/introducing-model-and-field-level-scopes#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/introducing-model-and-field-level-scopes#)

Table of contents

[Why We Built Scopes](https://www.merge.dev/blog/introducing-model-and-field-level-scopes#why-we-built-scopes)

[How Do I Access Scopes?](https://www.merge.dev/blog/introducing-model-and-field-level-scopes#how-do-i-access-scopes)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintroducing-model-and-field-level-scopes)

##### Just for you

No items found.

# Introducing model and field level Scopes

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae748c10442b0eba79_653701f158e63264e2e77528_How_to_get_employees_from_any_HRIS_with_Merge.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb2b0b7764b66a5aa8b6b8_Dan%20Rothman%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538316bd609b4c800381_62eff2ae1cef2850ec2d43ad_dan-rothman.webp)

Dan Rothman

Engineering

@Merge

Scopes at the common data model and field level allow Merge users granular access over the data Merge syncs.

In this blog post, we'll cover why we built scopes and how to toggle them on your Merge dashboard.

## Why We Built Scopes

At Merge, we aim to offer our customers [a comprehensive encapsulation](https://medium.com/mergeapi/what-is-a-unified-api-9c41403c584d) of HR, recruiting, accounting, and payroll API data. Here’s the thing: our customers occasionally want to limit the data that they pull from the API providers.

Maybe it’s because your product is operating off of a narrow part of an employee’s HR profile — such as time off data or employee directory — or maybe it’s because you want to alleviate any concerns during a sales process, and so don't want to pull specific fields. Whatever the reason, we knew that as Merge continued to scale more customers would benefit from being able to configure what data they chose to sync.

So Elton and I asked: What’s the best way to let our customers access the data _they_ want?

Simple: toggles.

With Scopes, Merge users are able to choose which data models and fields they’d like to sync with the flip of a (virtual) switch.

For example, if users don’t want to sync payroll runs for their HR integrations, they can now flip off our Payroll Run model. Being able to select the data that they pull is now in our user's hands. They have full control over their data and can choose what to stop syncing whenever they want. Even better, if at any point you want to re-enable a data model or field, you're able to toggle the switch back on and start syncing the data model again!

## How Do I Access Scopes?

In the [Merge portal](https://app.merge.dev/login), head towards the "Configuration" tab and select "Common Models."

Under the API you use (HRIS, ATS, or Accounting) find the relevant common model. You can disable the whole common model with the round toggle, or expand the model to access specific fields to toggle.

In the GIF below, you'll see us enabling scopes at the field and model level for the [Bank Info](https://www.merge.dev/docs/hris/bank-info#bank-info-object) object in our Unified HRIS API.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc091e660e3d95688bf8dd_62ed6c4a26ad07d17bb1d94d_Scopes_GIF.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc091e660e3d95688bf8dd_62ed6c4a26ad07d17bb1d94d_Scopes_GIF.gif)

If at any point you’d like to re-enable a common model, enabling is as simple as turning the toggle back on!

It’s that simple! With toggles, users now have a simple way to gain control over the data they’re interacting with when they use Merge.

If you want to learn more about an easy integration with any HR, recruiting, payroll, or accounting platform, [schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintroducing-model-and-field-level-scopes) with one of our integration experts today!

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=8d605707-178b-4b1d-8471-ddf8f7907a03&bo=2&sid=16598b903e8d11f0af75cdf26b725ce7&vid=165a7b503e8d11f08f8335bac7400ff9&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Introducing%20model%20and%20field%20level%20Scopes&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintroducing-model-and-field-level-scopes&r=&lt=674&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=880848)