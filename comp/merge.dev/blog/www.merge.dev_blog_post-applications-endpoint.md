---
url: "https://www.merge.dev/blog/post-applications-endpoint"
title: "Merge now lets you add candidates AND applications to customers’ ATS applications with a single endpoint!"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/post-applications-endpoint#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/post-applications-endpoint#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/post-applications-endpoint#)

Table of contents

[How we’ve improved the POST /applications endpoint](https://www.merge.dev/blog/post-applications-endpoint#how-weve-improved-the-post-applications-endpoint)

[How to access the POST /applications endpoint](https://www.merge.dev/blog/post-applications-endpoint#how-to-access-the-post-applications-endpoint)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fpost-applications-endpoint)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**How Merge helps companies in Europe build secure, reliable, and powerful product integrations at scale**](https://www.merge.dev/blog/how-merge-supports-europe)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cf278669e1fd520b99e_Snappy_Case_Study_%2525252528Blog%2525252529_%25252525282%2525252529.webp)**Why we made it onto G2’s list of “Fastest Growing Products for 2024”**](https://www.merge.dev/blog/g2-fastest-growing-products)

# Merge now lets you add candidates AND applications to customers’ ATS applications with a single endpoint!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Our team is laser focused on adding new integrations over time, but we’re equally committed to improving our existing integrations.

For example, here’s a snapshot of some of the enhancements we’ve made across our integration categories in a recent week (you can view them in detail by visiting [our changelog](https://www.merge.dev/changelog)):

[![Screenshot of Changelog](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fdd92abf796a4fd56a906_671fd972262ef60b4254ebad_AD_4nXejYrAcmMhrZPikI6NZLmmLJzBjrpE4pOLKd_qs5OV-_U56-CeFDyox_pOOCsfDmrSOouWwqqlNq0snjoebnS-WLGqEN2c9iTED6NK6IAemR5551nOuof-xulpXUfEWPbcPDTfjXrsgaAdiX4mMXcy_Jq8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fdd92abf796a4fd56a906_671fd972262ef60b4254ebad_AD_4nXejYrAcmMhrZPikI6NZLmmLJzBjrpE4pOLKd_qs5OV-_U56-CeFDyox_pOOCsfDmrSOouWwqqlNq0snjoebnS-WLGqEN2c9iTED6NK6IAemR5551nOuof-xulpXUfEWPbcPDTfjXrsgaAdiX4mMXcy_Jq8.webp)

With the goal of improving existing integrations in mind, we’re excited to announce that we’ve enhanced the POST /applications endpoint for our [ATS Unified API](https://www.merge.dev/categories/ats-recruiting-api)!

You can read on to learn more about how we’ve enhanced it and what you can do to use it.

## **How we’ve improved** **the POST /applications endpoint**

Before this improvement, our customers would need to use two separate endpoints whenever they wanted to add applications and the associated candidates.

They’d first need to create a candidate via a [POST /candidates request](https://docs.merge.dev/ats/candidates/#candidates_create); then they’d need to create an application via a [POST /applications request](https://docs.merge.dev/ats/applications/#applications_create), and the latter would involve including candidate information within the request body to associate the application with the candidate.

You can now avoid having to make two requests.

Simply call the POST /applications endpoint and include candidate information within the body to create either of the following in a customer’s ATS: a candidate and their application or just the application if the candidate already exists.

[![How POST /applications endpoint changed](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fdd92abf796a4fd56a8f4_671fd972cc1a132ba7491f3b_AD_4nXd2BobgATCRxd2hoinbjV960huSWPkWv16fSoovrGCsEDcX_iKZawuypLxIEN6CcI1OQ900MQx7LLDAXtMYFohoqR2KYY1SdUCz43W7wq8NQ-8ruqanP2PMixANjaTSlnaTDXjPPz94XWWBBGa537iSXU8P.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fdd92abf796a4fd56a8f4_671fd972cc1a132ba7491f3b_AD_4nXd2BobgATCRxd2hoinbjV960huSWPkWv16fSoovrGCsEDcX_iKZawuypLxIEN6CcI1OQ900MQx7LLDAXtMYFohoqR2KYY1SdUCz43W7wq8NQ-8ruqanP2PMixANjaTSlnaTDXjPPz94XWWBBGa537iSXU8P.webp)

As you can imagine, consolidating these requests offers a few benefits for you and your customers.

You can, for example, create candidates and applications in customers’ ATS solutions faster and more efficiently; and you’ll be able to diagnose, troubleshoot, and resolve integration issues more easily and quickly using [Merge’s Integration Observability tooling](https://www.merge.dev/features/integration-observability).

## **How to access the POST /applications endpoint**

The endpoint is now available for the following ATSs (this list will expand over time!):

- Ashby
- BambooHR
- Lever
- Bullhorn
- Comeet
- Greenhouse
- JazzHR
- Jobadder
- Jobvite
- SAP SuccessFactors
- SmartRecruiters
- Teamtailor
- UKG Pro Recruiting
- Workable
- Workday

Accessing and using it also won’t come at an additional cost, so we encourage you to start leveraging it.

That said, the endpoint is backwards compatible, so if you’d prefer to keep using the previous approach for creating applications and candidates, you can do so without any disruptions.

You can learn more about our improved endpoint by reading [this Help Center article](https://help.merge.dev/en/articles/10012366-updates-to-post-applications-oct-2024) and/or speaking to your designated customer success manager. And if you’re new to Merge, you can [schedule a demo with our team to learn more](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fpost-applications-endpoint).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=32c43b92-427f-498b-9f23-5e2afec3834e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8e3c8a57-a3f0-4f80-b45a-7df21a2d1670&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpost-applications-endpoint&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=32c43b92-427f-498b-9f23-5e2afec3834e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8e3c8a57-a3f0-4f80-b45a-7df21a2d1670&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpost-applications-endpoint&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

td.doubleclick.net

# This site can’t be reached

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743909796&cv=11&fst=1748743909796&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpost-applications-endpoint&hn=www.googleadservices.com&frm=0&tiba=Merge%20now%20lets%20you%20add%20candidates%20AND%20applications%20to%20customers’%20ATS%20applications%20with%20a%20single%20endpoint!&npa=0&pscdl=noapi&auid=436081654.1748743910&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

ERR\_SOCKET\_NOT\_CONNECTED

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743909796&cv=11&fst=1748743909796&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpost-applications-endpoint&hn=www.googleadservices.com&frm=0&tiba=Merge%20now%20lets%20you%20add%20candidates%20AND%20applications%20to%20customers’%20ATS%20applications%20with%20a%20single%20endpoint!&npa=0&pscdl=noapi&auid=436081654.1748743910&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

![](<Base64-Image-Removed>)![](<Base64-Image-Removed>)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=da4425b6-080e-46ad-9130-323f6d558117&bo=2&sid=c706aae03e8d11f08e5f05f38f6ed97a&vid=c70763403e8d11f08d40c727a488513c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Merge%20now%20lets%20you%20add%20candidates%20AND%20applications%20to%20customers%E2%80%99%20ATS%20applications%20with%20a%20single%20endpoint!&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpost-applications-endpoint&r=&lt=528&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=130833)