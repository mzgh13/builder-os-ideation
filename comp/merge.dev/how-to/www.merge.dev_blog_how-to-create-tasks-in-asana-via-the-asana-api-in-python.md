---
url: "https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python"
title: "How to create tasks in Asana via the Asana API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#prerequisites)

[Create a New Python Script](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#create-a-new-python-script)

[Handle Asana API Authentication](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#handle-asana-api-authentication)

[Create Tasks in Asana](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#create-tasks-in-asana)

[Fetch Tasks from Asana](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#fetch-tasks-from-asana)

[Final Thoughts](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-create-tasks-in-asana-via-the-asana-api-in-python)

##### Just for you

No items found.

# How to create tasks in Asana via the Asana API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cec57442f8cef1eb2a1_How_to_Create_Tasks_in_Asana_via_the_Asana_API_in_Python.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Kumar Harsh

@Merge

Asana, one of the most popular project management tools on the market, makes it easy to manage and collaborate on projects of all scales across platforms. It's not only easy to learn and use; it also offers integrations with a wide range of third-party tools and services.

Despite all these integrations, you still might need to access tasks and other data via APIs. For example, you might be [building a custom integration](https://www.merge.dev/blog/custom-api-integration), want to connect Asana with internal apps or tools, or set up custom automations. The Asana API can help you in these cases.

In this tutorial, you'll learn how to use the Asana API to create new tasks and fetch all available tasks programmatically using a Python script. The complete code for this tutorial is available in [this GitHub repo](https://gist.github.com/krharsh17/585d54e60dc808607d7587a7ff3b22b7).

## Prerequisites

To follow along with this tutorial, you'll need a local installation of [Python](https://realpython.com/installing-python/) and an [Asana account](https://asana.com/create-account).

## Create a New Python Script

The first step is to create a new Python script file by running the following command:

```bash
touch script.py

```

Alternatively, you can use any editor of your choice to create the file.

You also need to create an **input.csv** file to store the details of the tasks that the script will create in Asana. Use the following data for now:

```csv
Purchase ingredients, Purchase the ingredients required to make coffee, 2023-01-10,
Send out invitations, Send out the invitations for the housewarming party, 2023-01-11,
Buy grocery, Buy groceries for the next week, 2023-01-08

```

Each row on the CSV file above contains the following information:

- Task name (e.g., Purchase Ingredients)
- Task notes (e.g., Purchase the ingredients required to make coffee)
- Due On date (e.g., 2023-01-10)

You can add any [other attributes](https://developers.asana.com/docs/create-a-task) to your Asana tasks using the API, but for the sake of brevity, this tutorial uses only the attributes above.

_Related:_ [_The 7 steps for creating your access token in Asana_](https://www.merge.dev/blog/asana-personal-access-token)

## Handle Asana API Authentication

To interact with the Asana API, you must generate a [personal access token](https://developers.asana.com/docs/personal-access-token). Generating one is simple:

- Navigate to the [developer console](https://app.asana.com/-/developer_console).
- Click on the **Create new token** button.

[![Asana developer console](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4fb229d21b972a017d_ROpMGlu.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4fb229d21b972a017d_ROpMGlu.webp)

- Enter a description for the token and click on the **Create token** button.

[![Creating a new token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4f3915f817edab272d_PNEgeDl.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4f3915f817edab272d_PNEgeDl.webp)

- Asana will show you the token's value. Copy and store it safely as you will not be able to see this token again. You can always create a new token, but each token will be visible to you only once right after you create it.

[![Token created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4f9a879fc1c93bd902_cbvE6bL.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6453fe4f9a879fc1c93bd902_cbvE6bL.webp)

To use the token in your script, create a variable and store the token's value in it.

```python
PAT_TOKEN = ''
```

You'll now see how to use this token to authenticate a simple request to the Asana API that fetches your user details.

Install pip install requests and import the requests package in your script:

```python
import requests'
```

Next, define a few constants that you'll use in your requests:

```python
PAT_TOKEN = ''
BASE_URL = 'https://app.asana.com/api/1.0' # The base URL for the Asana API
USERS_ENDPOINT = '/users/me' # The users endpoint to fetch your own details
TASKS_ENDPOINT = '/tasks' # The tasks endpoint to create and fetch tasks from
'
```

Finally, write the request to fetch your own details:

```python
result = requests.get(
        BASE_URL + USERS_ENDPOINT,
        headers={
            'Content-Type': 'application/json',
            'Accept': 'application/json',
            'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
        }
    )

data = result.json()

print(data)

```

The result should look like this:

```bash
{"data":{"gid":"1203633602789119","email":"kumar@draft.dev","name":"Kumar Harsh","photo":null,"resource_type":"user","workspaces":[{"gid":"12036336567142129","name":"draft.dev","resource_type":"workspace"}]}}

```

It signifies that you have correctly set up authentication in your code for the Asana API.

Before continuing, you need to take care of one more thing. When creating tasks in Asana, you must associate them with a workspace, project, or a parent task. When fetching tasks from Asana, you need to specify either a project, tag, or a combination of workspace and assignee to filter the tasks before retrieving them.

To keep things simple, you'll use the default workspace and your own user ID as assignee with which to associate your tasks. The request that you created earlier in this tutorial fetched both of these details. All you now need to do is to wrap the request into a method and have it return only the two IDs you need. Here's what the method looks like:

```python
def getIds():
    result = requests.get(
        BASE_URL + USERS_ENDPOINT,
        headers={
            'Content-Type': 'application/json',
            'Accept': 'application/json',
            'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
        }
    )

    data = result.json()

    workspaceId = data["data"]["workspaces"][0]["gid"]
    assigneeId = data["data"]["gid"]

    return workspaceId, assigneeId

```

At this point, your **script.py** file should look like this:

```python
import requests

PAT_TOKEN = ""
BASE_URL = 'https://app.asana.com/api/1.0'
USERS_ENDPOINT = '/users/me'
TASKS_ENDPOINT = '/tasks'

HEADERS = {
    'Content-Type': 'application/json',
    'Accept': 'application/json',
    'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
},

def getIds():
    result = requests.get(
        BASE_URL + USERS_ENDPOINT,
        headers={
            'Content-Type': 'application/json',
            'Accept': 'application/json',
            'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
        }
    )

    data = result.json()

    workspaceId = data["data"]["workspaces"][0]["gid"]
    assigneeId = data["data"]["gid"]

    return workspaceId, assigneeId

```

## Create Tasks in Asana

Now you're ready to write the function that will create new tasks in Asana. To allow bulk task creation, you'll take input from the CSV file as described earlier and create a task for each row of the file:

```python
import csv

def createTasks():

    workspaceId, assigneeId = getIds()

    with open('./input.csv', 'r') as file:
        reader = csv.reader(file)
        for row in reader:
            data = {
                "data": {
                    "name": row[0].strip(), # Fetch from input file and strip any extra whitespaces from the text
                    "notes": row[1].strip(),
                    "due_on": row[2].strip(),
                    "workspace": workspaceId, # Add the default workspace ID
                    "assignee": assigneeId # Assign the task to the current user
                }
            }

            result = requests.post(
                BASE_URL + TASKS_ENDPOINT,
                headers={
                    'Content-Type': 'application/json',
                    'Accept': 'application/json',
                    'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
                },
                json=data
            )

            print(result.json())

```

The code is fairly simple to understand. You start by fetching the workspace and assignee IDs using the function you created earlier. Next, you open the input file and process each of its rows individually. For each row, you create a data object and send a request to the Asana API with the data object attached. Lastly, you print the result of the request.

You'll receive the details of the newly created tasks in response to your request. Here's what it will look like:

```bash
{'data': {'gid': '1203633772927990', 'projects': [], 'memberships': [], 'resource_type': 'task', 'created_at': '2023-01-01T23:03:02.484Z', 'modified_at': '2023-01-01T23:03:03.100Z', 'name': 'Purchase ingredients', 'notes': 'Purchase the ingredients required to make coffee', 'assignee': {'gid': '1203633602142119', 'resource_type': 'user', 'name': 'Kumar Harsh'}, 'completed': False, 'assignee_status': 'inbox', 'completed_at': None, 'due_on': '2023-01-10', 'due_at': None, 'resource_subtype': 'default_task', 'start_on': None, 'start_at': None, 'tags': [], 'workspace': {'gid': '1203633602142129', 'resource_type': 'workspace', 'name': 'draft.dev'}, 'num_hearts': 0, 'num_likes': 0, 'permalink_url': 'https://app.asana.com/0/1203633602142143/1203633772927990', 'parent': None, 'hearted': False, 'hearts': [], 'liked': False, 'likes': [], 'followers': [{'gid': '1203633602142119', 'resource_type': 'user', 'name': 'Kumar Harsh'}], 'assignee_section': {'gid': '1203633602142159', 'resource_type': 'section', 'name': '📬 New tasks'}, 'custom_fields': []}}
...

```

## Fetch Tasks from Asana

Next, you'll fetch the tasks you created by creating another function:

```python
def getAllTasks():

    workspaceId, assigneeId = getIds()

    result = requests.get(
        BASE_URL + TASKS_ENDPOINT +
        '?workspace={}&assignee={}'.format(workspaceId, assigneeId),
        headers={
            'Content-Type': 'application/json',
            'Accept': 'application/json',
            'Authorization': 'Bearer {}'.format(PAT_TOKEN) # Adding the PAT token for authentication
        }
    )
    data = result.json()["data"]

    print("Total number of tasks", len(data))
    print("Tasks ->")
    print(data)

```

This code is also straightforward. You're fetching the workspace and assignee IDs first. Then, you're making a request to the Asana API to fetch all tasks associated with the given workspace and assignee. Finally, you're counting the number of tasks and printing their details.

Here's how the output should look:

```bash
Total number of tasks 9
Tasks ->
[{'gid': '1203633604772198', 'name': 'Schedule brainstorm', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633604772200', 'name': 'Draft project proposal', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633604772202', 'name': 'Incorporate feedback', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633669717610', 'name': 'Buy grocery', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633604772184', 'name': '1️⃣ First: Get started using My Tasks', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633604772183', 'name': "2️⃣ Second: Find the layout that's right for you", 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633604772182', 'name': '3️⃣ Third: Get organized with sections', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633772927990', 'name': 'Purchase ingredients', 'resource_type': 'task', 'resource_subtype': 'default_task'}, {'gid': '1203633703510178', 'name': 'Send out invitations', 'resource_type': 'task', 'resource_subtype': 'default_task'}]

```

You can find the complete code for this tutorial [here](https://gist.github.com/krharsh17/585d54e60dc808607d7587a7ff3b22b7).

## Final Thoughts

While the Asana platform offers a robust UI to manage your tasks, there might be situations where you'd want programmatic access to your tasks to set up automations. The Asana API can come in handy in such cases.

As this tutorial showed, the Asana API is straightforward to use for simple use cases. However, figuring out configurations and maintaining them over time can be challenging. This is where Merge can help.

Merge offers a single API to integrate numerous products and services with your app easily. It lets you connect with numerous HRIS, ATS, accounting, CRM, and ticketing APIs, including [Asana](https://merge.dev/integrations/asana). If you're a B2B company, you'll love the power and simplicity that Merge will bring to your third-party tool integrations.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Kumar Harsh

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7c3f3940-33f0-4ff4-a443-8e965a3d22b4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f759ec7c-4e32-4d84-a0d6-a038c23e1bc5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-create-tasks-in-asana-via-the-asana-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7c3f3940-33f0-4ff4-a443-8e965a3d22b4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f759ec7c-4e32-4d84-a0d6-a038c23e1bc5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-create-tasks-in-asana-via-the-asana-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=db2f5000-5272-46bc-be7d-f6b8220bfa04&bo=2&sid=45758e103e8c11f0ac993bd4a0b2bbd4&vid=4575c3d03e8c11f080fa8d6b6f307e7a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20create%20tasks%20in%20Asana%20via%20the%20Asana%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-create-tasks-in-asana-via-the-asana-api-in-python&r=&lt=756&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=262031)