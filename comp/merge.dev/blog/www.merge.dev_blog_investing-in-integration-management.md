---
url: "https://www.merge.dev/blog/investing-in-integration-management"
title: "Investing in Integration Management"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/investing-in-integration-management#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/investing-in-integration-management#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/investing-in-integration-management#)

Table of contents

[What to anticipate for integration management (at scale)](https://www.merge.dev/blog/investing-in-integration-management#what-to-anticipate-for-integration-management-at-scale)

[Conclusion](https://www.merge.dev/blog/investing-in-integration-management#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Finvesting-in-integration-management)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**System integration: definition, examples, challenges, benefits**](https://www.merge.dev/blog/system-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API error handling: definition, example, best practices**](https://www.merge.dev/blog/api-error-handling)

# Investing in Integration Management

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadbbb5568970b2d91a_8.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

_You’re probably looking into the scope of your next integration project and thinking:_ what have I gotten myself into?

At Merge, we’re no strangers to integrations. While you probably have the upfront cost of building integration in your head: the engineering resources required to map and normalize data, the changes and updates to your front-end, UX, and team enablement, a prickly realization may emerge as you continue to add more and more integrations:

_There’s a lot more that goes into offering integrations at_ **_scale_** _than stringing together a few more endpoints_.

In fact, we’d argue that **integration management -** or, the activities, infrastructure, and time that you need to spend around the connections you build - soon begins to eclipse the actual cost of building the integration itself.

In this article, we’ll cover **the areas of integration management you need to anticipate as you scale out your integration offerings**, and look into how a unified API can work to alleviate those costs for you.

_Related:_ [_A guide to monitoring integrations_](https://www.merge.dev/blog/integration-monitoring)

## **What to anticipate for integration management (at scale)**

### **Authentication**

Every API is going to have a different form of how they handle authentication parameters (otherwise known as - how you’re able to identify yourself as an authorized user).

You’ll need to anticipate building and scaling out infrastructure that handles everything from basic authentication, to OAuth, to the weird forms in between (trust us - we’ve seen it all). While it may feel reasonable to manage just a few forms of authentication at first, as you scale your integration offerings into the tens of dozens the work of managing tokens, configuring access, and maintaining authentication with third-party platforms may start to take over more of your engineering time than you think. When platforms change protocols, things tend to break.

Unified APIs require just one form of authentication for every integration they offer. Merge, for example, uses just two primary protocols: a Merge API Key (to show you’re a Merge user) and a Linked Account Token (to specify which user and integration you’re authorized to access) to securely handle authentication for all of its APIs. Read more about the technical aspects of unified API authentication [here](https://merge.dev/docs/basics/authentication/).

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cca7_62d72023d0b190c371838c54_Code_Snippets_dark.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cca7_62d72023d0b190c371838c54_Code_Snippets_dark.gif)

_User authorization is handled via a single modal, called Merge Link, that passes on secure tokens to allow your app to programmatically handle authentication_

_Related:_ [_What is integration security? Here's what you need to know_](https://www.merge.dev/blog/integration-security)

### **Integration Maintenance**

Companies change. APIs change. Endpoints change. Your customers’ expectations that your integration work? They probably don’t change. In the best-case scenario, a platform will send out a notice about breaking changes, whether they be a deprecated endpoint or adjustments to required parameters. In the worst case, a change like this could happen overnight, impact your customers’ experience with your app, and cause your team to scramble to come up with a solution.

For a company that focuses on integrations, a unified API’s responsibility is not just building integrations, but maintaining them for the long term. Whether through [responsive customer service](https://www.g2.com/products/merge-api/reviews) or rapid patch notes, a unified API acts as the support team for integrations.

### **Control of Data - Object and Field Level Scopes**

How do you assure your users you’re only pulling the data they want you to?

As you scale your integrations, you’re probably considering how to move upmarket, too. Different customers will set different requirements over what data you can access on their behalf. You’ll probably need to accommodate this and build in the flexibility that will make this work across different users and different integrations. For example, if you deal with HR data, it’s not difficult to imagine a customer stipulating that your app is only able to process an employee’s first name, last name, and department (and nothing more).

A unified API handles this situation by providing built-in toggles for **object and field level scopes**. Simple switches, accessible from a management dashboard, allow you to configure what data is pulled at the **object level** (for example, never pulling something that is related to an Employee’s [Bank Info](https://merge.dev/docs/hris/overview/)) as well as the field level (for example, never pulling something related to an Employee’s **home address).** This way, you can guarantee your user that you only have access to the data that’s required to get the job done, and nothing more.

If you’re curious about how a platform like Merge handles object and field-level data controls, read more here.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cca2_62d720562eecc368d80140e8_Object_Scopes.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cca2_62d720562eecc368d80140e8_Object_Scopes.gif)

### **Rate Limits**

Rate limits are a lot like authentication: they vary from API to API, have their own nuances within systems, and are absolutely critical to consider when you think about the long-term health of your integrations at scale.

Managing API calls on behalf of many users to just one API platform is a challenge: imagine that on the scale of thousands or millions of API calls every day. At Merge, rate limiting is mission critical, and we’ve written [at length](https://merge.dev/blog/engineering/how-to-stop-being-rate-limited-best-practices-for-making-api-calls-at-scale/) about what to expect when building out your own system (and provide some insights on how we maintain our own. It’s safe to say we handle all the nuances of rate limit tracking for you.

### **Logs**

Third-party APIs typically have some form of response when things go wrong. Those responses, however, can be hit or miss. Sometimes error messages can be vague or misleading, sometimes they might not even be in your native language - it truly depends on the platform you’re integrating into. (If you’ve noticed a theme here, it’s that the difficulty of integration maintenance usually arises from just _how_ many ways different APIs manage different pieces).

A unified API often offers a single, standardized way of searching, viewing, and understanding logs across multiple integrations. For example, Merge features [fully searchable logs](https://www.merge.dev/blog/introducing-api-log-search) that cover every request you make to Merge and Merge makes to third-party platforms.

With additional developer-focused functionality like debug\_mode (a parameter that returns every log associated with an API request _in_ the API request) - unified APIs offer features that make your developer’s lives far easier.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cc9f_630e2585607f5fe36df2c99f_WEBHOOK%2520LOG.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689cc9f_630e2585607f5fe36df2c99f_WEBHOOK%2520LOG.gif)

_Related:_ [_A guide to API integration security_](https://www.merge.dev/blog/api-integration-security)

### **Issues**

As you go through the roll-out of your integration, it’s important to know that sometimes **basic** things break. API keys expire and permissions change. Even though the solution to these issues may be quick: just asking your user to refresh their key or adjust their access level, your ability to diagnose what these issues depend on the tooling you’ve built out around your integration infrastructure.

Unified APIs like Merge can offer full Issues dashboards and tooling that make it easy and accessible for your team to diagnose these types of problems. Merge features a section of its dashboard dedicated to providing insight into not just the thing that went wrong, but offers functionality that allows a member of customer success (and not engineering) to fix it.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689ccaa_62d720fd5f2bc18f1e4c147c_Issues.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08f80b0c47c26689ccaa_62d720fd5f2bc18f1e4c147c_Issues.gif)

_Related:_ [_Best practices for sourcing and enabling integration partners_](https://www.merge.dev/blog/integration-partners)

## **Conclusion**

As you continue to scale out your integration strategy, it’s important to consider **all** aspects of where you’ll need to invest time and resources to make your integrations work for you.

If you’re interested in exploring more about how a unified API works to handle all of these aspects of integration maintenance and more, then explore your own Merge Dashboard. Signing up for an account is free, and you’ll be able to investigate Logs, Issues, and more with demo data. It’s a great way to get started.

If you think a unified API might be suitable for your integration strategy and want to discuss your use case further, then feel free to [schedule a call with our experts](https://www.merge.dev/campaigns/pain-free-integrations) or reach out to us over Intercom. We’re more than happy to help talk through what your integration goals are and what solution works best for you.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b022d279-578a-4a52-9c77-5f8b497a0588&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bbc39662-9a23-452a-852e-286ca9665631&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Finvesting-in-integration-management&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b022d279-578a-4a52-9c77-5f8b497a0588&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bbc39662-9a23-452a-852e-286ca9665631&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Finvesting-in-integration-management&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

td.doubleclick.net

# This site can’t be reached

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743465090&cv=11&fst=1748743465090&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103211513~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&ptag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Finvesting-in-integration-management&\_ng=1&hn=www.googleadservices.com&frm=0&tiba=Investing%20in%20Integration%20Management&npa=0&pscdl=noapi&auid=1005103667.1748743465&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

ERR\_SOCKET\_NOT\_CONNECTED

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743465090&cv=11&fst=1748743465090&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103211513~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&ptag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Finvesting-in-integration-management&\_ng=1&hn=www.googleadservices.com&frm=0&tiba=Investing%20in%20Integration%20Management&npa=0&pscdl=noapi&auid=1005103667.1748743465&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

![](<Base64-Image-Removed>)![](<Base64-Image-Removed>)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=6dc8868e-8c79-48fa-918f-fd694e16b99d&bo=2&sid=bdefe5a03e8c11f0b635293e3163a59f&vid=bdf0d1e03e8c11f083f6b5a75cf6ec17&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Investing%20in%20Integration%20Management&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Finvesting-in-integration-management&r=&lt=494&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=43956)