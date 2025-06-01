---
url: "https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-python"
title: "How to get tickets from Jira using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-python#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tickets-from-jira-using-python)

##### Just for you

No items found.

# How to get tickets from Jira using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7000295f40b50711b2_API_key_guide.webp)

No items found.

_This tutorial is part of a series on building product integrations._

**Jira** is a powerful project management tool used by teams to track and manage work tasks, often called 'tickets' or 'issues'. With Jira, individual users and teams can collaborate, prioritize, and monitor the progression of tasks – which in our experience simplifies workflows and enhances productivity. Because of immediate updates and strong reporting features, Jira is frequently used in software companies for project management, and for bug and issue tracking.

You might find it useful to pull tickets from a customer’s Jira system for multiple reasons (e.g. enhancing project management or communication). Integrating the Jira API into your application allows you to automate the process of ticket retrieval which allows you toinvestigate ticket data, improves your efficiency, and solves for a range of potential customer use cases.

**In this article, we’ll cover:**

-  How to set up authentication for the Jira API
-  How to extract uniform data from Jira, incorporating get requests to pull tickets from Jira
-  How to utilize a single API endpoint to connect with multiple external ticketing systems

### Authenticating with Jira

Authentication for the Jira API is accomplished by using an **encoded header**. This header should be in the format: `Authorization: Basic {Email Address}:{API-KEY}`. The {Email Address} and {API-KEY} are your Jira account email address and API key, respectively and they should be base64 encoded. **The API key should be generated from your Jira account settings**.

_‍_ **_Note_** _: Be sure to replace {Email Address}, and {API-KEY} with your actual email address and API key._

Here’s an example of how to generate the base64 string in Python. This script uses the requests library to make the necessary **GET** requests to the Jira API, and the json library to parse and print the JSON response:

```python

import base64

email = "example@example.com"
api_key = "your_api_key"
base64_encoded_credentials = base64.b64encode(f"{email}:{api_key}".encode("ascii")).decode("ascii")

```

This will generate a base64 string from your email and API key which you can use in the header for authentication.

```python

import requests
import base64
import json

# Define your email and the API key
email = "your-email@example.com"
api_key = "your-api-key"

# Encode the credentials
credentials = base64.b64encode(f"{email}:{api_key}".encode('utf-8')).decode('utf-8')

headers = {
    "Authorization": f"Basic {credentials}",
    "Accept": "application/json"
}

# Define the domain
domain = "your-domain"

# Define the base URL
base_url = f"https://{domain}.atlassian.net/rest/api/3/search"

# Define the parameters
params = {
    "expand": "renderedFields",
    "maxResults": 50,
    "startAt": 0
}

# Initialize an empty list to store the tickets
tickets = []

# Loop until all tickets are fetched
while True:
    response = requests.get(base_url, headers=headers, params=params)
    data = response.json()

    # Add the fetched tickets to the list
    tickets.extend(data['issues'])

    # Check if there are more tickets to fetch
    if 'startAt' in data and data['startAt'] + data['maxResults'] < data['total']:
        # Update the startAt parameter for the next request
        params['startAt'] = data['startAt'] + data['maxResults']
    else:
        # If no more tickets, break the loop
        break

# Print the fetched tickets
print(json.dumps(tickets, indent=4))

```

### **How to get tickets from Jira**

The `base64` library is used to encode the email and API key in the required format for the Authorization header. The script gets **50 tickets at a time** (as defined by the `maxResults` parameter), and keeps getting more tickets until no more are available, by updating the `startAt` parameter for each subsequent request. The tickets are stored in the `tickets` list.

Here’s example of an individual item returned by this API Endpoint:

