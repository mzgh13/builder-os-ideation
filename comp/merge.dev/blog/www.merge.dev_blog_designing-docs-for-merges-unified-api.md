---
url: "https://www.merge.dev/blog/designing-docs-for-merges-unified-api"
title: "Designing docs for Merge's Unified API"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#)

Table of contents

[Hello world!](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#hello-world)

[Designing for an API](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#designing-for-an-api)

[Our Docs Journey Begins](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#our-docs-journey-begins)

[Docs Go Public](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#docs-go-public)

[Latest Docs Revamp](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#latest-docs-revamp)

[More Little Things](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#more-little-things)

[Code Snippets](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#code-snippets)

[Pending Changes](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#pending-changes)

[Conclusion](https://www.merge.dev/blog/designing-docs-for-merges-unified-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fdesigning-docs-for-merges-unified-api)

##### Just for you

No items found.

# Designing docs for Merge's Unified API

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7275667a019cb5e4dc_GTM_resources_roundup.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5384dd3f0d4cd4179027_62eff2be0b52a64e84e0aba8_simeon-lee.webp)

Simeon Lee

Founding Designer

@Merge

## Hello world!

My name is [Simeon Lee](https://twitter.com/simeonlee_) and I’m the Founding Designer at [Merge](https://www.merge.dev/). I’m thrilled to be sharing our design adventures in the public view. I’m most excited to share the inner workings and decisions of a designer sprinting across the user-facing surfaces of a high-growth seed stage company with a **lot** of design needs.

What does Merge do? Merge hosts the world’s first Unified API for HR, payroll, recruiting, and accounting. Whether you have customers that are currently using Trinet or ADP or Freshteam (or Hibob or Lever or Greenhouse or JazzHR or Quickbooks or Sage…), you no longer need to have hordes of engineers on staff and unending roadmap carve-outs for long-tail integrations. **Integrate once with Merge’s Unified API**, and we sync your users’ data with all of the integrations on our platform. We save you tremendous amounts of time, money, and tears.

_Related:_ [_12 unified API examples_](https://merge.dev/blog/unified-api-examples)

## Designing for an API

Even though creating documentation is not widely considered “exciting” work, our docs serve a critically important function to the success of our business: **they document and disambiguate Merge’s Unified API**. In writing this post, I’m hoping to shed light on the design decisions that culminated in the latest major release of our docs last week.

First off — **How do you generally design for an API?** There are multiple levels of design inherent in an application programming interface, but to simplify, I consider good user-focused design to focus on:

1. Engineering semantics, whether it be naming things to be relatively self-documenting or having a simple experience to implement full, predictable CRUD workflows.
2. Documentation that removes the unpredictability in an idiosyncratic application programming interface.

At Merge, code semantics are owned by our engineers, and so our engineers have needed to become designers themselves. This means building and testing integrated applications in various languages and integrating them with our Unified API, just like our customers. No small feat, but reliability is paramount at Merge!

I’ve been in charge of designing and fleshing out the other side of our API — the documentation. This means creating the onboarding experience, mapping out the information architecture of our API, collaborating with our engineers to ensure content is accessible and accurate, and iterating the visual style of the docs to be appealing and maintain a high level of quality in our API product.

## Our Docs Journey Begins

##### _November 2020_

When I first arrived at Merge, I was surprised to find that our docs lived inside the Merge dashboard web app. I would learn this decision was primarily to hide our product details while in stealth.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730645cf4077301add7ca_Docs_in_Dashboard.jpeg)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730645cf4077301add7ca_Docs_in_Dashboard.jpeg)

_Our first version of our docs lived in our dashboard_

I didn’t agitate to move our documentation outside of our dashboard immediately. With minimum viable experience in mind, I spent my first few months improving the quality and content of the documentation. This included polishing the onboarding experience so that new developers would have an easy 2-step guide to integrate Merge into their product. Step one of the guide featured dropping our Merge Link component into their frontend; step two featured integrating their backend with Merge using one of our many SDK’s. Both steps featured testing utilities to signal a successful integration with Merge (something familiar: make the red blinking light go green through a successful request).

_Related:_ [_A guide to reading API documentation_](https://www.merge.dev/blog/how-to-read-api-documentation)

## Docs Go Public

##### _March - April 2021_

There was so much to do in the early days that even when it was clear our docs were functionally different from our dashboard and should live in a separate context, we couldn’t prioritize rearranging our frontend assets until much  later.

After several months, we finally moved our docs into our landing page. This made our docs viewable to prospective customers (no signup required) while also making it publicly accessible via search engines. (Did I mention Merge was now [announced to the whole world](https://www.merge.dev/blog/company/announcing-merge%E2%80%99s-$4.5m-seed-round-and-accounting-api)?)

With the move, I wanted to visually differentiate our documentation from our dashboard web app. Our dashboard featured a white navigation bar, so I hastily made the left navigation sport a contrasting dark gray gradient and gave it a minimal home page. Aside from that, the design and information architecture of the documentation remained largely unchanged.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7308a492d2773bf000f93_Old_Docs.jpeg)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7308a492d2773bf000f93_Old_Docs.jpeg)

_This older version of our docs contained information architecture weaknesses_

In this widely viewable version of our documentation, we began to receive negative user feedback regarding poor informational architecture. The next challenge we would need to tackle would be to aid the user in uncovering the content they sought regarding the CRUD workflows for the many object classifications we have across our HR, payroll, recruiting and accounting integrations.

## Latest Docs Revamp

##### _May - June 2021_

In our latest major revamp of our docs, we went back to the drawing board and interrogated the content of our documentation as that would inform our layout. Remember: Form follows function!

Our documentation featured several groupings of information:

1. Merge Link Quickstart
2. SDK Overview
3. API Reference

Our API Reference broke down into these sections:

- Basics
- ATS
- HRIS
- Accounting
- Supplemental Data

The first two major groupings — **Merge Link Quickstart** and **SDK Overview** — constituted our “Get Started” guide. The final group of information — our **API reference** — was essential for customers to understand our standardized data model and available CRUD operations.

The biggest problem with our previous documentation’s API reference was that **the CRUD operations for all of our standardized data models** **were on one long scrollable page**. When we began to receive negative customer feedback regarding our docs — in particular, the difficulty of discovering information in this massive page — it pushed us to rethink our information architecture and overall design. We rapidly moved towards a new visual system for our documentation — see the results below:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730d139137481d2618158_New_Docs__merge.dev_.jpg)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730d139137481d2618158_New_Docs__merge.dev_.jpg)

_Our latest docs home page_

**In this latest redesign of the docs**, I exchanged out the dark gray style in favor of a muted gray theme with the _mildest_ slant of blue hue to imbue a subtle modernity.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730ef18207608adc74ea9_Swatch.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d730ef18207608adc74ea9_Swatch.png)

_The new gray_

Our biggest change was the creation of an information hierarchy that subsisted across a series of new nav bars. We chose to feature a primary top navigation, a secondary top sub-navigation, and a left navigation with vertical accordions used to dissemble standardized data objects and CRUD operations.

From there, we broke out the CRUD operations for each “Common Model” (what we term our standardized data types) onto separate pages:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7310e4bc804492e61f2c2_Hiearchy_Zoom_In.jpeg)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7310e4bc804492e61f2c2_Hiearchy_Zoom_In.jpeg)

_Our Common Models broken out on separate pages_

Assigning separate colors to each HTTP request method (e.g., GET, POST, PATCH, DELETE) helped create a delineation in the navigation between disparate concepts and establish a familiar pattern throughout the docs in the navigation and content.

With the separation of topics (remember — no more single long scrollable page), it was essential for our developer to implement elegant and fast interactions as our user flipped through each element. [Brendan Goggin](https://www.linkedin.com/in/brendangoggin/) — our full-stack wizard — implemented stimulating, artfully eased transitions making our docs feel like a seamless, organic, and delightfully explorable experience. Truly a marvel to click around and play with.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d741b8c5c6b7255bb8eaf1_designpreviewnew.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d741b8c5c6b7255bb8eaf1_designpreviewnew.gif)

_Interaction design preview_

## More Little Things

An assortment of other small information hierarchy improvements were made to improve clarity and help the user think less when looking for the information they sought.

The first was creating a more sensible design for child relations. Our Common Models have a nested hierarchy for certain relations — such as that between parent objects like Candidates and child objects like Phone Numbers (which aren’t simple string fields on the parent because they need extra fields to handle type differences).

For child objects, instead of having a whole separate section for them, we chose to simply show them in-place within the parent object themselves. See example below with Phone Number, Email Address, and URL:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d731821805d370c4598471_Child_Relation_Objects.jpeg)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d731821805d370c4598471_Child_Relation_Objects.jpeg)

## Code Snippets

Our code snippets all previously sported a dark blue theme. This included both executable code and API example response objects.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d731f4ed2d58462377f0c3_Old_Code_Snippet.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d731f4ed2d58462377f0c3_Old_Code_Snippet.png)

_Previously, all our code snippets featured this dark style_

However, API documentation has a lot of code snippets of different types — **some executable, others example response objects** — and having them all the same style made parsing and scanning lots of content burdensome. We created delineation and hierarchy in the information presented amongst our code snippets by keeping our executable code snippets dark and making our response examples and object schemas light:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7322d1665c51f3718370b_New_Code_Snippet.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62d7322d1665c51f3718370b_New_Code_Snippet.png)

_Our latest example response snippets now feature a new, distinguishing style_

## Pending Changes

One weakness we quickly discovered with our new design was that people couldn’t rely on CMD+F’ing their way to the information they were seeking. Still, even that one unexpected benefit of the monopage documentation was limited in scope: only experienced users knew what they were looking for. Newcomers were out of luck. We’re solving this in our new docs by simply adding a search bar.

## Conclusion

Designing documentation isn’t typically thought of as flashy work, but this project was a great exercise in information architecture, which breaks down into the artful use of typography pairings, subtle color cues, whitespace importance, and content groupings.

I think great design is about stripping away the unnecessary and letting idiosyncratic design notions get out of the way to present only that which is important to the user as quickly and sensibly as possible. The documentation of our Unified API is truly our most important user-facing product — without providing our customers an understandable map, it’s possible they may never successfully arrive at their desired destination.

Our startup’s mission is to provide our users the ability to integrate fast and integrate once. Great design will be our secret weapon in winning over our customers’ developers and ultimately the booster rocket which will propel our impact upon the API economy to stratospheric heights.

**Merge** provides a Unified API to transform how B2B companies implement user-facing integrations. Learn more about building once, building better, and building faster — [here](https://www.merge.dev/?utm_source=blog&utm_medium=blog&utm_campaign=designing-docs-simeon).

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Simeon Lee

Founding Designer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=9b9c14f0-010a-48b1-8b7c-27f1ed9f964a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=61a195be-000c-4fbd-b5a3-cd6c73437d6f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fdesigning-docs-for-merges-unified-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=9b9c14f0-010a-48b1-8b7c-27f1ed9f964a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=61a195be-000c-4fbd-b5a3-cd6c73437d6f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fdesigning-docs-for-merges-unified-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=52268353-097d-4c81-a019-e6cb5b11c283&bo=2&sid=ed2bc1f03e8d11f09472ab7445c72e30&vid=ed2bda303e8d11f0bcf15bca6f98e9db&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Designing%20docs%20for%20Merge%27s%20Unified%C2%A0API&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fdesigning-docs-for-merges-unified-api&r=&lt=523&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=433270)