---
url: "https://www.merge.dev/blog/guide-to-help-desk-apis"
title: "Guide to Customer Help Desk APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-help-desk-apis#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-help-desk-apis#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-help-desk-apis#)

Table of contents

[Top Help Desk APIs](https://www.merge.dev/blog/guide-to-help-desk-apis#top-help-desk-apis)

[Key Help Desk Concepts](https://www.merge.dev/blog/guide-to-help-desk-apis#key-help-desk-concepts)

[Help Desk API Data Schemas](https://www.merge.dev/blog/guide-to-help-desk-apis#help-desk-api-data-schemas)

[Top Help Desk API by SaaS Vertical](https://www.merge.dev/blog/guide-to-help-desk-apis#top-help-desk-api-by-saas-vertical)

[Getting Started with Customer Help Desk APIs](https://www.merge.dev/blog/guide-to-help-desk-apis#getting-started-with-customer-help-desk-apis)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-help-desk-apis)

##### Just for you

No items found.

# Guide to Customer Help Desk APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb038aa8a036846bad0_Guide_to_Customer_Help_Desk_APIs.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387b860cf29c5270b5b_62eff92b7e27e6371ea6b06a_Nick.webp)

Nick Kephart

VP of Marketing

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 10+ help desk integrations with one_ [_ticketing API_](https://www.merge.dev/categories-old/ticketing-api).

‍

Help desk software is the primary tool that customer support teams use day-in and day-out. So it’s not surprising that held desk software is commonly integrated with other products and that most have fully-featured APIs to support these integrations. If you’re building help desk integrations, accessing tickets via API, or working with help desk APIs, this article is your guide to:

- Top APIs - Which help desks are most popular
- Key concepts - How help desks work and how they differ
- Data schemas - How help desk APIs organize customer data
- Use cases - Common ways help desk data is used in product integrations
- Getting started - Approaching help desk integrations to your product

Note: We’ll focus on customer-facing help desk APIs here. If you’re looking for other ticketing APIs such as internal-facing IT service desk APIs or software project management APIs, check out those articles as well.

_Related:_ [_5 ticketing API examples_](https://merge.dev/blog/ticket-api)

## Top Help Desk APIs

Customer help desk software is a booming business, with hundreds of vendors. There are three major segments of the help desk market.

The largest, enterprise-focused help desks are Salesforce Service Cloud, Microsoft Dynamics 365, and Oracle Service Cloud, each part of broader CRM platforms (see our [Guide to CRM APIs](https://www.merge.dev/blog/ultimate-guide-to-crm-apis)).

SMB-focused vendors such as Zendesk, Freshdesk, Hubspot, and Zoho act as standalone help desks with CRM offerings as part of their platforms as well.

SMB-focused vendors that emphasize their bundled chat and conversation-based functionality include LiveChat, Intercom, Help Scout, Front, Kayako, Gorgias, Gladly, and Live Agent.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d040e252fda05cde3f8ecf_largest-customer-help-desks-by-number-of-customers.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d040e252fda05cde3f8ecf_largest-customer-help-desks-by-number-of-customers.webp)

Source: Company websites

_Related:_ [_Examples of lead APIs_](https://merge.dev/blog/lead-api)

## Key Help Desk Concepts

Although help desk APIs have similar objects and semantics, there are a couple of concepts that vary across APIs and are worthwhile to pay special attention to.

### **Agents and contacts**

There are two relevant sets of individuals associated with any ticket. Support team members responsible for handling a ticket are typically identified by an Agent, Admin, or User object. Customers requesting support are typically identified by a Contact object. Some systems, however, use one object for both concepts. For example, the Zendesk API has a User object with an Agent ‘role’ for support team members and an End User type for customers.

### **Ticket hierarchies**

Some help desks, such as Salesforce Service Cloud, offer the ability to have a hierarchy of tickets (aka Cases) to better organize complex or long-running support incidents. In these situations a ticket will have a parent reference.

## Help Desk API Data Schemas

At the center of customer help desk data is the concept of a [**Ticket**](https://merge.dev/docs/ticketing/tickets/) (aka conversation or case) that represents a support request or interaction. Each ticket is related to a contact that generated the support request and has assignees that are the support agents responsible to resolve the issue. Tickets also have statuses that they progress through as they are resolved. Tickets also include fields relating to their tags and types.

Tickets may have [**Comments**](https://merge.dev/docs/ticketing/comments/) associated with them as the contact and assignees (or multiple members of the support team) communicate back and forth. Comments also contain a body of text or HTML. Tickets may also have Attachments as a separate object.

Customers being helped are represented as [**Contacts**](https://merge.dev/docs/ticketing/contacts/), which include their name, email, and phone number. The Contacts belong to [**Accounts**](https://merge.dev/docs/ticketing/accounts/) (aka companies) that are useful for organizing B2B support relationships.

Agents within the support organization are [**Users**](https://merge.dev/docs/ticketing/users/) with names, emails, and roles. Users belong to [**Teams**](https://merge.dev/docs/ticketing/teams/), which map to the support team org structure.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d042f88c95463740a1b846_Table%20-%20Help%20Desk%20Systems%20by%20Data%20Schema.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d042f88c95463740a1b846_Table%20-%20Help%20Desk%20Systems%20by%20Data%20Schema.webp)

_Related:_ [_How companies support their APIs_](https://www.merge.dev/blog/api-integration-support)

## Top Help Desk API by SaaS Vertical

### **Customer experience**

Customer experience (CX) management systems include functionality for surveys, feedback forms, product requests, and voice of the customer. CX systems integrate with help desks to create new tickets or cases if a customer has negative feedback and to enrich tickets with contextual customer feedback and sentiment.

Examples: Uservoice, Productboard, SurveyMonkey, Medallia, Qualtrics

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3cedc3e0c6074b256ba3_qualtrics-hubspot-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3cedc3e0c6074b256ba3_qualtrics-hubspot-integration.webp)

_Qualtrics integrates with Hubspot to update ticket and CRM records, including triggering a new ticket when feedback or a survey is submitted._

### **Customer success management**

Customer success management systems provide a broad view of both customer health and support team efficiency. Customer success platforms integrate with help desks to display tickets in the context of customer health scores, track overall customer analytics, and to add feedback and ratings on customer success interactions.

Examples: Klaus, Gainsight, ChurnZero, Totango, Catalyst, ClientSuccess, Vitally

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3d906c0b12f06f6e7f6b_totango-zendesk-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3d906c0b12f06f6e7f6b_totango-zendesk-integration.webp)

_Totango integrates with the Zendesk API to read tickets and display key support data for a better view of customer success interactions by account._

### **Communication and chatbots**

Tracking customer communication is a core functionality of every help desk system. Help desks integrate with voice, video, and chat tools to kick off new tickets, update ticket status, append transcripts, queue support requests, escalate and route support requests, and exchange files.

Examples: Ada, Olark, Aircall, Talkdesk, Dialpad, Genesys, Zoom

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3c4a2df1a12f0b009986_ada-zendesk-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3c4a2df1a12f0b009986_ada-zendesk-integration.webp)

_Ada integrates with Zendesk live chat to manage queuing, escalation, agent routing, and transcription._

_Related:_ [_Examples of invoicing APIs_](https://www.merge.dev/blog/invoicing-api)

### **Time tracking and billing**

Help desk agents are often required to track their time on tickets to measure overall efficiency, bill clients for support, or get paid as a contractor. Time tracking software syncs with help desk systems to record the time spent per ticket and match it back to the client, project, and agent involved.

Examples: Harvest, Quickbooks Time, Replicon, Toggl, Evenhour, Clockify

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3d3a66671f41a5849092_quickbooks-freshdesk-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3d3a66671f41a5849092_quickbooks-freshdesk-integration.webp)

_Quickbooks integrates with the Freshdesk API to track time spent per ticket and to enrich ticket details with contact info from QuickBooks._

### **Incident management**

Some help desk tickets require immediate attention from engineering or operations teams via an incident management system. Help desk systems integrate with incident management tools to create tickets from an ongoing incident, create an incident from a new ticket, and to link the two for ongoing updates.

Examples: PagerDuty, xMatters, Opsgenie, Statuspage

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3c8da5bd924395fa8a50_pagerduty-zendesk-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3c8da5bd924395fa8a50_pagerduty-zendesk-integration.webp)

_PagerDuty integrates with the Zendesk API to link incidents to tickets and display incident details._

### **CRM**

Customer relationship management (CRM) software keeps a comprehensive record of a customer account, including support cases and tickets. CRM and help desk systems are commonly integrated to trigger new issues in the help desk from customer interactions, to provide rich customer context within the help desk, and to create new tasks in the CRM based on ticket status.

Examples: Salesforce, Hubspot, Zoho, Microsoft Dynamics 365

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3dbd121eef0d0395bbce_intercom-salesforce-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3dbd121eef0d0395bbce_intercom-salesforce-integration.webp)

_Intercom integrates with Salesforce to sync help desk tickets with CRM tasks, accounts, and contact information._

### **Knowledge management**

Customer support agents need relevant information at their fingertips, often stored within knowledge management systems. These systems integrate with help desks to surface relevant knowledge base articles, playbooks, and common answers in the context of a given ticket.

Examples: Guru, Notion, Confluence

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3cb9981414351f8a6a1f_guru-customer-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63cf3cb9981414351f8a6a1f_guru-customer-integration.webp)

_Guru integrates with Kustomer to provide knowledge base suggestions that are optimized for language in tickets or customer records._

## Getting Started with Customer Help Desk APIs

In addition to understanding customer help desk API schemas, you’ll also want to keep in mind a few additional topics as you start building:

- API format - REST, SOAP, etc.
- Authentication
- Pagination
- Rate Limits
- Test Accounts

If you don’t want to manage differences between each help desk API, you can use a unified API. Merge unifies multiple customer help desk APIs into one, making it easy to integrate your app with every vendor that your customers use. The [Unified Ticketing API](https://www.merge.dev/categories-old/ticketing-api) is REST-based, with common authentication, pagination, and rate limiting. It also includes automated logging and issue detection to make integration maintenance painless.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Nick Kephart

VP of Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=34e34b9f-e5f7-4673-8a00-e12c6aafb713&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0b21e709-a31f-4dce-a00a-7e5f606e6e30&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-help-desk-apis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=34e34b9f-e5f7-4673-8a00-e12c6aafb713&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0b21e709-a31f-4dce-a00a-7e5f606e6e30&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-help-desk-apis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f88fa9f3-27e9-4b47-aebf-99eb05da2169&bo=2&sid=3c49f0903e8d11f09c198da4e3fd39c8&vid=3c4a9d203e8d11f0821569c503a8312c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20Customer%20Help%20Desk%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-help-desk-apis&r=&lt=553&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=744409)