---
url: "https://www.merge.dev/blog/api-error-handling"
title: "API error handling: definition, example, best practices"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-error-handling#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-error-handling#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-error-handling#)

Table of contents

[What is API error handling?](https://www.merge.dev/blog/api-error-handling#what-is-api-error-handling)

[API error handling example](https://www.merge.dev/blog/api-error-handling#api-error-handling-example)

[API error handling best practices](https://www.merge.dev/blog/api-error-handling#api-error-handling-best-practices)

[Manage any API errors with ease through Merge](https://www.merge.dev/blog/api-error-handling#manage-any-api-errors-with-ease-through-merge)

[API error handling FAQ](https://www.merge.dev/blog/api-error-handling#api-error-handling-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-error-handling)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**API sandbox: definition, examples, best practices, benefits**](https://www.merge.dev/blog/api-sandbox)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856caf87ff8c191004f86e_Multiple_API_integration.webp)**API integration support: what to expect for native integrations**](https://www.merge.dev/blog/api-integration-support)

# API error handling: definition, example, best practices

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

API integrations can fail for a number of reasons.

Maybe you didn’t add the endpoint’s URL correctly; or you used an invalid or expired token; or you sent data in a format the API doesn’t support.

Whatever the cause, your team needs to be able to diagnose the issue swiftly, identify the appropriate steps to remediate the issue on time, and execute those steps quickly and successfully.

In short, you need to build robust error handling processes across your API integrations.

We’ll help you build these processes by breaking down an example and by highlighting several best practices worth implementing. But to get us started, let’s align on the definition of API error handling.

## **What is API error handling?**

It’s the process of identifying and responding to a specific error from an API response with the goal of resolving the issue as quickly as possible.

[![A visual depiction of API error handling](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b27d57a265aa97dd1fecc9_API%20error%20handling%20(2).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b27d57a265aa97dd1fecc9_API%20error%20handling%20(2).webp)

API responses typically provide specific error codes and messages (e.g. “404 Not Found”), which can help your team diagnose the issue. Your team is, however, on the hook for pinpointing the solution and implementing it.

_Related:_ [_What is an API response code? Here's what you need to know_](https://www.merge.dev/blog/api-response-codes)

## **API error handling example**

To help clarify our definition, let’s break down a specific example: Say you make a GET request to an API endpoint to retrieve details on a specific employee in an HRIS solution. However, the employee doesn’t exist in the HRIS solution—leading you to receive a “Not Found” error message.

The log from this request is added to your monitoring tool. The tool then parses the log, extracts key information (e.g. the error code), and—if configured—alerts the relevant stakeholders of the error. From there, your developers can review the request to make sure it was formatted properly, analyze the error in conjunction with others to determine if it’s part of a trend, and more.

## **API error handling best practices**

Here are just a few ways to implement error handling effectively.

### **Configure your monitoring system to accommodate payload details**

API responses often include details that extend beyond the status code and error message. For example, there can be a longer message that describes the error; a timestamp that shows when the error occurred; a suggestion for addressing the error; and even a link to documentation that can help your engineers troubleshoot it.

You should configure your monitoring system so that it can capture this additional information whenever it’s available. And while it’s not always helpful, it can potentially help your engineers understand integration errors more easily, which better positions them to troubleshoot and resolve issues faster.

_Related:_ [_API logging tips_](https://www.merge.dev/blog/api-logging-best-practices)

### **Use exponential backoffs for server-side issues**

In many cases, the error is on the API provider’s end. When it is, you’ll receive a 5xx error that can specify why, exactly, the server-side error occurred.

Whenever you find yourself in this situation, you can use exponential backoffs—which allow you to retry a specific API call at increasing intervals when they lead to failed requests. This gives the server time to recover, minimizes your number of failed requests, and likely saves you money, as you don’t have to make as many API calls.

Note: You should also use exponential backoffs when you receive a 429 error; this type of error indicates that you’ve sent too many requests in a certain period of time and may be violating the API provider’s rate limiting policy.

### **Integrate your monitoring system with Slack and/or your email service provider**

Your engineers may not see issues crop up in your monitoring tool quickly, leading the issues to persist. Moreover, there can be so many logs to sift through that your engineers may have a hard time finding the issues that they’re equipped to solve.

To address both of these issues, you can integrate your monitoring system with your business communications platform (e.g. Slack) and/or email service provider. You can then build an automation where once a log with a certain status code comes in, a notification goes out automatically to the appropriate individual or team through Slack or email.

[![A visualization of a workflow that notifies users when there are integration issues](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc0e_PyU_jPFYmCbajJTG8WHXwZ0lFhbycikT31_bIuRi-cwjXLpZJaUysnLRjuk_1Rnd0bv2RYrTvS3MFUJWecXwnOBxcPC-f8CH0O_6ZdrSnnf8I5FeXD-uYpMq0gXuWh9ID7b66IBjik_fb9x6m4TH_Pw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65b02ecd3818ddecdc3fbc0e_PyU_jPFYmCbajJTG8WHXwZ0lFhbycikT31_bIuRi-cwjXLpZJaUysnLRjuk_1Rnd0bv2RYrTvS3MFUJWecXwnOBxcPC-f8CH0O_6ZdrSnnf8I5FeXD-uYpMq0gXuWh9ID7b66IBjik_fb9x6m4TH_Pw.webp)

### **Document each error handling process**

As the engineers who manage your integrations leave, you don’t want them to take their knowledge of your error handling workflows with them. This can leave your remaining engineers poorly-positioned to manage issues when they crop up, leading the issues to go unresolved for a longer duration.

In addition, as new engineers join your team, the process of introducing them to your error handling workflows can be time-intensive for your longer-tenured engineers.

You can tackle both of these issues by tasking your engineers with documenting each error handling process. The documentation can cover specific status codes in more depth, offer concrete steps for investigating and tackling each type of error, provide previous examples, and more.

_Related:_ [_API polling best practices_](https://www.merge.dev/blog/api-polling-best-practices)

### Review each error handling process frequently

Your API error handling processes may not work as well as expected. Moreover, they may break or become less effective for a variety of reasons over time (e.g. the 3rd-party APIs you've built to change or undergo version updates that lead them to use new error codes or different error response formats).

To help your team spot any error handling workflows that don't perform up to par, you can review each error handling process' performance with the relevant stakeholders consistently, such as every month.

## **Manage any API errors with ease through Merge**

Merge, which is a single API that lets you add hundreds of integrations to your product, can automatically detect issues and provide steps for remediating them. Your customer-facing team can then pass along these steps to the affected client quickly, enabling the client to resolve the issue with little delay.

[![An example of Merge's Automated Issue Detection feature in action](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2959df7dd916026443516_iCmrcQ2I5eRTg_7pjcIZFRyRp7sy1v766qinGPHB-LV0EvqTFLUcX3SomLX_3lOD15csSNxZdtna5hJB8QwYMd9d3qI_bg1HViBmyhBOaSMFu-wMmA40KgKbjlRhvFWYOkoVtcjzBTfgkfcMhKD7UFk.webp)

In addition, Merge offers fully-searchable logs to help you find and diagnose 5xx issues. And we provide integration maintenance—through our partner engineering team—to solve for countless edge cases across your integrations.

You can learn more about Merge’s integration management features, maintenance support, and  Unified API by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-error-handling).

## **API error handling FAQ**

In case you have more questions on API error handling, we’ve addressed a few more below:

### **What are some popular REST API error codes?**

The error codes are bucketed into 5 categories: 1xx, 2xx, 3xx, 4xx, and 5xx. Each category has a high level meaning, while the error code within a category lets you determine what, exactly, happened.

Here are some common error codes per category:

- 1xx (informational; server lets the client know that the request is still processing): 100 Continue, 101 Switching Protocols, and 103 Early Hints

- 2xx (Success; the client’s request was successfully received and processed): 200 OK, 201 Created, and 204 No Content

- 3xx (Redirection; the request was received, but in order to process it successfully, the client needs to take additional actions): 301 Moved Permanently, 307 Temporary Redirect, 300 Multiple Choices

- 4xx (Client Errors; the client’s request was flawed in some way): 404 Not Found, 401 Unauthorized, 403 Forbidden

- 5xx (Server Errors; the server experienced an unexpected issue that prevented it from processing the request successfully): 500 Internal Server Error, 502 Bad Gateway, and 503 Service Unavailable

### **How should you test your API error handling processes?**

You should write tests that cover every potential issue. That way, you can evaluate each process and confirm that it works as expected. If, however, you have limited resources and can only test for a certain length of time, it’s worth prioritizing common HTTP status code errors, like 404 Not Found, 401 Unauthorized, and 503 Service Unavailable.

In addition, you should use an automated API testing tool, like Postman or SoapUI, to save your engineers’ time and perform more tests quickly.

### **What is an API error handling strategy?**

It’s the set of steps an organization takes to monitor and address response errors. This involves deciding on the employees who need to participate and how they’re involved. And it includes alignment on the tools that are used and the capacity in which they’re leveraged.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c4e8d782-f97a-4d28-8cf6-86db7ac55334&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=22e7b2ea-c21e-4e91-a780-9548a5eafc8a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-error-handling&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c4e8d782-f97a-4d28-8cf6-86db7ac55334&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=22e7b2ea-c21e-4e91-a780-9548a5eafc8a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-error-handling&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=5e31dd44-5eef-4782-8646-4889e4d983a9&bo=2&sid=18d96e503e8e11f0bd604d9b5d00330e&vid=18d98cc03e8e11f0868f452ea82accde&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=API%20error%20handling%3A%20definition,%20example,%20best%20practices&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-error-handling&r=&lt=446&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=789066)