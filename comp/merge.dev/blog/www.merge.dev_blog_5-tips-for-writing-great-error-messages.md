---
url: "https://www.merge.dev/blog/5-tips-for-writing-great-error-messages"
title: "5 Tips for Writing Great Error Messages"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/5-tips-for-writing-great-error-messages#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/5-tips-for-writing-great-error-messages#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/5-tips-for-writing-great-error-messages#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F5-tips-for-writing-great-error-messages)

##### Just for you

No items found.

# 5 Tips for Writing Great Error Messages

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cecc577c4fdf07e6241_Blog_Graphic_-_5_tipes_for_writing_great_error_messages.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26ba0966dc16ec12d14a_Irene%20Hu%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f082f3162f9f1c94ba54a_irene-hu_min.webp)

Irene Hu

Marketing

@Merge

A good error message is part of creating a good user experience. While encountering them as an end user may cause frustration, a comprehensive error message can provide the necessary insights to debug and troubleshoot effectively.

When it came to building our new **Detailed Error Messages** feature — now available to all Merge customers, we knew it was important to consider not only what types of errors but how to communicate those errors. These are shown to our customers’ end users when they interface Merge Link.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/643efddc1904c313c3b21ad2_DfI96_Jl7yrR0xKKcgofPvhGIDrCcZYpLGqg57-V_XyLHAECeJjWY7DLXqJrJQowsOYg1_N5Zf8bBvWQxMXv895TORHLbjPEuGb7F-pWshEz-7nOoWnfEenwFo_W9jTN6sSW26A-cEH6skrlFxstwuY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/643efddc1904c313c3b21ad2_DfI96_Jl7yrR0xKKcgofPvhGIDrCcZYpLGqg57-V_XyLHAECeJjWY7DLXqJrJQowsOYg1_N5Zf8bBvWQxMXv895TORHLbjPEuGb7F-pWshEz-7nOoWnfEenwFo_W9jTN6sSW26A-cEH6skrlFxstwuY.webp)

Two examples of our Detailed Error Messages in Merge Link

