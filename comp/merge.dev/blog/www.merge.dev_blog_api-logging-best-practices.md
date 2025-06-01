---
url: "https://www.merge.dev/blog/api-logging-best-practices"
title: "7 API logging best practices worth implementing"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-logging-best-practices#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-logging-best-practices#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-logging-best-practices#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-logging-best-practices)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7de0a9323838512e363_Autoprovisioning.webp)**What is an integration partner? Here’s what you need to know**](https://www.merge.dev/blog/integration-partners)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**API Integration Services**](https://www.merge.dev/blog/api-integration-services)

# 7 API logging best practices worth implementing

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cef5c33a545135e9dde_How_to_get_your_ChatGPT_API_key.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

API integrations inevitably break or perform poorly.

Whenever either scenario affects your organization, your team will need to quickly analyze the relevant API calls and responses. In other words, your team will need to audit an integration’s API logs to diagnose the issue.

To help you perform this analysis effectively, we’ll highlight some best practices for setting up informative, actionable, and secure logs.

#### Access comprehensive, searchable logs with Merge

Merge lets you add hundreds of product integrations through a single build. Merge also offers robust logging functionality to help you manage integration issues with ease.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-logging-best-practices)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### **Incorporate meaningful insights into your logs**

Your logs are only as valuable as the information they provide.

To maximize their value, you should include details like the endpoint that’s accessed, the request method that’s used, the specific status code that’s returned, the client that's making the request, and the timestamp of the request. You should also go a step further by including the request headers and bodies as well as the response headers and bodies if and when applicable.

