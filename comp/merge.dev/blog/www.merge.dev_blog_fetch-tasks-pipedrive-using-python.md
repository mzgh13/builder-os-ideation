---
url: "https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python"
title: "How to fetch tasks from Pipedrive using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python#)

Table of contents

[Authentication](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python#authentication)

[How to retrieve tasks from Pipedrive](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python#how-to-retrieve-tasks-from-pipedrive)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffetch-tasks-pipedrive-using-python)

##### Just for you

No items found.

# How to fetch tasks from Pipedrive using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Pipedrive is a comprehensive customer relationship management (CRM) platform that lets you track interactions with potential clients, organize contacts, dissect sales data for business strategy optimization, and more.

The platform collects various types of data that can be valuable to your product, and its tasks are no exception. You can post tasks to your business communications platform (e.g. Slack) to make them more visible; sync them with your ticketing tool when there’s issues at an account and additional stakeholders need to be looped in—and much more.

To help facilitate these use cases, we’ll walk you through the process of collecting a list of tasks from Pipedrive by connecting to [its API](https://developers.pipedrive.com/docs/api/v1).

## **Authentication**

To access data from the Pipedrive API, authentication is required. This is performed using an API token which can be found in the Pipedrive web app settings.

Once you have your API token, it needs to be included in every API request you make to Pipedrive. The token is added to the request headers as the value of the 'Authorization' key.

## How to retrieve tasks from Pipedrive

The script below first defines the base URL for the Pipedrive API, using the provided domain and API key. It then sets up the query parameters for the request, including the type of activity (task), the number of items to request (limit), and the starting point for the request (start). The script then enters a loop, where it sends a GET request to the Pipedrive API and processes the response.

The response is parsed as JSON, and the tasks are extracted from the 'data' field of the response. The script prints out each task, and the loop continues as long as there are more items in the collection, as indicated by the 'more\_items\_in\_collection' field in the 'additional\_data'->'pagination' path of the response. For each iteration of the loop, the 'start' parameter is incremented by the 'limit' to fetch the next batch of tasks.

```python

import requests
import json
# Your Pipedrive domain and API key
DOMAIN = "your_domain"
API_KEY = "your_api_key"
# Base URL for the Pipedrive API
BASE_URL = f"https://{DOMAIN}.pipedrive.com/api/v1/activities?api_token={API_KEY}"
# Define query parameters
params = {
    "type": "task",
    "limit": 50,
    "start": 0
}
while True:
    response = requests.get(BASE_URL, params=params)
    data = response.json()
    tasks = data['data']
    for task in tasks:
        # Process task data here
        print(task)
    # Check for more items
    if not data['additional_data']['pagination']['more_items_in_collection']:
        break
    # Update the 'start' parameter for pagination
    params['start'] += params['limit']

```

Here’s a potential response from this API endpoint:

```python

{
    "id": 1,
    "done": false,
    "type": "Call",
    "subject": "Follow up with client",
    "user_id": 123,
    "add_time": "2022-01-01T10:30:00Z",
    "due_date": "2022-01-02",
    "due_time": "10:00:00",
    "duration": "00:30:00",
    "type_name": "Phone Call",
    "company_id": 456,
    "owner_name": "John Doe",
    "active_flag": true,
    "update_time": "2022-01-01T11:00:00Z",
    "public_description": "Call to discuss project details",
    "assigned_to_user_id": 789,
    "marked_as_done_time": "2022-01-02T10:30:00Z",
    "created_by_user_id": 123
}

```

### **Looking to connect to more CRMs?**

For those seeking to establish connections with multiple CRM systems, Merge's [CRM Unified API](https://merge.dev/categories/crm-api) provides an efficient solution.

It allows you to access numerous CRM platforms, Pipedrive included, via a single API, thereby letting you offer multiple integrations while letting your engineers focus on your core product.

To learn more about Merge, you can [request a demo](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffetch-tasks-pipedrive-using-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b59d8073-15a8-4fa4-9cdb-2dac0cf52dc3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=544cedc1-bfb3-438a-baa5-a99ea9007447&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-tasks-pipedrive-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b59d8073-15a8-4fa4-9cdb-2dac0cf52dc3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=544cedc1-bfb3-438a-baa5-a99ea9007447&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-tasks-pipedrive-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0eb215bc-dd4b-4e8a-8a98-fbff705eb071&bo=2&sid=4135b2e03e8d11f0810ee9a9b8f684ba&vid=4135ef803e8d11f0acaebbe024a222f2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20tasks%20from%20Pipedrive%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-tasks-pipedrive-using-python&r=&lt=460&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=106993)