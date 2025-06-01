---
url: "https://www.merge.dev/blog/api-key"
title: "What is an API key? Here’s what you need to know"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-key#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-key#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-key#)

Table of contents

[What is an API key?](https://www.merge.dev/blog/api-key#what-is-an-api-key)

[API key examples](https://www.merge.dev/blog/api-key#api-key-examples)

[How to get your API key](https://www.merge.dev/blog/api-key#how-to-get-your-api-key)

[API key pros and cons](https://www.merge.dev/blog/api-key#api-key-pros-and-cons)

[Best practices for using API keys](https://www.merge.dev/blog/api-key#best-practices-for-using-api-keys)

[Avoid authenticating to every 3rd-party API you want to integrate with](https://www.merge.dev/blog/api-key#avoid-authenticating-to-every-3rd-party-api-you-want-to-integrate-with)

[API key FAQ](https://www.merge.dev/blog/api-key#api-key-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-key)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API integration security: what it is and best practices**](https://www.merge.dev/blog/api-integration-security)

# What is an API key? Here’s what you need to know

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7e9622ad316dbc0168b_What_is_an_API_key_.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

API keys are an essential part of any API request.

They allow you, the requestor, to perform the specific action you want on a given resource; and they enable the API provider to both confirm that you have the appropriate permissions to perform the action and aren’t exceeding your rate limit for the current window.

To help you use API keys successfully as well as decide whether to use them in the first place, we’ll walk through how a few widely-used applications accept API keys for authentication, a common set of steps you’ll need to follow to retrieve them, and the pros and cons of using them.

But first, let’s take a closer look at what an API key is.

## **What is an API key?**

It’s a unique identifier that a client has to add to their API requests. The server uses it to validate that a client can, in fact, perform the desired action on the resource and isn’t violating their rate limit in the current window.

[![Examples of API keys for two separate applications](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f364b2d9ba3849ee2ff1d1_5Bfsf1CcLpkjPHoQRdZJ7aUkb1BbS91hMS0i7Lgh9X34pSXLwL7NxwLjkekkhIcxEvIhNZU6Q--TZU7c2ZwvDHkcFniA9ZDGvGof0g6ipHRPgbks9wyndPeh7G8BXhcVG8kF-nPvopt5blTZD6Q3x_w.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f364b2d9ba3849ee2ff1d1_5Bfsf1CcLpkjPHoQRdZJ7aUkb1BbS91hMS0i7Lgh9X34pSXLwL7NxwLjkekkhIcxEvIhNZU6Q--TZU7c2ZwvDHkcFniA9ZDGvGof0g6ipHRPgbks9wyndPeh7G8BXhcVG8kF-nPvopt5blTZD6Q3x_w.webp)

_API keys are a unique string of characters that can vary in complexity—depending on the API provider’s requirements_

Depending on the API provider and the nature of the request, the client would add the API key in their header, body, or URL.

_Related:_ [_What is low-code integration? Here's what you need to know_](https://www.merge.dev/blog/low-code-integration)

## **API key examples**

To help make our definition more tangible, let’s break down how common API providers accept API keys.

### **BambooHR**

The popular HRIS solution uses an extremely lengthy and complex API key to keep their API endpoints secure.

According to [their documentation](https://documentation.bamboohr.com/docs/getting-started), their API keys are 160-bit numbers represented in hexadecimal form. Moreover, for basic authentication, they require you to use the API key as the username and allow you to use whatever string of characters you want for the password.

More specifically, if you’re using curl to make API requests, the API key can be included before the URL and a dummy password can be added in place of “x.”

```python

curl -i -u "{API Key}:x" "https://api.bamboohr.com/api/gateway.php/{subdomain}/v1/employees/directory"

```

_Related:_ [_How REST API authentication works_](https://www.merge.dev/blog/rest-api-authentication)

### **Sendoso**

The gift-giving platform doesn’t explicitly cite the level of their API keys’ complexity. However, given the example output they use in [their documentation](https://developer.sendoso.com/rest-api/overview/authentication), we can assume that it’s complex—though not as lengthy as BambooHR’s.

To use the API key in requests, you would include it in the authorization header. In particular, it should replace “token.”

```python

curl --request GET \  --url https://app.sendoso.com/api/v3/sends \
--header 'Authorization: Bearer <token>'

```

## **How to get your API key**

Every application has a unique process for generating and accessing API keys. However, there are often a common set of steps you’ll need to follow.

Here are a few of these steps:

1. **Sign up or create an account.** As you can probably guess, you’ll need to be a user to generate an API key. You also might need to be on a certain plan and/or have a certain user role to be able to generate the API key.

2. **Navigate to your settings.** The application’s settings page or dropdown should have several buttons, where you can learn more about your subscription, users, privacy settings, API access, and more.

3. **Click on the “API” button (or something similar).** From here, you can probably find high level information on the vendor’s API as well as links that let you drill down on specific areas.

4. **Select the “API keys” button (or something similar).** You should land on a page that makes it easy to generate a unique API key.

5. **Create your API key.** Once you create it, you should copy it immediately (since the provider won’t show it again) and store it in a secure location.

_Related:_ [_How to get your ChatGPT API key_](https://www.merge.dev/blog/chatgpt-api-key)

## **API key pros and cons**

Depending on the API provider, you may be able to use authentication methods that extend beyond API keys, such as OAuth or JSON Web Tokens.

Deciding whether API keys are the right approach for your API requests, therefore, requires you to review each approach's pros and cons carefully.

We’ll help you start this exercise by highlighting the top benefits and drawbacks of API keys.

### **Benefits of API keys**

- **Accessibility:** As long as you have the right permissions, you can easily access the API key in the provider’s platform **‍**
- **Adaptable:** API keys can always be regenerated or revoked. This ensures that if they get in the wrong hands, there’ll be minimal harm to your business **‍**
- **Time to value:** Once you retrieve your API key, you should be all set to start making API requests

### **Drawbacks of API keys**

- **Exposure risks:** Your API keys can easily be discovered if the proper precautions aren’t taken, putting your data at risk
- **Manual rotations:** Some API providers don’t allow you to automatically rotate API keys (i.e., update or change them). Your team will have to carry out this work manually, which can be time-intensive and cause human errors—such as forgetting to rotate them on time.
- **Compliance:** Depending on the nature of the data being accessed, API keys may not be enough to comply with critical data protection and privacy measures, like GDPR or HIPAA

## **Best practices for using API keys**

Whenever you use API keys, you should keep the following in mind:

- **Store your keys in a secure location:** Since API keys let you access sensitive data, they can do the same for anyone else who gets their hands on them. To limit API key use to the appropriate set of individuals at your organization, you can store and manage them in a secrets management service (e.g., AWS Secrets Manager)

- **Use separate keys for different environments:** In other words, use unique API keys for testing, development, and production environments. Doing so reduces the potential harm of a compromised API key, as it likely can’t access data in production

- **Rotate API keys for sensitive data frequently:** By rotating these API keys often (e.g., every 4 weeks) you’re able to mitigate any adverse impact attackers have on your business

- ‍ **Monitor a range API key-related activities:** This can include when requests with API keys are used, which keys were used, what the outcomes were, where the requests came from, and more to quickly identify potential issues

_Related:_ [_A guide to monitoring API integrations_](https://www.merge.dev/blog/integration-monitoring)

## **Avoid authenticating to every 3rd-party API you want to integrate with**

The process of finding your API keys across software providers, incorporating them into your API calls, rotating them consistently, and more, can quickly overwhelm your team. This is especially true when you consider all the other steps of building to an API and the sheer volume of API connections you need to build and maintain.

To help your engineers avoid all of this complexity, you can simply build to Merge’s Unified API.

Once you’ve built to it, you can add hundreds of integrations to your product, allowing you to cover all the customer-facing integrations your clients and prospects want and need.

‍ _You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-key) _._

## **API key FAQ**

In case you have any more questions on API keys, we’ve addressed several more below.

### **When should you use API keys?**

Since API providers determine their method(s) of authentication, you typically can’t decide whether to use API keys; you either need to use them or you can’t.

In some cases, however, an API provider lets you choose from several authentication methods. For instance, they might let you authenticate via API keys, OAuth 2.0, or through basic authentication.

Whenever your authentication options include and extend beyond API keys, you should compare the methods carefully to determine the one that’s most secure for your business.

### **What’s the difference between an API and an API key?**

An API key is a component of an API; it ensures that a resource exposed from an endpoint is accessed securely and without violating the provider’s rate limit policies.

### **How much does an API key cost?**

The cost of accessing one depends on the API provider.

Some API providers require you to enter into a formal business partnership to access their API key (among other items, like their [sandbox accounts](https://www.merge.dev/blog/api-sandbox)). These partnerships can cost anywhere from $10-50k per year.

That said, most API providers will make their API keys readily accessible and without any charges; you’ll just need to create accounts with the API providers—which include their free plans—and follow a few simple steps (as outlined earlier in this article) to generate it.

### **What are the different types of API keys?**

There are public and private API keys.

Private API keys are any that can be generated by an individual who’s met certain requirements, such as having an account set up. They’re specific to that individual and can be used to access sensitive data and functionalities that fall within the individual's scope of permissions.

Public API keys, on the other hand, are any that several individuals—if not anyone—can use to access publicly-available data or functionality in a product.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5e3e80e-6076-4456-b610-20d21510b5d6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=be2c9fbc-4946-4b23-80a7-e9078e790d23&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-key&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5e3e80e-6076-4456-b610-20d21510b5d6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=be2c9fbc-4946-4b23-80a7-e9078e790d23&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-key&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=fe6d377a-ea9e-483b-96f8-72696351a1bb&bo=2&sid=46c016b03e8d11f09123371c7cccb2d1&vid=46c065603e8d11f0a0424f516fb1cf13&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=What%20is%20an%20API%20key%3F%20Here%E2%80%99s%20what%20you%20need%20to%20know&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-key&r=&lt=951&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=281797)