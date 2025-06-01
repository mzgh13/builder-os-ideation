---
url: "https://www.merge.dev/blog/crm-api"
title: "A guide to CRM APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/crm-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/crm-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/crm-api#)

Table of contents

[What is a CRM API?](https://www.merge.dev/blog/crm-api#what-is-a-crm-api)

[Example of a CRM API](https://www.merge.dev/blog/crm-api#example-of-a-crm-api)

[How to leverage CRM APIs](https://www.merge.dev/blog/crm-api#how-to-leverage-crm-apis)

[Integrate with CRM systems at scale by leveraging Merge](https://www.merge.dev/blog/crm-api#integrate-with-crm-systems-at-scale-by-leveraging-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcrm-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**User onboarding automation: examples, benefits, and tools**](https://www.merge.dev/blog/user-onboarding-automation)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**8 integration challenges you’ll face in 2025**](https://www.merge.dev/blog/integration-challenges)

# A guide to CRM APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to implement integrations with CRM systems, you’ll likely want to build to their endpoints so that you can sync data quickly and reliably.

To help you do just that, we’ll share a popular CRM provider's API endpoints. We’ll also break down impactful internal and customer-facing CRM integrations to help serve as inspiration.

But first, let’s align on the definition of a CRM API.

## **What is a CRM API?**

It’s any endpoint that lets you create, read, update, or delete data in/from a CRM system. This can apply to data associated with either leads or customers.

_Related:_ [_What is a lead API?_](https://www.merge.dev/blog/lead-api)

## **Example of a CRM API**

To help bring our definition to life, let’s use Insightly, a popular CRM provider, as an example.

Insightly offers an extremely comprehensive set of endpoints for any given resource.

Take contacts, for example. You can perform the following API requests, among many others, on this resource alone:

- GET a filtered list of contacts through the endpoint `https://api.insightly.ly/v3.1/Contacts/Search` (you could include the filters you want applied by appending specific parameters)

- GET a specific contact by specifying its ID in Insightly: `https://api.insightly.ly/v3.1/Contacts/{id}`

- Create a new contact by making a POST request to `https://api.insightly.ly/v3.1/Contacts/{id}`

- Add a file attachment to a contact by making a POST request to `https://api.insightly.ly/v3.1/Contacts/{id}/FileAttachments`

- Delete a note associated with a contact by making a DELETE request to ` https://api.insightly.ly/v3.1/Contacts/{id}/Note/{childEntityId}`

Note: You can learn more about Insightly’s endpoints by reading [their API documentation](https://api.na1.insightly.com/v3.1/#!/Overview/Introduction).

## **How to leverage CRM APIs**

It’s one thing to understand the endpoints available for a given CRM API provider; it’s another to leverage their endpoints effectively.

To help you with the latter, we’ll break down [impactful CRM integrations](https://www.merge.dev/blog/crm-api-integration).

Our first two examples will be for internal integrations (i.e., integrating your CRM with the other applications your organization uses) while the next two will be customer-facing (i.e., integrating your product with customers’ CRM systems).

#### **Connect your CRM system with your file storage application to keep documents secure and easily accessible**

Your sales reps and customer success managers will likely collect a wide range of important documents from prospects and customers, whether that’s related to NDAs, purchase orders, renewal agreements, etc.

To ensure these documents don’t get lost and are easy to find for key stakeholders (e.g., your finance team), you can connect your CRM with your file storage application and build the following sync: Once a file is uploaded to your CRM (e.g., Salesforce), it’s automatically added to the associated folder in your file storage tool (e.g., Box).

[![Sync between Salesforce and Box](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6b0b84b6f8698902f6_AD_4nXfQ8stnhTaqSgra1KK6eorJmpvFwNq-P9hs4vmmsayr1L-gU_eqXr8wGOMjGIBYyN4m8aNJgfNSDPWPomVqXFlr1KPgA1ENyFJvaee8tezGOKASd6YUPf1RIkeSkiByPEvIOIf24OkYjWF9x7dxA5QzuLX6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6b0b84b6f8698902f6_AD_4nXfQ8stnhTaqSgra1KK6eorJmpvFwNq-P9hs4vmmsayr1L-gU_eqXr8wGOMjGIBYyN4m8aNJgfNSDPWPomVqXFlr1KPgA1ENyFJvaee8tezGOKASd6YUPf1RIkeSkiByPEvIOIf24OkYjWF9x7dxA5QzuLX6.webp)

‍

#### **Integrate your CRM with your marketing automation solution to help sales reps follow-up with warm leads**

To help your sales reps become aware of warm leads and follow-up with them quickly, you can connect your marketing automation solution (e.g., HubSpot) with your CRM and build a sync where once a lead reaches a certain score in the former, they’re automatically added to the latter.

The newly-created lead in the CRM can include key information, such as the specific activities that’ve led them to reach a high qualification score. That way, your reps can also reach out in a more thoughtful, effective way.

[![Sync between HubSpot and Salesforce](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bc6f89f4cec14391f_AD_4nXdHmNjnTTgZ8GUHyPkNHtmxiEdi4cD2vC_GRrtMlfqhoCW6uaqduN96l0yfFPo5vsPgWVVrtuwI67YiXMG7yJP0KMrlqZ_T87QNmz8POt0NWpsq4kLWV_Idw0fGYdLA_NEKJnO07tXihWBlCclJgJsDRMuD.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bc6f89f4cec14391f_AD_4nXdHmNjnTTgZ8GUHyPkNHtmxiEdi4cD2vC_GRrtMlfqhoCW6uaqduN96l0yfFPo5vsPgWVVrtuwI67YiXMG7yJP0KMrlqZ_T87QNmz8POt0NWpsq4kLWV_Idw0fGYdLA_NEKJnO07tXihWBlCclJgJsDRMuD.webp)

_Related:_ [_A guide to integrating with marketing automation software_](https://www.merge.dev/blog/marketing-automation-integration)

#### **Enable field sales teams by providing additional context on accounts**

Imagine you offer a platform that lets field sales teams record their appointments with prospects and customers.

To help sales reps and their managers analyze appointments, you can connect with their CRM systems and pull their prospects’ data. The data can be included alongside the recordings, helping sales reps and managers leverage this contextual information effectively and easily.

[![Adding information on accounts to your product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bf58837d56b423c42_AD_4nXd5QGzgfw5mPuzKXXcDL4cvBxp3_WfxYqc9KJOZJjYanHs9QBaRC8OsiYUiSul8zuwuDXIILuhj1kcYa_JcwOEJhewSZ6fS-2f8MTM2gT-C87f71nAuW_NyUpGJxdcmvNf3XdPQUOaWnkchdtGbvee-zn1b.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bf58837d56b423c42_AD_4nXd5QGzgfw5mPuzKXXcDL4cvBxp3_WfxYqc9KJOZJjYanHs9QBaRC8OsiYUiSul8zuwuDXIILuhj1kcYa_JcwOEJhewSZ6fS-2f8MTM2gT-C87f71nAuW_NyUpGJxdcmvNf3XdPQUOaWnkchdtGbvee-zn1b.webp)

#### **Provide lead recommendations based on customers’ CRM data**

Say you offer a sales automation tool that provides recommendations on the leads a company should pursue.

To ensure these recommended leads are highly relevant to each customer, you can connect to their CRM solution and feed specific data—opportunities that have recently closed, the contacts associated with closed-won opportunities, etc.—to your machine learning model.

From there, your platform can consistently recommend leads that a given customer will be most likely to convert.

You can also leverage the integration to help customers add leads from your platform to their CRM systems, seamlessly.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6c982d92c45206ccad_AD_4nXeTPo-xVdfHOtaZaeMlMeZ-ynqupoHWR5HKrZOwjqhDaebkwPXtRz_eyqrXCkYW65KfeUQi4nvrvnPwUL8o3eQ8YwMpmNGLhlqRz-e3MkM36z_EPdYIhAclxIc8A-cH5ESI8-6fn3JCEs1y2dqgjX9TUizM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6c982d92c45206ccad_AD_4nXeTPo-xVdfHOtaZaeMlMeZ-ynqupoHWR5HKrZOwjqhDaebkwPXtRz_eyqrXCkYW65KfeUQi4nvrvnPwUL8o3eQ8YwMpmNGLhlqRz-e3MkM36z_EPdYIhAclxIc8A-cH5ESI8-6fn3JCEs1y2dqgjX9TUizM.webp)

## **Integrate with CRM systems at scale by leveraging Merge**

Every customer-facing CRM integration comes with its own set of implementation requirements and maintenance challenges. As a result, your engineers can spend countless time building to and maintaining these integrations.

To offload this work from your dev team and help you integrate at scale, you can use Merge, the leading unified API platform.

Simply building once to Merge’s CRM Unified API allows you to add 20+ CRM integrations to your product.

[![Some of the CRM integrations Merge supports](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bcaf2d86c9fc7806f_AD_4nXd4BXwSjLChUUKWf3xsW-oYyp-dRAen8xhDjAYW0-AWTSR_9dlXPVNEaD8eJlzqmFrPc6mBIQc2tq10dLoNmJQQ0XRc8byVuWHvqSTxAAPWEg2ihHcPYXXKzNIrf_mHnSaV43teyC8ZHWdlQRGwPi5GVy8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b28b6bcaf2d86c9fc7806f_AD_4nXd4BXwSjLChUUKWf3xsW-oYyp-dRAen8xhDjAYW0-AWTSR_9dlXPVNEaD8eJlzqmFrPc6mBIQc2tq10dLoNmJQQ0XRc8byVuWHvqSTxAAPWEg2ihHcPYXXKzNIrf_mHnSaV43teyC8ZHWdlQRGwPi5GVy8.webp)

_A snapshot of some of the_ [_CRM integrations Merge supports_](https://www.merge.dev/categories/crm-api)

In addition, once you’ve added these integrations, your customer-facing teams can access Merge’s Integration Observability tooling—which includes fully-searchable logs, automated issue detection capabilities, and a holistic dashboard—enabling them to manage each integration with ease.

[![A screenshot of Merge's automated issue detection functionality](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)

_You can automatically identify specific integration issues and uncover the steps to remediate them in Merge’s Dashboard_

Learn more about how Merge can help you add and maintain CRM integrations with your product by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcrm-api).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2cdb17e1-94f0-483b-ac56-fb2b92623684&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2af5ca3c-6dd6-45fe-a9b9-62063179e021&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcrm-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2cdb17e1-94f0-483b-ac56-fb2b92623684&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2af5ca3c-6dd6-45fe-a9b9-62063179e021&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcrm-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=3e213b21-b9fe-4947-aaeb-277816ff1e88&bo=2&sid=fc95a6903e8c11f0819a634eebb5fd56&vid=fc9651303e8c11f0b5ce8dac93236ca2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20CRM%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcrm-api&r=&lt=617&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=230446)