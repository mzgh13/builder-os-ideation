---
url: "https://www.merge.dev/blog/jira-api-get-attachments-python"
title: "How to get attachments from Jira using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-get-attachments-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-get-attachments-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-get-attachments-python#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-get-attachments-python#authenticating-with-jira)

[Testing your Jira integration](https://www.merge.dev/blog/jira-api-get-attachments-python#testing-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-get-attachments-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-attachments-python)

##### Just for you

No items found.

# How to get attachments from Jira using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a sophisticated project management tool created by Atlassian, facilitates the planning, tracking, and release of software, making it a favorite among numerous software development teams. [Jira](https://www.merge.dev/integrations/jira) also boasts features like customizable workflows, extensive reporting tools, and a potent API, all of which empower businesses to optimize their project management and boost productivity.

Given the platform’s versatility, it stores a variety of valuable data—and attachments are no exception. Getting attachments can help teams automate and streamline various processes, such as issue examination or data backups. And by leveraging the Jira API, you can programmatically fetch these files as needed.

To help you get attachments from the Jira API, we’ll cover everything you need to know. This includes setting up authentication for the Jira API and performing get requests to fetch attachments.

## **Authenticating with Jira**

To interact with the Jira API and retrieve attachments, you need to authenticate your requests.

Jira uses Basic Authentication, which requires you to include a header with your request.

This header should be in the format `Authorization: Basic {Email Address}:{API-KEY}`.

You can generate the Base-64 encoded string of your email address and API key, then use this string in your authorization header. In addition, your email address and API key are the credentials Jira uses to authenticate your API request. You can find your API key—which is a secure, revocable key—, within your Atlassian account.

_Related:_ [_What you need to do to get projects from the Jira API_](https://www.merge.dev/blog/jira-api-get-projects-python)

### **Pulling attachments from Jira**

The Python code to pull attachments from the Jira API involves two steps.

First, we need to hit the search API endpoint and paginate through the response. Second, we’ll retrieve the details of each issue and include the attachments by using the issue API endpoint.

### **Hit the search API endpoint**

Here is the Python code that accomplishes this:

```python

import requests
import base64
import json
# Authentication
email = "YOUR_EMAIL"
api_key = "YOUR_API_KEY"
base64_user_pass = base64.b64encode(f"{email}:{api_key}".encode()).decode()
# Pagination
offset = 0
limit = 50
has_next_page = True
# Search API Endpoint
search_url = "https://{DOMAIN}.atlassian.net/rest/api/3/search"
headers = {
    "Authorization": f"Basic {base64_user_pass}",
    "Accept": "application/json"
}
while has_next_page:
    query = {
        "expand": "renderedFields",
        "maxResults": limit,
        "startAt": offset
    }
    response = requests.get(search_url, headers=headers, params=query)
    data = response.json()
    if 'issues' in data:
        for issue in data['issues']:
            print(issue['id'])
    else:
        has_next_page = False
    offset += limit

```

This script will loop through paginated issues and print each issue's ID to the console.

### **Hit the issue API endpoint**

The next step is to get the attachments of each issue. You can do this by hitting the issue API endpoint for each issue ID:

```python

# Issue API Endpoint
issue_url = "https://{DOMAIN}.atlassian.net/rest/api/3/issue/{id}"
for issue_id in issue_ids:
    response = requests.get(issue_url.format(id=issue_id), headers=headers)
    issue_data = response.json()
    if 'fields' in issue_data and 'attachment' in issue_data['fields']:
        for attachment in issue_data['fields']['attachment']:
            print(attachment['filename'])

```

This script will print the filename of each attachment in each issue to the console.

An example of an individual item returned by this API Endpoint is:

```json
{
    "expand": "schema,names",
    "id": "10002",
    "self": "https://myinstance.atlassian.net/rest/api/2/issue/10002",
    "key": "PROJ-10002",
    "fields": {
        "statuscategorychangedate": "2019-07-02T12:32:49.134+0000",
        "issuetype": {
            "self": "https://myinstance.atlassian.net/rest/api/2/issuetype/5",
            "id": "5",
            "description": "The sub-task of the issue",
            "iconUrl": "https://myinstance.atlassian.net/secure/viewavatar?size=medium&avatarId=10318&avatarType=issuetype",
            "name": "Sub-task",
            "subtask": true,
            "avatarId": 10318,
            "entityId": "80ed3c99-57ff-4beb-9a24-31bdb051d650",
            "hierarchyLevel": 4
        },
        "timespent": null,
        "project": {
            "self": "https://myinstance.atlassian.net/rest/api/2/project/10001",
            "id": "10001",
            "key": "PROJ",
            "name": "Project",
            "simplified": false,
            "avatarUrls": {
                "48x48": "https://myinstance.atlassian.net/secure/projectavatar?pid=10001&avatarId=10412",
                "24x24": "https://myinstance.atlassian.net/secure/projectavatar?size=small&pid=10001&avatarId=10412",
                "16x16": "https://myinstance.atlassian.net/secure/projectavatar?size=xsmall&pid=10001&avatarId=10412",
                "32x32": "https://myinstance.atlassian.net/secure/projectavatar?size=medium&pid=10001&avatarId=10412"
            },
            "projectTypeKey": "software"
        },
        "fixVersions": [],
        "customfield_10018": {
            "hasEpicLinkFieldDependency": false,
            "showField": true,
            "nonEditableReason": {
                "reason": "NOT_EDITABLE",
                "message": "This field cannot be edited in the current transition."
            }
        },
        "customfield_10019": "Some value",
        "aggregatetimespent": null,
        "workratio": -1,
        "attachment": [\
            {\
                "self": "https://myinstance.atlassian.net/rest/api/2/attachment/10010",\
                "id": "10010",\
                "filename": "picture.jpg",\
                "created": "2019-07-02T12:37:53.273+0000",\
                "size": 23123,\
                "mimeType": "image/jpeg",\
                "content": "https://myinstance.atlassian.net/secure/attachment/10010/picture.jpg",\
                "thumbnail": "https://myinstance.atlassian.net/secure/thumbnail/10010/picture.jpg",\
                "author": {\
                    "self": "https://myinstance.atlassian.net/rest/api/2/user?accountId=557058:2baf9c2d-6aad-4b09-a0b1-df776702a9e3",\
                    "accountId": "557058:2baf9c2d-6aad-4b09-a0b1-df776702a9e3",\
                    "avatarUrls": {\
                        "48x48": "https://myinstance.atlassian.net/secure/useravatar?avatarId=10346",\
                        "24x24": "https://myinstance.atlassian.net/secure/useravatar?size=small&avatarId=10346",\
                        "16x16": "https://myinstance.atlassian.net/secure/useravatar?size=xsmall&avatarId=10346",\
                        "32x32": "https://myinstance.atlassian.net/secure/useravatar?size=medium&avatarId=10346"\
                    },\
                    "displayName": "User Name",\
                    "active": true,\
                    "timeZone": "America/Los_Angeles",\
                    "accountType": "atlassian"\
                }\
            }\
        ],
        "lastViewed": "2019-07-02T12:37:57.802+0000"
    }
}
```

_Related:_ [_What you need to do to fetch comments from Jira (using Python)_](https://www.merge.dev/blog/jira-api-get-comments)

## **Testing your Jira integration**

It's a common scenario where everything seems fine during the development and testing phases, but when you go live in the production environment, unexpected issues  arise. These problems could stem from network instability, data format discrepancies, code conflicts, among other factors.

To proactively identify and address potential issues, here's what you can do:

- **Create a test plan:** This plan should outline what you aim to achieve with each test, ensuring thorough coverage of all integration aspects. For example, you might include tests for user authentication or data syncing.

- **Performance testing:** This step is crucial to ensure your integration can handle real-world demands. Include tests like load testing, where you simulate a high number of users, or stress testing, to see how the system performs under extreme conditions.

- **Use the right tools:** Choosing the best tools can significantly enhance your testing effectiveness. Consider tools like [JMeter](https://jmeter.apache.org/) for performance testing or [SoapUI](https://www.soapui.org/) for API testing, which can provide comprehensive testing capabilities.

- **Validate JSON and XML schemas:** Ensuring that your JSON and XML schemas are correct is vital for seamless data exchange. You can do this by using schema validators to check for any inconsistencies or errors in your data formats.

- **Security testing:** Last but not least, security testing is paramount. This involves checking for vulnerabilities that could be exploited once the integration is live, ensuring that both your data and the system are safeguarded against potential threats.

## **Final thoughts**

In the diverse world of ticketing systems, Jira is hardly the only player. There's a whole universe of other ticketing applications out there, such as Asana, ClickUp, and Zendesk.

Seamlessly integrate with the ticketing systems your clients use at scale by leveraging Merge's [Ticketing Unified API](https://www.merge.dev/categories/ticketing-api). You can learn more about Merge and its Ticketing Unified API by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-attachments-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=68f5bb76-ded1-458d-84f8-78cee2a57946&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f631d056-904a-46b4-befc-2e5f4dd96cd0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=68f5bb76-ded1-458d-84f8-78cee2a57946&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f631d056-904a-46b4-befc-2e5f4dd96cd0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ba8e3cdd-a213-414c-a016-8573d9d67a39&bo=2&sid=003c8e103e8e11f092e3c7b5f174dbf7&vid=003cae603e8e11f0b6fae53a8c6b7e8a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20attachments%20from%20Jira%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-attachments-python&r=&lt=454&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=855316)