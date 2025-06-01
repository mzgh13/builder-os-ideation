---
url: "https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first"
title: "Integrations in 3 methods — why Merge is API-first"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#)

Table of contents

[Scraping? For enterprise data?](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#scraping-for-enterprise-data)

[Internal APIs — could that be an alternative?](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#internal-apis-could-that-be-an-alternative)

[Official APIs](https://www.merge.dev/blog/integrations-in-3-methods-why-merge-is-api-first#official-apis)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegrations-in-3-methods-why-merge-is-api-first)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c748a90c28c8112da97_iPaaS_vs_embedded_iPaaS.webp)**A guide to API-led integration**](https://www.merge.dev/blog/api-led-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)**13 API integration tools to consider using in 2025**](https://www.merge.dev/blog/api-integration-tools)

# Integrations in 3 methods — why Merge is API-first

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ceba6710a493b164a4a_API_vs_screen_scraping.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca144474ee504865a64c_Gil%20Feig%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538373652c2e2b27cb16_62eff29f5cac0a91347b9dbd_gil-feig.webp)

Gil Feig

CTO and co-founder

@Merge

Enterprise B2B companies need to integrate and maintain an average of 90+ vendors to ensure customer satisfaction. Developers need to decide the best method to build those integrations: scraping, reverse-engineering internal APIs, or [building with official APIs](https://www.merge.dev/blog/building-integrations). At Merge, we build our integrations with official APIs because of their speed, scalability, and stability. [**We build for enterprise customers.**](https://medium.com/mergeapi/why-we-started-merge-1fd19c18b263)

## **Scraping? For enterprise data?**

Yup. This time-tested method for pulling data is also the easiest way to build-out an integration. A scraperpulls information from the target platform as if you were copy and pasting all the data yourself. What you see on an HR platform, the computer sees and compiles.

Scraping is visual: you’re pinpointing the user interface (UI) elements of the target platform to pull relevant data for your API. Since you only need to have a registered account, getting access isn’t a hassle. Scrapy, Beautiful Soup, and Selenium are popular technologies that exist to help you scrape with blistering ease.

**Scraping seems great! What could go wrong?**

A lot — we’ll break it down by stage.

Scrapers start by logging in to user accounts. If a user’s session expires, the scraper will need a new sign-on. But with tiered security: 2-factor authentication, Google authentication, and FIDE keys, you’re now requiring a physical person to log back on and re-authenticate their server. That’s an unnecessary hassle for your customer.

Remember that part about the UI that made scraping so easy? It’s also its biggest weakness. UI gets tweaked, HTML elements change, and links break all the time. The customer doesn’t care about “session links” or “UI adjustments — ” they care about their product working. With scraping, developers leave too many critical variables out of their control.

Even if you had a fully built-out, well-maintained scraping integration, you’re still not going to be the best in show: scraping is plain slow. Imagine pulling 10,000 employees from a system by going page by page. Because you’re reliant on a public UI, you’re dependent on that UI’s speed.

**While scraping may be easy to demonstrate as a proof of concept, it’s simply unacceptable for the requirements of enterprise-level integration management.**

_Related:_ [_Scraping vs APIs_](https://www.merge.dev/blog/screen-scraping-vs-api)

## **Internal APIs — could that be an alternative?**

Absolutely. Remember: the internal API communicates data between the front-end (what the user sees) and the back-end (the logic controller of the website). Through any browser you can study network traffic, just like you can inspect elements and adjust HTML. Studying the network requests that a platform makes shows you how the internal API behaves. By repeating the requests the website makes, your own integration is able to pull data.

With internal APIs, reliability is more dependable than scraping. Even though you’re going in ‘blind,’ assuming you craft a decent integration, a platform rarely changes its API to be backward incompatible. And, compared to scraping, reverse engineering is significantly faster: you’re only making a few directed requests as opposed to pulling from tens of thousands of individual pages.

**Sounds great — but I feel like something could be wrong…**

You’re absolutely right. Companies can still change internal APIs without notice, which could break how your integration talks to the backend. Additionally, you may not have all of the data you need to make smart decisions. Since you’re still going off of what is publicly available, only a minimal amount of data is passed down from the website to populate the given UI. Behind the scenes, there is a whole host of data that you’re missing out on.

_Related:_ [_What is external system integration? Here's what you need to know_](https://www.merge.dev/blog/external-system-integration)

## **Official APIs**

Now the good stuff. Official APIs are by far the best way to integrate — they just need a little extra love from the developer (hint: this is where Merge comes in).

This involves integrating with an API explicitly created for this purpose. A given platform allows external companies to integrate with their product. Unlike with scraping, a user never has to re-authenticate their integration: it’s permanent until disconnected. In terms of speed and quality, there’s nothing better. An integration built with the Greenhouse API can pull 5,000,000 candidates in minutes. Imagine scraping that: it would take hours or even days. Most official APIs allow the pushing and pulling of almost every piece of data, meaning you can have all of the information you need.

Official APIs are directly supported by their platforms, making them highly reliable. Companies know backward-incompatible changes could break integrating applications, so they agree not to. Additionally, platforms seek to be developer-friendly. They often advertise partnerships with companies who use their official APIs — you can see some of ours [here](https://www.merge.dev/categories/hr-payroll-api) and [here](https://www.merge.dev/categories/ats-recruiting-api).

**So what’s the catch?**

There are a few for the developer building out the integration.

Linking accounts is a bit more complicated, and may involve getting an API key.

**With Merge, that’s not necessary.** We make connecting with official APIs simple for end users.

Different platforms also expose data in different ways, and this can lead to headaches when accessing large quantities of data from different vendors. With Merge’s Unified API, we’ve already done the heavy lifting to normalize your data. Your job is to use it.

Integrating once with Merge gives you access to over 60+ integrations in HR, payroll, and recruiting. Want to test it out yourself? Sign-up for a demo [here](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegrations-in-3-methods-why-merge-is-api-first).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a6c66be0-1b6e-4ee7-b790-4b937da0af0f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4d010ec2-d0c0-4974-bcb4-fa2491b3ec9d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegrations-in-3-methods-why-merge-is-api-first&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a6c66be0-1b6e-4ee7-b790-4b937da0af0f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4d010ec2-d0c0-4974-bcb4-fa2491b3ec9d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegrations-in-3-methods-why-merge-is-api-first&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=bd137745-bb06-42f2-b19a-e29ee48f6ff4&bo=2&sid=3fc1e0203e8e11f0a4793d7c56c63c60&vid=3fc3d5403e8e11f0b9594187a72d9dec&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Integrations%20in%203%20methods%20%E2%80%94%20why%20Merge%20is%20API-first&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegrations-in-3-methods-why-merge-is-api-first&r=&lt=482&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=734890)