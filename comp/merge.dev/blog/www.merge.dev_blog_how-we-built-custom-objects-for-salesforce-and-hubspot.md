---
url: "https://www.merge.dev/blog/how-we-built-custom-objects-for-salesforce-and-hubspot"
title: "From the Eng Org: How we built Custom Objects for Salesforce and Hubspot (so you don’t have to)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-we-built-custom-objects-for-salesforce-and-hubspot#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-we-built-custom-objects-for-salesforce-and-hubspot#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-we-built-custom-objects-for-salesforce-and-hubspot#)

Table of contents

[H2 link](https://www.merge.dev/blog/how-we-built-custom-objects-for-salesforce-and-hubspot#)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-we-built-custom-objects-for-salesforce-and-hubspot)

##### Just for you

No items found.

# From the Eng Org: How we built Custom Objects for Salesforce and Hubspot (so you don’t have to)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cebeb21529aacadcf7c_Custom_Objects_-_Oral_History.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53863af779c6de1fac49_62eff958629f189b8b5fe851_Prannoiy.webp)

Prannoiy Chandran

Platform + Product

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53877b8f26a5217961a2_62eff8f30b52a6d340e12550_Josh.webp)

Joshua Learn

Software Engineer

@Merge

Supporting [custom objects](https://www.merge.dev/blog/read-write-update-custom-objects-from-any-crm-with-one-api) in a [Unified API](https://merge.dev/categories/crm-api) was not an easy build. But it was absolutely worth it to support our customers’ need for customized data models.

To accompany Merge’s launchof Custom Objects for Salesforce, Hubspot, and Zendesk Sell, we sat down with two key players on the project: Prannoiy Chandran, CRM API Platform Lead, and Joshua Learn, Expansion Engineer, to hear first-hand what it took to go from initial spec to launch-ready build.

If you’re looking to add support for custom objects to your own product — we hope to make the process of adding scalable support a tiny bit smoother.

‍ **Merge: Let’s start with this: how did custom objects make it to the roadmap?**

**Prannoiy Chandran (PC):** Even when scoping our CRM API _\[launched in Q2 2022\]_, we knew custom objects were a key part of any CRM system. Still, we wanted to gather data points on _how_ our customers wanted to use them, before committing to any feature-specific build: **we knew custom objects were not going to be easy.**

By Q4 of 2022, we had enough context on the capabilities our customers wanted, and we could respond by scoping out a feature-set that would enable users to read, write, and update custom objects from their customers’ CRMs. **‍**

**Merge: You mentioned customer use cases, can you give us context on what things companies are trying to build with custom objects?**

‍ **PC:** Absolutely. Custom objects are super flexible by nature, but we really saw use cases pop up everywhere, such as representing a product’s data — or really, their unique value — directly in a CRM. Additionally, being able to pull in custom objects **related** to key CRM models was critical: it would allow users to do things like build up complex reports and analysis on sales data. This is all super important stuff when you’re offering CRM integrations to your customers.

**Merge: You mentioned custom objects ‘were not going to be easy,’ why is that?**

‍ **Joshua Learn (JL):** Most CRMs store the same type of data: Leads, Opportunities, etc. So for normal, standard types of objects, ‘non-custom’ objects, they are represented pretty uniformly, even in different APIs.

When it comes to Custom Objects, **it suddenly becomes very difficult to unify.**

I’ll explain. You have to not only express the actual data being stored inside the CRM; you also have to be able to express the schema, the types of things that it can hold, the types of things that it can be related to, _and_ you have to generalize that in a way that [unifies across all those different CRMs](https://merge.dev/blog/what-is-a-unified-api).

All the while, you’re going to need to provide capabilities that actually take into account everything that all of these different CRMs are capable of: such as GET, POST, or PATCH support.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08cdb493eabe3e255bac_641e152d117efe5e937e2a5b_image2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08cdb493eabe3e255bac_641e152d117efe5e937e2a5b_image2.webp)

_Custom Objects, as it appears in Merge’s guide_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08cdb493eabe3e255baf_641e153ce1bf8350d77951a9_image1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc08cdb493eabe3e255baf_641e153ce1bf8350d77951a9_image1.webp)

