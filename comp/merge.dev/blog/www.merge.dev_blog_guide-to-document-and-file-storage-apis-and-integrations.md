---
url: "https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations"
title: "Guide to document and file storage APIs and integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations#)

Table of contents

[Top File Storage APIs](https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations#top-file-storage-apis)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-document-and-file-storage-apis-and-integrations)

##### Just for you

No items found.

# Guide to document and file storage APIs and integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387b860cf29c5270b5b_62eff92b7e27e6371ea6b06a_Nick.webp)

Nick Kephart

VP of Marketing

@Merge

File storage integrations—browsing, uploading, and downloading files—are one of the most commonly integrated products. Products like Google Drive, OneDrive, and Dropbox have robust ecosystems of hundreds of apps that they integrate with. File storage integrations with collaboration, project management, design, security, and other software enrich user workflows, creating strong user adoption and retention.

Read on in this Guide to File Storage APIs to learn about:

- **Top File Storage APIs** \- Which cloud content systems are most popular
- **Key Concepts** \- How file storage systems work
- **Data Schemas** \- How file and documentation data is organized
- **Use Cases** \- Common ways file data is used in product integrations **‍**
- **How to Get Started** \- Approaching file storage API integrations within your own product

## Top File Storage APIs

The file storage market is dominated by a handful of large cloud office suites—Google and Microsoft—as well as file storage-specific companies—Dropbox, Box, Zoho, and Egnyte. Each has widely varying numbers of users versus customers. Google, Dropbox, and Microsoft serve both the business and consumer markets, while Box, Zoho, and Egnyte primarily serve the business market.

| File Storage Software | Number of Customers (2023) | Number of Users (2023) |
| --- | --- | --- |
| Google Drive (Workspace) | 9,000,000 | [3,000,000,000](https://workspace.google.com/blog/product-announcements/workflows-across-workspace) |
| Dropbox | 17,000,000 | 700,000,000 |
| Sharepoint and OneDrive (Office 365) |  | [360,000,000](https://office365itpros.com/2023/01/26/teams-user-numbers-280million/) |
| Box | [100,000](https://s21.q4cdn.com/328470014/files/doc_financials/2024/ar/ny20006774x3_ars.pdf) | 14,000,000 |
| Zoho WorkDrive | [800,000](https://www.zoho.com/workdrive/) | [7,500,000](https://www.zoho.com/blog/workdrive/customer-testimonial.html) |
| Egnyte | 17,000 |  |

_Related:_ [_A guide to file storage APIs_](https://www.merge.dev/blog/file-storage-api)

### Key File Storage API Concepts for Developers

#### Permissions

File storage permissions are implemented in widely varying ways across providers. Permissions may vary by user/type, role, and/or the specific file/folder depending on the provider. For example, Box represents sharing permissions as “collaborations” and shared links as “shared\_links”. Google Drive represents both under their “permissions” sub-model.

#### File Types and Folders

Some providers represent files and folders as discreet concepts, whereas others make folders a file type. Google Drive represents folders as a specific [file type](https://developers.google.com/drive/api/guides/mime-types) and OneDrive / SharePoint have a similar concept where folders and files are represented as DriveItems.

#### File Selectors

Google, Dropbox, and Box all offer UI components that can be embedded to select files. However, each is built differently with unique styling, so you may want to consider a solution like Merge for a unified file picker experience.

#### Webhooks

With typical webhooks, a webhook payload event corresponds to an individual object. With file storage providers such as Google Drive, OneDrive, and SharePoint, the webhook payload only indicates that “something has changed” and then requires a separate API request to process the changes.

#### Getting OAuth Approval

Many file storage providers have very stringent requirements for getting app approval. If you don't receive approval your users may see an "unverified" label or have a maximum user cap. Ensure you investigate these requirements ahead of time or choose a Unified API instead.

### File Storage API Data Schemas

[Users](https://docs.merge.dev/filestorage/users/) are individual file storage accounts that have a permission for a given Drive, Folder, or File. [Groups](https://docs.merge.dev/filestorage/groups/) are collections of users or company domains that inherit similar permissions.

[Drives](https://docs.merge.dev/filestorage/drives/) are the top level container where all of a user's or organizations folders and files are stored. Some file storage systems use the concept of a Folder rather than a Drive. [Folders](https://docs.merge.dev/filestorage/folders/) are a collection of Folders (which can be nested) and Files. [Files](https://docs.merge.dev/filestorage/files/) can be in a variety of formats (documents, spreadsheets, slides, video, music, images, etc.) and are placed within a Folder or Drive.

Folders and Files contain metadata about when they were created, updated, and deleted, which can be useful to filter appropriate files and kick off workflows. Folders and Files have a set of permissions mapped back to Users and/or Groups.

|  | Groups | Users | Drives | Folders | Files |
| --- | --- | --- | --- | --- | --- |
| [Box](https://developer.box.com/reference/) | /groups | /users |  | /folders | /files |
| [Dropbox](https://www.dropbox.com/developers/documentation/http/overview) | /groups | /members |  | /list\_folders | /files |
| [Google Drive](https://developers.google.com/drive/api/reference/rest/v3) |  |  | /drives |  | /files |
| [OneDrive and SharePoint](https://learn.microsoft.com/en-us/graph/api/resources/onedrive?view=graph-rest-1.0) | /groups | /users | /drives | /items | /items |

‍

### Top File Storage API Use Cases

File storage systems are one of the most commonly integrated products into other SaaS apps. Common use cases include browsing for documents, uploading contracts, sharing files with collaborators, and downloading documents for compliance purposes.

#### Sync All Company Docs so Employees Can Search For Them

Knowledge management and project management apps are commonly used to access documents and link them to projects or workflows. These apps frequently include integrations with file storage to make document discovery and sharing easy.

‍ **Examples**: Asana, Assembly, ClickUp, Guru, Monday, Notion, Wrike

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baef8de6d99621faf51dc1_Dropbox.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baef8de6d99621faf51dc1_Dropbox.webp)

_Asana integrates with Dropbox to select files from Dropbox and attach them to tasks._

#### ‍ **Upload and Organize Documents and Contracts**

E-signature apps and industry vertical apps (e.g. construction, biotech, and more) integrate with document storage to share documents with collaborators and upload draft and final versions for record keeping.

‍ **Examples**: Adobe Sign, Benchling, Docusign, Fieldwire, PandaDoc, Raken

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baefcd3e197c22d136645e_DocuSign.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baefcd3e197c22d136645e_DocuSign.webp)

_DocuSign integrates with Google Workspace to quickly access agreements, upload to collect signatures, and then save them to a Google Drive folder._

#### Search and Select Files From Your Product to Share

Design, creative, and collaboration tools frequently need to allow users to share documents for commenting, review, and project handoffs.

‍ **Examples**: AutoCAD, Canva, Gmail, [LucidChart](https://www.lucidchart.com/pages/), Miro, Outlook, Slack, Teams, Zoom

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baeff8942b87704a1ed24e_AutoCAD.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baeff8942b87704a1ed24e_AutoCAD.webp)

_AutoCAD web app integrates with multiple storage providers to allow for listing, creating, and updating of documents._

#### Download Relevant Files for Compliance Controls

Many business processes related to security and compliance require documentation to be stored for record keeping. IT and security tools commonly integrate with file storage systems to download and upload documents.

**Examples**: Drata, Okta, ServiceNow, Snyk, SumoLogic, Vanta

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baf0217db2a42ecad0e9a6_ServiceNow.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64baf0217db2a42ecad0e9a6_ServiceNow.webp)

_ServiceNow integrates with Box to create workflows for IT projects and incidents, including workflows based on updates to a document._

### Getting Started with File Storage APIs

Once you’re ready to kick the tires integrating with a cloud storage collaboration provider, you’ll want to keep in mind a few additional topics:

- **API Format** \- Which standards do the underlying APIs support (REST, SOAP, etc.)
- **Authentication** \- Which auth methods each API uses (e.g. OAuth, basic auth, etc.)
- **Pagination and Rate Limits** \- How large responses are accessed in each API
- **Test Accounts** \- How to access sandboxes for each API

We’ve built Merge to help developers easily integrate with multiple file storage systems. Our [File Storage Unified API](https://merge.dev/categories/file-storage-api) is all REST-based, with one type of authentication, pagination, rate limiting, and automated issue detection to make development simple.

For all of this info in one comprehensive place, plus more in-depth examples of file storage integrations, download the Guide to File Storage APIs and Integrations or [sign up](https://app.merge.dev/signup) to get started.

{{blog-cta-100+}}

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7d107e09-a4bd-4aee-80cc-fb33e59f48e0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d6d52265-c781-4949-8cdc-d41e4789cd14&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-document-and-file-storage-apis-and-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7d107e09-a4bd-4aee-80cc-fb33e59f48e0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d6d52265-c781-4949-8cdc-d41e4789cd14&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-document-and-file-storage-apis-and-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=d9ef9b5e-936c-45b0-8aea-3b24531f2e15&bo=2&sid=d17cf1b03e8c11f0b45585fb7dc1e2f8&vid=d17eb8703e8c11f082e81340342b847f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20document%20and%20file%20storage%20APIs%20and%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-document-and-file-storage-apis-and-integrations&r=&lt=548&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=688822)