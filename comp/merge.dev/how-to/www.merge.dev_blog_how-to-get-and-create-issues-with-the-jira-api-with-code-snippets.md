---
url: "https://www.merge.dev/blog/how-to-get-and-create-issues-with-the-jira-api-with-code-snippets"
title: "How to GET and create issues with the Jira API (with code snippets!)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-and-create-issues-with-the-jira-api-with-code-snippets#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-and-create-issues-with-the-jira-api-with-code-snippets#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-and-create-issues-with-the-jira-api-with-code-snippets#)

Table of contents

[Understanding Jira’s API](https://www.merge.dev/blog/how-to-get-and-create-issues-with-the-jira-api-with-code-snippets#understanding-jiras-api)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-and-create-issues-with-the-jira-api-with-code-snippets)

##### Just for you

No items found.

# How to GET and create issues with the Jira API (with code snippets!)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856d2a22f3719980bde386_Jira_API_Logo.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538592637517da99427a_62eff91f58ad1560481786c6_Max.webp)

Max Gong

Platform

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538484e0976358929031_62eff2f406d84893e1c8be19_aaron.webp)

Aaron Lu

Growth Marketing

@Merge

Jira is one of the most popular Ticketing and Task Management API platforms developers integrate with. If you deal at all in the realm of project management or ticketing integrations, then you're probably creating an issue with the Jira API.

In this article, we’ll cover how to handle authentication, building a GET request, and building a POST request - in short, everything you’ll need to successfully call the Jira API!

## Understanding Jira’s API

As far as enterprise APIs go, Jira’s is relatively simple. It's a REST API that returns responses in JSON. The biggest hurdles people face when integrating with Jira, however, is handling authentication.

#### Add dozens of ticketing integrations to your product with Merge

Learn how Merge's Unified API can help you add countless ticketing integrations—including Jira—in a matter of hours.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-and-create-issues-with-the-jira-api-with-code-snippets)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Authenticating with the JIRA API

Jira uses basic auth, which is a method for HTTP user agents to provide credentials to validate requests to the API.

Jira’s basic auth requires three values:

