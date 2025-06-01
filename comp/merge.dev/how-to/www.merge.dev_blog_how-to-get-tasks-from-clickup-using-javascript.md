---
url: "https://www.merge.dev/blog/how-to-get-tasks-from-clickup-using-javascript"
title: "How to get tasks from ClickUp using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-tasks-from-clickup-using-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-tasks-from-clickup-using-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-tasks-from-clickup-using-javascript#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tasks-from-clickup-using-javascript)

##### Just for you

No items found.

# How to get tasks from ClickUp using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c752d0976eef5e0ea4a_ClickUp_hero_image.webp)

No items found.

_This tutorial is part of a series on building product integrations._

### What is ClickUp?

ClickUp is an all-in-one project management tool that empowers teams to manage tasks, projects, and workflows efficiently. It's packed with features ranging from process management to time tracking and collaboration tools, enabling teams to simplify operations and boost productivity. ClickUp comes with a powerful API, allowing you to retrieve tasks and integrate with other software or platforms.

#### What you’ll learn

By using the ClickUp API, you can expand and customize ClickUp's functionality, leading to more user functionality for your customers. In this tutorial, we’ll cover accessing tasks from a customer’s ClickUp system including:

- Navigating your way through ClickUp API authentication
- Understanding how to extract \[normalized data\] from ClickUp, including executing get requests for task retrieval
- Ways to use a single API endpoint to connect with hundreds of different third-party ticketing systems

### Getting started with authentication

To get tasks from the ClickUp API, you will need to make a **GET** request to the ClickUp API endpoint for tasks. The endpoint URL is: \` **https://api.clickup.com/api/v2/list/{list\_id}/task** \`. The \` **list\_id** \` parameter in the URL should be replaced with the ID of the list that you want to retrieve tasks from.

**Note**: this will only return tasks from the specific list, not from any sublists.

### Getting tickets from ClickUp

An example of a JavaScript **GET** request to the ClickUp API might look like this:

```javascript

fetch('https://api.clickup.com/api/v2/list/{list_id}/task', {
    method: 'GET',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': {ACCESS-TOKEN}
    }
})
.then(response => response.json())
.then(data => console.log(data));

```

In this code, replace \`{list\_id}\` with the ID of your list, and \`{ACCESS-TOKEN}\` with your access token. The \`fetch\` function sends a GET request to the ClickUp API, and the headers object includes the necessary authorization and content type headers.

The response from the ClickUp API will be a JSON object, which we convert to a JavaScript object with \`response.json()\`. The resulting \`data\` object will be an array of task objects, each with properties such as \`id\`, \`name\`, \`status\`, \`assignees\`, \`due\_date\`, and more.

‍ **Remember to handle any errors that might occur during the fetch operation**. You can do this by adding a \`.catch()\` block to the promise chain:

```javascript

fetch('https://api.clickup.com/api/v2/list/{list_id}/task', {
    method: 'GET',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': {ACCESS-TOKEN}
    }
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));

```

This will log any errors to the console, but in a production environment, you might want to handle errors in a different way, such as by displaying an error message to the user.

The following script first gets the access token using the provided client ID, client secret, and authorization code. It then fetches the teams from the ClickUp API and for each team, it gets the tasks in a paginated manner. The `fetchTasks` function is recursive and continues to fetch the next page of tasks as long as tasks are returned from the API. When no more tasks are returned, the recursion stops and the function returns.

````javascript

```javascript
const axios = require('axios');
const client_id = 'YOUR_CLIENT_ID'; // Replace with your client ID
const client_secret = 'YOUR_CLIENT_SECRET'; // Replace with your client secret
let access_token = '';

