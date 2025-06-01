---
url: "https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis"
title: "Building integration-first products right using adaptive UIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#)

Table of contents

[The Mixed-Functionality Problem](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#the-mixed-functionality-problem)

[The Solution: Build an Adaptive UI](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#the-solution-build-an-adaptive-ui)

[How does Merge help implement this? “Available Actions.”](https://www.merge.dev/blog/building-integration-first-products-right-using-adaptive-uis#how-does-merge-help-implement-this-available-actions)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbuilding-integration-first-products-right-using-adaptive-uis)

##### Just for you

No items found.

# Building integration-first products right using adaptive UIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7387ff8c191004c1e8_6.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

## The Mixed-Functionality Problem

When building an integrated product, we need to acknowledge that not all integrations are created equal.

For example, your vision is to create an interactive application that allows companies to build and plan org charts. The application needs to visualize data fed from HR systems for employees, managers, teams/departments, job titles, and relevant compensation data. To maximize TAM, you want to make sure you’re able to offer integrations with your customers’ respective HR systems. In theory it all sounds fine and dandy, but in practice you will inevitably encounter a problem: mixed-functionality.

**Mixed-functionality means you are completely limited by the functionality of the other application when building integrations.** The application you’ve envisioned _should_ display an interactive organization chart with layers of hierarchy, similar to a family tree. That makes user-sense. The problem is, the vast majority of common HR systems do not store team hierarchy. Employees belong to departments, but teams do not have references to parent or children teams. How can we reconcile this?

_Related:_ [_What best-in-class integration monitoring tools offer_](https://www.merge.dev/blog/integration-monitoring-tools)

## The Solution: Build an Adaptive UI

If a platform doesn’t store team hierarchy such as parent and children, our vision of building a family-tree style org chart faces two choices. We either throw out our initial design completely, or we cut out a significant portion of our market by using less feature-rich platforms to power an HR function. Both aren’t great.

By going back to the drawing board and designing a slightly different experience — such as showing all teams side by side, or approximating based on other information such as manager — you can... but this eventually becomes a game of whack-a-mole where you end up hitting yourself on the head just to cater towards the lowest common denominator. Mixed-functionality looks bleak, unless…

The storied third option: **build a UI (user interface) that adapts to the functionality of each given platform to instantly support a wider customer base.**

At Merge, we’ve found that more and more platforms are simply opening up. Companies not only allow increased access to their APIs, but also invest heavily in the developer experience. Existing APIs are modernized and support increased functionality. For each integration, we know we have to build our integrations in a way that supports the maximum amount of functionality these APIs support. This means our user interface _must_ be adaptable.

## How does Merge help implement this? “Available Actions.”

When building an adaptive UI-based application with Merge, it is imperative to take advantage of the [Available Actions](https://www.merge.dev/docs/hris#available-actions?utm_source=blog-adaptive-uis) endpoint. Available via our API and SDKs, this endpoint allows you to ask Merge: “For this given customer’s choice of platform, what functionality am I able to take advantage of?” When you ask Merge for information on a given customer, we respond to you with the following information:

- **Available operations:** This piece of data is the most important when building an adaptive UI. For the provided customer’s integration, we return each supported data model, the supported fetch/create/update/delete operations, the supported fields, and the required fields to create an instance of that model.
- **Integration data:** Includes name, categories, image, square image, and primary color. Using this information, you can display a custom UI that accurately reflects the integration your user has chosen to link.
- **Passthrough available:** This is almost always true, and it defines whether you are able to use the [Passthrough endpoint](https://www.merge.dev/docs/hris/#passthrough?utm_source=blog-adaptive-uis) to make custom requests of any kind to the given API. Remember: anything that is possible with native APIs is possible with Merge using [Supplemental Data](https://www.merge.dev/docs/supplemental-data/?utm_source=blog-adaptive-uis).

Remember our HR-hierarchy problem? Using Merge, your platform simply needs to check if **available actions** include a supported field for the data you need. It’s that simple.

Keeping up with evolving APIs is not fun. We make sure you don’t have to. Our team constantly monitors platforms for new functionality and adds support where needed. Our Unified API makes it possible to automatically adapt to new functionality as it’s released.

Want to try it yourself? [Sign-up](https://app.merge.dev/signup?utm_source=blog-adaptive-uis) for a free demo today.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7f08bbfc-f32d-41a7-9639-7c4875add477&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1d0be971-9130-4c6a-9e68-90ac86e2531e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-integration-first-products-right-using-adaptive-uis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7f08bbfc-f32d-41a7-9639-7c4875add477&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1d0be971-9130-4c6a-9e68-90ac86e2531e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-integration-first-products-right-using-adaptive-uis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ba21ad4a-c36b-42c5-b7f6-b20508a2a45e&bo=2&sid=e9e43c203e8d11f08ffcc3ef9557411c&vid=e9e455603e8d11f098d9171879655681&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Building%20integration-first%20products%20right%20using%20adaptive%20UIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-integration-first-products-right-using-adaptive-uis&r=&lt=512&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=291842)