---
url: "https://www.merge.dev/blog/jira-api-get-projects-python"
title: "How to get projects from Jira using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-get-projects-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-get-projects-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-get-projects-python#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-get-projects-python#authenticating-with-jira)

[Pulling projects from Jira](https://www.merge.dev/blog/jira-api-get-projects-python#pulling-projects-from-jira)

[Tips for testing your Jira integration](https://www.merge.dev/blog/jira-api-get-projects-python#tips-for-testing-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-get-projects-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-projects-python)

##### Just for you

No items found.

# How to get projects from Jira using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7387ff8c191004c1e8_6.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a leading ticketing and project management solution, boasts an expansive API that lets developers engage with its data programmatically, paving the way for effortless integration with other tools and systems.

In many cases, your team may want to extract projects from the Jira API; doing so can provide  invaluable insights on a project to other applications, such as a project’s status, description, or its assignee.

To help you get projects from Jira, we’ll break down how you can set up authentication for the Jira API and execute 'get' requests to pull projects via Python.

_Note: If you'd prefer to use Javascript to fetch projects in Jira, you can_ [_read this guide_](https://www.merge.dev/blog/jira-api-get-projects-javascript) _._

## **Authenticating with Jira**

Before making any requests to the Jira API, you need to provide authentication.

This is done using basic authentication, where your email address and the API key are combined and encoded in Base64 format. This Base64 encoded string is then included in the headers of your HTTP requests to the API.

The header should be in the format: `Authorization: Basic {Email Address}:{API-KEY}`.

_Related:_ [_A guide to getting attachments from Jira via Python_](https://www.merge.dev/blog/jira-api-get-attachments-python)

## **Pulling projects from Jira**

The following script will print the name of every project in Jira:

```python

import requests
import base64
import json
# Define the base url and endpoint
base_url = "https://{DOMAIN}.atlassian.net"
endpoint = "/rest/api/3/project/search"
# Define the headers for the request
email = "{Email Address}"
api_key = "{API-KEY}"
base_64_auth = base64.b64encode(bytes(f'{email}:{api_key}', 'utf-8')).decode('ascii')
headers = {
    'Authorization': f'Basic {base_64_auth}',
    'Accept': 'application/json'
}
# Define the query parameters
query_params = {
    'expand': 'description',
    'maxResults': 50,
    'startAt': 0
}
# Make the initial request
response = requests.get(base_url + endpoint, headers=headers, params=query_params)
# Check if the request was successful
if response.status_code == 200:
    # Parse the JSON response
    data = json.loads(response.text)

    # Loop through the pages
    while data['values']:
        # Process the data
        for project in data['values']:
            print(project['name'])

        # Update the startAt parameter for the next page
        query_params['startAt'] += query_params['maxResults']

        # Make the request for the next page
        response = requests.get(base_url + endpoint, headers=headers, params=query_params)

        # Parse the JSON response
        data = json.loads(response.text)
else:
    print(f"Request failed with status code {response.status_code}")

```

If you want to do something different with the project data, replace the `print(project['name'])` line with whatever processing you need to do. Also, remember to replace `"{DOMAIN}"`, `"{Email Address}"`, and `"{API-KEY}"` with your actual Jira domain, email address, and API key, respectively.

An example of an individual item returned by this API Endpoint is:

```json
{
    "expand": "field",
    "self": "http://www.example.com/jira/rest/api/2/project/EX",
    "id": "10000",
    "key": "EX",
    "description": "Example Project",
    "name": "Example",
    "avatarUrls": {
        "48x48": "http://www.example.com/jira/secure/projectavatar?pid=10000&avatarId=10011",
        "24x24": "http://www.example.com/jira/secure/projectavatar?size=small&pid=10000&avatarId=10011",
        "16x16": "http://www.example.com/jira/secure/projectavatar?size=xsmall&pid=10000&avatarId=10011",
        "32x32": "http://www.example.com/jira/secure/projectavatar?size=medium&pid=10000&avatarId=10011"
    },
    "projectTypeKey": "business",
    "simplified": false,
    "style": "classic",
    "isPrivate": false,
    "properties": {}
}
```

_Related:_ [_A guide to fetching comments from the Jira API_](https://www.merge.dev/blog/jira-api-get-comments)

## Tips for testing your Jira integration

To prevent any issues once you push the integration to production, you should adopt a comprehensive approach to testing. To that end, here are some measures you can take:

- **Define clear test objectives:** It's crucial to know exactly what you're testing for. By setting specific goals, like verifying seamless data exchange or ensuring user interface consistency, you'll have a clear focus during testing.

- **Create a test plan:** A well-structured test plan is your roadmap to a successful integration. Think about including a variety of cases, such as how the system behaves under heavy load or how it recovers from a network interruption, so that you're covering a range of scenarios.

- **Use the right tools:** Selecting appropriate tools is key to effective testing. Explore options like [Postman](https://www.postman.com/) for API testing or [Selenium](https://www.selenium.dev/) for automated browser testing to find what best suits your needs.

- **Test for different HTTP methods:** It's important to check how the integration handles various HTTP methods like GET, POST, or PUT. You can do this by simulating requests and examining the responses to ensure they're as expected.

- **Test under different conditions:** Finally, don't forget to test in different environments and conditions. This includes varying network speeds, different user loads, and cross-platform compatibility to ensure robust performance in real-world scenarios.

## **Final thoughts**

In this guide, we've walked you through how to harness the power of Python to interface with Jira and fetch projects. However, it's worth noting that Jira is just one of many ticketing systems your clients might be using.

You can easily expand your integration to reach other popular ticketing applications, such as Asana and ClickUp, by building to a single API—namely, [Merge's Ticketing Unified API](https://www.merge.dev/categories/ticketing-api).

You can learn more about Merge's Ticketing Unified API, and Merge more broadly, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-projects-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2e120772-8d65-40ce-82fe-c0209a5c679c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=da8b77ab-b97c-40b6-8ae8-adff436fefc7&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2e120772-8d65-40ce-82fe-c0209a5c679c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=da8b77ab-b97c-40b6-8ae8-adff436fefc7&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=b23e4b26-8013-4fb5-a770-d3fbf3df8e25&bo=2&sid=b1f656303e8d11f0b4f0c304269cfc5c&vid=b1f683303e8d11f0bea80979d357199c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20projects%20from%20Jira%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-python&r=&lt=434&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=311311)