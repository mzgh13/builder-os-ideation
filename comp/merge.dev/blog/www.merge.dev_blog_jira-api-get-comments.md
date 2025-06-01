---
url: "https://www.merge.dev/blog/jira-api-get-comments"
title: "How to get comments from Jira using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-get-comments#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-get-comments#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-get-comments#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-get-comments#authenticating-with-jira)

[Pulling comments from Jira](https://www.merge.dev/blog/jira-api-get-comments#pulling-comments-from-jira)

[Best practices for testing your Jira integration](https://www.merge.dev/blog/jira-api-get-comments#best-practices-for-testing-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-get-comments#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-comments)

##### Just for you

No items found.

# How to get comments from Jira using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7241fab85507bb23f5_SharePoint_API_key.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a popular project management and ticketing platform, presents users with robust APIs, which provide the ability to engage with the platform in a programmatic manner.

This opens up the potential for automating various tasks—and pulling comments from tickets might be at the top of your list.

Pulling comments and adding them to other applications can help your teams stay on top of customer feedback, track issues, and monitor progress in real-time, leading to faster and more effective responses.

To help you get comments from Jira, we’ll walk through how you can set up authentication for the Jira API and make get requests in Python.

## **Authenticating with Jira**

Before you can pull comments from the Jira API, you'll need to authenticate your requests.

To do this, you’ll need to include an \`Authorization\` header in the format \`Authorization: Basic {Email Address}:{API-KEY}\` in your request.

Using this format, \`{Email Address}\` should be replaced with the email address you use for your Jira account, and \`{API-KEY}\` should be replaced with your Jira API key. Both of these values should be encoded in Base64.

_Related:_ [_What you need to do to get attachments from the Jira API_](https://www.merge.dev/blog/jira-api-get-attachments-python)

## **Pulling comments from Jira**

To pull comments from the Jira API via Python, you’ll need to make two separate API calls. One to fetch the ticket ids and then another to fetch the comments related to those tickets.

The following script first fetches the ticket ids by sending a GET request to the Jira search API. It then iterates over the returned ticket ids to fetch the comments related to each ticket by sending a GET request to the Jira issue comment API. The comments are then printed to the console.

\`\`\`python
import requests
import base64
import json
\# Authentication
email = 'YOUR\_EMAIL'
api\_key = 'YOUR\_API\_KEY'
domain = 'YOUR\_DOMAIN'
auth\_str = '{}:{}'.format(email, api\_key)
base64\_auth\_str = base64.b64encode(auth\_str.encode()).decode()
headers = {
'Authorization': 'Basic {}'.format(base64\_auth\_str),
'Accept': 'application/json'
}
\# Fetch tickets
url = 'https://{}.atlassian.net/rest/api/3/search'.format(domain)
query = {'fields': 'comment', 'maxResults': 50, 'startAt': 0}
response = requests.get(url, headers=headers, params=query)
tickets = json.loads(response.text)\['issues'\]
\# Fetch comments
for ticket in tickets:
ticket\_id = ticket\['id'\]
url = 'https://{}.atlassian.net/rest/api/3/issue/{}/comment'.format(domain, ticket\_id)
query = {'expand': 'renderedBody', 'maxResults': 50, 'startAt': 0}
response = requests.get(url, headers=headers, params=query)
comments = json.loads(response.text)\['comments'\]
for comment in comments:
print(comment\['body'\])
\`\`\`

Replace \`'YOUR\_EMAIL'\`, \`'YOUR\_API\_KEY'\`, and \`'YOUR\_DOMAIN'\` with your actual email, API key, and domain associated with your Jira account. The \`maxResults\` query parameter is set to 50 as per the instructions, and \`startAt\` is initially set to 0 and should be incremented by 50 for each subsequent request to handle pagination.

Here’s an example of an individual item returned by this API endpoint:

```json
{
    "self": "https://jira.example.com/rest/api/2/issue/10001/comment/1",
    "id": "1",
    "author": {
        "self": "https://jira.example.com/rest/api/2/user?username=jsmith",
        "accountId": "5b109f2e9729b51fdf808842",
        "emailAddress": "jsmith@example.com",
        "avatarUrls": {
            "48x48": "https://avatar.example.com/user/avatar/48",
            "24x24": "https://avatar.example.com/user/avatar/24",
            "16x16": "https://avatar.example.com/user/avatar/16",
            "32x32": "https://avatar.example.com/user/avatar/32"
        },
        "displayName": "John Smith",
        "active": true,
        "timeZone": "America/Los_Angeles",
        "accountType": "atlassian"
    },
    "body": {
        "version": 1,
        "type": "doc",
        "content": [\
            {\
                "type": "paragraph",\
                "content": [\
                    {\
                        "type": "text",\
                        "text": "This is a comment on the issue"\
                    }\
                ]\
            }\
        ]
    },
    "renderedBody": "This is a comment on the issue",
    "updateAuthor": {
        "self": "https://jira.example.com/rest/api/2/user?username=jsmith",
        "accountId": "5b109f2e9729b51fdf808842",
        "emailAddress": "jsmith@example.com",
        "avatarUrls": {
            "48x48": "https://avatar.example.com/user/avatar/48",
            "24x24": "https://avatar.example.com/user/avatar/24",
            "16x16": "https://avatar.example.com/user/avatar/16",
            "32x32": "https://avatar.example.com/user/avatar/32"
        },
        "displayName": "John Smith",
        "active": true,
        "timeZone": "America/Los_Angeles",
        "accountType": "atlassian"
    },
    "created": "2019-05-15T14:00:00.000+0000",
    "updated": "2019-05-15T14:00:00.000+0000",
    "jsdPublic": true
}
```

_Related:_ [_The steps for fetching projects from the Jira API_](https://www.merge.dev/blog/jira-api-get-projects-python)

## Best practices for testing your Jira integration

Even when everything seems perfect with your Jira integration in the development stage, unexpected challenges can emerge when it's deployed in a production environment. These challenges could vary widely, from connectivity issues to permission conflicts to unexpected data formats.

To proactively identify and address these potential pitfalls, consider implementing these strategies:

- **Set up a testing environment**. Creating a dedicated testing environment is crucial to mimic real-world scenarios without affecting your production system. You can set this up by duplicating your production environment, ensuring a realistic and controlled testing platform.

- **Perform a variety of test cases**: It’s essential to cover all bases by testing various scenarios, including edge cases and typical user behaviors. For instance, test how the integration handles large data sets or reacts to invalid input.

- **Leverage API testing solutions**: Integrating robust API testing tools is key to ensuring smooth operation. Explore options like [Postman](https://www.postman.com/) or [SoapUI](https://www.soapui.org/), which are popular for their comprehensive testing capabilities.

- **Automate the tests**: Automation not only saves time but also ensures consistency in testing. Utilize scripting or tools like [Selenium](https://www.selenium.dev/) to automate your test cases, which allows for frequent and efficient testing cycles.

- **Test for security and compliance**: Ensuring that your integration adheres to security standards and compliance regulations is non-negotiable. Regularly test for vulnerabilities and compliance to safeguard your data and operations.

## **Final thoughts**

Your clients might utilize ticketing systems that extend beyond Jira.

You have the flexibility to integrate with numerous other ticketing platforms, such as Asana, Zendesk, ClickUp, ServiceNow, by building to Merge’s [Ticketing Unified API](https://www.merge.dev/categories/ticketing-api).

Learn more about Merge’s Ticketing Unified API, the platform’s management and maintenance capabilities, and much more by [scheduling a demo with our team of integration specialists](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-comments).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=9635d3fb-51e8-46ef-b967-5ef5e51f9aaa&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4b114b2d-a9f5-4788-92a1-f31bd360ed89&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-comments&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=9635d3fb-51e8-46ef-b967-5ef5e51f9aaa&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4b114b2d-a9f5-4788-92a1-f31bd360ed89&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-comments&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=fdb615bc-fae6-4530-93a5-568d39e0ce72&bo=2&sid=c9d07f003e8d11f0b8510d097e4c06b6&vid=c9d095d03e8d11f0871f19427fa1de3f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20comments%20from%20Jira%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-comments&r=&lt=496&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=624040)