[Merge Link](https://docs.merge.dev/get-started/link/) is our seamless UI component that guides our customer’s end user through setting up an integration with just a few clicks. Merge Link can be easily embedded into our customer’s app, showcasing the different integrations that are available via Merge.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/643efddbb5c3292d3ee8af33_VCVVuPGmkk6hdsIXj14NSE-d-fMRcAZxUWV5pJ2TvI8HtoHNscptneixUyBm8M0EzbC5K9X1XSHYqIrzX7TdnzeZDAtdXWj-kn4LAXTYqs4QUG-TCG9hMxPagsy97jM_TTYbplQrJU6WEt1l36EB6Xg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/643efddbb5c3292d3ee8af33_VCVVuPGmkk6hdsIXj14NSE-d-fMRcAZxUWV5pJ2TvI8HtoHNscptneixUyBm8M0EzbC5K9X1XSHYqIrzX7TdnzeZDAtdXWj-kn4LAXTYqs4QUG-TCG9hMxPagsy97jM_TTYbplQrJU6WEt1l36EB6Xg.webp)

Merge Link

Because Merge Link is the main interface that our customers’ end users will use, and is part of our customers’ product experience, we knew it was crucial to invest time and effort into building out custom error messages for challenging integrations. These integrations are more complex to authorize than the simple, “Sign in with your credentials and share the API key.”

Ankit Deshmukh and Lee Wang on our engineering team and Yash Gogri on our post-sales team shared 5 key takeaways when it comes to writing error messages:

#### 1\. Find the most common errors

In order to make sure our detailed error messages would have the highest impact, our team looked at product data involving thousands of customers using the 100+ integrations we support.

We looked at the most frequently used integrations, the percentage of successful linked accounts at the integration level, as well as customer feedback to prioritize which integrations to add detailed error messages and the types of error messages.

Because we chose the right starting points, we’ve already seen over a 30% increase in our linked account success rate for HRIS integrations during the beta phase.

_Related:_ [_5 API error handling best practices_](https://www.merge.dev/blog/api-error-handling)

#### 2\. Keep the error messages simple

We wish we didn’t have to write this, but legendary error messages like, “Task failed successfully,” made us think twice. Detailed error messages need to be simple and easy for readers to understand.

Merge Link’s interface makes it easy for any business user to access the technical power of APIs. That means error messages need to be written in a way that’s accessible across all levels of technical understanding.The end user might be an HR manager who might not know what an API is.

When we wrote our error messages, we kept the messages clear and direct, focusing on the problem and steps required to solve it, and avoided any jargon or philosophical paradoxes.

#### 3\. Display a helpful call to action

Sometimes, an error can be so complex that a concise message wouldn’t help. Having a clear call to action that directs to [a longer help center article](https://help.merge.dev/en/articles/5699428-workday-isu-and-web-services-endpoint-authentication), with videos and/or screenshots can be the next step an end user needs when the error message may not be sufficient enough.

#### 4\. Consider the backend logic and rules so the proper error message appears

Our engineering team needed to make sure the correct error messages popped up at the right time.

After careful consideration and planning, they had to code the logic to ensure the correct error message displayed based on specific triggers.

For example, showing the main error message that caused downstream errors enables the end user to find a resolution. If they don’t see the right error message, it would result in unresolved issues, an ineffective error reporting system, and an endless bout of headaches.

#### 5\. Test, test, and test some more!

The most important thing that the team did when building this feature was testing each integration’s linking flow, putting themselves in the perspective of a Merge Link end user.

This made sure our team captured edge cases and addressed any additional areas of confusion in the linking flow. Going through the actual user experience is crucial, there’s no shortcut around this!

### See Detailed Error Messages in Action

Detailed error messages will enable our customers’ support teams to save time, and guide end users to independently troubleshoot integration issues.

Not only can this save hours of each of our customers’ support team’s time, it also delivers a better in-product experience. Best of all, Merge Link can take care of all of this, so our customers don’t need to spend time thinking through and building their own error logic and messages.

Want to see this in action? The Detailed Error Messages feature is available to everyone, including those on our Launch plan where customers can start on for free! [Sign up now](https://app.merge.dev/signup).

If you’re looking to learn more about Merge and see it in action, you can [get a demo](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2F5-tips-for-writing-great-error-messages).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26ba0966dc16ec12d14a_Irene%20Hu%20-%20Merge.png)

Irene Hu

Marketing

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

[iframe](https://app.qualified.com/w/1/faa5v4dWtZ1a9fXx/messenger?uuid=d727b458-95c3-48f4-b28d-86d05b0c736a)![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=77489f21-2fa6-48d7-a4cc-83863e8884b5&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=68e107ba-bc27-4e83-8cb6-155e671d1332&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F5-tips-for-writing-great-error-messages&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=77489f21-2fa6-48d7-a4cc-83863e8884b5&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=68e107ba-bc27-4e83-8cb6-155e671d1332&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2F5-tips-for-writing-great-error-messages&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748744119524&cv=11&fst=1748744119524&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2F5-tips-for-writing-great-error-messages&_ng=1&hn=www.googleadservices.com&frm=0&tiba=5%20Tips%20for%20Writing%20Great%20Error%20Messages&npa=0&pscdl=noapi&auid=20265468.1748744119&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748744119616&cv=11&fst=1748744119616&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2F5-tips-for-writing-great-error-messages&_ng=1&hn=www.googleadservices.com&frm=0&tiba=5%20Tips%20for%20Writing%20Great%20Error%20Messages&did=dZTQ1Zm&gdid=dZTQ1Zm&npa=0&pscdl=noapi&auid=20265468.1748744119&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=efdd3d83-93f4-4501-9152-5d7980f2a596&bo=2&sid=43fec9b03e8e11f08446e9cebdf59549&vid=43fefe003e8e11f08e9e4bdbcb5c5119&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=5%20Tips%20for%20Writing%20Great%20Error%20Messages&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2F5-tips-for-writing-great-error-messages&r=&lt=316&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=720649)