[![A screenshot of logs in Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d86afb8ce23d45655f_G-20Jh5BV2KgVe6Bx5Hs2vCbb7pnYwHktyuhA6WPTiAUn53glntCf51SWZJezoli4qbkQOvNiuF1elaI8W7dFA6DQEfUTe5aSZQyvluQCxW5NM7fry9kQ1qYjMQTbYK2DjU2LhS19C6Oe-bxq_CRuqg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d86afb8ce23d45655f_G-20Jh5BV2KgVe6Bx5Hs2vCbb7pnYwHktyuhA6WPTiAUn53glntCf51SWZJezoli4qbkQOvNiuF1elaI8W7dFA6DQEfUTe5aSZQyvluQCxW5NM7fry9kQ1qYjMQTbYK2DjU2LhS19C6Oe-bxq_CRuqg.webp)

_Merge offers comprehensive logs to help you analyze any API integration at a glance._

### **Pick a single tool for logging data**

Storing logs in disparate applications presents a variety of problems.

You’ll need to hop between applications to find specific logs, which can be time consuming and tedious. You’ll also need to become familiar with different applications’ UIs and their specific logging formats and standards, which can take time. Finally, certain logging applications may not offer the same level of security controls, leaving you potentially vulnerable if those applications' logs collect sensitive data.

When you couple these factors together, it becomes clear that logging data in multiple places can compromise your team’s ability to troubleshoot and debug issues quickly, effectively, and safely.

_Related:_ [_How API logs work_](https://www.merge.dev/blog/api-logs)

### **Redact sensitive information**

Your API integrations likely handle sensitive data on employees and clients, such as social security numbers, banking information, home addresses, etc.

Storing this information via logs can lead you to become non-compliant with prominent privacy measures and regulations (e.g. GDPR), and it can lead ill-intentioned individuals to access the information, which carries risk for the employees and clients associated with the data.

To prevent the scenarios above from coming to fruition, you can use specific methods to proactively redact confidential information. For example, you can use pattern matching to replace sensitive data with hashed values; or you can use data masking to only show certain information (e.g. the last four digits of a social security number). Alternatively, you can use scopes to ensure that you’re not even requesting sensitive information.

[![A screenshot of Common Model Scopes in Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d876e85a5c7f9e6763_gBMXoHaSlj3XIZLT1pj9_szaObOskUfoIVdLMSTZwXZKj-JNDsvmQJnSM76MaBri-g6HYNr0GcS63HIeOiyEznCtjfvNXrhhiO9S9-tBZT73QOBsJIuBJfVZ5-qPPhUM9CiP0PHJnMjIX_8V1TtfySI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d876e85a5c7f9e6763_gBMXoHaSlj3XIZLT1pj9_szaObOskUfoIVdLMSTZwXZKj-JNDsvmQJnSM76MaBri-g6HYNr0GcS63HIeOiyEznCtjfvNXrhhiO9S9-tBZT73QOBsJIuBJfVZ5-qPPhUM9CiP0PHJnMjIX_8V1TtfySI.webp)

_Merge uses_ [_Common Model Scopes_](https://help.merge.dev/en/articles/5950052-common-model-and-field-scopes) _to help users pick the client data they want to access._

_Related:_ [_A guide to polling API endpoints successfully_](https://www.merge.dev/blog/api-polling-best-practices)

### **Set up alerts based on the log data that’s collected**

While your developers can comb through the logs to uncover and diagnose issues, they may not be able to discover issues on time if they’re left to their own devices.

You can enable them to identify issues quickly and without performing any manual work by setting up automated alerts that notify them in an application like Slack or through email.

[![Sending issue notifications from API logs to Slack or email](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d854054db21876cee8_u1c9LJt27Vye0wmRnMBCTsiPzBXHTPcZ2df2_0oy3lzGHv9fgaIyMQaDgH0C0dNAwIfiV3f9gAe-dAU960tyPZJtiT1CgRoA8JDNFiZzLLLV3Y7vmN7jb2zcF6-41FZWc0vdGypYDf0rCQKoH_XfZAU.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d854054db21876cee8_u1c9LJt27Vye0wmRnMBCTsiPzBXHTPcZ2df2_0oy3lzGHv9fgaIyMQaDgH0C0dNAwIfiV3f9gAe-dAU960tyPZJtiT1CgRoA8JDNFiZzLLLV3Y7vmN7jb2zcF6-41FZWc0vdGypYDf0rCQKoH_XfZAU.webp)

While the alerts you set up depend on your unique circumstances, common options include unexpected errors, delayed response times, or a spike in requests or errors over a specific period of time.

### **Closely monitor your logging system’s users and their access levels**

Assuming your logs contain sensitive information, you’ll need to pay especially careful attention to who can access your logging system and how much access they have.

To help minimize any potential risks, you should adopt a logging tool that offers role-based access and includes robust security for accessing the application—such as two-factor authentication. You should also look to follow the principle of least privilege when assigning users access; in other words, users should only be able to access the data they absolutely need.

[![A screenshot of managing users in Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d89134eb9ebd950b0c_CsY5rm95p8qmG1ufNruTuD0A5oLKcNMBTkm0M9Fqdzt5zJI9Ov2DNUMsp-wnyPZ-k_gxuDYzuJShZXNQXOx_UZZVDttoa7qatEbxg7nsrIHy4LPhye_ZADbz_TvPbeAAkVYf8w-otJHs0Szy8R32d_o.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65aee4d89134eb9ebd950b0c_CsY5rm95p8qmG1ufNruTuD0A5oLKcNMBTkm0M9Fqdzt5zJI9Ov2DNUMsp-wnyPZ-k_gxuDYzuJShZXNQXOx_UZZVDttoa7qatEbxg7nsrIHy4LPhye_ZADbz_TvPbeAAkVYf8w-otJHs0Szy8R32d_o.webp)

_Merge can enforce two-factor authentication and lets you assign users different roles, depending on how much access you want them to have._

_Related:_ [_An example of API error handling_](https://www.merge.dev/blog/api-error-handling)

### **Implement a log retention policy**

As you collect more logs over time, it’s critical that there’s a mechanism in place for archiving old ones.

This can help you save on storage space, which translates to cost savings and performance improvements (as you can find information faster and more easily). And it allows you to comply with auditing and compliance requirements more easily, as they might require you to delete logs after a certain period of time.

### Build and maintain documentation on your logging system and processes

As new developers join your team, you'll need a scalable way for them to understand your logging system, data, and processes. This includes insights on how they can access your logging system, interpret the logs, troubleshoot common issues based on the logs, etc.

Logging documentation neatly addresses this need. Moreover, it allows you to be less reliant on the developers who oversee and act on your API logs today; if they leave, the documentation ensures that key information doesn't go with them.

### **Leverage fully-searchable, comprehensive logs with Merge**

Merge, which offers a single API that lets you add hundreds of integrations to your product, not only offers comprehensive API logging functionality but also provides automated issue detection to help your team (and your clients) easily diagnose and remediate any integration issues.

You can learn more about [Merge’s logging capabilities](https://www.merge.dev/features/integrations-management), [integrations](https://www.merge.dev/integrations), and much more by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-logging-best-practices).

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