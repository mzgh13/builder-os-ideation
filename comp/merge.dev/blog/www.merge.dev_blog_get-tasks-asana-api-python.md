---
url: "https://www.merge.dev/blog/get-tasks-asana-api-python"
title: "How to GET tasks from the Asana API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-tasks-asana-api-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-tasks-asana-api-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-tasks-asana-api-python#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/get-tasks-asana-api-python#prerequisites)

[Authenticating to the Asana tasks API](https://www.merge.dev/blog/get-tasks-asana-api-python#authenticating-to-the-asana-tasks-api)

[Generating a personal access token](https://www.merge.dev/blog/get-tasks-asana-api-python#generating-a-personal-access-token)

[Fetching tasks from the Asana API in Python](https://www.merge.dev/blog/get-tasks-asana-api-python#fetching-tasks-from-the-asana-api-in-python)

[Final thoughts](https://www.merge.dev/blog/get-tasks-asana-api-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-tasks-asana-api-python)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)**How to fetch tasks from Pipedrive using Python**](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cec57442f8cef1eb2a1_How_to_Create_Tasks_in_Asana_via_the_Asana_API_in_Python.webp)**How to create tasks in Asana via the Asana API in Python**](https://www.merge.dev/blog/how-to-create-tasks-in-asana-via-the-asana-api-in-python)

# How to GET tasks from the Asana API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735d06bd38a725e7fb_Rate_limiting_best_practices.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663cd9cbae01fdc89348c6ad_7E2A6999%20(1).webp)

Gabby Schwartz

Software Engineer

@Merge

While tasks in Asana can be used in a variety of ways, they’re even more valuable when they can be accessed by your other internal applications or your product.

Regardless of your specific integration use case, we'll walk through every step you should take to get tasks from the Asana API using Python.

## **Prerequisites**

To follow along, you’ll need:

- A valid [Asana account](https://app.asana.com/-/login?_gl=1*1ojnqd3*_ga*MTM0MDY2NzczNC4xNzE1MTk3NzU0*_ga_J1KDXMCQTH*MTcxNTE5Nzc1My4xLjEuMTcxNTE5Nzc2MS42MC4wLjU4MjQ4NTkyMg..*_fplc*WDNmJTJGdlRKRkFuY2olMkZmU0VxWjBzNGtXVHJIbU9wd1RBQkxQYnNvSm1HZmpOYW54MnUzb3Z3eTNFc3pvZE1BT3pyMWVIcXVrNmpab3hST0EyREt2bG9NQVV6aFZHUlRWdU1RbGtYT1YlMkY2MW1qUDZCbU4wOWtET01wdzZDaHZRJTNEJTNE)
- Python version 3.10 or later
- The python requests library installed in your environment (like your laptop)

## **Authenticating to the Asana tasks API**

There are 3 ways you can authenticate with Asana’s APIs **‍**

### **1\. Personal Access Token**

A personal access token is similar to a username & password when logging into Asana, but it grants you unique access to using their API endpoints associated with your account.

You have to generate a token through the Asana developer console. These tokens will be passed through the Authorization header when making requests.

Note: We’ll be using this token for our walkthrough. Learn more about [generating a personal access token in Asana](https://www.merge.dev/blog/asana-personal-access-token).

### **2\. OAuth**

OAuth provides an additional layer of security when sending in authorization tokens because your credentials are then “exchanged” for temporary access tokens. This process is also described in [Asana’s docs](https://developers.asana.com/docs/oauth).

### **3\. OpenID Connect**

This process uses JSON Web Tokens instead of access tokens for sending in authentication information. This requires an additional scope enabled for openid on your account. You can [read about](https://developers.asana.com/docs/openid-connect) this form of authentication with Asana.

## **Generating a personal access token**

You’ll need to generate a personal access token (“PAT”) through the Asana develop console.

1. Visit the [developer console](https://app.asana.com/0/my-apps) while logged into your Asana account.
2. Press “Create new token” and assign it a name that describes how this specific token will be used.

‍

[![Creating a token in Asana](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88ac2cdb9827c64171c_hOupC0q4TZb2AYwPUCIGeFkyLJkS5Tz1wVXyT3Of1U7Hi1OoFr79iwElIWapJVUj9O-_R2PesiVcICmfhI-13fguOLgpWEkDpdb971BtJeiRxRLlkD-Ogprtwc5rd42eAdTiaPHY0sT35rWHWbEhpwM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88ac2cdb9827c64171c_hOupC0q4TZb2AYwPUCIGeFkyLJkS5Tz1wVXyT3Of1U7Hi1OoFr79iwElIWapJVUj9O-_R2PesiVcICmfhI-13fguOLgpWEkDpdb971BtJeiRxRLlkD-Ogprtwc5rd42eAdTiaPHY0sT35rWHWbEhpwM.webp)

3. Note that you must save the token after you generate it, as there will be no way to access it after it has been created and shown to you. DO NOT store this token directly in your application code. Tokens should be treated similar to passwords and have the appropriate security protocols.

We are now ready to take our access token and make some authenticated requests!

When making a request, send your token through the headers as so:

```python

curl https://app.asana.com/api/1.0/users/me \
  	-H "Authorization: Bearer ACCESS_TOKEN"

```

## **Fetching tasks from the Asana API in Python**

We’ll walk through an example of fetching all of your organization’s tasks for a specific project through the Asana API. We will also go through adding some filters to make this API response more suited to our specific needs. The endpoint I’ll be using is [documented here](https://developers.asana.com/reference/gettasks).

First we’ll import the necessary requests package and construct the URL that we want to make a request to.

We know based on the documentation that our endpoint URL should be **https://app.asana.com/api/1.0/tasks.**

For this endpoint, we need to know the Project ID for the tasks we’re fetching.

If you log into Asana on your browser, click on a project under the “Projects Tab” that you want to retrieve the tasks for. When you do, you should get redirected to a URL that looks like **https://app.asana.com/0/{PROJECT\_ID}/{viewing\_tab}.**

Grab the ID location where I defined PROJECT\_ID in the URL above. For example, my test project has the following URL: **https://app.asana.com/0/1202095602265837/1204819944726585.**

[![the project ID for a specific project in Asana](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88aa309ffa31963c811_1StLdJShtrOAHPy8huRQeujQCIoqqCg5rfCd4xeXU-MTUhRG_I1hERz5aaTO5eEV8TL9sfm60hhFMsvncBwoHinVXaUnZzZg3d_PHF-C7sq4ikFOXV5UJdBaFFBYjqR9BbcKl9scOqaISknViqIRzuI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88aa309ffa31963c811_1StLdJShtrOAHPy8huRQeujQCIoqqCg5rfCd4xeXU-MTUhRG_I1hERz5aaTO5eEV8TL9sfm60hhFMsvncBwoHinVXaUnZzZg3d_PHF-C7sq4ikFOXV5UJdBaFFBYjqR9BbcKl9scOqaISknViqIRzuI.webp)

My Project ID in this case will be: 1202095602265837

We can set up our call with the following information:

```python

import requests

ASANA_BASE_TASK_URL = "https://app.asana.com/api/1.0/tasks"

PROJECT_ID = "1202095602265837" # This is hardcoded for the purpose of this  example, but I would recommend grabbing the ID you want from an additional API call

```

Now, we’re ready to use our requests library to make a GET request to the URL we constructed to fetch all of the tasks from the project we’re looking at.

We’ll want to set up the headers for our request, which will contain our personal access token in the “Authorization” key.

```python

personal_access_token = "fake-token" # Grab this from env variables or secrets where you saved it!

headers = {
   "Authorization": f"Bearer {personal_access_token}"}

```

After this, we can pass in the headers to our request and make an authenticated request to the Asana API. We’ll need to add our “Project ID” to our base URL as an additional input in our request since Asana requires you to filter the endpoint by either Project, Tag, Assignee or Workspace.

When sending in an additional parameter through the API request, we can use URL query parameters by adding a “?” with the query name and value added to the end as “ _?project=1202095602265837”_. If you want to join multiple query parameters, just add a “&” in between them.

```python

url = f"{ASANA_BASE_TASK_URL}?project={PROJECT_ID}"
# This constructed URL should look something like this: https://app.asana.com/api/1.0/tasks?project=1202095602265837

# Make the API Request. Note the .get() function, which corresponds to the HTTP GET method of our request
response = requests.get(url, headers=headers)

# If the status code is 200, it means the request was successful
if response.status_code == 200:
   tasks = response.json()
   # After this -- you can do whatever you want with the tasks that is useful to you!

# If status code is not 200, print an error message since something went wrong
else:
   print(f"Failed to retrieve tasks. Status code: {response.status_code}")

```

We’ve now successfully made an authenticated request to the GitHub API and retrieved useful information.

We can add extra query parameters to filter down the information we’re retrieving even more. There are tons of different possible filters defined in the [API endpoint docs](https://developers.asana.com/reference/gettasks). Something that is often useful is using “modified\_since” to grab all the tasks changed since you last called this endpoint.

The “https://app.asana.com/api/1.0/tasks” could return thousands of tasks within a project, however, and all of these tasks might not fit within one API response. For this reason, this endpoint is paginated with a max of 100 tickets returned in one page. We can set the page size smaller if we want using the “limit” parameter.

In the API response, we know there is more info available if we receive a “next\_page” key. For example, if I request the API with more than 100 tasks, I receive the following in the response JSON.

[![JSON response if there are more than 100 tasks](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88addc9d631d573e872_5l3zdXTasc6I2JPzggspKhPJZY7ozJQkCf5ydXdB2w7L6XVzfFkpaz171OjZex88wmlUQ0hzyMa8OVdAD3mh8dXLuc2yEtg1lE4PJ9mSRvS0YF9yDlJHZx4GgdAgpAAfJ7Mp35HNTWKwsZGgFeKBGXI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/663bd88addc9d631d573e872_5l3zdXTasc6I2JPzggspKhPJZY7ozJQkCf5ydXdB2w7L6XVzfFkpaz171OjZex88wmlUQ0hzyMa8OVdAD3mh8dXLuc2yEtg1lE4PJ9mSRvS0YF9yDlJHZx4GgdAgpAAfJ7Mp35HNTWKwsZGgFeKBGXI.webp)

I can check for a “next page” in my response and continue requesting until it’s empty. We can use the “URI” returned to properly access the next page of results.

```python

url = f"{ASANA_BASE_TASK_URL}?project={PROJECT_ID}"
has_next = True

while has_next and url is not None:
   response = requests.get(url, headers=headers)

   if response.status_code == 200:
       page = response.json()
       tasks = page.get("data", [])
       # After this -- you can do whatever you want with the tasks that is useful to you!
       # Do this before proceeding to the next page

       next_page = page.get("next_page", None)
       # Proceed to the next page
       if next_page:
           url = next_page.get("uri", None)
       else:
           has_next = False

   else:
       print(f"Failed to retrieve tasks. Status code: {response.status_code}")
       break

```

Now we’ve successfully gone through how to retrieve ALL tasks associated with your Asana project! All of the other Asana APIs should be very similar in how to request and access information if you follow the API docs.

## **Final thoughts**

As you can tell, retrieving tasks from Asana via API requests can be technically complex and time consuming to set up (and maintain!). These issues only get exacerbated when you consider the other project management tools your clients want to integrate with your product, such as Trello or Jira.

To help you integrate with any of your clients' project management solutions, you can simply build to [Merge's Ticketing and Project Management Unified API](https://www.merge.dev/categories/ticketing-api).

You can learn more about Merge and its Unified API by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-tasks-asana-api-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Gabby Schwartz

Software Engineer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d2929720-ac62-4fd0-b0a5-71763c6df968&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8088290f-90a3-4bdf-8930-e1b1b6a737fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-tasks-asana-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d2929720-ac62-4fd0-b0a5-71763c6df968&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8088290f-90a3-4bdf-8930-e1b1b6a737fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-tasks-asana-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=747e38c3-c348-44e1-a01c-7e8554d80a19&bo=2&sid=80da03403e8c11f0950c63fba183efda&vid=80dac7103e8c11f0ab68fba04309ce48&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20tasks%20from%20the%20Asana%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-tasks-asana-api-python&r=&lt=702&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=497827)