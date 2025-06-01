---
url: "https://www.merge.dev/blog/automated-vs-assisted-integrations"
title: "Why Merge is API-first and doesn’t have assisted integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/automated-vs-assisted-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/automated-vs-assisted-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/automated-vs-assisted-integrations#)

Table of contents

[How automated integrations can outperform assisted integrations](https://www.merge.dev/blog/automated-vs-assisted-integrations#how-automated-integrations-can-outperform-assisted-integrations)

[Evaluating the security impact of assisted integrations against your organization’s policies](https://www.merge.dev/blog/automated-vs-assisted-integrations#evaluating-the-security-impact-of-assisted-integrations-against-your-organizations-policies)

[Final thoughts](https://www.merge.dev/blog/automated-vs-assisted-integrations#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomated-vs-assisted-integrations)

##### Just for you

No items found.

# Why Merge is API-first and doesn’t have assisted integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856caef10efcff9bfdd738_Assisted_vs_automated_integrations.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

If you’re evaluating Finch, a unified API solution, you’ll inevitably run into the term “assisted integrations.”

It’s referenced on their integration page and developer documentation, and it’s a reason why they can offer 200+ HR and payroll integrations.

Just by understanding how their assisted integrations work, however, you’ll realize that they can be problematic:

[![How Finch's assisted integrations work](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65fd9920d8b87069959414b1_LaNPLgLS2dN4DpUqZPw2rGE8OeCELUMFwX2xJmxGn6UMWLJ9d_xxcULkE5bGm-T5qC-U9D8BgPZ3VDqQZVZU2xZ1fETO8B1pKhMS4hiFRgoNBvi7q1rrrMdAzyT0vNU-GNootshDS9zjUpAhgtajDzk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65fd9920d8b87069959414b1_LaNPLgLS2dN4DpUqZPw2rGE8OeCELUMFwX2xJmxGn6UMWLJ9d_xxcULkE5bGm-T5qC-U9D8BgPZ3VDqQZVZU2xZ1fETO8B1pKhMS4hiFRgoNBvi7q1rrrMdAzyT0vNU-GNootshDS9zjUpAhgtajDzk.webp)

We firmly decided not to offer assisted integrations because they can lead to poor performance, disappointing customer experiences, and worst of all, breed significant security risks. Instead, we solely provide automated integrations, or integrations that sync data by communicating with 3rd-party endpoints.

You can read on to learn why automated integrations outperform assisted integrations in both security and performance.

## **How automated integrations can outperform assisted integrations**

Assisted integrations are extremely manual. _You’re depending on an individual to take data from clients’ systems, normalize them properly, and upload them to Finch._

Since Finch’s team is dealing with countless assisted integrations across their customer base, they can experience delays in carrying out this work. A given assisted integration may, for example, take at least a week to sync data successfully.

In addition, the human intervention work that’s involved can naturally lead to a high rate of syncing errors. Individuals may forget to add specific data to Finch or go on to add the wrong data, leading syncs to either go uncompleted or provide clients with the wrong information.

Automated integrations, on the other hand, don’t require manual intervention to sync data. A unified API solution (like Merge) is directly communicating with the clients’ API endpoints, allowing the solution to access the relevant data in near real-time.

As a result, automated integrations, coupled with webhooks, can support time-sensitive processes effectively, while assisted integrations, in our opinion, can’t.

[![A visual of some of the processes that automated integrations support](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65fd99203b6662d1df6d6cd5_j1gkI8-CG492tiAxmWNHwhE8n280-wx4gFAPykKFm4AFPX0wiwaU_OUlgt23w-U7kHVswmBaA9BmoyLfHlkJ5MM-0xg6NCvckgtOiDuMnaouey5_FI5U1EVLq_mZ0OVYhGtpqYv6ZsWzD4KxxoFKv5M.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65fd99203b6662d1df6d6cd5_j1gkI8-CG492tiAxmWNHwhE8n280-wx4gFAPykKFm4AFPX0wiwaU_OUlgt23w-U7kHVswmBaA9BmoyLfHlkJ5MM-0xg6NCvckgtOiDuMnaouey5_FI5U1EVLq_mZ0OVYhGtpqYv6ZsWzD4KxxoFKv5M.webp)

## **Evaluating the security impact of assisted integrations against your organization’s policies**

Assisted integrations require an individual to _sign in with the credentials that your customer has entrusted you with to pull the data every time a sync happens._

Therefore, when evaluating whether assisted integrations pose a security risk to your company, ask who is actually doing the pulling. In other words, is this work contracted out? And if so, who’s contracted to perform it? Ensure that your organization’s policies around protecting data are followed throughout the transfer, including any requirements for the data to remain encrypted in transit and at rest.

Unless you are evaluating assisted integrations against your organization’s policies for processing data, you could be compromising your ability to comply with data protection and privacy regulations like GDPR, HIPAA, and SOC 2 Type 2. This naturally gives your rivals a significant edge in winning new business, and it makes it all but impossible to build and maintain trust with clients.

## **Final thoughts**

You likely have at least somewhat unique requirements when it comes to the customer-facing integrations you need to support.

However, we believe that there’s little reason to invest in assisted integrations. They can put your clients at risk, hamper your integrations’ performance, and, ultimately, cause meaningful harm to your business.

You can learn more about Merge’s automated integrations, as well as our other features and capabilities for building, maintaining, and managing your integrations, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomated-vs-assisted-integrations).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6f8bed14-239a-4341-b7f8-bb030b845b8a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c011c650-438f-476c-90d1-5cb0d6ff9d6d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-vs-assisted-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6f8bed14-239a-4341-b7f8-bb030b845b8a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c011c650-438f-476c-90d1-5cb0d6ff9d6d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-vs-assisted-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f5a113eb-faa3-47ab-a2ad-caa627f36976&bo=2&sid=0bca38603e8e11f0ac2db96e760fc12f&vid=0bca8fe03e8e11f0a6ac110b201649e8&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Why%20Merge%20is%20API-first%20and%20doesn%E2%80%99t%20have%20assisted%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomated-vs-assisted-integrations&r=&lt=1090&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=495236)