_Custom Objects, as it appears in Merge docs_

**PC:** Going off of that unification challenge — today, for example, we launched with Custom Objects support for [Salesforce](https://merge.dev/integrations/salesforce), [HubSpot](https://merge.dev/integrations/hubspot), and [Zendesk Sell](https://merge.dev/integrations/zendesk-sell). They've really been the focus of this whole project.

But one critical need early on was to prove out a valid unified approach that we could extrapolate to other integrations.

Our initial feature set included four data models that fit the majority of use cases we were seeing:

- Custom Object records
- Custom Object classes
- Associations
- Association types

It would also allow us to scale to many integrations.

‍ **Merge: Focusing on the engineering side, could you tell us about how you decided on those features?**

‍ **JL:** That was design spec’ing: You figured out what your customers want, now you need to design a customer-facing feature set, like a [customer-facing API](https://docs.merge.dev/crm/), and what types of information they might want to know or troubleshoot via dashboard.

‍ **These things get really complicated, but you don't want it to be too complicated for anyone to use, or they're not going to use it.**

We also needed to spec the actual implementation on our side:

- How we're actually going to achieve this in our backend infrastructure
- How we’re going to store the data models
- How someone would interact with them
- How we’d surface them via our API

There are all sorts of challenges with this. When you have something that's a completely arbitrary structure, that you only know the shape of once your customers are using it, you have to be able to handle a very flexible schema.

Engineering spec’ing is also a great challenge: how are we going to achieve what we put in the customer facing spec?

‍ **Merge: So you’ve spec’d the specs — what was the build like?**

‍ **JL:** It was a continual pair programming back and forth between me and Prannoiy.

I was working from the backend infrastructure point of view, figuring out how we're actually implementing, how we're going to handle it in a way that is broadly applicable to all of the different APIs and integrations Merge wants to build out for customers and users.

Prannoiy was more on the customer facing side and actually building out the support per integration, doing the research on the integrations: what they offer, and what they support.

Then it involved a lot of testing and validating with our initial customers to make sure we got things right.

‍ **Merge: Even now that the feature is launched, do you consider the work finished?**

**JL:** Of course not. We want to continue to support this feature, address edge cases as they come up, make sure any issues are resolved, and expand support to more integrations.

‍ **Merge: And tell us — what’s on the roadmap for the future?**

‍ **PC:** Merge Custom Objects currently supports Salesforce, HubSpot, and Zendesk Sell. On the short term roadmap, we’ll be supporting ActiveCampaign, Zoho CRM, and Microsoft Dynamics, and looking into further developing future iterations of Merge Custom Objects.

We’ve currently just built out the API aspect of it. We have thought about the visual aspect, in terms of adding it to the dashboards. If we get more demand for it, we can get more data points and can strategize on how we are going to design it, and what kind of use cases it may serve.

This is a pretty complex situation to try to normalize. We've made some decisions here, as to how to do it, **but we set it up in a way that leaves the door open to adding a lot more functionality.**

‍ **Merge: Any closing thoughts?**

‍ **JL:** We’re extremely excited to see what people build.

If you want to learn more about Merge Custom Objects, please [reach out to our team to discuss how we can support your use case](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-we-built-custom-objects-for-salesforce-and-hubspot).

If you're a Merge customer on the Professional and Enterprise plans, you'll be able to use Custom Objects right away.

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Prannoiy Chandran

Platform + Product

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Joshua Learn

Software Engineer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=0293baa8-da7b-4652-8f66-8013574601ea&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=53cf4742-6f08-43e6-9279-b7068be24c4e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-we-built-custom-objects-for-salesforce-and-hubspot&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=0293baa8-da7b-4652-8f66-8013574601ea&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=53cf4742-6f08-43e6-9279-b7068be24c4e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-we-built-custom-objects-for-salesforce-and-hubspot&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)