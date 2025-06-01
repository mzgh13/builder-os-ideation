---
url: "https://www.merge.dev/blog/jira-api-get-attachments-javascript"
title: "How to get attachments from Jira using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-get-attachments-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-get-attachments-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-get-attachments-javascript#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-get-attachments-javascript#authenticating-with-jira)

[Pulling attachments from Jira](https://www.merge.dev/blog/jira-api-get-attachments-javascript#pulling-attachments-from-jira)

[Tips for testing your Jira integration](https://www.merge.dev/blog/jira-api-get-attachments-javascript#tips-for-testing-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-get-attachments-javascript#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-attachments-javascript)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7387ff8c191004c1e8_6.webp)**How to get projects from Jira using Python**](https://www.merge.dev/blog/jira-api-get-projects-python)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7b1f480601b9ebf11ce_Jira_API_Key.webp)**How to get your Jira API key (5 steps)**](https://www.merge.dev/blog/jira-api-key)

# How to get attachments from Jira using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cebc1bfb5f5db304e2e_How_to_get_attachments_from_Jira_via_JavaScript.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a dynamic ticketing system for issue tracking and project management, offers countless API endpoints that can help you get the data and documents you need. And while there’s a myriad of important types of data and documents you can collect, attachments are arguably the most important.

Fetching attachments lets you enhance data transparency, streamline operations, improve collaboration, elevate your record keeping, and much more.

To help you retrieve attachments, whether that’s for your product or your internal applications, we’ll cover how you can set up authentication for the Jira API and use 'get' requests to retrieve attachments. We’ll then introduce you to a single API endpoint that can help you connect your product with dozens of ticketing systems (including Jira).

_Note: Discover how you can fetch attachments from Jira via Python by reading_ [_this article_](https://www.merge.dev/blog/jira-api-get-attachments-python) _._

#### Add ticketing integrations to your product with ease

Learn how Merge can help you add dozens of ticketing integrations—including Jira—through a single, unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-attachments-javascript)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Authenticating with Jira**

Authentication is a crucial aspect when interacting with the Jira API, as it ensures secure access to your data.

To authenticate your requests, you need to provide the necessary credentials in the header of your HTTP request.

The format you should use is \`Authorization: Basic {Email Address}:{API-KEY}\`. This means that you need to include your email address and API key, both encoded in Base64, in the header.

Make sure to replace \`{Email Address}\` and \`{API-KEY}\` with your actual email address and API key.

## **Pulling attachments from Jira**

The script below uses the \`axios\` library to make HTTP requests and the \`btoa\` function to encode the authentication header. Moreover, the \`getAttachments\` function fetches issues from the Jira API, with each issue being fetched by the \`GET /search\` API endpoint. The script then iterates over each issue and fetches its attachments using the \`GET /issue/{id}\` API endpoint. Each attachment is added to the \`attachments\` array.

Finally, the script continues fetching issues in batches of 50 (the \`maxResults\` query parameter) until there are no more issues to fetch (when the \`issues\` array is empty).

```javascript

// Required node modules
const axios = require('axios');
const btoa = require('btoa');
// Your Jira domain
const DOMAIN = 'your-domain';
// Your email address and API key
const EMAIL = 'your-email';
const API_KEY = 'your-api-key';
// Basic authentication header
const AUTH_HEADER = {
  headers: {
    Authorization: `Basic ${btoa(`${EMAIL}:${API_KEY}`)}`
  }
};
const MAX_RESULTS = 50;
// Function to get attachments
async function getAttachments() {
  let attachments = [];
  let startAt = 0;
  while (true) {
    const searchUrl = `https://${DOMAIN}.atlassian.net/rest/api/3/search?expand=renderedFields&maxResults=${MAX_RESULTS}&startAt=${startAt}`;
    const searchResponse = await axios.get(searchUrl, AUTH_HEADER);
    const issues = searchResponse.data.issues;
    if (issues.length === 0) {
      break;
    }
    for (const issue of issues) {
      const issueUrl = `https://${DOMAIN}.atlassian.net/rest/api/3/issue/${issue.id}`;
      const issueResponse = await axios.get(issueUrl, AUTH_HEADER);
      attachments.push(...issueResponse.data.fields.attachment);
    }
    startAt += MAX_RESULTS;
  }
  return attachments;
}

```

Once all issues and their respective attachments have been fetched, the \`getAttachments\` function returns the \`attachments\` array. Here’s an example of an individual item returned by this API endpoint:

```json

{
    "expand": "schema,names",
    "id": "10236",
    "self": "https://your-domain.atlassian.net/rest/api/3/issue/10236",
    "key": "JRA-9",
    "fields": {
        "statuscategorychangedate": "2021-09-01T03:37:29.272+0000",
        "issuetype": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issuetype/1",
            "id": "1",
            "description": "A problem or error.",
            "iconUrl": "https://your-domain.atlassian.net/secure/viewavatar?size=medium&avatarId=10303&avatarType=issuetype",
            "name": "Bug",
            "subtask": false,
            "avatarId": 10303,
            "entityId": "id_1",
            "hierarchyLevel": 0
        },
        "project": {
            "self": "https://your-domain.atlassian.net/rest/api/3/project/10000",
            "id": "10000",
            "key": "JRA",
            "name": "Sample Project",
            "projectTypeKey": "software",
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
        "issuerestriction": {
            "issuerestrictions": {},
            "shouldDisplay": false
        },
        "watches": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/JRA-9/watchers",
            "watchCount": 3,
            "isWatching": false
        },
        "lastViewed": "2021-09-01T05:07:46.798+0000",
        "created": "2021-09-01T03:37:29.272+0000",
        "priority": {
            "self": "https://your-domain.atlassian.net/rest/api/3/priority/3",
            "iconUrl": "https://your-domain.atlassian.net/images/icons/priorities/medium.svg",
            "name": "Medium",
            "id": "3"
        },
        "labels": [],
        "customfield_10018": {
            "hasEpicLinkFieldDependency": false,
            "showField": true,
            "nonEditableReason": {
                "reason": "NOT_EDITABLE",
                "message": "This field is not editable."
            }
        },
        "customfield_10019": "10021_*:*_1_*:*_10105_*|*_10100_*:*_1",
        "versions": [],
        "issuelinks": [],
        "updated": "2021-09-01T05:07:46.798+0000",
        "status": {
            "self": "https://your-domain.atlassian.net/rest/api/3/status/1",
            "description": "The issue is open and ready for the assignee to start work on it.",
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
        "components": [],
        "timetracking": {},
        "attachment": [],
        "summary": "Login screen has rendering issue",
        "creator": {
            "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10ac8d82e05b22cc7d4ef5",
            "accountId": "5b10ac8d82e05b22cc7d4ef5",
            "emailAddress": "admin@example.com",
            "avatarUrls": {
                "48x48": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/48",
                "24x24": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/24",
                "16x16": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/16",
                "32x32": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/32"
            },
            "displayName": "admin",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "subtasks": [],
        "reporter": {
            "self": "https://your-domain.atlassian.net/rest/api/3/user?accountId=5b10ac8d82e05b22cc7d4ef5",
            "accountId": "5b10ac8d82e05b22cc7d4ef5",
            "emailAddress": "admin@example.com",
            "avatarUrls": {
                "48x48": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/48",
                "24x24": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/24",
                "16x16": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/16",
                "32x32": "https://avatar-management--avatars.us-west-2.prod.public.atl-paas.net/5b10ac8d82e05b22cc7d4ef5/32"
            },
            "displayName": "admin",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "customfield_10000": "example custom field",
        "aggregateprogress": {
            "progress": 0,
            "total": 0
        },
        "progress": {
            "progress": 0,
            "total": 0
        },
        "votes": {
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/JRA-9/votes",
            "votes": 0,
            "hasVoted": false
        },
        "comment": {
            "comments": [],
            "self": "https://your-domain.atlassian.net/rest/api/3/issue/10236/comment",
            "maxResults": 0,
            "total": 0,
            "startAt": 0
        },
        "worklog": {
            "startAt": 0,
            "maxResults": 20,
            "total": 0,
            "worklogs": []
        }
    }
}
```

_Related:_ [_What you need to do to get projects from Jira (using JavaScript)_](https://www.merge.dev/blog/jira-api-get-projects-javascript)

## Tips for testing your Jira integration

Even if your integration is performing well in the initial stages, various issues can pop up in production, whether that's due to configuration errors, compatibility issues, unforeseen user scenarios, etc.

To effectively preempt these challenges, here are some best practices to follow:

- **Understand the API specifications:** It’s essential to grasp the API specs fully. This means [digging into the API documentation](https://www.merge.dev/blog/how-to-read-api-documentation) to understand request and response formats, endpoint behaviors, and error handling.

- **Set up a testing environment:** Using this environment, you can simulate real-world scenarios like how the integration handles large data volumes or reacts to invalid user inputs to ensure robustness.

- **Test for different HTTP methods:** Testing how the integration responds to various HTTP methods (GET, POST, PUT, DELETE) is crucial. Tools like [Postman](https://www.postman.com/) or [Swagger](https://swagger.io/) can be really helpful for this, allowing you to send requests and inspect responses easily.

- **Check response status codes:** Paying attention to response status codes is vital to ensure the integration is communicating correctly. You can do this by using tools to monitor and validate the codes returned by the API for different requests, ensuring they align with expected outcomes.

- **Continuous Integration and Continuous Deployment (CI/CD):** Implementing CI/CD practices is important for maintaining a smooth and efficient development pipeline. This approach helps in automatically testing and deploying changes, ensuring that the integration remains stable and up-to-date.

_Related:_ [_A guide to using JavaScript to retrieve comments from Jira_](https://www.merge.dev/blog/jira-api-javascript-get-comments)

## **Final thoughts**

It’s worth remembering that your clients might be using other ticketing systems, whether that’s Asana, ServiceNow, ClickUp, etc.

You can offer customer-facing integrations with all of the ticketing systems your clients use by connecting to [Merge's Ticketing Unified API](https://www.merge.dev/categories/ticketing-api).

Learn more about Merge’s Ticketing Unified API, along with the other features and capabilities provided by the platform, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-attachments-javascript).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fd96ea81-3392-443c-b669-000d089b418a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=563bc668-1fe2-4e69-a606-7c9a709efd1e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fd96ea81-3392-443c-b669-000d089b418a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=563bc668-1fe2-4e69-a606-7c9a709efd1e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=22881cf3-55b4-47a6-b856-37075012eeca&bo=2&sid=282426003e8e11f0ab815ff4963908f9&vid=2824a8303e8e11f0ad6de13f6ba1a0a0&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20attachments%20from%20Jira%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-javascript&r=&lt=578&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=220882)