```json
{
    "expand": "renderedFields,names,schema,operations,editmeta,changelog,versionedRepresentations",
    "id": "10100",
    "self": "https://jira.example.com/rest/api/2/issue/10100",
    "key": "PRJ-1",
    "fields": {
        "statuscategorychangedate": "2021-08-01T14:20:10.674+0000",
        "issuetype": {
            "self": "https://jira.example.com/rest/api/2/issuetype/3",
            "id": "3",
            "description": "A task that needs to be done.",
            "iconUrl": "https://jira.example.com/secure/viewavatar?size=xsmall&avatarId=10318&avatarType=issuetype",
            "name": "Task",
            "subtask": false,
            "hierarchyLevel": 0
        },
        "parent": {
            "id": "10001",
            "key": "PRJ-2",
            "self": "https://jira.example.com/rest/api/2/issue/10001",
            "fields": {
                "summary": "Parent Issue",
                "status": {
                    "self": "https://jira.example.com/rest/api/2/status/1",
                    "description": "The issue is open and ready for the assignee to start work on it.",
                    "iconUrl": "https://jira.example.com/images/icons/statuses/open.png",
                    "name": "Open",
                    "id": "1",
                    "statusCategory": {
                        "self": "https://jira.example.com/rest/api/2/statuscategory/2",
                        "id": 2,
                        "key": "new",
                        "colorName": "blue-gray",
                        "name": "To Do"
                    }
                },
                "priority": {
                    "self": "https://jira.example.com/rest/api/2/priority/3",
                    "iconUrl": "https://jira.example.com/images/icons/priorities/major.png",
                    "name": "Major",
                    "id": "3"
                },
                "issuetype": {
                    "self": "https://jira.example.com/rest/api/2/issuetype/5",
                    "id": "5",
                    "description": "The sub-task of the issue",
                    "iconUrl": "https://jira.example.com/secure/viewavatar?size=xsmall&avatarId=10316&avatarType=issuetype",
                    "name": "Sub-task",
                    "subtask": true,
                    "hierarchyLevel": 1
                }
            }
        },
        "project": {
            "self": "https://jira.example.com/rest/api/2/project/10000",
            "id": "10000",
            "key": "PRJ",
            "name": "Project",
            "projectTypeKey": "business",
            "simplified": true,
            "avatarUrls": {
                "48x48": "https://jira.example.com/secure/projectavatar?pid=10000&avatarId=10011",
                "24x24": "https://jira.example.com/secure/projectavatar?size=medium&pid=10000&avatarId=10011",
                "16x16": "https://jira.example.com/secure/projectavatar?size=xsmall&pid=10000&avatarId=10011",
                "32x32": "https://jira.example.com/secure/projectavatar?size=small&pid=10000&avatarId=10011"
            }
        },
        "fixVersions": [],
        "workratio": -1,
        "lastViewed": "2021-08-02T14:28:01.332+0000",
        "watches": {
            "self": "https://jira.example.com/rest/api/2/issue/PRJ-1/watchers",
            "watchCount": 3,
            "isWatching": false
        },
        "created": "2021-08-01T14:20:10.674+0000",
        "priority": {
            "self": "https://jira.example.com/rest/api/2/priority/3",
            "iconUrl": "https://jira.example.com/images/icons/priorities/major.png",
            "name": "Major",
            "id": "3"
        },
        "labels": [\
            "api",\
            "jira"\
        ],
        "customfield_10018": {
            "hasEpicLinkFieldDependency": false,
            "showField": true,
            "nonEditableReason": {
                "reason": "NOT_EDITABLE",
                "message": "This field cannot be edited."
            }
        },
        "customfield_10019": "10031",
        "versions": [],
        "issuelinks": [],
        "assignee": {
            "self": "https://jira.example.com/rest/api/2/user?username=assignee",
            "accountId": "5b10ac8d82e05b22cc7d4ef5",
            "emailAddress": "assignee@example.com",
            "avatarUrls": {
                "48x48": "https://jira.example.com/secure/useravatar?ownerId=5b10ac8d82e05b22cc7d4ef5&avatarId=10346",
                "24x24": "https://jira.example.com/secure/useravatar?size=medium&ownerId=5b10ac8d82e05b22cc7d4ef5&avatarId=10346",
                "16x16": "https://jira.example.com/secure/useravatar?size=xsmall&ownerId=5b10ac8d82e05b22cc7d4ef5&avatarId=10346",
                "32x32": "https://jira.example.com/secure/useravatar?size=small&ownerId=5b10ac8d82e05b22cc7d4ef5&avatarId=10346"
            },
            "displayName": "Assignee Name",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "updated": "2021-08-02T14:28:01.332+0000",
        "status": {
            "self": "https://jira.example.com/rest/api/2/status/1",
            "description": "The issue is open and ready for the assignee to start work on it.",
            "iconUrl": "https://jira.example.com/images/icons/statuses/open.png",
            "name": "Open",
            "id": "1",
            "statusCategory": {
                "self": "https://jira.example.com/rest/api/2/statuscategory/2",
                "id": 2,
                "key": "new",
                "colorName": "blue-gray",
                "name": "To Do"
            }
        },
        "components": [],
        "customfield_10014": "10020",
        "summary": "This is a summary of the issue",
        "creator": {
            "self": "https://jira.example.com/rest/api/2/user?username=creator",
            "accountId": "5b109f2e9729b51b54dc274d",
            "emailAddress": "creator@example.com",
            "avatarUrls": {
                "48x48": "https://jira.example.com/secure/useravatar?ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "24x24": "https://jira.example.com/secure/useravatar?size=medium&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "16x16": "https://jira.example.com/secure/useravatar?size=xsmall&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "32x32": "https://jira.example.com/secure/useravatar?size=small&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343"
            },
            "displayName": "Creator Name",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "subtasks": [],
        "reporter": {
            "self": "https://jira.example.com/rest/api/2/user?username=reporter",
            "accountId": "5b109f2e9729b51b54dc274d",
            "emailAddress": "reporter@example.com",
            "avatarUrls": {
                "48x48": "https://jira.example.com/secure/useravatar?ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "24x24": "https://jira.example.com/secure/useravatar?size=medium&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "16x16": "https://jira.example.com/secure/useravatar?size=xsmall&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343",
                "32x32": "https://jira.example.com/secure/useravatar?size=small&ownerId=5b109f2e9729b51b54dc274d&avatarId=10343"
            },
            "displayName": "Reporter Name",
            "active": true,
            "timeZone": "Australia/Sydney",
            "accountType": "atlassian"
        },
        "aggregateprogress": {
            "progress": 0,
            "total": 0
        },
        "customfield_10000": "10002",
        "progress": {
            "progress": 0,
            "total": 0
        },
        "votes": {
            "self": "https://jira.example.com/rest/api/2/issue/PRJ-1/votes",
            "votes": 0,
            "hasVoted": false
        }
    },
    "renderedFields": {
        "statuscategorychangedate": "2021-08-01T14:20:10.674+0000",
        "lastViewed": "2021-08-02T14:28:01.332+0000",
        "created": "2021-08-01T14:20:10.674+0000",
        "customfield_10017": "10019",
        "updated": "2021-08-02T14:28:01.332+0000",
        "description": "This is a description of the issue",
        "environment": "Testing environment"
    }
}
```

### Use a unified ticketing API to integrate at scale

In this article, we walked through the process of getting tickets from Jira using Python. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tasks—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's Ticketing and Project Management Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tickets-from-jira-using-python) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e7c5b6c7-6e01-4a8f-88c1-130ebf3cf5a7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bcc90819-d4cd-4961-ab2f-cbefc4481a91&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tickets-from-jira-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e7c5b6c7-6e01-4a8f-88c1-130ebf3cf5a7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bcc90819-d4cd-4961-ab2f-cbefc4481a91&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tickets-from-jira-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=a2e8e799-0b63-4e83-adc6-292c951c1afd&bo=2&sid=da106d703e8b11f0840a815ace9b1dd9&vid=da10b3a03e8b11f089b30dfc453ad24e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20tickets%20from%20Jira%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tickets-from-jira-using-python&r=&lt=576&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=295297)