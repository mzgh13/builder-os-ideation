---
url: "https://www.merge.dev/blog/guide-to-it-service-desk-apis"
title: "Guide to IT Service Desk APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-it-service-desk-apis#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-it-service-desk-apis#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-it-service-desk-apis#)

Table of contents

[Top IT Service Desk APIs](https://www.merge.dev/blog/guide-to-it-service-desk-apis#top-it-service-desk-apis)

[IT Service Desk API Data Schemas](https://www.merge.dev/blog/guide-to-it-service-desk-apis#it-service-desk-api-data-schemas)

[Top IT Service Desk API Use Cases](https://www.merge.dev/blog/guide-to-it-service-desk-apis#top-it-service-desk-api-use-cases)

[Getting Started with IT Service Desk APIs](https://www.merge.dev/blog/guide-to-it-service-desk-apis#getting-started-with-it-service-desk-apis)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-it-service-desk-apis)

##### Just for you

No items found.

# Guide to IT Service Desk APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ceec1bfb5f5db305075_Guide_to_IT_Service_Desk_APIs.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387b860cf29c5270b5b_62eff92b7e27e6371ea6b06a_Nick.webp)

Nick Kephart

VP of Marketing

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 20+ service desk and ticketing integrations with one_ [_ticketing API_](https://merge.dev/categories/ticketing-api).

‍

Service desks are an important software system of record for IT teams, helping them keep track of requests, respond to incidents, and manage system changes. As a core part of IT workflows, service desk APIs for products like Jira, ServiceNow, and Freshservice are commonly used to build integrations with internal systems and between SaaS products.

Read on for a guide on everything you need to know about IT Service Desk APIs:

- Top APIs - Which IT service desks are most popular
- Key concepts - How service desks work
- Data schemas - How service desk APIs organize IT data
- Use cases - Common ways service desk data is used in product integrations
- Getting started - Approaching service desk integrations to your product

_Related:_ [_What is a ticket API?_](https://merge.dev/blog/ticket-api)

## Top IT Service Desk APIs

Service desks are commonly found in [mid to large-size IT teams](https://www.electric.ai/blog/guide-to-it-department) that need to track internal user requests. Common tools focused on the broad market from SMBs to enterprises include Jira, which has a Service Management version of their popular project tracker, Ivanti, and Freshservice. Enterprise-focused tools are more commonly found in Global 2000 companies, with the leading service desks in this segment being ServiceNow and BMC Helix.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52e3732dc990c63738df4_Table%20-%20IT%20Service%20Desk%20Tools%20by%20Customers.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52e3732dc990c63738df4_Table%20-%20IT%20Service%20Desk%20Tools%20by%20Customers.webp)

IT service desks are commonly used in conjunction with other ticket tracking software, such as project management tools. For more on these APIs and integrations, check out the [Guide to Project Management APIs](https://www.merge.dev/blog/guide-to-project-management-apis) (Asana, ClickUp, Monday, and more) and the [Guide to Software Project Management APIs](https://www.merge.dev/blog/guide-to-software-project-management-apis) (Github, Gitlab, Jira, and more).

## IT Service Desk API Data Schemas

Service desks are a system of record for incidents (aka [**Tickets**](https://merge.dev/docs/ticketing/tickets/)) that represent a task or issue to resolve. Tickets come in several types relevant to service desks, including 'incidents', 'problems', and 'changes'. Tickets also have statuses that they progress through as they are resolved, attachments, and tags.

Tickets may have [**Comments**](https://merge.dev/docs/ticketing/comments/) associated with them as the contact and assignees (or multiple members of the IT team) communicate back and forth. Comments also contain a body of text or HTML.

Each ticket is related to a contact that generated the support request and has assignees that are the IT team members responsible to resolve the issue. Internal users being helped are represented as [**Contacts**](https://merge.dev/docs/ticketing/contacts/), which include their name, email, and phone number. The Contacts may belong to [**Accounts**](https://merge.dev/docs/ticketing/accounts/) that represent departments or parts of an organization.

IT team members are [**Users**](https://merge.dev/docs/ticketing/users/) with names, emails, and roles. Users belong to [**Teams**](https://merge.dev/docs/ticketing/teams/), which map to the IT and/or R&D team org structure.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52e454cf19c0cedc0279b_Table%20-%20IT%20Service%20Desk%20Tools%20by%20Data%20Schema.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52e454cf19c0cedc0279b_Table%20-%20IT%20Service%20Desk%20Tools%20by%20Data%20Schema.webp)

## Top IT Service Desk API Use Cases

### **Source code management and CI/CD**

IT service desk systems often act as a system of record for major service changes, including code changes. Integrations with SCM (source code management) and continuous integration and deployment (CI/CD) systems makes it seamless for IT teams to keep a record of changes and approve or deny them if necessary.

Examples: Github, Gitlab, Bitbucket, Jenkins, SonarQube, Snyk, Jfrog, Harness, CircleCI

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f427b4b1268afb55302_azure-devops-servicenow-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f427b4b1268afb55302_azure-devops-servicenow-integration.webp)

ServiceNow integrates with Azure DevOps to trigger a change request when code is being deployed and block deployment until the change request is approved.

### **Asset, device, and endpoint management**

IT ticketing systems commonly integrate with security tooling to create tickets when vulnerabilities are detected, sync data about the relevant device or service to the ticket, and update lists of assets.

Examples: Microsoft SCCM, Jamf, Cloudstrike, Qualys, Tenable, Kandji, Sophos

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52ee7f793d8d330a56706_crowdstrike-servicenow-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52ee7f793d8d330a56706_crowdstrike-servicenow-integration.webp)

Crowdstrike integrates with ServiceNow to trigger new tickets (incidents) when a security vulnerability is detected.

### **Compliance management**

IT service desk systems have tight integrations with compliance management systems, including the ability to create tickets to track compliance tasks, updating tickets on the risk or vulnerability, and linking resolved tickets for evidence of compliance.

Examples: Vanta, Drata, Tugboat Logic

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52ef43b0ed65c28d98ebb_tugboat-logic-jira-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52ef43b0ed65c28d98ebb_tugboat-logic-jira-integration.webp)

Jira integrates with Tugboat Logic to create tickets whenever security risks, controls, or vulnerabilities require work and then links the completed ticket for evidence.

### **Monitoring and logging**

Monitoring systems are a first line of detection for IT issues. Integrating these systems with IT service desks allows for generating tickets based on monitoring alerts and updating or closing those tickets as alerts are resolved.

Examples: Datadog, Logic Monitor, NewRelic, AppDynamics, Dynatrace, Azure, AWS, Splunk, SolarWinds

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f2b395f20e179229101_sysaid-solarwinds-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f2b395f20e179229101_sysaid-solarwinds-integration.webp)

SysAid integrates with Solarwinds to create and update tickets based on application, infrastructure, or network alerts.

### **Incident management**

Incident management systems are a natural integration point for service desk software. These integrations often include the ability to create new tickets from an incident, sync status updates and comments, and sync on-call schedules to facilitate quick response and clear record keeping.

Examples: PagerDuty, xMatters, Opsgenie, Statuspage

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f16395f20253d227e06_xmatters-servicenow-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e52f16395f20253d227e06_xmatters-servicenow-integration.webp)

xMatters integrates with ServiceNow to update incident comments and status.

## Getting Started with IT Service Desk APIs

In addition to understanding IT service desk API schemas, you’ll also want to keep in mind a few additional topics as you start building:

- API format - REST, SOAP, etc.
- Authentication
- Pagination
- Rate Limits
- Test Accounts

If you don’t want to manage differences between each help desk API, you can use a unified API. Merge unifies multiple IT service desk APIs into one, making it easy to integrate your app with every vendor that your customers use. The [Unified Ticketing API](https://www.merge.dev/categories/ticketing-api) is REST-based, with common authentication, pagination, and rate limiting. It also includes automated logging and issue detection to make integration maintenance painless.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=725b133d-bb17-4ed4-9b8f-927fb1c1919c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=649a77f1-5e49-4362-811f-bda278a552ff&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-it-service-desk-apis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=725b133d-bb17-4ed4-9b8f-927fb1c1919c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=649a77f1-5e49-4362-811f-bda278a552ff&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-it-service-desk-apis&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0faccc70-570d-46f0-a752-33bbdc9d26fd&bo=2&sid=11d8b2c03e8d11f0a90ff906b5f43f0d&vid=11d8ea803e8d11f0b54ce3932487ca02&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20IT%20Service%20Desk%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-it-service-desk-apis&r=&lt=487&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=623256)