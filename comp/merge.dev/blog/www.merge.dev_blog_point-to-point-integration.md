---
url: "https://www.merge.dev/blog/point-to-point-integration"
title: "Point-to-point integration: pros, cons, and alternatives"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/point-to-point-integration#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/point-to-point-integration#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/point-to-point-integration#)

Table of contents

[What is a point-to-point integration?](https://www.merge.dev/blog/point-to-point-integration#what-is-a-point-to-point-integration)

[Examples of point-to-point integrations](https://www.merge.dev/blog/point-to-point-integration#examples-of-point-to-point-integrations)

[Benefits of point-to-point integration](https://www.merge.dev/blog/point-to-point-integration#benefits-of-point-to-point-integration)

[Drawbacks of point-to-point integration](https://www.merge.dev/blog/point-to-point-integration#drawbacks-of-point-to-point-integration)

[Best practices for building point-to-point integrations](https://www.merge.dev/blog/point-to-point-integration#best-practices-for-building-point-to-point-integrations)

[Alternatives to point-to-point integration](https://www.merge.dev/blog/point-to-point-integration#alternatives-to-point-to-point-integration)

[Point-to-point integration FAQ](https://www.merge.dev/blog/point-to-point-integration#point-to-point-integration-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fpoint-to-point-integration)

##### Just for you

No items found.

# Point-to-point integration: pros, cons, and alternatives

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e81a194b3bce109447c6_Unified_API_Benefits.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Your organization will, inevitably, need to build integrations between applications, whether that’s connecting the applications your organization uses or [integrating your product to the apps your clients use](https://merge.dev/blog/product-integrations).

Your initial preference for building any might be an approach that's referred to as point-to-point integration (also known as a native integration or P2P integration). But that doesn’t necessarily mean it’s the best option for your given integration use cases.

We’ll walk you through what this approach means, when it’s worth using (and avoiding), and your alternative options for implementing and maintaining integrations. That way, you can better decide what approach to use for each scenario.

Everything you need to know about native integrations - YouTube

Merge

202 subscribers

[Everything you need to know about native integrations](https://www.youtube.com/watch?v=hDDZmPJtzL0)

Merge

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

[Watch on YouTube](https://www.youtube.com/watch?v=hDDZmPJtzL0 "Watch on YouTube")

## **What is a point-to-point integration?**

It’s the use of custom code to connect one application with another. The code can be in any language and is typically geared towards accessing and communicating with a specific API endpoint provided by a 3rd-party application.

[![The two types of point to point integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65822abc407c71baaea9b633_BSHEHEuBjT8GqvG1EPYlQaFJPN9SY_nrEaBPAuIBz78tpqL9Lf3FZ1f3B-45Xd2ktb6GdJvHuwFpnJhZVkXH1egARFeONJbv7lde09nDLdQmhyc7MBr8SOa7sMtQgFLaVXEB85YTAcAqPf-GO4Iaa-M.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65822abc407c71baaea9b633_BSHEHEuBjT8GqvG1EPYlQaFJPN9SY_nrEaBPAuIBz78tpqL9Lf3FZ1f3B-45Xd2ktb6GdJvHuwFpnJhZVkXH1egARFeONJbv7lde09nDLdQmhyc7MBr8SOa7sMtQgFLaVXEB85YTAcAqPf-GO4Iaa-M.webp)

Note: This definition differs from star integration (also known as spaghetti integration), which is simply a collection of internal integrations that are built using the point-to-point approach.

_Related:_ [_A guide to native integrations_](https://merge.dev/blog/native-integrations)

## **Examples of point-to-point integrations**

To bring our definition to life, let’s cover some common point-to-point integration examples. We’ll start by breaking down a few internal use cases and then review a couple customer-facing scenarios.

### **Ticket escalations**

Your customer-facing team likely receives a number of client issues that require other internal stakeholders to resolve—in many cases, engineering.

To help your customer-facing employees flag issues to engineers successfully, you can build a point-to-point connection between the ticketing tool the former uses (e.g., Zendesk) with the tool the latter uses (e.g., GitHub) and build the following flow: Once a ticket is marked as "urgent" in the customer-facing team’s tool, it’s automatically routed to the engineering team’s platform.

The sync can also be bidirectional. In other words, as engineering updates the ticket, those changes get reflected in the associated ticket within the customer-facing team’s tool—allowing them to stay in the loop throughout the process of resolving it.

[![Point-to-point integration example between Zendesk and GitHub](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f9bbd2ce27f4d3c727a00e_FvefPU5XWLNLqFCjvyw52BUMSkvqCnv7PjJiZs3cz-sJ0p89B3y04IAX4IEwqqtIATYkNfjbrF0XRlj-Kff6P-wPa1XpJslrgGboOTfAK4z_SbmDK9vhffZBG9qOkapibAzBWzqh-z9d_Y8ST9uyWDI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f9bbd2ce27f4d3c727a00e_FvefPU5XWLNLqFCjvyw52BUMSkvqCnv7PjJiZs3cz-sJ0p89B3y04IAX4IEwqqtIATYkNfjbrF0XRlj-Kff6P-wPa1XpJslrgGboOTfAK4z_SbmDK9vhffZBG9qOkapibAzBWzqh-z9d_Y8ST9uyWDI.webp)

### **Employee pre-boarding**

As candidates sign their offer letters, your team will need to move quickly in pre-boarding them—whether that’s purchasing equipment, provisioning applications, acquiring swag, etc.—so that their first day goes smoothly.

To help your team pre-board each new hire effectively, you can integrate your ATS and HRIS solutions and build a flow where any time a candidate is marked as hired in the former, their profile gets created in the latter. From there, HR and IT can learn about the incoming employee, and based on the information that was synced over to the HRIS, they can go on to complete the right set of pre-boarding tasks on the new hire’s behalf.

### **Automated user provisioning**

To help any client manage users in your product with ease, you can build a point-to-point integrations with their HRIS solution and build a flow where any time an employee gets added, updated, or removed from the client’s HRIS, the corresponding change takes place in the client’s instance of your product.

[![Automated user provisioning visualizatiod](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65df88aec8533035cac8db68_wi03SvUHmFX_6Q7nhQUyOZhtEnHOn3ike8-OubOvB5NaDtM0PtSXUaaBWekt4nRiQCvcUMmhsFFCKrPbWTEJPyFMxSVmQudp4-fvf_5c8R8QGAY2en_kkWy-cwtgXLovdWhzNfHTqTUxFLjU1itaGTw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65df88aec8533035cac8db68_wi03SvUHmFX_6Q7nhQUyOZhtEnHOn3ike8-OubOvB5NaDtM0PtSXUaaBWekt4nRiQCvcUMmhsFFCKrPbWTEJPyFMxSVmQudp4-fvf_5c8R8QGAY2en_kkWy-cwtgXLovdWhzNfHTqTUxFLjU1itaGTw.webp)

_Related:_ [_How to automate user provisioning_](https://www.merge.dev/blog/automated-provisioning)

### **Intelligent employee intranet**

Say you offer an employee intranet product for companies of all sizes, and as part of your product, you provide AI-powered search functionality.

To help your search bar answer questions thoroughly and with complete accuracy for each client, you can build point-to-point integrations between your product and clients’ file storage solutions. From there, you can implement a flow where any time a client adds, updates, or removes certain files in their file storage solution, the associated actions take place in your product.

[![A visualization of adding clients' files to your product](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f9bbd2e82715983740d441_K1prhV90aIsqvVuYqWt1Wlww9qT86a8cazuWqkrEPfgULeeVfTUWXrMpJDoTbfrEnacOpUtA1u3GWDFhUPVPjjA-8rkLbX3BeuDoIcmeIhscWzsNlbac2pFacKp3XCQ2yfnUQj5jTGB6ssmj_eDRoyw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f9bbd2e82715983740d441_K1prhV90aIsqvVuYqWt1Wlww9qT86a8cazuWqkrEPfgULeeVfTUWXrMpJDoTbfrEnacOpUtA1u3GWDFhUPVPjjA-8rkLbX3BeuDoIcmeIhscWzsNlbac2pFacKp3XCQ2yfnUQj5jTGB6ssmj_eDRoyw.webp)

Your AI and machine learning models can read the data from these files and use their information to immediately answer commonly-asked questions, like “What’s the company’s PTO policy?”

## **Benefits of point-to-point integration**

Here are some reasons to implement point-to-point integrations:

### **Addresses your requirements (if certain conditions are met)**

If, say, you only have a few integrations you’d like to implement, they’re relatively shallow in scope, and you have engineering resources that can be allocated towards integration projects, then you might be able to build integrations successfully through the point-to-point approach.

### **Provides a somewhat simple path to management (if, again, certain conditions are met)**

If you only plan to build a few point-to-point integrations and you have the right engineering resources available to maintain them, then it may be feasible to manage the integrations in-house over time.

That said, most organizations need to implement more than a couple of integrations, especially in the case of [product integrations](https://www.merge.dev/blog/product-integrations); so, while this benefit may apply to your business today, it may not in the months or years ahead.

### **Allows you to prioritize specific integrations**

Certain integrations are naturally more important to your business and/or your clients. By keeping integrations in-house, you can decide which to focus on and then build deeper connections— than what might be available from 3rd-party providers—to those apps.

### **Enables developers to work on a project they're familiar with**

Assuming you have engineers who have experience in building and maintaining certain point-to-point integrations, they may feel comfortable in taking on a similar integration project(s) in the future.

### **Lets you avoid working with another 3rd-party**

Aside from costs, 3rd-parties can be time consuming for your team—from having to go through renewal conversations to holding recurring check-ins. In addition, they can introduce risks to your business, whether that’s related to security (e.g. allowing data to fall into the wrong hands) or performance (e.g. 3rd-party experiences downtime).

Finally, as we’ll cover shortly, many 3rd-party integration solutions are fairly complex. Your engineers will, as a result, have to dedicate ample time in familiarizing themselves with this type of platform before they even start using it.

## **Drawbacks of point-to-point integration**

Unfortunately, point-to-point integrations present several shortcomings.

### **Suboptimal use of engineering’s time**

Your engineers are uniquely positioned to tackle business-critical initiatives—from bugs that hurt the end-user experience to feature enhancements that can differentiate your product. And while integrations are important, forcing your engineers to focus on them at the expense of other product-specific areas can ultimately be detrimental to your business.

### **Difficult to scale**

Point-to-point integrations are difficult to scale because of the limited resources that can be allocated toward building and maintaining them. In addition, you likely have a seemingly never-ending list of integrations that need to get built—and engineering will find it difficult, if not impossible, to keep pace with this demand.

### **Over-reliance on select individuals**

You likely have a handful of engineers (maybe just an individual) who can build and manage your P2P integrations. If and when they leave, they'll likely take information on the integrations they were involved in with them.

This leaves your organization vulnerable when the integrations break or need to be improved; the remaining engineers will need to pick up the pieces and learn how the integrations work—let alone where they live.

### **Hard to manage**

When integrations break, it’s likely imperative that their issues get resolved immediately. Any delays risks a poor customer experience and/or critical disruptions to your business processes, which carry downstream effects (e.g. leads stop getting routed).

Using point-to-point integrations, it can be difficult to uncover issues on time, diagnose them with ease, and resolve them quickly—which can lead to the aforementioned consequences becoming reality.

### **Performance issues**

With P2P integrations, it’s often difficult to move data quickly, especially in large volumes. This makes it poorly-suited to handle time-sensitive data syncs, such as syncing newly-signed clients between your CRM and ERP system so you can invoice them on time.

_Related:_ [_The benefits of SaaS integration_](https://merge.dev/blog/saas-integration)

### **Introduces security and compliance vulnerabilities**

Depending on how your point-to-point integrations get built, they can present several vulnerabilities.

For instance, if data isn’t encrypted in transit, the data can easily get intercepted and manipulated by attackers. And, depending on how a point-to-point connection handles the data, it may not comply with the data protection and privacy regulations you’re expected to follow; this not only leaves you prone to significant fees and  reputational damage—it also affects your relationship with existing clients.

## **Best practices for building point-to-point integrations**

Let’s assume that you considered these pros and cons and ultimately decided to try implementing point-to-point integrations.

Here’s a few tips to help you build them successfully:

- **Assign multiple engineers to a given integration project.** Your engineers can leave at any point. To ensure they don’t take meaningful knowledge of the point-point-integrations they build and/or maintain with them, you can have multiple employees work on every integration

- **Build out and maintain documentation on each integration.** Even if your engineers stay at your company, they can easily forget crucial details on an integration. You can avoid relying on their memory by tasking them with documenting each point-to-point integration they build and/or maintain

- **Perform a wide range of API integration tests.** Building secure, performant, and reliable integrations requires conducting a range of different tests before pushing the integration to production, such as scale testing (to see how the integration performs when dealing with a significant volume of data), load testing (to see how effective the integration is in processing a high number of simultaneous requests), and so on

- **Build robust monitoring and alerting processes.** Every integration will, inevitably, break. To ensure that the impact of any issue isn’t significant, you can adopt a monitoring tool like Datadog and connect it to your business communications solution (e.g., Slack) and/or email so that every issue can get flagged to the appropriate stakeholders directly

## **Alternatives to point-to-point integration**

If you decide to [outsource your integrations](https://www.merge.dev/blog/outsourcing-integration) you’ll likely consider a specific set of categories of tools. These tools will vary, depending on whether you plan to implement integrations for internal systems or between customers’ applications and your product.

### **Integration tools for internal applications**

Here are the two most popular options for integrating your internal tools:

#### **Integration platform as a service (iPaaS)**

An iPaaS is a cloud-based integration solution that lets you implement integrations via APIs and deploy data flows that work across them.

[![A visual illustration of iPaaS](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2c045eef89e999b2e_VaeSMciUKkeyr6XChP7QycUeuZimzh_JfHhEhQYkc5AnC_9bwUkczLdVMr7ydX15xZM-UZeR-QhL8GjJLmFjLWcp9iiBjCDsiL2ceOGzK9QSNxN-ymqBHO5xS48x7yRkJN5Acx3wyT6wMXfQXJUpcBE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2c045eef89e999b2e_VaeSMciUKkeyr6XChP7QycUeuZimzh_JfHhEhQYkc5AnC_9bwUkczLdVMr7ydX15xZM-UZeR-QhL8GjJLmFjLWcp9iiBjCDsiL2ceOGzK9QSNxN-ymqBHO5xS48x7yRkJN5Acx3wyT6wMXfQXJUpcBE.webp)

Their integrations are considered reliable and high-performing (since they use APIs). That said, the platform itself often requires technical expertise to use—which likely forces you to rely on engineers who can manage it. This, coupled with the fact that you’re only able to build one integration at a time with an iPaaS, makes it difficult to scale your integrations quickly.

#### **Robotic process automation (RPA) software**

RPA software uses scripts (also referred to as “bots”) to mimic human tasks at the human level—such as copying and pasting data between applications.

This tool works great when the applications you’re looking to integrate don’t offer APIs, or don’t offer the API endpoints you need. However, the bots are often relatively brittle—a simple UI change can be all it takes to break a bot. In addition, the process of developing, deploying, and managing bots can also require technical expertise, which can make it difficult to scale your integrations and automations.

### **Integration tools for your product**

Here are your main options for outsourcing product integrations:

#### **Embedded iPaaS**

An [embedded iPaaS](https://merge.dev/blog/embedded-ipaas) is simply an iPaaS that’s embedded into your product.

You can deploy it in various ways. For instance, you can allow clients to use it within your application; you can use it internally and allow clients to access the integrations your team ends up building; or you can adopt a combination of both approaches.

It offers similar benefits and drawbacks to an iPaaS. Namely, its integrations are reliable, but the process of building them quickly and at scale can be challenging.

_Related:_ [_The advantages and drawbacks of an embedded iPaaS_](https://www.merge.dev/blog/embedded-ipaas-benefits)

#### **Unified API**

A unified API—or [universal API](https://merge.dev/blog/universal-api)—solution lets you offer multiple integrations with your product in a specific category (e.g. CRM) by simply building to a single, aggregated API.

[![A visual illustration of a unified API solution](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2876336ff0190f66a_-bP6-SNcu63bECvnqI1rnm-ENcZlsKKlsmJIw3duX-_y0FqtcKGABNozsBhmdpSrgJ1Ybig5M4r3UGVIHHruw8WzJJbjfvpgJuC6SmBxU4Dj0NmzRL3mIS4XBX9vLGEjd3tu_5NuH9fkF7CSL3_p4cs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64f1f3f2876336ff0190f66a_-bP6-SNcu63bECvnqI1rnm-ENcZlsKKlsmJIw3duX-_y0FqtcKGABNozsBhmdpSrgJ1Ybig5M4r3UGVIHHruw8WzJJbjfvpgJuC6SmBxU4Dj0NmzRL3mIS4XBX9vLGEjd3tu_5NuH9fkF7CSL3_p4cs.webp)

‍ [Unified API solutions](https://merge.dev/blog/what-is-a-unified-api) allow you to easily integrate at scale, which addresses the key drawbacks of embedded iPaaS solutions and point-to-point integrations. However, not all unified API solutions are created equal.

Merge, the leading Unified API solution, stands out in several ways.

The platform offers hundreds of integrations across key software categories, from CRM to marketing automation to file storage to ticketing; it allows you to manage your clients’ integrations with ease through robust [Integrations Management](https://merge.dev/features/integrations-management) capabilities; and it lets your clients get all of the data they need via [our comprehensive common models](https://merge.dev/features/common-models) and through features that can access objects and fields outside of these models, like [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/).

_Learn more about Merge by scheduling a demo with one of our integration experts._

## **Point-to-point integration FAQ**

In case there’s still lingering confusion on point-to-point integrations, we’ve addressed several more commonly-asked questions below.

### **What is the difference between point-to-point integration and APIs?**

Point-to-point integration is a specific approach to implementing integrations and may or may not involve APIs. An API, on the other hand, is essentially code that allow applications to communicate with one another.

### **How is point-to-point integration different from an enterprise service bus (ESB)?**

The two offer fundamentally different approaches to integration; using an ESB architecture, organizations can connect applications via a bus-like infrastructure, otherwise known as a “bus”. In addition, organizations that adopt the ESB approach typically leverage a [3rd-party integration platform](https://www.merge.dev/blog/3rd-party-integration) (e.g. Mulesoft).

### **What are the differences between point-to-point integration and an iPaaS?**

An iPaaS is a 3rd-party solution while point-to-point integration is simply a way to build integrations in-house. That said, they overlap in that they approach integration builds on an application-to-application level (as opposed to unified APIs, which offer a one-to-many approach to integration).

### **What’s the relationship between point-to-point integration and middleware?**

The two represent fundamentally different approaches to implementing integrations. Point-to-point integration doesn’t involve the use of middleware—which is a 3rd-party tool that can help you implement and maintain integrations.

### **How does point-to-point integration compare to hub-and-spoke integration?**

Point-to-point integration doesn’t involve a central hub that facilitates communication between applications (which is essentially what hub-and-spoke integration entails); instead, point-to-point integration allows applications to communicate directly with one another.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ad1cae4e-e934-42ee-9b8d-84a59adf47e1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0cac44e9-54f2-4f37-8b93-8750034c5260&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpoint-to-point-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ad1cae4e-e934-42ee-9b8d-84a59adf47e1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0cac44e9-54f2-4f37-8b93-8750034c5260&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpoint-to-point-integration&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=33ce2510-7b99-4733-ab9f-1de9f273a1e3&bo=2&sid=d9f6ea703e8d11f090301f0d55b383e9&vid=d9f70fd03e8d11f0aa18e500b0b4babc&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Point-to-point%20integration%3A%20pros,%20cons,%20and%20alternatives&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fpoint-to-point-integration&r=&lt=760&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=731892)