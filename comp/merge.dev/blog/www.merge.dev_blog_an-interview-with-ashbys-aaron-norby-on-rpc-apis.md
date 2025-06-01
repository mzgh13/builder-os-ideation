---
url: "https://www.merge.dev/blog/an-interview-with-ashbys-aaron-norby-on-rpc-apis"
title: "An interview with Ashby on RPC APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/an-interview-with-ashbys-aaron-norby-on-rpc-apis#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/an-interview-with-ashbys-aaron-norby-on-rpc-apis#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/an-interview-with-ashbys-aaron-norby-on-rpc-apis#)

Table of contents

[H2 link](https://www.merge.dev/blog/an-interview-with-ashbys-aaron-norby-on-rpc-apis#)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fan-interview-with-ashbys-aaron-norby-on-rpc-apis)

##### Just for you

No items found.

# An interview with Ashby on RPC APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadbbb5568970b2d91a_8.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

‍ _In this piece, Shensi Ding (Co-founder at Merge) talks with Ashby engineer Aaron Norby about integrating with RPC APIs. Ashby is a next-generation Applicant Tracking System (ATS), with customers like VanMoof, Deel, Census and Modern Treasury. Merge’s integration with Ashby is live and available for all users._

Gil and I first met the Ashby team when one of their customers wanted us to add Ashby\` to our ATS API. We immediately loved the founders, Benjamin and Abhik, and were excited to start working on adding their integration once they built out their API. When their API launched, I was intrigued— it was **RPC**.

RPC stands for Remote Procedure Call, and stands apart from the most common API styles— REST (Representational State Transfer), GraphQL, SOAP— because it is relatively uncommon for public-facing APIs.

Luckily, Aaron Norby, the lead on Ashby’s API creation, agreed to sit down with me to discuss how Ashby chose their API-style, and what his team has learned since. Even after releasing our [**integration with Ashby**](https://www.merge.dev/ashby/?utm_source=medium&utm_medium=blog&utm_campaign=rpc-ashby-interview), I learned a lot in this discussion, and I hope you all do as well!

{{blog-cta-100+}}

‍

**Shensi Ding: Tell us the backstory about Ashby’s API.**

**Aaron Norby**: The original impetus for building an API was that we had a customer who wanted to completely build their own website for applying, posting job boards, taking applications, and to use Ashby for analytics. We originally built it to help with that use case.

Our internal API is not REST— it’s not RPC either. We use GraphQL, and since we were outside of the REST framework anyway, we were more open to seeing what else was out there.

**What were the different styles of APIs that you considered, and what were the pros and cons of each?**

We knew we didn’t want GraphQL for our external API because there was a heavy lift for learning. GraphQL is getting more popular, but it’s not widely adopted yet. It’s also a very opinionated decision— not everyone who will want to use the API wants to use GraphQL or is familiar with it.

When we were considering REST, it was less about the downside and more about how easy it is to learn and understand immediately what to do to get something done. REST uses standard HTTP verbs, and there are standards about how they should be used and what they should mean. From my previous experience it’s not always that easy. Occasionally, you’ll want to do a relatively simple operation, but you’ll need to spend a lot of time thinking in circles to figure out exactly what entity you’re addressing and making decisions about.

One example that comes to mind is our current method application.change\_source. Would this fit with the application entity or is there a separate source entity? Would this be a POST or a PATCH on the source / application entity? It’s not that easy to figure out.

**How did you become familiar with RPC APIs?**

Right before this project, I was working on an integration with Slack. Slack’s API is RPC. When I was building that out, I encountered their API and needed to read their documentation to figure out how to do things, and it felt much easier and significantly more intuitive than trying to figure out what endpoint / method was necessary to get things done. It was very simple and felt a lot like what an engineer is used to when writing functions.

**What was different during the process of building out the API?**

Things would have felt more weird if we weren’t coming from GraphQL, but the main difference was that everything is a POST vs. in the REST world where you’re using a variety of HTTP verbs. It didn’t take much to get over that mental hurdle.

There was also the discussion of how to do error handling. Once you say you’re not going to use the standard REST way of doing things in terms of HTTP stuff then that either opens up or puts a burden on how you handle if somebody gets an endpoint for a single entity. The standard response is returning a 404, but here we could return a more helpful error response with information about their problem.

**Were there any downsides that your team considered as you were deciding on RPC APIs?**

One downside is that it’s less familiar overall. REST is much more familiar and widely used for publicly-facing integrations, and RPC is more widely used for communication between services within a system. We considered this when we were rolling out our API to customers and whether it was too much of a learning curve, but ultimately decided that it wasn’t that bad. Our first few customers also seemed very happy with it.

**Any surprise benefits from using an RPC-based approach?**

Documenting our API was a lot easier than we thought it would be!

**What feedback have you received?**

Feedback has been pretty good so far! It’s been satisfying as we’re onboarding more people onto using it.

[_Merge_](https://merge.dev/?utm_source=medium&utm_medium=blog&utm_campaign=rpc-ashby-interview) _provides the tools to transform how B2B companies realize customer-facing integrations. Want to integrate with Ashby just once? Check out our solutions_ [_here_](https://www.merge.dev/ashby/?utm_source=medium&utm_medium=blog&utm_campaign=rpc-ashby-interview) _._

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)

Shensi Ding

CEO and co-founder

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0f8ca19c-eb47-4694-bccf-7ecc9b28d845&bo=2&sid=53db1b603e8d11f0a4321fd2914058a0&vid=53dd1d103e8d11f0b18a1ddb2cb24046&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=An%20interview%20with%20Ashby%20on%20RPC%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fan-interview-with-ashbys-aaron-norby-on-rpc-apis&r=&lt=744&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=470232)