---
url: "https://www.merge.dev/blog/how-to-use-python-to-get-tasks-from-clickup"
title: "How to use python to get tasks from ClickUp"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-use-python-to-get-tasks-from-clickup#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-use-python-to-get-tasks-from-clickup#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-use-python-to-get-tasks-from-clickup#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-use-python-to-get-tasks-from-clickup)

##### Just for you

No items found.

# How to use python to get tasks from ClickUp

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae2cda4f9f53213290_ClickUp.webp)

No items found.

_This tutorial is part of a series on building product integrations._

You can think of **ClickUp** as a digital command center. It's a unified hub where teams can easily track and manage tasks, projects, and workflows. ClickUp’s API allows you to pull tasks and analyze task details for a range of use cases. In this article, we'll walk through how to use Python to connect to the ClickUp API, including:

1. How to get your ClickUp API authentication up and running
2. How to pull data from ClickUp in a normalized format, including how to make get requests for retrieving tasks
3. How a single API endpoint can be your gateway to hundreds of different third-party ticketing systems

{{blog-cta-100+}}

### Initial setup

To access tasks from the ClickUp API, you need to make a **GET** request. The endpoint for accessing tasks is \`https://api.clickup.com/api/v2/list/{list\_id}/task\`, where {list\_id} is the id of the list from which you want to pull tasks.

Here is a sample Python code snippet for making the **GET** request:

```python

import requests

url = 'https://api.clickup.com/api/v2/list/{list_id}/task'
headers = {
    'Authorization': 'ACCESS_TOKEN',
    'Content-Type': 'application/json'
}

response = requests.get(url, headers=headers)

tasks = response.json()

```

Replace ' **ACCESS\_TOKEN**' with your actual access token and {list\_id} with the id of the list from which you want to retrieve tasks. The response from the API will be in JSON format, which you can then parse to access the tasks.

**_Note_** _: The ClickUp API uses rate limiting to protect the service from being overloaded with requests. The rate limits are 100 requests per second per workspace, and 1000 requests per 15 minutes per IP address. If you exceed these limits, the API will respond with a 429 Too Many Requests status code. Make sure to implement proper error handling in your code to manage these situations._

Firstly, we require the `requests` and `json` libraries. If they are not already installed, you can add them using pip:

```python

pip install requests
pip install json

```

### Accessing tasks from the ClickUp API

Next, let’s actually get tickets from the ClickUp API. We’ll need to first obtain the access token:

```python

import requests
import json

# Client ID and secret provided by ClickUp
client_id = 'your_client_id'
client_secret = 'your_client_secret'

# URL to get the access token
token_url = 'https://api.clickup.com/api/v2/oauth/token'

# Request body parameters
params = {
    "client_id": client_id,
    "client_secret": client_secret,
    "grant_type": "authorization_code",
    "redirect_uri": "your_redirect_url",
    "code": "authorization_code_from_redirect_uri"
}

# Request the access token
response = requests.post(token_url, data=params)

# Parse the JSON response
json_response = json.loads(response.text)

# Extract the access token
access_token = json_response['access_token']

```

The access token is then used in the header of every request to the API in the format `Authorization: {ACCESS-TOKEN}`:

```python

headers = {
    "Authorization": access_token
}

```

Next, we get the teams:

```python

# URL to get the teams
teams_url = 'https://api.clickup.com/api/v2/team'

# Request the teams
response = requests.get(teams_url, headers=headers)

# Parse the JSON response
json_response = json.loads(response.text)

# Extract the teams
teams = json_response['teams']

```

Finally, for each team, we retrieve its tasks. The code below will give you access to all tasks for all teams. Remember to replace `your_client_id`, `your_client_secret`, `your_redirect_url`, and `authorization_code_from_redirect_uri` with your actual ClickUp credentials.

```python

# Loop over the teams
for team in teams:
    # URL to get the tasks
    tasks_url = f'https://api.clickup.com/api/v2/team/{team["id"]}/task'

    # Request the tasks
    response = requests.get(tasks_url, headers=headers, params={
        "order_by": "updated",
        "subtasks": True,
        "include_closed": True
    })

    # Parse the JSON response
    json_response = json.loads(response.text)

    # Extract the tasks
    tasks = json_response['tasks']

    # Process the tasks
    for task in tasks:
        # Add your code here

```

This is an example of an individual item returned by this API Endpoint:

```json
{
    "id": "task1",
    "url": "https://taskurl.com",
    "list": {
        "id": "list1",
        "name": "Task List",
        "access": true
    },
    "name": "New Task",
    "tags": [\
        {\
            "name": "urgent",\
            "tag_bg": "#FF0000",\
            "tag_fg": "#FFFFFF",\
            "creator": 12345\
        }\
    ],
    "space": {
        "id": "space1"
    },
    "folder": {
        "id": "folder1",
        "name": "Task Folder",
        "access": true,
        "hidden": false
    },
    "parent": "parent1",
    "status": {
        "type": "InProgress",
        "color": "#FFFF00",
        "status": "active",
        "orderindex": 1
    },
    "creator": {
        "id": 12345,
        "color": "#0000FF",
        "email": "creator@email.com",
        "username": "creatorusername",
        "profilePicture": "https://profilepicture.com"
    },
    "project": {
        "id": "project1",
        "name": "Project Name",
        "access": true,
        "hidden": false
    },
    "team_id": "team1",
    "archived": false,
    "due_date": "2022-12-30",
    "priority": {
        "id": "priority1",
        "color": "#FF0000",
        "priority": "high",
        "orderindex": "1"
    },
    "watchers": [],
    "assignees": [\
        {\
            "id": 12345,\
            "color": "#0000FF",\
            "email": "assignee@email.com",\
            "initials": "AS",\
            "username": "assigneeusername"\
        }\
    ],
    "checklists": [],
    "orderindex": "1",
    "time_spent": 120,
    "date_closed": "2022-12-31",
    "description": "Task description",
    "date_created": "2022-01-01",
    "date_updated": "2022-01-02",
    "dependencies": [],
    "linked_tasks": [],
    "text_content": "Task text content",
    "custom_fields": [\
        {\
            "id": "custom1",\
            "name": "Custom Field",\
            "type": "text",\
            "required": false,\
            "type_config": {\
                "default": 1,\
                "options": [\
                    {\
                        "id": "option1",\
                        "name": "Option 1",\
                        "orderindex": 1\
                    }\
                ]\
            },\
            "date_created": "2022-01-01",\
            "hide_from_guests": false\
        }\
    ],
    "permission_level": "admin"
}
```

### Use a unified ticketing API to integrate at scale

In this article, we walked through the process of getting Tasks from ClickUp using Python. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tasks—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's Ticketing and Project Management Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-use-python-to-get-tasks-from-clickup) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c9ddf37b-e53e-4b16-9e36-27c2eb9f7abb&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a166b732-f451-4569-911c-a3cc4bb5551d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tasks-from-clickup&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c9ddf37b-e53e-4b16-9e36-27c2eb9f7abb&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a166b732-f451-4569-911c-a3cc4bb5551d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tasks-from-clickup&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=af238c43-4c34-4942-b20f-83b1a17faa0e&bo=2&sid=e687c3e03e8d11f09cb0118c3bb7d2fc&vid=e6883f303e8d11f0806193bdecf778b1&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20use%20python%20to%20get%20tasks%20from%20ClickUp&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tasks-from-clickup&r=&lt=529&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=366901)