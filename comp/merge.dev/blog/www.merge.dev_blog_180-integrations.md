---
url: "https://www.merge.dev/blog/180-integrations"
title: "What the new version of “180 integration” means and why it’s detrimental to your business"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/180-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/180-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/180-integrations#)

Table of contents

[180 integration overview](https://www.merge.dev/blog/180-integrations#180-integration-overview)

[The drawbacks of 180 integrations](https://www.merge.dev/blog/180-integrations#the-drawbacks-of-180-integrations)

[Merge provides the integrations your clients need and expect](https://www.merge.dev/blog/180-integrations#merge-provides-the-integrations-your-clients-need-and-expect)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F180-integrations)

##### Just for you

No items found.

# What the new version of “180 integration” means and why it’s detrimental to your business

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

A 180 integration has, historically, been a synonym for a [one-way sync with a 3rd-party API](https://www.merge.dev/blog/one-way-sync). In other words, it either involves reading data from or writing data to a platform through API requests and responses.

However, specific integration vendors have managed to muddy the waters by carving out another meaning for the term—confusing both prospects and clients.

This rebranded version of 180 integration fundamentally differs from its predecessor. More than that, it presents an approach to [product integrations](https://www.merge.dev/blog/product-integrations) that carries performance issues and security risks.

Given their issues, we never considered offering 180 integrations—we only provide API-based integrations. We’ve also taken additional measures to ensure that our integrations are secure and performant. For example, we offer enterprise-grade security features, like scopes and activity audit logs; and we ensure that our integrations can access any fields and objects, sync data in real-time, and are easy to monitor by offering [webhooks](https://docs.merge.dev/basics/webhooks/overview/), [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/), robust [Integration Observability tooling](https://www.merge.dev/features/integration-observability), and more.

With that said, let’s take a closer look at why a 180 integration is worth avoiding at all costs by breaking down how it functions and highlighting the top drawbacks of using it.

_Note: For the purposes of this article, we’re only referring to 180 integrations that are provided by 3rd-party platforms. If a company provides 180 integrations directly to clients, many of the drawbacks highlighted below aren’t as—if at all—applicable._

## **180 integration overview**

Assuming you use a 180 integration to power a product integration, here’s how it’d work: Every time you make an API call to the 3rd-party integration provider, the provider—or, more likely, whoever the provider contracts the work out to—manually logs into an end-user’s platform (i.e. your client’s platform), downloads or copies the data they care about, and adds it to the integration provider’s platform. The integration provider then normalizes this data and shares it back to you.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65974827cc72d2e9e393e704_180%20integration%20(3).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65974827cc72d2e9e393e704_180%20integration%20(3).webp)

## **The drawbacks of 180 integrations**

The issues associated with using 180 integrations come in a few different forms:

[![The drawbacks of 180 integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/659745eb482b92a91a37da19_aW-VzhGkfcBijrWzlU_N9JtoKLRURbip1umf-i_J4udlInsjZcQ6zkWECPLLIZkQ_Z4AgeE0CsOrykpQBeYs7Wku0Yb8bOtWqn5sBvQan8v21mYWEpxKtWzZxmbYg7s6ZEt5fK65lSV4-rmG8LsGU6U.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/659745eb482b92a91a37da19_aW-VzhGkfcBijrWzlU_N9JtoKLRURbip1umf-i_J4udlInsjZcQ6zkWECPLLIZkQ_Z4AgeE0CsOrykpQBeYs7Wku0Yb8bOtWqn5sBvQan8v21mYWEpxKtWzZxmbYg7s6ZEt5fK65lSV4-rmG8LsGU6U.webp)

Let’s take a closer look at each:

### **Disappointing customer experience**

Your clients aren’t just giving their login credentials to an integration provider (which, in and of itself, would be bad enough); they’re giving it to an individual or organization that the integration provider contracts this work out to.

Your clients don’t know who this contractor(s) is—let alone who the integration provider is—, so they’ll likely feel deeply uncomfortable with giving them access to their company’s sensitive and business-critical information. Merely asking clients for their login credentials and having to explain how your 180 integration works can, therefore, be all it takes to diminish their trust in your business, along with their appetite for using your product.

### **High security risk**

Asking clients to pass their login credentials along to someone they don’t know isn’t just uncomfortable—it’s also unsafe.

Since the 3rd-party contractor needs admin-level permissions to your clients’ applications, they’ll likely have access to data that leads your clients to violate data privacy laws and regulations, such as HIPAA and GDPR. The 3rd-party contractor can also use the data in ways that harm your clients and their employees or customers, whether that’s changing the data in your clients’ applications, removing the clients’ users from their applications, and even selling the information from your clients’ applications on the dark web.

### **Poor performance**

Given the fact that the process is entirely manual on the integration provider’s end, you’ll have to wait a while to receive data from—or add data to—a client's application. In most cases, an API response takes multiple weeks to come back, which likely falls well below your clients’ expectations and needs.

In addition, 180 integrations typically scope a limited set of data, which prevents your clients from accessing a lot, if not all, of the data they’re interested in. And they don’t let you keep a log of the API calls and responses, which makes it difficult to diagnose and remediate integration issues on your clients’ behalf.

## **Merge provides the integrations your clients need and expect**

Merge, which is a single platform that lets you add an entire category of integrations to your product, neatly addresses all of the drawbacks of 180 integrations.

As mentioned in the beginning, all of our integrations are API-based, which ensures that they’re performant (you can sync data at least once a day, if not more often) and secure (your clients never have to share their login credentials with a random 3rd-party).

Finally, your customer-facing team gets access to our full suite of [Integration Observability features](https://www.merge.dev/features/integration-observability), allowing them to help your clients identify, troubleshoot, and resolve any integration issues quickly and easily; and we perform [integration maintenance](https://www.merge.dev/maintenance) work on your engineers’ behalf—all but ensuring that your integrations are reliable over time.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F180-integrations).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8e546b56-d9fc-4827-9cf5-9b9dc86c6428&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0d32c8b1-cc67-4f01-bc3a-67eb039684a4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F180-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8e546b56-d9fc-4827-9cf5-9b9dc86c6428&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0d32c8b1-cc67-4f01-bc3a-67eb039684a4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F180-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ccdf6c32-216a-4123-983e-ddc35477d608&bo=2&sid=d34730c03e8b11f0bc3031eb8abf371d&vid=d3475e203e8b11f080227f29501621fb&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=What%20the%20new%20version%20of%20%E2%80%9C180%20integration%E2%80%9D%20means%20and%20why%20it%E2%80%99s%20detrimental%20to%20your%20business&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2F180-integrations&r=&lt=417&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=661958)