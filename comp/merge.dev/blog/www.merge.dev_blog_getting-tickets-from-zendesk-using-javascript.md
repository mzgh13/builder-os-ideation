---
url: "https://www.merge.dev/blog/getting-tickets-from-zendesk-using-javascript"
title: "Getting tickets from Zendesk using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/getting-tickets-from-zendesk-using-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/getting-tickets-from-zendesk-using-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/getting-tickets-from-zendesk-using-javascript#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgetting-tickets-from-zendesk-using-javascript)

##### Just for you

No items found.

# Getting tickets from Zendesk using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fbf4169a2e89f9ada599b_Zendesk.webp)

No items found.

_This article is part of a series on building product integrations with third-party platforms._

You can think of a ticketing system like Zendesk as the control center for customer support. It's a one-stop-shop where businesses monitor and work on customer issues, filed as "tickets". Zendesk, along with similar platforms, offers tools like automation, analytics, and integration capabilities to make the customer service process smoother and boost customer satisfaction.

We frequently see use cases where developers need to access tickets from a client’s Zendesk system (think of assessing customer service performance, finding recurring problems, or even automating specific responses). The Zendesk API is useful here by allowing engineers to integrate tickets directly into their own apps or databases.

In this tutorial, we’ll dig into the Zendesk API and cover:

- Setting up the authentication process
- How to extract normalized data from Zendesk including get requests to pull tickets
- An alternative to building integrations one at a time by using a single API endpoint

{{blog-cta-100+}}

### Setting up the authentication process

In order to access the Zendesk API, the requests you send need to be authenticated. This involves including a specific header in your request, which is formatted as \`Authorization: Basic {Email Address}/token:{API-KEY}\`. This string is a base64 encoded version of your email address, followed by '/token', and then your API key. This header tells Zendesk that your request is authorized, allowing you to successfully pull tickets from their API.

```javascript
javascript
const https = require('https');
const { Buffer } = require('buffer');
const email = 'YOUR_EMAIL';
const token = 'YOUR_API_TOKEN';
const domain = 'YOUR_ZENDESK_DOMAIN';

let options = {
  hostname: `${domain}.zendesk.com`,
  path: '/api/v2/search/export?query=type:ticket&filter[type]=ticket',
  method: 'GET',
  headers: {
    'Authorization': 'Basic ' + Buffer.from(`${email}/token:${token}`).toString('base64')
  }
};

let req = https.request(options, (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    let jsonResponse = JSON.parse(data);
    let tickets = jsonResponse['results'];

    console.log('Fetched tickets:', tickets);

    if(jsonResponse['meta']['has_more'] === true) {
      options.path = jsonResponse['links']['next'];
      req = https.request(options, res => res.end());
    }
  });
});

req.on('error', (error) => {
  console.error(`Problem with request: ${error.message}`);
});

req.end();
```

Replace \`YOUR\_EMAIL\`, \`YOUR\_API\_TOKEN\`, and \`YOUR\_ZENDESK\_DOMAIN\` with your actual email, API token, and Zendesk domain respectively. This code uses Node.js built-in modules - \` **https** \` for making an HTTP request, and \` **buffer** \` for encoding your email and token into base64 format.

### **How to get tickets from Zendesk**

The code above prepares an options object that includes the request details - the hostname, path, HTTP method, and headers. The authorization header is included as specified, where the email and token are encoded in base64.

Then, it sends a **GET** request to the Zendesk API. When the response data is received, it aggregates the data chunks into a complete JSON string. Once all data has been received, it parses the JSON string into a JavaScript object and logs the tickets to the console. If the \` **has\_more** \` field in the \` **meta** \` object of the response is true, it sets the path in the options object to the \`next\` link and sends another GET request. If there's an error with the request, it logs the error message to the console. Finally, it calls \` **req.end()** \` to signify the end of the request.

Here's an example of an individual item returned by this API Endpoint:

```json
{
    "url": "http://example.com/ticket/1",
    "id": 1,
    "via": {
        "channel": "email",
        "source": {
            "from": {},
            "to": {}
        }
    },
    "created_at": "2021-06-01T00:00:00Z",
    "updated_at": "2021-06-01T00:00:00Z",
    "type": "issue",
    "subject": "Test Ticket",
    "raw_subject": "Test Ticket",
    "description": "This is a test ticket",
    "priority": "high",
    "status": "open",
    "requester_id": 2,
    "submitter_id": 3,
    "assignee_id": 4,
    "group_id": 5,
    "collaborator_ids": [],
    "follower_ids": [],
    "email_cc_ids": [],
    "has_incidents": false,
    "is_public": true,
    "tags": [],
    "custom_fields": [],
    "sharing_agreement_ids": [],
    "fields": [],
    "followup_ids": [],
    "ticket_form_id": 6,
    "brand_id": 7,
    "allow_channelback": false,
    "allow_attachments": true,
    "result_type": "ticket"
}
```

_Related:_ [_The steps for reading API documentation_](https://www.merge.dev/blog/how-to-read-api-documentation)

### Use a unified API to offer a variety of ticketing integrations

In this article, we walked through the process of leveraging Javascript to connect with Zendesk and retrieve tickets. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tickets—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's ticketing Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgetting-tickets-from-zendesk-using-javascript) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

No items found.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2a2ca87b-c1f8-4123-b445-2438dce0343d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=07c1f095-edfb-4051-8b6b-1b74df246b7f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgetting-tickets-from-zendesk-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2a2ca87b-c1f8-4123-b445-2438dce0343d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=07c1f095-edfb-4051-8b6b-1b74df246b7f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgetting-tickets-from-zendesk-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=d0cf5a0f-dd20-4da3-a740-2c734a80bda3&bo=2&sid=3f29d5403e8c11f09e2d05ea46787de7&vid=3f2a29a03e8c11f09c7bdf0644125129&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Getting%20tickets%20from%20Zendesk%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgetting-tickets-from-zendesk-using-javascript&r=&lt=474&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=573416)