1. Sub-domain of the end-user’s account.
2. Email Address of the end-user’s account. However, to ensure the user has permissions necessary to access the required API endpoint, it is preferred that the end-user’s role be an administrator. To assign roles to individual users, view the Jira help docs [here](https://support.atlassian.com/user-management/docs/give-users-admin-permissions/).
3. API Token - the end-user can create and access the standard API Token from their profile [here](https://id.atlassian.com/manage-profile/security/api-tokens).

_Related:_ [_The steps for fetching comments from the Jira API (via Python)_](https://www.merge.dev/blog/jira-api-get-comments)

### Building the GET request for Jira issues

To search for issues with Jira’s API, you can hit this endpoint:

```python
https://{{SUB-DOMAIN}}.atlassian.net/rest/api/3/search?jql=projectType=software AND updatedDate>=2022-05-26&expand=renderedFields&startAt=0&maxResults=50
```

For Jira's documentation, look [here](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-issue-search/#api-rest-api-3-search-get).

There are a few parts of this request to note, you’ll need to replace certain fields to fit your use cases.

`SUB-DOMAIN` is your end-user subdomain for their JIRA account, you can generally find this post login, where the url will look like `SUB-DOMAIN.jira.com`.

JQL (Jira Query Language) is a query parameter that’s unique to Jira and allows for advanced search for anything that the standard endpoints do not offer (learn more [here](https://support.atlassian.com/jira-software-cloud/docs/what-is-advanced-searching-in-jira-cloud/)). For issues, there are a few specific query parameters we’ll want to add.

`projectType=software` is a must-have query parameter - Jira has multiple products, and to filter issues from only Jira Software and not Service Management, we need to include this.

`updatedDate>=2022-05-26` pulls the issues modified on or after 2022-05-26. In general, we want to keep the time range small to avoid overloading the response.

`Pagination uses startAt=0` which indicates the 0th issue, and `maxResults=50`, which indicates how many results to return (At Merge, we use [pagination to batch faster API calls](https://www.merge.dev/docs/basics/pagination/) to avoid overload as well.)

`expand=renderedFields` is needed to pull the issue details in HTML form. Otherwise, you’ll have to deal with Atlassian Document Format, which is... a little difficult to deal with. HTML is easy to normalize and display for your integration. (link [here](https://developer.atlassian.com/cloud/jira/platform/apis/document/structure/) to learn more about Atlassian document format)

Example of GET response:

```python
{
   "expand": "names,schema",
   "startAt": 1,
   "maxResults": 50,
   "total": 2,
   "issues": [\
       {\
           "expand": "operations,versionedRepresentations,editmeta,changelog,customfield_10010.requestTypePractice,renderedFields",\
           "id": "10001",\
           "self": "https://mgongv8.atlassian.net/rest/api/3/issue/10001",\
           "key": "PROJ-2",\
           "renderedFields": {\
               "statuscategorychangedate": "20/Apr/22 5:42 PM",\
               "lastViewed": "27/May/22 11:37 AM",\
               "created": "20/Apr/22 5:42 PM",\
               "updated": "27/May/22 11:45 AM\
           },\
           "fields": {\
               "statuscategorychangedate": "2022-04-20T17:42:19.815-0400",\
               "issuetype": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/issuetype/10001",\
                   "id": "10001",\
                   "description": "Tasks track small, distinct pieces of work.",\
                   "iconUrl": "https://mgongv8.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10318?size=medium",\
                   "name": "Task",\
                   "subtask": false,\
                   "avatarId": 10318,\
                   "entityId": "4f728257-309e-458d-a31a-dbc67b0fa0a7",\
                   "hierarchyLevel": 0\
               },\
               "timespent": null,\
               "customfield_10030": [],\
               "customfield_10031": null,\
               "project": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/project/10000",\
                   "id": "10000",\
                   "key": "PROJ",\
                   "name": "project",\
                   "projectTypeKey": "software",\
                   "simplified": true,\
               },\
               "workratio": -1,\
               "watches": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/issue/PROJ-2/watchers",\
                   "watchCount": 1,\
                   "isWatching": true\
               },\
               "lastViewed": "2022-05-27T11:37:28.074-0400",\
               "created": "2022-04-20T17:42:19.396-0400",\
               "priority": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/priority/3",\
                   "iconUrl": "https://mgongv8.atlassian.net/images/icons/priorities/medium.svg",\
                   "name": "Medium",\
                   "id": "3"\
               },\
               "customfield_10018": {\
                   "hasEpicLinkFieldDependency": false,\
                   "showField": false,\
                   "nonEditableReason": {\
                       "reason": "PLUGIN_LICENSE_ERROR",\
                       "message": "The Parent Link is only available to Jira Premium users."\
                   }\
               },\
               "customfield_10019": "0|i00007:",\
               "aggregatetimeoriginalestimate": null,\
               "timeestimate": null,\
               "versions": [],\
               "issuelinks": [],\
               "assignee": null,\
               "updated": "2022-05-27T11:45:21.163-0400",\
               "status": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/status/10000",\
                   "description": "",\
                   "iconUrl": "https://mgongv8.atlassian.net/",\
                   "name": "To Do",\
                   "id": "10000",\
                   "statusCategory": {\
                       "self": "https://mgongv8.atlassian.net/rest/api/3/statuscategory/2",\
                       "id": 2,\
                       "key": "new",\
                       "colorName": "blue-gray",\
                       "name": "To Do"\
                   }\
               },\
               "summary": "Wow another issuesfasdf",\
               "creator": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/user?accountId=626069fc9e7c190069e7bc4c",\
                   "accountId": "626069fc9e7c190069e7bc4c",\
                   "emailAddress": "mgongv8@gmail.com",\
                   "displayName": "Max G",\
                   "active": true,\
                   "timeZone": "America/New_York",\
                   "accountType": "atlassian"\
               },\
               "subtasks": [],\
               "customfield_10040": null,\
               "customfield_10041": null,\
               "customfield_10042": null,\
               "reporter": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/user?accountId=626069fc9e7c190069e7bc4c",\
                   "accountId": "626069fc9e7c190069e7bc4c",\
                   "emailAddress": "mgongv8@gmail.com",\
                   "displayName": "Max G",\
                   "active": true,\
                   "timeZone": "America/New_York",\
                   "accountType": "atlassian"\
               },\
               "aggregateprogress": {\
                   "progress": 0,\
                   "total": 0\
               },\
               "progress": {\
                   "progress": 0,\
                   "total": 0\
               },\
               "votes": {\
                   "self": "https://mgongv8.atlassian.net/rest/api/3/issue/PROJ-2/votes",\
                   "votes": 0,\
                   "hasVoted": false\
               }\
           }\
       }\
   ]
}
```

We’ve shortened the API response, but there are several things that should be noted about the ticket pulled. There are several notable common fields that you’ll likely need if you’re looking to GET tickets.

`summary` \- The summary is actually the name of the Ticket

`status.name` \- This field is the status of the Jira issue (complete, backlog etc.)

`issuetype` \- Denotes the type of issue in Jira, whether that be a bug, story, epic, task, or subtask

`duedate` \- The due date for the ticket

`renderedFields.description` \- This field would be the HTML version of the description of the Jira Ticket

_Related:_ [_A guide to getting attachments from the Jira API_](https://www.merge.dev/blog/jira-api-get-attachments-python)

### Python Example for calling the Jira API

There are a few ways to call the Jira API using python. JIRA has a python package that you’re able to use to call the API - [https://pypi.org/project/jira/](https://pypi.org/project/jira/).

As this package is well documented, we’ll show an alternative way that we use that’s more similar to our other tutorials using the requests and JSON packages.

```python
Import requests
From requests.auth import HTTPBasicAuth
Import json

Headers = {“Accept”: “application/json”}
Query = {‘jql’: ‘projectType=software AND updatedDate>={{date_not_tooo_long_ago&expand=renderedFields&startAt=0&maxResults=50}}

Response = requests.get(“https://{{SUB_DOMAIN}}.atlassian.net/rest/api/3/search”, headers=headers, auth=auth, params=query)

You should get a json response here, to load it as a dict, we can use json.loads

Response_dict = json.loads(response.text)
```

You should get a JSON response here. To load it as a `dict`, we can use `json.loads`.

That’s it! If you’re interested in not only integrating with [Jira](https://merge.dev/integrations/jira) but also [Asana](https://merge.dev/integrations/asana), [Linear](https://merge.dev/integrations/linear), and [Azure DevOps](https://merge.dev/integrations/azure-devops) to provide integrations for your customers, Merge allows you to integrate with one [Ticketing Unified API](https://merge.dev/categories/ticketing-api) to integrate with any ticketing or task management systems your customers may have. Explore our technical [Get Started](https://www.merge.dev/docs/get-started/introduction/) to see what it means to build with Merge. You can also [schedule a demo with one of our integration experts to learn more](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-and-create-issues-with-the-jira-api-with-code-snippets).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Max Gong

Platform

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Aaron Lu

Growth Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b16da8fa-81c2-471d-84c4-368962df604d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=637ac785-26f6-40cb-9562-bb5b92dc114c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-and-create-issues-with-the-jira-api-with-code-snippets&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b16da8fa-81c2-471d-84c4-368962df604d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=637ac785-26f6-40cb-9562-bb5b92dc114c&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-and-create-issues-with-the-jira-api-with-code-snippets&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)