// Fetch access token
axios.post('https://api.clickup.com/api/v2/oauth/token', {
client_id: client_id,
client_secret: client_secret,
code: 'AUTHORIZATION_CODE' // Replace with your authorization code
}).then(response => {
access_token = response.data.access_token;

// Fetch teams
axios.get('https://api.clickup.com/api/v2/team', {
    headers: {
      Authorization: access_token
    }
}).then(response => {
    const teams = response.data.teams;

    // Fetch tasks for each team
    teams.forEach(team => {
      let page = 0;
      const team_id = team.id;

      const fetchTasks = () => {
        axios.get(`https://api.clickup.com/api/v2/team/${team_id}/task`, {
          params: {
            order_by: 'updated',
            subtasks: true,
            include_closed: true,
            page: page
          },
          headers: {
            Authorization: access_token
          }
        }).then(response => {
          const tasks = response.data.tasks;
          // Process tasks here

          if (tasks && tasks.length > 0) {
            // If there are tasks, fetch next page
            page++;
            fetchTasks();
          }
        }).catch(error => {
          console.error('Error fetching tasks:', error);
        });
      };

      // Start fetching tasks
      fetchTasks();
    });
}).catch(error => {
    console.error('Error fetching teams:', error);
});
}).catch(error => {
console.error('Error fetching access token:', error);
});
```
````

**You should replace** `YOUR_CLIENT_ID`, `YOUR_CLIENT_SECRET`, and `AUTHORIZATION_CODE` **with your actual client ID, client secret, and authorization code**. Also replace `// Process tasks here` with whatever you want to do with the tasks (e.g., printing them out, storing them in a database, etc.).

An example of an individual item returned by this API Endpoint is:

```json
{
    "id": "task1",
    "url": "https://app.clickup.com/t/task1",
    "list": {
        "id": "list1",
        "name": "Design",
        "access": true
    },
    "name": "Design Homepage",
    "tags": [\
        {\
            "name": "design",\
            "tag_bg": "#f2f2f2",\
            "tag_fg": "#000000",\
            "creator": 1\
        }\
    ],
    "space": {
        "id": "space1"
    },
    "folder": {
        "id": "folder1",
        "name": "Website Redesign",
        "access": true,
        "hidden": false
    },
    "parent": "task0",
    "status": {
        "type": "Open",
        "color": "#ff0000",
        "status": "active",
        "orderindex": 1
    },
    "creator": {
        "id": 1,
        "color": "#f2f2f2",
        "email": "johndoe@example.com",
        "username": "johndoe",
        "profilePicture": "https://example.com/profile.jpg"
    },
    "project": {
        "id": "project1",
        "name": "Website Redesign",
        "access": true,
        "hidden": false
    },
    "team_id": "team1",
    "archived": false,
    "due_date": "2022-12-31T00:00:00.000Z",
    "priority": {
        "id": "high",
        "color": "#ff0000",
        "priority": "High",
        "orderindex": "1"
    },
    "watchers": [],
    "assignees": [\
        {\
            "id": 1,\
            "color": "#f2f2f2",\
            "email": "johndoe@example.com",\
            "initials": "JD",\
            "username": "johndoe",\
            "profilePicture": null\
        }\
    ],
    "checklists": [],
    "orderindex": "1",
    "time_spent": 3600,
    "date_closed": null,
    "description": "Design the new homepage for the website.",
    "date_created": "2022-01-01T00:00:00.000Z",
    "date_updated": "2022-01-02T00:00:00.000Z",
    "dependencies": [],
    "linked_tasks": [],
    "text_content": "Design the new homepage with a modern and clean look.",
    "custom_fields": [\
        {\
            "id": "custom1",\
            "name": "Notes",\
            "type": "text",\
            "required": false,\
            "type_config": {\
                "default": null,\
                "options": [],\
                "placeholder": null\
            },\
            "date_created": "2022-01-01T00:00:00.000Z",\
            "hide_from_guests": false\
        }\
    ],
    "time_estimate": null,
    "permission_level": "admin"
}
```

### Use a unified ticketing API to integrate at scale

In this article, we walked through the process of getting Tasks from ClickUp using JavaScript. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tasks—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's Ticketing and Project Management Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-tasks-from-clickup-using-javascript) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5a2fc24a-5021-4d91-8b91-2365750f0514&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a6cb10d4-5a79-4d0b-adc4-3ea973a749d5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tasks-from-clickup-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5a2fc24a-5021-4d91-8b91-2365750f0514&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a6cb10d4-5a79-4d0b-adc4-3ea973a749d5&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tasks-from-clickup-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=2ef322e6-490b-4fbe-9b4d-a9676d1f5513&bo=2&sid=ce9926003e8d11f0a981f96093e3802b&vid=ce993b003e8d11f0aee99d92210c589a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20tasks%20from%20ClickUp%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-tasks-from-clickup-using-javascript&r=&lt=388&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=503446)