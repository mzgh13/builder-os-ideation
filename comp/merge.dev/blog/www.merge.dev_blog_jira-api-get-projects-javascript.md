---
url: "https://www.merge.dev/blog/jira-api-get-projects-javascript"
title: "How to get projects from Jira using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-get-projects-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-get-projects-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-get-projects-javascript#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-get-projects-javascript#authenticating-with-jira)

[Pulling projects from Jira](https://www.merge.dev/blog/jira-api-get-projects-javascript#pulling-projects-from-jira)

[How to test your Jira integration](https://www.merge.dev/blog/jira-api-get-projects-javascript#how-to-test-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-get-projects-javascript#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-projects-javascript)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6733d7b1f480601b9ebf11ce_Jira_API_Key.webp)**How to get your Jira API key (5 steps)**](https://www.merge.dev/blog/jira-api-key)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**API Integration Services**](https://www.merge.dev/blog/api-integration-services)

# How to get projects from Jira using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c722dc8eb7739cb26c1_SDK_examples.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a robust project management tool, offers a powerful API that lets developers extract a variety of important information.

The projects that are stored and managed in Jira are no exception.

By pulling project data from Jira—either for your product or the other applications you use internally—you can more effectively perform tasks like monitoring and reporting. You can also prevent employees (or users, if you're integrating Jira with your product) from having to hop between multiple applications to find and/or enter in data.

To help you get projects from Jira, we’ll guide you through the process of setting up authentication for the Jira API and then break down how you can execute a GET request to retrieve projects. Lastly, we'll walk through a single API endpoint that can connect to dozens of third-party ticketing systems.

_Related:_ [_How you can fetch attachments from Jira via JavaScript_](https://www.merge.dev/blog/jira-api-get-attachments-javascript)

## **Authenticating with Jira**

To access data from the Jira API, you need to authenticate your requests. You can do this by including an authorization header in your API request.

The format for this header is \`Authorization: Basic {Email Address}:{API-KEY}\`.

You'll need to base64 encode your email address and API key, and combine them in the format \`email:API-KEY\`. Then, prepend the result with the word "Basic" and a space to form the full authorization header value.

Here's the full code snippet to authenticate the request:

````python

```javascript
const fetch = require('node-fetch');
const email = "YOUR EMAIL";
const apiToken = "YOUR API TOKEN";
const domain = "YOUR DOMAIN";
let offset = 0;
const base64Credentials = Buffer.from(`${email}:${apiToken}`).toString('base64');
const headers = {
'Authorization': `Basic ${base64Credentials}`,
'Accept': 'application/json'
};
```

````

Remember to replace `"YOUR EMAIL"`, `"YOUR API TOKEN"` and `"YOUR DOMAIN"` with your actual credentials and domain.

_Related:_ [_A guide to fetching comments from JavaScript_](https://www.merge.dev/blog/jira-api-javascript-get-comments)

## **Pulling projects from Jira**

We’ll hit the API endpoint: `https://{DOMAIN}.atlassian.net/rest/api/3/project/search` with the query param `expand` set to `description`.

We’ll also use offset-based pagination to limit the number of items requested at a time. The `maxResults` query param will be set to `50` and the offset will be included in the request as the path parameter `startAt`.

````javascript

```javascript
async function getProjects(offset) {
const response = await fetch(`https://${domain}.atlassian.net/rest/api/3/project/search?expand=description&maxResults=50&startAt=${offset}`, { headers });
const data = await response.json();
if (data.values.length === 0) {
    console.log('No more projects.');
} else {
    console.log(data.values);
    offset += 50;
    getProjects(offset);
}
}
getProjects(offset);
```

````

This function will recursively fetch all projects in batches of 50 until there are no more projects to fetch. The projects will be logged to the console.

Here’s an example of an individual item returned by this API endpoint:

```json
{
    "expand": "field",
    "self": "http://www.example.com/jira/rest/api/2/project/PRJ",
    "id": "10000",
    "key": "PRJ",
    "description": "This is a sample project",
    "name": "Sample Project",
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

_Related:_ [_What you need to do to retrieve projects from Jira via Python_](https://www.merge.dev/blog/jira-api-get-projects-python)

## How to test your Jira integration

Even if everything seems perfect during your internal testing, there are numerous reasons why it might encounter issues once deployed in production. These could include unforeseen user interactions, compatibility issues, or environmental differences.

Here are some proactive measures you can take to mitigate these risks:

- **Understand the API specifications:** It's crucial to fully understand the API you're working with. Dive into the documentation to get a grip on the request and response structures, endpoints, and expected behaviors. This will help you anticipate potential issues.

- **Create a test plan:** Developing a comprehensive test plan is vital in ensuring that you're prepared for various real-world situations. This should include scenarios like how the system handles large data payloads or reacts to invalid inputs. **‍**

- **Test under different conditions:** It's important to test your integration in varied environments. You can use tools like [Apache JMeter](https://jmeter.apache.org/) or [Blazemeter](https://www.blazemeter.com/) to simulate different network conditions, loads, and user behaviors to see how your integration holds up.

- **Security testing:** Conducting thorough security testing is imperative to protect your data and systems. Use a tool like [Nessus](https://www.merge.dev/blog/jira-api-get-projects-javascript#) to scan for vulnerabilities and ensure your integration is secure against potential threats.

- **Version control for test cases:** Implementing version control for your test cases is essential. This practice allows you to track changes, manage different test scenarios effectively, and ensures consistency in your testing process over time.

## **Final thoughts**

In all likelihood, your clients use a spectrum of ticketing systems.

You can broaden the integrations you offer quickly and easily by building to [Merge's Ticketing Unified API](https://www.merge.dev/categories/ticketing-api). Once connected to the API, you’ll be able to offer 30+ integrations, which include tools like Jira, ClickUp, Zendesk, ServiceNow, etc.

‍ _To get a deeper understanding of Merge, you can_ [_schedule a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-get-projects-javascript) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=823a5fbc-e98f-4743-bfb8-ac93827c320d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1812c853-a8d5-4a9d-8c46-c2f5543a9d1e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=823a5fbc-e98f-4743-bfb8-ac93827c320d&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1812c853-a8d5-4a9d-8c46-c2f5543a9d1e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0c196469-3c53-44ef-85e5-7fa3b1ea7f30&bo=2&sid=cc740a903e8d11f08541f1ce57008503&vid=cc7455f03e8d11f0a9397dffd3137129&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20projects%20from%20Jira%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-get-projects-javascript&r=&lt=445&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=425445)