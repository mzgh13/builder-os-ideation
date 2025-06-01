---
url: "https://www.merge.dev/blog/api-integration-best-practices"
title: "7 best practices for building and maintaining API integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-integration-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-integration-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-integration-best-practices#)

Table of contents

[Overview on API integrations](https://www.merge.dev/blog/api-integration-best-practices#overview-on-api-integrations)

[API integration and maintenance challenges](https://www.merge.dev/blog/api-integration-best-practices#api-integration-and-maintenance-challenges)

[Best practices for building API integrations](https://www.merge.dev/blog/api-integration-best-practices#best-practices-for-building-api-integrations)

[Best practices for maintaining API integrations](https://www.merge.dev/blog/api-integration-best-practices#best-practices-for-maintaining-api-integrations)

[Final thoughts](https://www.merge.dev/blog/api-integration-best-practices#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API integration security: what it is and best practices**](https://www.merge.dev/blog/api-integration-security)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856caf87ff8c191004f86e_Multiple_API_integration.webp)**API integration support: what to expect for native integrations**](https://www.merge.dev/blog/api-integration-support)

# 7 best practices for building and maintaining API integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

James Walker

@Merge

Navigating the API integration process can be daunting because you need to orchestrate technical concerns, usage constraints, and documentation requirements.

This article will guide you through seven best practices that'll ensure your API integrations are a success, regardless of whether you're building integrations between your internal applications or between your product and clients' applications.

## Overview on API integrations

API integrations let you easily deploy advanced functionality that would be too complex or time-consuming to build yourself. For instance, integrating with [Stripe](https://stripe.com/docs/api) lets you process payments within your app, and using the [ChatGPT API](https://openai.com/blog/introducing-chatgpt-and-whisper-apis) provides access to cutting-edge generative AI.

The process of creating an API integration involves, first, reading the provider's documentation and, second, in your project, writing code that consumes the API. Once you've developed the integration, you should test it to ensure it functions correctly and is compliant with the provider's requirements. After launch, you must maintain your integration as changes occur within your product (assuming it's a [product integration](https://www.merge.dev/blog/product-integrations)) and the API.

#### Add hundreds of integrations to your product with ease

Learn how Merge can help you add and maintain hundreds of product integrations through our Unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-best-practices)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## API integration and maintenance challenges

API integrations simplify complex software development tasks. However, the teams responsible for building and maintaining integrations routinely face several challenges:

- **API versioning:** API vendors frequently release new API versions. You may have to upgrade versions to access new features. However, switching to a later version could break your existing integrations.
- **APIs that change over time:** APIs can change over time, even when a new version hasn't been released. Vendors that don't version their APIs or that make small behavioral changes without warning can unexpectedly disrupt your services.
- **Authentication and security:** API integrations need to be correctly configured with credentials that let your app authenticate to the third-party service. The security of data, credentials, and integration config values needs to be preserved at all times.
- **Error handling:** API interactions are asynchronous activities that occur across network boundaries. Any feature used by your integration could fail due to API downtime or network issues. It's vital that [robust error handling](https://www.merge.dev/blog/api-error-handling) is included.
- **Scalability:** Using an API integration makes you dependent on that third-party service. This can affect the scalability and reliability of your own app (assuming it's a customer-facing integration). For example, growth in your customer base could exceed limits applied by the API provider.
- **Testing:** API integrations should be supported by test suites that let you verify that each feature works correctly. Without tests, it's challenging to check whether your app is adversely affected by API updates.
- **Rate limiting:** Rate limiting is ubiquitous among API providers. You'll be temporarily blocked if you send too many requests in a given period; this is to preserve a global quality of service. You should implement mechanisms that handle rate limiting and schedule a retry later on as well as automated warnings when a rate limit overage is about to occur.
- **Documentation and knowledge transfers:** Long-term maintenance of APIs is often troublesome because it's unclear what APIs are used and how they work. Clear documentation is essential to keep developers informed.

To succeed with your integration, you need to efficiently mitigate these challenges so that API-powered app functionality is both reliable and easy to implement. You can achieve this by utilizing the following API integration best practices.

_Related:_ [_Common API integration challenges_](https://www.merge.dev/blog/api-integration-challenges)

## Best practices for building API integrations

The techniques in this section focus on strategies that help you build API integrations at the point when you add them to your product or another app you use internally. They'll ensure your integration is functionally robust.

### Understand the API before integrating it

The first stage of any API integration should focus on research and understanding. Individual APIs often have their own best practices and standards that you should follow. It's also important to learn the API's data model, URI structure, and the formats in which it provides and receives data.

Here are a few areas to focus on:

- **URLs for live and staging environments:** Discover the API endpoints used for different environments so you know where to direct requests, both during development and in production.
- **Error formats:** Learn how the API reports errors and what you can do to respond to them.
- **Response formats:** Check which response data formats are supported, such as JSON and XML; then decide how you'll parse them.
- **Different API types:** Many platforms offer multiple APIs for the same service, such as [REST](https://www.redhat.com/en/topics/api/what-is-a-rest-api) and [GraphQL](https://graphql.org/). Before deciding which you'll use, it's worth checking if any of the features you require are only present in one of the versions.

Analyzing the documentation before you integrate should create a sense of familiarity with the API and the features available. For example, Stripe's API supports parameters that allow you to [expand nested objects](https://stripe.com/docs/api/expanding_objects) in API responses, while GitLab's API defines a [standard syntax for pagination](https://docs.gitlab.com/ee/api/rest/#pagination) that applies across most of its endpoints. You need to understand the conventions of the specific API you're using before you can successfully integrate it into your project.

### Support API versioning

APIs are continually developed as their vendors implement new features in their products. Future updates could introduce incompatibilities with your app, so it's important to plan for change as part of your [integration process](https://www.merge.dev/blog/api-integration-process).

Most major API providers use API versioning to introduce breaking changes without affecting existing integrations. Multiple versions of the API will be served at any one time; you indicate the one you're using with each API request you make. For example, GitHub allows you to specify a particular API version [by setting the X-GitHub-Api-Version HTTP header](https://docs.github.com/en/rest/overview/api-versions) in your requests.

Nonetheless, older API versions may eventually be discontinued, forcing you to upgrade.

To implement support for versioning and plan for change from the outset, you can:

- **Regularly upgrade to the latest API version:** Switching to new API releases as they become available will avoid a pressured crunch period when the old API is turned off.
- **Avoid using deprecated features:** Don't depend on deprecated API endpoints or parameters because they're likely to be removed in later versions.
- **Implement fallbacks in case an API schema changes:** Prepare for unexpected changes by ensuring you have fallbacks and alerting systems configured. For example, an email can be sent to developers if an expected property is missing from an API response.

None of these steps entirely eliminate the risk that APIs will change in ways that affect your connections, but they do allow you to create a buffer against change. This gives you time to respond to API updates more methodically.

_Related:_ [_How to integrate software successfully_](https://www.merge.dev/blog/software-integration-best-practices)

### Use standard and secure authentication and authorization methods

The supported authentication and authorization methods can vary significantly between APIs. Some providers rely on API keys, which are usually simple string values you include in your request's HTTP headers, while others require the use of a standard, such as OAuth.

Where a choice is given, it's prudent to select the securest option. This is typically OAuth because supporting API use cases is one of the specification's main aims. OAuth uses access tokens and refresh tokens to secure API access, with support for multiple token grant types.

The type of authentication used can significantly affect the complexity of your API integration. API keys or bearer tokens given in request headers are normally trivial to implement in your code, but implementing a full OAuth flow requires more work. You need mechanisms for acquiring, storing, and refreshing your OAuth tokens, which adds to the requirements list for your integration.

Although detailed OAuth implementation guidance is out of scope for this article, the following [Node.js](https://nodejs.org/en/) code illustrates a rudimentary example of how you can [authenticate your app's integration](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/authenticating-to-the-rest-api-with-an-oauth-app) to the GitHub API on behalf of a user:

```python

const axios = require("axios");
const express = require("express");

const client_id = "";
const client_secret = "";

const app_port = 8080;

app.get("/github/oauth/begin", (req, res) => {
    res.redirect(
        302,
        "https://github.com/login/oauth/authorize?" +
        `client_id=${client_id}&` +
        `scope=user:email`
    );
});

app.get("/github/oauth/complete", async (req, res) => {

    const code = req.query.code;
    console.log(`Got code ${code}`);

    const response = await axios({
        method: "post",
        url: "https://github.com/login/oauth/access_token",
        data: {
            client_id,
            client_secret,
            code
        },
        headers: {
            Accept: "application/json"
        }
    });

    const accessToken = response.data.access_token;
    console.log(`Got access token ${accessToken}`);

    const githubProfile = await axios({
        method: "get",
        url: "https://api.github.com/user",
        headers: {
            Accept: "application/json",
            Authorization: `token ${accessToken}`
        }
    });

    res.send(githubProfile.data);

});

app.listen(app_port, () => console.log(`Listening.`));

```

You can generate the values for and by registering a new OAuth application in your [GitHub developer settings](https://github.com/settings/developers):

[![Screenshot of registering an OAuth app for GitHub](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6556959c4ade217aa7888f36_539oHHe.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6556959c4ade217aa7888f36_539oHHe.webp)

To initialize the OAuth flow, you must first visit your app's /github/oauth/begin endpoint, which redirects you to GitHub to authenticate yourself. The /github/oauth/complete endpoint is then used as the callback URL that GitHub will send you back to. This exchanges the temporary OAuth code for an access token that can be used to interact with the API:

[![Screenshot of an OAuth application's registration in GitHub's developer settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6556959c51298e2ebe564b0e_IwvamXS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6556959c51298e2ebe564b0e_IwvamXS.webp)

### Respect rate limiting

It's important to respect any rate limits that your API provider applies to your API account. Overages will cause disruption to your service because you'll be unable to access the API. If repeated incidents occur, some providers may apply penalties to your account.

To this end, you should take steps to ensure you can easily monitor API utilization and react to any usage spikes. If your app is accessed by many different customers, then you might need to set up your own API usage quotas on a per-customer basis. This prevents noisy neighbor customers who frequently use your integration's functions from consuming all the capacity.

Here are a few other steps you can take to respect rate limiting:

- **Implement your own second-layer rate limiting:** As mentioned previously, adding rate limiting within your application prevents you from hitting the rate limit at the upstream provider. Your integration could disable itself when its rate limit has been reached, preventing overages.
- **Regularly review API usage and rate limits:** You should continually monitor your API usage to determine whether the rate limits on your account remain suitable. If you're regularly nearing your quota in a usage period, you should consider contacting your provider to upgrade to a more generous plan.
- **Consider whether you can reduce API usage:** Look for ways to make your API usage more efficient, such as by batching requests together where the provider supports it. This can reduce your bill by lowering the total request volume that reaches the service.

Implementing mechanisms that control rate limiting maximizes your API's integration uptime and ensures your account remains in good standing.

## Best practices for maintaining API integrations

The following best practices will help you effectively maintain your API integrations after the initial implementation period. It's critical to acknowledge maintenance requirements early so your integration can be easily adapted to support new API revisions as well as additional product requirements.

_Related:_ [_Best practices for connecting software applications_](https://www.merge.dev/blog/application-integration-best-practices)

### Write documentation

Writing comprehensive documentation for your API integration is one of the simplest and most effective ways to promote long-term maintainability. Clear documentation that details what the integration does and how it works ensures that future development teams have a clear starting point when adding features or troubleshooting problems.

Your documentation should ideally cover all aspects of the integration process, including the decisions you made at each point. This includes the following:

- **Why the integration was required and what it achieves for your app.** As your integration inventory grows, it can become unclear why certain services were required in the first place.
- **How authentication is handled and which standards are used.** Future developers need to know the API's authentication requirements and how you fulfill them, such as the mechanisms used to generate and renew access tokens.
- **What rate limits and other constraints you're subject to.** Rate limits don't just affect API usage—they can also influence future feature implementations. If another feature is added, it could cause you to hit your account's limits, so clearly documenting all applicable account constraints is important.
- **How the integration is integrated with your app, including how to test it.** The technical details of how your app uses the integration, where the code resides, how to set up a development instance, and what the testing procedures are should all be easily accessible to ensure the integration is maintainable.
- **What the potential replacement services are if the API is discontinued.** When depending on third-party services, it's always important to make contingencies for unexpected events. As part of your provider evaluation process, it's likely you'll identify several potential substitutes for the API you're using. Recording these—and how they could be implemented in your app—will help you respond promptly should your chosen solution be shutdown or compromised.

In order to be useful, this information must be stored somewhere that developers can easily find. Comments written into source files are often appropriate for technical details about the integration's implementation, but higher-level background summaries can be more useful when they're included in team-level wikis and engineering handbooks.

### Set up automated testing procedures

API integrations need to be tested to ensure they function—and continue to function—as expected. As API versions change, it's likely that some of your features will break or require revisions. Similarly, changes within your own app could affect your integration or cause regressions to previous fixes.

You can mitigate these risks by establishing automated testing procedures that let you verify the integration is working correctly:

- **Automate testing in your continuous integration, continuous delivery (CI/CD) pipelines.** Tests are best when they're fully automated. Running your test suite as part of your CI/CD pipeline ensures your app can't deploy with broken integrations.
- **Set up pipeline schedules to catch changes on the API side.** Because your integration could break outside your change cycle due to updates on the API side, you should also run tests periodically using scheduled pipelines. Failures act as an alert to developers that the integration may require attention.
- **Set up API test environments.** Simplify development by setting up tooling that lets you quickly create and iterate on API test environments using sandbox accounts. This helps team members quickly get started working on new features and fixes.
- **Use monitoring and logging to capture errors and unexpected events.** Errors returned by the API should be logged so you can detect issues and make changes when required. [Integration monitoring](https://www.merge.dev/blog/integration-monitoring) complements your regular tests by letting you know as soon as faults occur in production. No matter how comprehensive your test suite is, it's safe to assume some issues will occur.

Regular automated tests make it more likely you'll find and fix errors before your users do. You should implement testing from the outset so that your tests execute against a known baseline.

_Related:_ [_How to test API integrations_](https://www.merge.dev/blog/api-integration-testing)

### Establish clear feedback loops with the API provider

One final tip is to maintain clear communication lines with your API provider. APIs aren't black boxes devoid of all human interaction. Most providers have support teams who are there to assist with your integration and resolve any queries you may have.

Signing up to receive developer newsletters, release announcements, and integration guides also helps you stay informed about any updates and deprecations that could affect your integration. If you need more resources, or even extra features, it's always worth asking the provider.

## Final thoughts

Even with all these best practices in place, integrating APIs is still time-consuming and error-prone.

Fortunately, Merge, the leading [unified API platform](https://www.merge.dev/blog/what-is-a-unified-api), can help.

Simply build to one of Merge's Unified APIs to access a whole category of integrations, whether that's CRM, HRIS, ticketing, file storage, etc.

Merge also provides comprehensive maintenance support and [management features](https://www.merge.dev/features/integrations-management) out-of-the-box—empowering your customer-facing employees to manage the integrations themselves.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-best-practices) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

James Walker

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8003eb29-3787-48a7-a17f-5390dd91bf22&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b9d6c0ba-68a1-4799-802e-ababa69ffa5d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8003eb29-3787-48a7-a17f-5390dd91bf22&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b9d6c0ba-68a1-4799-802e-ababa69ffa5d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-best-practices&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=304256fd-40d5-40e7-9028-6f77cb8475c8&bo=2&sid=2e9186003e8c11f0af32efef31792f84&vid=2e91c7303e8c11f09d6a4da8a6aa4a23&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=7%20best%20practices%20for%20building%20and%20maintaining%20API%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-best-practices&r=&lt=878&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=686845)