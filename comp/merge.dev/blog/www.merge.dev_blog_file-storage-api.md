---
url: "https://www.merge.dev/blog/file-storage-api"
title: "7 file storage APIs you should integrate with"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/file-storage-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/file-storage-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/file-storage-api#)

Table of contents

[Microsoft OneDrive](https://www.merge.dev/blog/file-storage-api#microsoft-onedrive)

[Microsoft SharePoint](https://www.merge.dev/blog/file-storage-api#microsoft-sharepoint)

[Google Drive](https://www.merge.dev/blog/file-storage-api#google-drive)

[Dropbox](https://www.merge.dev/blog/file-storage-api#dropbox)

[Box](https://www.merge.dev/blog/file-storage-api#box)

[Zoho WorkDrive](https://www.merge.dev/blog/file-storage-api#zoho-workdrive)

[Egnyte](https://www.merge.dev/blog/file-storage-api#egnyte)

[Final thoughts](https://www.merge.dev/blog/file-storage-api#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffile-storage-api)

##### Just for you

No items found.

# 7 file storage APIs you should integrate with

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26ba0966dc16ec12d14a_Irene%20Hu%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f082f3162f9f1c94ba54a_irene-hu_min.webp)

Irene Hu

Marketing

@Merge

The majority of your clients likely use a file storage solution to share, collaborate on, and store key documents and information.

The value these solutions—and your product—provide only increases when they’re integrated with your product.

Once integrated, clients can access all the documents they need without leaving your application; they can accessthe most up-to-date documents and files in your product; and they can ensure that users only access the documents that meet their scope of permissions in your product.

You can even use the information in clients’ files to train AI models that support your product ( [which is exactly what Assembly did](https://www.merge.dev/case-studies/how-merge-unblocked-10x-in-sales-for-assembly))

Given all these benefits, the question isn’t whether to implement file storage integrations—it’s how.

We’ll provide some guidance by walking you through 7 popular file storage platforms’ APIs. We’ll then introduce you to a solution that can help you build file storage integrations via a [_single_ universal API](https://www.merge.dev/blog/universal-api).

## **Microsoft OneDrive**

Microsoft OneDrive is an extremely popular file storage platform.

It’s used in [over 500 million devices and by more than 85% of Fortune 500 companies](https://learn.microsoft.com/en-us/graph/onedrive-concept-overview).

OneDrive’s API is accessed through Microsoft Graph which is Microsoft’s single API.

Microsoft structures their API with “Drive” and “DriveItem”. “Drive” represents a container of files (like a document library or a user's OneDrive), while “DriveItem” represents an item within a drive (e.g., a document, photo, video, or folder). “DriveItem” can be accessed using their id by using /items/{item-id} syntax. Microsoft Graph also allows your app to create sharing links, add permissions and send invitations to items in a drive.

When working with large data sets, Microsoft Graph API uses paging. When querying for data that spans multiple pages, the API returns an "@odata.nextLink" URL in the response to access the next page of results. To retrieve all data, follow these URLs until no "@odata.nextLink" is returned.

Microsoft Graph supports a wide range of SDK languages: C#, CLI, PowerShell, TypeScript, JavaScript, Java, Go, PH, and Python. Microsoft also provides a file picker SDK to seamlessly access, download, save, and share OneDrive-stored files within your app, providing users with a familiar OneDrive experience.

_You can learn more about OneDrive’s documentation_ [_here_](https://learn.microsoft.com/en-us/graph/onedrive-concept-overview) _._

## **Microsoft SharePoint**

SharePoint is also part of Microsoft’s ecosystem and has [hundreds of millions of users](https://www.microsoft.com/en-us/microsoft-365/blog/2020/12/08/over-200-million-users-rely-on-sharepoint-as-microsoft-is-again-recognized-as-a-leader-in-the-2020-gartner-content-services-platforms-magic-quadrant-report/).

SharePoint structures their API with three major “resource types” which are “Site” (top-level object), “List”, and “ListItem”. With these resource types, SharePoint’s API can support use cases such as accessing SharePoint sites, lists, and drives (document libraries), and giving various levels of access to different lists or listItems.

Since SharePoint and OneDrive use the same API, rate limiting, pagination, and the SDKs supported are all the same.

_You can see SharePoint’s API documentation_ [_here_](https://learn.microsoft.com/en-us/graph/sharepoint-concept-overview) _._

[Related](https://www.merge.dev/blog/sharepoint-api-python?blog-related=image)

#### [How to integrate with the SharePoint API via Python](https://www.merge.dev/blog/sharepoint-api-python?blog-related=image)

[![How to integrate with the SharePoint API via Python](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)](https://www.merge.dev/blog/sharepoint-api-python?blog-related=image)

## **Google Drive**

Google Drive is Google’s file storage platform. It’s popular both amongst individual users and organizations. Case in point: The platform [surpassed a billion users several years ago](https://www.theverge.com/2018/7/25/17613442/google-drive-one-billion-users).

The Google Drive API offers versatile functionalities for seamless file management. It lets you download and upload files, perform comprehensive searches based on metadata, and can share files, folders, and drives for collaborative efforts. Additionally, the integration with the Google Picker API allows for thorough searching across all Drive files; you can retrieve specific details like file names, URLs, modification dates, and user information.

Google provides the following per-minute quotas in their documentation. As long as you stay below the max, there's no limit to the number of requests you can make per day.

[![Google Drive's rate limit quotas](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6563a62076162d6c7b338ea0_NMt03Y-0xjFpHXUmT3qBxRJlEbBmgNUB575DzpeKtubo50GT9cITHxt43O0EeHKaPJemreggXqy3fwqIX7KmIh5JaXCwZov9FpdhxG6CmSXrVgtygTMAj7O9YBjNWOHgh_zyo-1gWEjRwVU4j0Qdzpo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6563a62076162d6c7b338ea0_NMt03Y-0xjFpHXUmT3qBxRJlEbBmgNUB575DzpeKtubo50GT9cITHxt43O0EeHKaPJemreggXqy3fwqIX7KmIh5JaXCwZov9FpdhxG6CmSXrVgtygTMAj7O9YBjNWOHgh_zyo-1gWEjRwVU4j0Qdzpo.webp)

Google Drive's API manages pagination using page tokens. When retrieving large result sets, the API response includes a nextPageToken if more results exist beyond the current set. To access subsequent pages, developers use this token in subsequent requests, enabling sequential retrieval of results until there's no more nextPageToken, signifying the end of available results.

Google currently supports the following SDK languages: Javascript, Go, Java, Node.js, and Python.

_You can find Google Drive’s API documentation_ [_here_](https://developers.google.com/drive/api/guides/about-sdk) _._

_Related:_ [_A guide to document and file storage integrations_](https://www.merge.dev/blog/guide-to-document-and-file-storage-apis-and-integrations)

## **Dropbox**

Dropbox is a popular file storage platform for both business and individuals; the platform has over [17 million customers](https://www.statista.com/statistics/819605/number-of-paying-dropbox-users/) and [700 million users](https://www.statista.com/statistics/819605/number-of-paying-dropbox-users/).

Common endpoints for Dropbox include managing (uploading, downloading, creating, updating, deleting, and searching) files and folders, managing users, and managing shared links and permissions for shared items.

Dropbox doesn’t publish exact rate limits. Your Dropbox Business plan will determine the number of data transport calls allowed per month to specific API endpoints. If this limit is exceeded, API calls will fail with a 403 status code and an error message indicating the limit has been reached.

In terms of pagination, you’ll need to implement cursor-based pagination. Dropbox uses a separate endpoint—https://api.dropboxapi.com/2/files/list\_folder/continue—with a provided cursor to output the rest of the response.

Dropbox currently offers and supports the following SDK languages: Swift, Objective-C, Python, .NET, Java, JavaScript, and HTTP.

_You can access Dropbox’s API documentation_ [_here_](https://www.dropbox.com/developers/documentation/http/overview) _._

## **Box**

Box has gained widespread adoption, particularly among larger companies; they have [nearly 100,000 clients and 68% of Fortune 500 companies use their file storage platform](https://www.box.com/about-us).

Some common endpoints for Box are creating, updating, deleting or retrieving folders and files, managing users and groups and permissions, and tracking and retrieving events related to your Box account.

Box has grouped their rate limiting into three categories:

- **User-based limits:** each user has a maximum number of API calls they can make per minute (usually around 1000)
- **Quality of service limits:** these limits protect the system's performance. If too many requests are made at once, temporary restrictions might be put in place to prevent problems like system slowdowns.
- **Licensing-based limits:** Box's different plans have a set number of allowed API calls per month.

The Box API supports two pagination methods: offset-based and marker-based. Offset-based is used for fixed-length item lists, while marker-based suits changing or unknown-length item sets.

Finally, Box currently offers and supports the following SDK languages: Java, .NET, Python, Node, iOS, and Android.

_You can learn more about Box’s API by reading through their documentation_ [_here_](https://developer.box.com/reference/) _._

_Related:_ [_How to get your API key in Box_](https://www.merge.dev/blog/box-api-key)

## **Zoho WorkDrive**

As an integral part of the Zoho suite, WorkDrive offers a dynamic cloud storage and file-sharing platform tailored for businesses of all sizes. There are [more than 7.5 million active users worldwide using Zoho WorkDrive](https://www.zoho.com/workdrive/digest/new-leader-in-content-collaboration.html).

Similar to other file storage platforms, WorkDrive’s most common endpoints are viewing, uploading, creating, and deleting files and folders, managing users, and sharing and setting document permissions.

WorkDrive APIs use offset-based pagination that follows the JSON API specification. By default, APIs return a maximum of 50 items per response. To customize this number, you can use query parameters like ?page\[offset\]=0&page\[limit\]=50, setting offset as the starting value and limit as the desired number of items.

_You can see Zoho WorkDrive’s API documentation_ [_here_](https://workdrive.zoho.com/apidocs/v1/overview) _._

## **Egnyte**

Egnyte is a relatively smaller file storage platform— [they have 26,000 clients—that serves businesses of varying industries and sizes](https://www.egnyte.com/customers).

Some common endpoints in Egynte’s API include uploading, downloading, updating, and deleting files and folders, getting user information and managing permissions, and creating shared links.

The table below shows Egnyte’s API rate limits by default. It’s worth noting that these rate limits and daily usage limits are enforced per access token rather than against the entire key.

[![Egnyte's default rate limits](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6563a6204f13f50fc871c1af_208eD6TV9AYzcanxPUsQPrIsba5qm1xczE-JLltHEKzRtJxaSgXjoxQ054QYzY2l9FS3rrUFfGDbgA97hi3a4DMcQJSpnXNZdNrbPePto45RljFk-QoLT6JKP-FyeLXjZVPEtdzvNu_QAoz0Ff7YbVw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6563a6204f13f50fc871c1af_208eD6TV9AYzcanxPUsQPrIsba5qm1xczE-JLltHEKzRtJxaSgXjoxQ054QYzY2l9FS3rrUFfGDbgA97hi3a4DMcQJSpnXNZdNrbPePto45RljFk-QoLT6JKP-FyeLXjZVPEtdzvNu_QAoz0Ff7YbVw.webp)

Egnyte offers standard ways to paginate your results. You can ask Egnyte for a specific starting point or limit the number of users per page. For example, start from the 10th user or only show 50 users per page. You can also ask for specific users based on things like their email, identification, or usernames.

Egnyte currently offers SDKs in the following languages: Javascript, Python (available as-is but not supported), Ruby (available as-is but not supported), .NET, Android, and iOS. Note that the depth and support offered by these SDKs may vary.

_You can see Egnyte’s API documentation_ [_here_](https://developers.egnyte.com/docs/read/Home) _._

## **Final thoughts**

Your clients likely use an array of file storage solutions, including those covered above.

You can avoid having to build, manage, and maintain all the file storage integrations your clients need by simply building to Merge's [File Storage Unified API](https://www.merge.dev/categories/file-storage-api).

You can learn more about our File Storage Unified API and our platform's maintenance support and management tooling by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffile-storage-api).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8d4d83b4-1679-487f-8508-49766796482f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0b10f20d-cdde-487a-9fbe-b555e405a65c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffile-storage-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8d4d83b4-1679-487f-8508-49766796482f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0b10f20d-cdde-487a-9fbe-b555e405a65c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffile-storage-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=fad7d5ed-7701-4e94-863f-77c5671b298f&bo=2&sid=a7f1b2203e8d11f0aabdf7fa20be676c&vid=a7f1d2a03e8d11f0baed4dfe3a94fb2b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=7%20file%20storage%20APIs%20you%20should%20integrate%20with&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffile-storage-api&r=&lt=641&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=290961)

[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743857818&cv=11&fst=1748743857818&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffile-storage-api&hn=www.googleadservices.com&frm=0&tiba=7%20file%20storage%20APIs%20you%20should%20integrate%20with&npa=0&pscdl=noapi&auid=991499630.1748743858&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743857953&cv=11&fst=1748743857953&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffile-storage-api&hn=www.googleadservices.com&frm=0&tiba=7%20file%20storage%20APIs%20you%20should%20integrate%20with&did=dZTQ1Zm&gdid=dZTQ1Zm&npa=0&pscdl=noapi&auid=991499630.1748743858&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)