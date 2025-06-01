---
url: "https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript"
title: "How to get tickets from Jira using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript#)

Table of contents

[Setting up authentication](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript#setting-up-authentication)

[Use a Unified CRM API to Integrate With a Variety of Ticketing Systems](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-javascript#use-a-unified-crm-api-to-integrate-with-a-variety-of-ticketing-systems)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tickets-from-jira-using-javascript)

##### Just for you

No items found.

# How to get tickets from Jira using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cef927891cdb6506d64_Jira.webp)

No items found.

‍ _This tutorial is part of a series on building product integrations._

If you've ever worked on a software team, you've probably come across **Jira**, a project management tool that’s useful when it comes to tracking and streamlining tasks. It’s popular with teams that need to track bugs, issues, and manage agile projects. What’s great about Jira is its ability to work well with other digital tools; you can use the Jira API to access ticket data for analysis with other systems.

A common example we see at Merge is developers who want to pull tickets from a customer’s Jira system to automate ticket management or minimize manual labor. For the rest of this article, we’ll dig into how to do this by using the Jira API:

- How to set up authentication
- How to pull normalized data from Jira, specifically using fetch requests to pull tickets
- The benefits of a single API endpoint to access third-party ticketing platforms

## Setting up authentication

For authenticating with the Jira API, you'll need to include an HTTP header in your requests. This header should be in the format \`Authorization: {Email Address}:{API-KEY}\`. Here, \`{Email Address}\` is your Jira account email and \`{API-KEY}\` is the API key generated from your Jira account. Both of these values should be base64-encoded.

This is how you can generate the base64-encoded string of your email and API key in JavaScript:

```javascript

var email = 'your-email@example.com';
var token = 'your-api-token';
var buff = new Buffer(email + ':' + token);
var base64data = buff.toString('base64');
console.log('Encoded Token: ' + base64data);

```

The resulting string will be used in the \` **Authorization** \` header of your requests. You’ll first need to install the \` **node-fetch** \` and \` **btoa** \` libraries using the command \` **npm install node-fetch btoa** \` in your terminal or command line interface.

```javascript

const fetch = require("node-fetch");
const btoa = require("btoa");

```

Next, create a function that will get the tickets from Jira. The function will take in three arguments: \` **email** \`, \` **apiKey** \`, and \` **domain** \`.

```javascript

async function fetchTickets(email, apiKey, domain) {
  const base64auth = btoa(`${email}:${apiKey}`);
  const headers = {
    "Authorization": `Basic ${base64auth}`
  };

  let startAt = 0;
  let maxResults = 50;
  let tickets = [];

  while (true) {
    const response = await fetch(`https://${domain}.atlassian.net/rest/api/3/search?expand=renderedFields&startAt=${startAt}&maxResults=${maxResults}`, { headers });
    const data = await response.json();

    tickets = tickets.concat(data.issues);

    if (!data.issues.length) {
      break;
    }

    startAt += maxResults;
  }

  return tickets;
}

```

To use this function, you can call it in your application and pass in your email, API key, and domain associated with your Jira account.

```javascript

fetchTickets('YOUR-EMAIL', 'YOUR-API-KEY', 'YOUR-DOMAIN')
  .then(tickets => console.log(tickets))
  .catch(err => console.log(err));

```

This function will continuously pull data from the Jira API until there are no more tickets to retrieve. Tickets are returned as an array of JSON objects. Below is an example of an individual item returned by this API Endpoint:

```json
{
    "expand": "renderedFields,names,schema,operations,editmeta,changelog,versionedRepresentations",
    "id": "10001",
    "self": "https://your-domain.atlassian.net/rest/api/3/issue/10001",
    "key": "JRA-1",
    "fields": {
        "statuscategorychangedate": "2019-07-02T08:44:10.162+0000",
        "issuetype": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issuetype/10001",
            "id": "10001",
            "description": "An error in the code",
            "iconUrl": "https://your-domain.atlassian.net/secure/viewavatar?size=medium&avatarId=10303&avatarType=issuetype",
            "name": "Bug",
            "subtask": false,
            "hierarchyLevel": 0
        },
        "parent": {
            "id": "10000",
            "key": "JRA-1",
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/10000",
            "fields": {
                "summary": "Parent issue",
                "status": {
                    "self": "https://your-domain.atlassian.net/rest/api/3/status/1",
                    "description": "",
                    "iconUrl": "https://your-domain.atlassian.net/images/icons/statuses/open.png",
                    "name": "Open",
                    "id": "1",
                    "statusCategory": {
                        "self": "https://your-domain.atlassian.net/rest/api/3/statuscategory/2",
                        "id": 2,
                        "key": "new",
                        "colorName": "blue-gray",
                        "name": "To Do"
                    }
                },
                "priority": {
                    "self": "https://your-domain.atlassian.net/rest/api/3/priority/3",
                    "iconUrl": "https://your-domain.atlassian.net/images/icons/priorities/major.svg",
                    "name": "Major",
                    "id": "3"
                },
                "issuetype": {
                    "self": "https://your-domain.atlassian.net/rest/api/3/issuetype/1",
                    "id": "1",
                    "description": "A problem which impairs or prevents the functions of the product.",
                    "iconUrl": "https://your-domain.atlassian.net/secure/viewavatar?size=medium&avatarId=10303&avatarType=issuetype",
                    "name": "Bug",
                    "subtask": false,
                    "hierarchyLevel": 1
                }
            }
        },
        "project": {
            "self": "https://your-domain.atlassian.net/rest/api/3/project/10000",
            "id": "10000",
            "key": "JRA",
            "name": "Jira",
            "projectTypeKey": "business",
            "simplified": true,
            "avatarUrls": {
                "48x48": "https://your-domain.atlassian.net/secure/projectavatar?pid=10000&avatarId=10424",
                "24x24": "https://your-domain.atlassian.net/secure/projectavatar?size=small&pid=10000&avatarId=10424",
                "16x16": "https://your-domain.atlassian.net/secure/projectavatar?size=xsmall&pid=10000&avatarId=10424",
                "32x32": "https://your-domain.atlassian.net/secure/projectavatar?size=medium&pid=10000&avatarId=10424"
            }
        },
        "fixVersions": [],
        "workratio": -1,
        "lastViewed": "2019-07-02T04:26:56.147+0000",
        "watches": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/JRA-1/watchers",
            "watchCount": 2,
            "isWatching": true
        },
        "created": "2019-06-26T10:24:16.594+0000",
        "priority": {
            "self": "https://your-domain.atlassian.net/rest/api/3/priority/5",
            "iconUrl": "https://your-domain.atlassian.net/images/icons/priorities/trivial.svg",
            "name": "Trivial",
            "id": "5"
        },
        "labels": [\
            "bugfix",\
            "blitz_test"\
        ],
        "customfield_10018": {
            "hasEpicLinkFieldDependency": false,
            "showField": true,
            "nonEditableReason": {
                "reason": "PLUGIN_LICENSE_ERROR",
                "message": "The Parent Link is only available to Jira Software users."
            }
        },
        "customfield_10019": "10014_*:*_1_*:*_10000_*|*_10100_*:*_1_*:*_0",
        "versions": [],
        "issuelinks": [],
        "assignee": {
            "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b109f2e9729b51fdf8082c5",
            "accountId": "5b109f2e9729b51fdf8082c5",
            "emailAddress": "assignee@example.com",
            "avatarUrls": {
                "48x48": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar48",
                "24x24": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar24",
                "16x16": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar16",
                "32x32": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar32"
            },
            "displayName": "User",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "updated": "2019-07-02T08:44:10.883+0000",
        "status": {
            "self": "https://your-domain.atlassian.net/rest/api/3/status/10000",
            "description": "",
            "iconUrl": "https://your-domain.atlassian.net/images/icons/statuses/open.png",
            "name": "To Do",
            "id": "10000",
            "statusCategory": {
                "self": "https://your-domain.atlassian.net/rest/api/3/statuscategory/2",
                "id": 2,
                "key": "new",
                "colorName": "blue-gray",
                "name": "To Do"
            }
        },
        "components": [],
        "customfield_10014": "IC-994",
        "summary": "This is a test issue",
        "creator": {
            "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b109f2e9729b51fdf8082c5",
            "accountId": "5b109f2e9729b51fdf8082c5",
            "emailAddress": "creator@example.com",
            "avatarUrls": {
                "48x48": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar48",
                "24x24": "https://avatar-cdn.atlassian.net/secure/useravatar?size=medium&avatarId=10323",
                "16x16": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar16",
                "32x32": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar32"
            },
            "displayName": "User",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "subtasks": [],
        "reporter": {
            "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b109f2e9729b51fdf8082c5",
            "accountId": "5b109f2e9729b51fdf8082c5",
            "emailAddress": "reporter@example.com",
            "avatarUrls": {
                "48x48": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar48",
                "24x24": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar24",
                "16x16": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar16",
                "32x32": "https://avatar-cdn.atlassian.com/5b109f2e9729b51fdf8082c5%3Aavatar32"
            },
            "displayName": "User",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "aggregateprogress": {
            "progress": 0,
            "total": 0
        },
        "customfield_10000": "10000_*:*_1_*:*_10000_*|*_10100_*:*_1_*:*_0",
        "progress": {
            "progress": 0,
            "total": 0
        },
        "votes": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/JRA-1/votes",
            "votes": 1,
            "hasVoted": false
        }
    },
    "renderedFields": {
        "statuscategorychangedate": "2019-07-02T08:44:10.162+0000",
        "lastViewed": "2019-07-02T04:26:56.147+0000",
        "created": "2019-06-26T10:24:16.594+0000",
        "customfield_10017": "This is a custom field",
        "updated": "2019-07-02T08:44:10.883+0000",
        "description": "This is a test issue for JSON schema API",
        "environment": "Testing"
    }
}
```

## Use a Unified CRM API to Integrate With a Variety of Ticketing Systems

In this article, we walked through the process of leveraging Javascript to connect with Jira and retrieve tickets. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tickets—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's CRM Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tickets-from-jira-using-javascript) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8de12bd7-71c4-4796-be89-a9b30f007c90&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=29625d5e-9d74-4b65-b5e9-9aefc2b49c43&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tickets-from-jira-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8de12bd7-71c4-4796-be89-a9b30f007c90&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=29625d5e-9d74-4b65-b5e9-9aefc2b49c43&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tickets-from-jira-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)