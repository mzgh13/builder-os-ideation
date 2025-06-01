---
url: "https://www.merge.dev/blog/api-response-codes"
title: "API response codes: examples and error-handling strategies"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-response-codes#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-response-codes#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-response-codes#)

Table of contents

[What is an API response code?](https://www.merge.dev/blog/api-response-codes#what-is-an-api-response-code)

[Common API response codes](https://www.merge.dev/blog/api-response-codes#common-api-response-codes)

[Final thoughts](https://www.merge.dev/blog/api-response-codes#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-response-codes)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API error handling: definition, example, best practices**](https://www.merge.dev/blog/api-error-handling)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**A guide to API logs**](https://www.merge.dev/blog/api-logs)

# API response codes: examples and error-handling strategies

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you make API calls to different API providers, you’ll likely receive a wide range of response codes.

These can vary based on how providers implement HTTP status codes and the nature of the issues associated with the requests. So, theoretically, you can end up receiving countless response codes.

However, you’ll likely only run into a certain set of codes consistently.

We’ll help you understand and respond to each of the most common ones so that you can manage your API calls effectively over time.

But first, let’s align on the definition of an API response code.

## **What is an API response code?**

It’s an HTTP status code that a server returns to a client for a given API request. The code reveals whether the request was successful or not, and, if not, provides additional context on the issue—enabling the client to debug the issue if it’s on their end.

[![The categories of API response codes](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671124657e500c1aa0737fe2_6711242c69ef42275511fbb9_API%2520response%2520code%2520categories%2520(4).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671124657e500c1aa0737fe2_6711242c69ef42275511fbb9_API%2520response%2520code%2520categories%2520(4).webp)

#### Avoid managing integrations at scale

Merge lets you add hundreds of integrations to your product by simply building to its Unified API.

[Schedule demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-response-codes)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Common API response codes**

Here are the top response codes to be aware of.

### **200 OK**

You’ll hopefully see this response code in the majority of your API calls. It simply means that the request was successful.

[![An example of a 200 OK status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e1114ac42fbd5a2c40cc_AD_4nXfZ4Gp4vhVPcRyygGlHr2Fwz2YAuzYhTBGfh_T0jedkcNqe2zNOh59b3mmtDqPrNnMiIU96Lsx0MMAYsSq0_1FT1mbRH-jMMnoOfDY2g1XKKZ4RHofnWrCt77dbrmOpopGosw18KH1Aol7fA52iZbopDdvg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e1114ac42fbd5a2c40cc_AD_4nXfZ4Gp4vhVPcRyygGlHr2Fwz2YAuzYhTBGfh_T0jedkcNqe2zNOh59b3mmtDqPrNnMiIU96Lsx0MMAYsSq0_1FT1mbRH-jMMnoOfDY2g1XKKZ4RHofnWrCt77dbrmOpopGosw18KH1Aol7fA52iZbopDdvg.webp)

If you used a GET request, you should see the requested resource below the code, allowing you to easily pull the data. While if you used a method like PATCH, you might get a message that the data was updated on the server successfully and see the specific data that was updated.

### **201 Created**

This means that request was successful and a resource was created on the server.

Here’s a simplified look at how the HTTP header can look for a successful response:

[![HTTP response header for 201 status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3dce1355a41827664b3c_AD_4nXedGGjQcurXhGN9yXLoK0qAUGRQyhsyO6o5tD-gThrnptfvGdzov6q40q-ju2WQvWHFwPTiKx1ZGkbL5KFXY4lk41dCJay7Y26-n7cBNGMFjTopQvxTXlBfCS0_b0nnEoTWMOh_Gq-AD8NbmAnZNvXjBWhi.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3dce1355a41827664b3c_AD_4nXedGGjQcurXhGN9yXLoK0qAUGRQyhsyO6o5tD-gThrnptfvGdzov6q40q-ju2WQvWHFwPTiKx1ZGkbL5KFXY4lk41dCJay7Y26-n7cBNGMFjTopQvxTXlBfCS0_b0nnEoTWMOh_Gq-AD8NbmAnZNvXjBWhi.webp)

The body can include details on the resource that was created.

[![HTTP response body for 201 status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3dce91ce8e49eb62184f_AD_4nXdmbTIK40AMG2ohW_5xxEbYaK6AQfPHRgMvtlcF_fFsIZtg2AfJisQ3qCPKqOIY6cLy3vE-eRT0C14fWOV52X5BcUMOrIjOwBxItLGEkOVE2BiLcaYGyv3n-uZ-3T_Nn6xec0ffyqhuoU9Mg3nM6HoHcms.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3dce91ce8e49eb62184f_AD_4nXdmbTIK40AMG2ohW_5xxEbYaK6AQfPHRgMvtlcF_fFsIZtg2AfJisQ3qCPKqOIY6cLy3vE-eRT0C14fWOV52X5BcUMOrIjOwBxItLGEkOVE2BiLcaYGyv3n-uZ-3T_Nn6xec0ffyqhuoU9Mg3nM6HoHcms.webp)

This is associated with either POST requests, where a new resource is created on the server, or PUT requests, where a resource is either created or replaced on the server.

### **301 Moved Permanently**

API providers may end up changing their resources’ locations over time, leading you to receive this error.

Fortunately, the API provider typically shares the resource's new URL within the response’s location header, which allows you to automatically redirect current and future requests for that resource.

[![Example of a 301 status code response](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3e011f1f4c77256f3771_AD_4nXd7W0jKrYA7SV-J-03sld4D3_OwiHqCIy1NfKeW4sczWld6vlmXs-qfQJdN1OoUmbr5zhfJRWNNf8cVemGnlTUQwroXrKIwv06BwE9ILCm8tTMkcsFivv_zvu06MGGNtumDDLM26BNBlibptIro_gbV7sOj.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3e011f1f4c77256f3771_AD_4nXd7W0jKrYA7SV-J-03sld4D3_OwiHqCIy1NfKeW4sczWld6vlmXs-qfQJdN1OoUmbr5zhfJRWNNf8cVemGnlTUQwroXrKIwv06BwE9ILCm8tTMkcsFivv_zvu06MGGNtumDDLM26BNBlibptIro_gbV7sOj.webp)

You likely won’t need to debug this error, as most HTTP libraries handle redirects automatically.

### **302 Found**

This status code means that the requested resource is located in a different URL temporarily.

Similar to the 301 status code, the response includes the temporary URL within the location header.

[![Example of a 302 status code response](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3e02668398933a4dac5f_AD_4nXdgoctiVFW6B1gXQYPFB51bBxxsjfyu25CCxgpoRdpNteefNEX2Nm3k_nEDT1O5OaODSDdrgKKZS3YonmeIeluVkrsIDk4xWjgGfL_bsQ92UDFyuZjNWHAbvtsNCIqudUxV8Y_oVyTP97FfTGo6aGFcpsk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3e02668398933a4dac5f_AD_4nXdgoctiVFW6B1gXQYPFB51bBxxsjfyu25CCxgpoRdpNteefNEX2Nm3k_nEDT1O5OaODSDdrgKKZS3YonmeIeluVkrsIDk4xWjgGfL_bsQ92UDFyuZjNWHAbvtsNCIqudUxV8Y_oVyTP97FfTGo6aGFcpsk.webp)

Also like the 301 status code, there’s likely little you need to do. Your request will automatically redirect to the temporary URL, and all future requests will—and should—continue to use the original URL, as the redirect is temporary.

### **404 Not Found**

This means that the requested resource either doesn’t exist or isn’t available.

[![An example of a 404 Not Found status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111edb2d2a01c6664a7_AD_4nXeoeGzNAAtNFQ3gfvYXJ1jaSm50cYgTBhUefu9r5jQgSTdbYl4chOK2sHe80JfAVe-ZNbQt0p9NiAlM2CnCbNj1nlSsP5rqDrujzka8GWCZpTHlGx2v2NNxWszS1DgU3lFrW2wr6DKJaHMNEJKEG4jP1ZPJ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111edb2d2a01c6664a7_AD_4nXeoeGzNAAtNFQ3gfvYXJ1jaSm50cYgTBhUefu9r5jQgSTdbYl4chOK2sHe80JfAVe-ZNbQt0p9NiAlM2CnCbNj1nlSsP5rqDrujzka8GWCZpTHlGx2v2NNxWszS1DgU3lFrW2wr6DKJaHMNEJKEG4jP1ZPJ.webp)

You can debug this in a few ways:

- **Double check the request URL and your parameters.** Any minor mistake (like one misplaced letter or character) can be the root cause of the issue

- **See if there are similar resources you can request instead.** It may be worth identifying and calling another endpoint that helps you access similar data

- **Determine if the endpoint has been moved or deprecated.** You can typically confirm this by reviewing the API provider’s documentation and/or their community forum. If it's been deprecated, it may be worth following the previously mentioned tip **‍**

_Related:_ [_Top integration issues to look out for_](https://www.merge.dev/blog/integration-issues)

### **429 Too Many Requests**

This indicates that you’ve reached your rate limit for calling a certain endpoint in the current rate limit window.

[![429 Too Many Requests status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3f9b9bc7c28c11b9368e_6669f66e6d10c457f11645ad_Screenshot%25202024-06-12%2520at%25203.25.42%25E2%2580%25AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3f9b9bc7c28c11b9368e_6669f66e6d10c457f11645ad_Screenshot%25202024-06-12%2520at%25203.25.42%25E2%2580%25AFPM.webp)

To troubleshoot this response code, you can:

- **Look for opportunities to optimize requests.** You can, for example, batch requests. You can also cache responses so that identical requests are served from the cache instead of the server

- **Upgrade your plan with the API provider.** In some cases, your rate limits for certain resources are determined by the plan you’re on with the 3rd-party service. If that’s the case and it’s critical that you can make more requests than the current plan allows, it may be worth the investment

- **Use a backoff strategy that retries the request in the following window.** This may not be the solution you’re after, but it may prove inevitable if the options above aren’t helpful

### **401 Unauthorized**

This means that the request either doesn’t have authentication credentials or the credentials don’t have sufficient privileges to perform the desired action on the resource.

[![401 API status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111e4b224c6c737c31f_AD_4nXff23lGk30JAdcfDQRFEPsMxt7tmabqyrlnMcbx3ynww33mcBEBog5DyAgueyZmf-4ogTfo9RkCJF1qRQzpFHj3nPNKlU2Bwm6V8ZKNMgtSz9SdaqB06gePNF-i77OOR3gJp3NBd67hxJJ2QlgdEDZdNQ3H.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111e4b224c6c737c31f_AD_4nXff23lGk30JAdcfDQRFEPsMxt7tmabqyrlnMcbx3ynww33mcBEBog5DyAgueyZmf-4ogTfo9RkCJF1qRQzpFHj3nPNKlU2Bwm6V8ZKNMgtSz9SdaqB06gePNF-i77OOR3gJp3NBd67hxJJ2QlgdEDZdNQ3H.webp)

To manage this type of error, you can try any of the following:

- **Double check your authentication credentials.** You may have inadvertently used the wrong ones, put them in incorrectly, or let them expire

- **Verify the status of the 3rd-party authentication provider (if you use one).** A service like AuthO may be experiencing an issue themselves (e.g., a status outage). In this case, you’ll just need to wait until the provider’s issue gets resolved

- **Review the API provider’s authentication requirements.** They may have updated them without your knowledge (although backwards incompatible changes are rare) or you might have misread them. For instance, you may have thought that the provider accepts basic authentication but they actually require access tokens instead

_Related:_ [_How to decide between building and buying integrations_](https://www.merge.dev/blog/build-vs-buy-integrations)

### **500 Internal Server Error**

The request couldn’t be completed successfully because of an issue on the server’s end.

[![500 API status code](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111a9cf29029cffbc10_AD_4nXfjxtoFGe2Qj3qdW2N7_ufUHws1MKHeXlDPxAdsfGRxm4vjvFahEPhF9s108iGm0PWClsu5OQVOrPyULpB1_7obdHRodnDMYMTPSZuoqGuPCUbWstEJ3AtHTHdPbjZNxDqB-UZr35oxphUPEYK0pLd8O6st.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6669e111a9cf29029cffbc10_AD_4nXfjxtoFGe2Qj3qdW2N7_ufUHws1MKHeXlDPxAdsfGRxm4vjvFahEPhF9s108iGm0PWClsu5OQVOrPyULpB1_7obdHRodnDMYMTPSZuoqGuPCUbWstEJ3AtHTHdPbjZNxDqB-UZr35oxphUPEYK0pLd8O6st.webp)

To address this status code effectively, you can:

- **Get more context on the nature of the issue.** Given how vague the 500 status code is, it can be hard to even know where to start in troubleshooting it. You can try to get more insight on the server issue by enabling debugging mode either in the application or server configuration

- **Assess changes to the code base.** Check if there were any changes in the API request’s code before the last error occurred. You might find this in your organization’s change management system and/or any other places that document changes to your code base

- **Contact the API provider’s support team.** Through the provider’s API documentation, you may be able to chat with their support team or submit a ticket that explains the issue

### **503 Service Unavailable**

This generally means that a server is unavailable—whether that’s because it’s overloaded with traffic, undergoing maintenance, etc.

The API provider might include details on when you should retry the request in the header field “Retry-After”, where the timeframe for retrying can be presented in seconds or through a specific timestamp.

[![503 status code response error](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3ef57154bda3ab378440_AD_4nXcCnPGgjaYGkFiMoKfL0mPDEm1HKX_e7yCMBYA4XKVhxiSWaMghC4u98MfRM861OfNG26VDL4Q43B2fWydw2Cynv-GW1e6Qp6BhjFBvjo1A7nfS8pIRhIx3G1CU0JeOZULJNP_3s_1ktrYrlD_29sjam7w-.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66da3ef57154bda3ab378440_AD_4nXcCnPGgjaYGkFiMoKfL0mPDEm1HKX_e7yCMBYA4XKVhxiSWaMghC4u98MfRM861OfNG26VDL4Q43B2fWydw2Cynv-GW1e6Qp6BhjFBvjo1A7nfS8pIRhIx3G1CU0JeOZULJNP_3s_1ktrYrlD_29sjam7w-.webp)

To address this status code effectively, you can:

- Incorporate retry logic within your request body
- Leverage exponential backoff when there isn’t a retry-after header field to limit unnecessary requests
- Limit the number of retries when there isn’t a retry-after header field, as the server may experience significant, long-term issues

## **Final thoughts**

Analyzing and responding to individual status code errors can be overwhelming if left to your engineers. This is especially true for customer-facing integrations, as you might be supporting dozens of integrations that are used by countless end-users (your customer’s customers).

To offload this work to your customer-facing employees and to help these employees identify, diagnose, and resolve integration issues effectively and easily, your team can use [Merge’s Integration Observability tooling](https://www.merge.dev/features/integration-observability).

Learn more about this tooling and how our unified API lets you add hundreds of integrations to your product through a single build by [scheduling a demo with one of our integration experts.](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-response-codes)

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