---
url: "https://www.merge.dev/blog/automated-provisioning-and-deprovisioning"
title: "How to automate user provisioning and deprovisioning (3 examples)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#)

Table of contents

[Overview on automated provisioning and deprovisioning](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#overview-on-automated-provisioning-and-deprovisioning)

[Examples of automating user provisioning and deprovisioning](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#examples-of-automating-user-provisioning-and-deprovisioning)

[Benefits of automating user provisioning and deprovisioning](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#benefits-of-automating-user-provisioning-and-deprovisioning)

[Tools to automate user provisioning and deprovisioning](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning#tools-to-automate-user-provisioning-and-deprovisioning)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomated-provisioning-and-deprovisioning)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7600295f40b5071d63_Custom_API_integration_guide.webp)**‍Build or buy integrations? How to land on the best decision**](https://www.merge.dev/blog/build-vs-buy-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**8 integration challenges you’ll face in 2025**](https://www.merge.dev/blog/integration-challenges)

# How to automate user provisioning and deprovisioning (3 examples)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

As you look to increase product adoption and mitigate security risks for customers, you’ll likely need to automate both the process of adding users to your product and removing them.

We’ll help you tackle both areas by breaking down how real-world companies have gone about automating these processes in their products. We’ll also share specific tools you can use to implement these automations.

But to start, let’s align on the definitions of automated provisioning and automated deprovisioning.

## **Overview on automated provisioning and deprovisioning**

Automated provisioning refers to the process of adding users to your platform automatically. Certain fields associated with these users will also get populated, and they'll receive the right set of permissions by default.

This process is typically initiated when a customer adds an employee to an HRIS solution that's connected to your product or establishes an initial connection between your product and their HRIS solution.

[![Automated provisioning visualization](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f937ce1df548fd806_AD_4nXdiQkjkl8-uJ2My0xtSmWWuKCTZ9E1B1B3Gk-csNzyn-eSnJTJVgaaE5fsWi6EKBzf5Oj_Iw2bDctm5blK3Ow029MuHFkoUMxP0NZQeFZAHYE2F3qs5QHuNcx7A33q-JnJZvsTPdA6r7uJgQz5HoOBZm8U.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f937ce1df548fd806_AD_4nXdiQkjkl8-uJ2My0xtSmWWuKCTZ9E1B1B3Gk-csNzyn-eSnJTJVgaaE5fsWi6EKBzf5Oj_Iw2bDctm5blK3Ow029MuHFkoUMxP0NZQeFZAHYE2F3qs5QHuNcx7A33q-JnJZvsTPdA6r7uJgQz5HoOBZm8U.webp)

Automated deprovisioning is simply the process of removing users from your platform automatically. This normally happens when a customer marks an employee as terminated in or removes them from the integrated HRIS.

[![Automated deprovisioning visualization](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82fda553fc741464768_AD_4nXedd-1XWSgvXjS2PSTJkf640mRFaVYdd8PkDCYU2TqGaFCNC5qBfV5LWO4Mu4BsQ4dyK-kF0rQYGWmempsTSL3IbG70YYFAnijKhkkDhoorFirB4vfBfm-ar411xL0TS8ZnZQV971tdVsIwfxtrPbkl1laK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82fda553fc741464768_AD_4nXedd-1XWSgvXjS2PSTJkf640mRFaVYdd8PkDCYU2TqGaFCNC5qBfV5LWO4Mu4BsQ4dyK-kF0rQYGWmempsTSL3IbG70YYFAnijKhkkDhoorFirB4vfBfm-ar411xL0TS8ZnZQV971tdVsIwfxtrPbkl1laK.webp)

Note: Automated provisioning can sometimes refer to both adding users to and removing users from your platform. We’ll restrict its definition to the former in this article.

_Related:_ [_A guide to automated provisioning_](https://www.merge.dev/blog/automated-provisioning)

## **Examples of automating user provisioning and deprovisioning**

To bring this definition to life, let’s walk through how a few companies provision and deprovision users seamlessly.

### **Ramp**

Ramp, a financial operations platform, needed to automate user provisioning and deprovisioning to ensure new hires could access the appropriate corporate cards as early as possible and departing employees lose access to theirs from the moment they leave.

To help facilitate this, Ramp [integrates with customers’ HRIS solutions](https://www.merge.dev/blog/guide-to-hris-api-integrations), which allows admin users to implement and use the following flows:

- Any time an email address or phone number is added to the integrated HRIS and isn’t found in Ramp, the associated employee will appear as a potential candidate to be added to the platform

The admin could then add this user within Ramp in just a few clicks. And, based on the user’s information and the rules a customer sets for issuing corporate cards, the user would automatically get assigned the appropriate card(s) with the right spending limit(s).

[![How Ramp automates user provisioning](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95337af3f57dc2858292_AD_4nXdWAPNJwUcXu7_rtyf6A8HY0WhPuiI8PekutVXpmWcnO-zVXFIzhbCqV7lbyPUQZHmPrR7feFOyOVHpiyaN25qUb1HTiS8GyZjUqvYa58WwSqMpfBAVSBtoMJgY2tNAq6i-4G_OZVyi8xfnapRuQrjbvIja.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95337af3f57dc2858292_AD_4nXdWAPNJwUcXu7_rtyf6A8HY0WhPuiI8PekutVXpmWcnO-zVXFIzhbCqV7lbyPUQZHmPrR7feFOyOVHpiyaN25qUb1HTiS8GyZjUqvYa58WwSqMpfBAVSBtoMJgY2tNAq6i-4G_OZVyi8xfnapRuQrjbvIja.webp)

- Any time an employee’s associated email address or phone number gets removed from the integrated HRIS, the admin will get notified in Ramp and can remove them in a few clicks

[![How Ramp automates user deprovisioning](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f28e9a2b553813aa9_AD_4nXc6KSCpKGuCx0jxg-ZEiN8EJyU71kuh5NyAbK9sgCZeZT3UnC4ytwu919FvSv_wJCrQXu3_idC4cz73DHAj3piv9wKyu__XnQNzS2yaBuBXnA8CX5RDwMnWr9MIRp-wytTWby6PcWKoTegHzulcRCgnG4ti.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f28e9a2b553813aa9_AD_4nXc6KSCpKGuCx0jxg-ZEiN8EJyU71kuh5NyAbK9sgCZeZT3UnC4ytwu919FvSv_wJCrQXu3_idC4cz73DHAj3piv9wKyu__XnQNzS2yaBuBXnA8CX5RDwMnWr9MIRp-wytTWby6PcWKoTegHzulcRCgnG4ti.webp)

_Related:_ [_Examples of automating the user onboarding process_](https://www.merge.dev/blog/user-onboarding-automation)

### **AngelList**

AngelList Equity, which offers modern cap table management for companies, needed to automate provisioning and deprovisioning so that new hires can receive their equity awards on time and employees stop receiving theirs once they leave.

To enable this, AngelList Equity can integrate with customers’ HRIS solutions and build flows where once a customer is added to an HRIS solution and they receive equity compensation, their profile gets created in AngelList Equity.

Similarly, once an employee is removed from or marked as terminated in the integrated HRIS, they are also marked as terminated in AngelList Equity automatically.

[![How AngelList Equity deprovisions users](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe8303e4e73aa68984f11_AD_4nXe0qCJAZmfSmY6hB1KvaaWq3RygVyu3qgz-Q0CIx_FqM_slI8j-vrmaskKDxESjOQzJQ5-DPBQh4tlL4hI_k96T0GSYn3RNz4ZVUh8g5JXgFd_nGNydSMvz-aPUNEHHZ2n5-gz3dE-WAwY-lCCOQaT-wpCZ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe8303e4e73aa68984f11_AD_4nXe0qCJAZmfSmY6hB1KvaaWq3RygVyu3qgz-Q0CIx_FqM_slI8j-vrmaskKDxESjOQzJQ5-DPBQh4tlL4hI_k96T0GSYn3RNz4ZVUh8g5JXgFd_nGNydSMvz-aPUNEHHZ2n5-gz3dE-WAwY-lCCOQaT-wpCZ.webp)

_AngelList Equity automatically updates when an employee is marked as terminated in a customer’s HRIS_

### **BILL**

Similar to Ramp, BILL wanted to automate the provisioning and deprovisioning flows for their product—BILL Spend & Expense—to help new hires get a corporate card on day 1 with the appropriate spend limits. In addition, they wanted to help customers deactivate corporate cards for users that leave as soon as possible to prevent them from spending more money.

To help customers on both fronts, they built HRIS integrations and set up automated provisioning and deprovisioning flows:

- Once an employee is added to the integrated HRIS, an admin in BILL Spend & Expense can review them in their platform and decide whether to add them.

In the case that several employees join the company in a short period of time, the admin in BILL Spend & Expense can also create specific groups to find and add the right set of users more easily and quickly.

[![How BILL automates user provisioning](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95330fc437183c8133c5_AD_4nXdpCYz_ivX_A-vdhuwJGihYy6AtR7UBhAbTxqON3ENI_JumVEC2vG5TqsGj9JuMzud8VJzKupYwOBGMP388d2jhULHroW2gXW_WAtzpIpv4xkoNb7SHF8ihZzJRDZG3wJdJVah9RnwJ98UPaYLSxuneqSPr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95330fc437183c8133c5_AD_4nXdpCYz_ivX_A-vdhuwJGihYy6AtR7UBhAbTxqON3ENI_JumVEC2vG5TqsGj9JuMzud8VJzKupYwOBGMP388d2jhULHroW2gXW_WAtzpIpv4xkoNb7SHF8ihZzJRDZG3wJdJVah9RnwJ98UPaYLSxuneqSPr.webp)

- Once an employee is marked as terminated in or removed from the integrated HRIS, the admin for BILL Spend and Expense gets notified and, with the click of a button, can go on to remove them as a user

[![How BILL automates user deprovisioning](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f0a84017fd66c92f7_AD_4nXfEGhQiPb8wm6W-yW23NsomQxfWChdbpUQqk-6tvh1gfVYCyrF99UPAnb_uvNke_YGWNw8bJ8mxWPUI4fWDrBAn63KmwA2YIop_ZkmFK3jgqqGI6YetEaH_P_OppaJtAFw9nm3GanI-iM39ntnF4gtQEb4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82f0a84017fd66c92f7_AD_4nXfEGhQiPb8wm6W-yW23NsomQxfWChdbpUQqk-6tvh1gfVYCyrF99UPAnb_uvNke_YGWNw8bJ8mxWPUI4fWDrBAn63KmwA2YIop_ZkmFK3jgqqGI6YetEaH_P_OppaJtAFw9nm3GanI-iM39ntnF4gtQEb4.webp)

## **Benefits of automating user provisioning and deprovisioning**

Here are some of the top benefits to keep in mind:

- **Protecting sensitive information:** Automated provisioning ensures that users receive the right set of permissions, while streamlining deprovisioning ensures that former employees can’t access your data.

In both cases, you’re better positioned to comply with data protection measures and regulations (e.g., GDPR) and avoid having bad actors harm your customers.

- **Enhanced user experience:** Allowing customers’ admins to avoid adding and removing users manually allows them to save countless time. In addition, users can adopt your platform more easily and faster, which helps them realize a faster time to value

- **Improved customer retention and close rate:** By helping customers use and realize value from your platform faster—while preventing security risks—you’re more likely to deliver experiences that lead them to stay on longer. Moreover, if your product can deliver these automated experiences while your competitors' platforms can't, you might also be able to win more competitive deals

We’ve seen the latter benefit play out in the wild. For example, Paul Durocher, a Senior Sales Manager at Ramp, says that “One of the first questions a prospect asks is if we integrate with their HRIS application (to automate user provisioning). Being able to say we do has **consistently helped us close more deals.**”

_Related:_ [_The benefits of HR integrations_](https://www.merge.dev/blog/hr-integration)

## **Tools to automate user provisioning and deprovisioning**

As our examples highlighted, automating your provisioning and deprovisioning flows requires your customers to connect their HRIS solutions with your product.

To help you build these integrations, you can either [use an embedded iPaaS or unified API solution](https://www.merge.dev/blog/embedded-ipaas-vs-unified-api).

[An embedded iPaaS](https://www.merge.dev/blog/embedded-ipaas) lets you build HRIS integrations through pre-built connectors, which likely accelerates your team’s development cycle. However, these tools can be complex and difficult to learn, often taking your technical personnel (e.g., engineers) weeks, if not months, to get comfortable using. In addition, the platform forces you to build one HRIS integration at a time, making it even more difficult to scale your integration builds.

A unified API solution, on the other hand, lets you build to a unified API once to access dozens of HRIS integrations, allowing the platform to be more scalable and offer a faster time to value.

[![Merge's HRIS integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82fcb3554cdbb2f7f1a_AD_4nXfM0sLahdumPAxlVVxbtEigsSx4lW9uTHV7KTw38fwBpMcFvB_peV04CdAVysHnky1MwxawvBmyoZCZRlEQgTXIxaAPPHjv7zmW1Oa9F2weBHPqTP2PETsIAlRNaMEHUoafh5ZGRLpji60QV5UD1TfBsv_K.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abe82fcb3554cdbb2f7f1a_AD_4nXfM0sLahdumPAxlVVxbtEigsSx4lW9uTHV7KTw38fwBpMcFvB_peV04CdAVysHnky1MwxawvBmyoZCZRlEQgTXIxaAPPHjv7zmW1Oa9F2weBHPqTP2PETsIAlRNaMEHUoafh5ZGRLpji60QV5UD1TfBsv_K.webp)

_Once you’ve built to Merge’s Unified API, you can access 60+ HRIS integrations_

In addition, Merge, the leading unified API solution, lets you access additional categories of integrations (accounting, ticketing, ATS, file storage, CRM), sync custom fields, monitor integrations effectively and easily, and more.

Learn more about how Merge can help you automate your platform’s provisioning and deprovisioning flows by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomated-provisioning-and-deprovisioning).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=114902a3-acef-4061-8223-0a2fb56ad540&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=df183daa-2fb5-4667-b7ff-c256460459f5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-provisioning-and-deprovisioning&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=114902a3-acef-4061-8223-0a2fb56ad540&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=df183daa-2fb5-4667-b7ff-c256460459f5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-provisioning-and-deprovisioning&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=c9200547-18bd-4276-b54e-5a8d3299c35c&bo=2&sid=2aedd4d03e8d11f09325213508061b6d&vid=2aee16703e8d11f09c995f0468b4236c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20automate%20user%20provisioning%20and%20deprovisioning%20(3%20examples)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-provisioning-and-deprovisioning&r=&lt=526&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=645419)