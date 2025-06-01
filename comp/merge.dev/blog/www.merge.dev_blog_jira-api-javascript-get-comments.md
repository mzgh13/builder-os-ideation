---
url: "https://www.merge.dev/blog/jira-api-javascript-get-comments"
title: "How to get comments from Jira using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/jira-api-javascript-get-comments#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/jira-api-javascript-get-comments#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/jira-api-javascript-get-comments#)

Table of contents

[Authenticating with Jira](https://www.merge.dev/blog/jira-api-javascript-get-comments#authenticating-with-jira)

[Pulling comments from Jira](https://www.merge.dev/blog/jira-api-javascript-get-comments#pulling-comments-from-jira)

[Tips for testing your Jira integration](https://www.merge.dev/blog/jira-api-javascript-get-comments#tips-for-testing-your-jira-integration)

[Final thoughts](https://www.merge.dev/blog/jira-api-javascript-get-comments#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-javascript-get-comments)

##### Just for you

No items found.

# How to get comments from Jira using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb198dcb1a5cce561fd_SaaS_integration_challenges.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jira, a potent ticket management tool, provides a powerful API that gives developers the means to extract key data. And while there are a variety of different types of data you can fetch, comments in Jira might be at the top of your list.

Fetching comments for your product or the other systems you’re using internally allows you to elevate collaboration, streamline task management, and ultimately save employees’ time.

We’ll help you get comments from Jira via JavaScript by covering how you can set up authentication for the Jira API, and then make get requests to pull comments.

_Related:_ [_What you need to do to retrieve attachments from Jira using JavaScript_](https://www.merge.dev/blog/jira-api-get-attachments-javascript)

## **Authenticating with Jira**

To interact with the Jira API, you'll need to authenticate your requests.

You can do this by including an \`Authorization\` header with your HTTP requests.

The value of this header should be \`Basic\` followed by a base64-encoded string, which is a combination of your email address and API key.

The format of this header should look like this: `Authorization: Basic {Email Address}:{API-KEY}`.

To obtain your API key, you can visit the Atlassian account settings. The email address should be the one associated with your Atlassian account.

For example, if your email is \`johndoe@example.com\` and your API key is \`1234567890abcdef\`, the base64-encoded string would be the result of base64-encoding \`johndoe@example.com:1234567890abcdef\`. This encoded string is what you should use in your \`Authorization\` header.

It’s worth noting that this is a basic form of HTTP authentication and may not be suitable for all use cases. For higher security, consider using OAuth.

_Related:_ [_How to fetch comments from the Jira API using Python_](https://www.merge.dev/blog/jira-api-get-comments)

## **Pulling comments from Jira**

The code below leverages the `axios` library to send GET requests to the Jira API. The first API endpoint is hit to get the list of issues, using pagination to get all issues. For each issue, the ticket\_id is extracted and used to hit the second API endpoint to get the comments for that issue. The comments are then logged to the console.

It’s also worth noting that the pagination logic for the comments is kept simple for this demonstration, but it can be expanded to handle more complex scenarios.

```javascript

const axios = require('axios');
const BASE64 = Buffer.from("Email Address:API-KEY").toString('base64');
let startAt = 0;
let hasMoreData = true;
async function getComments() {
  while (hasMoreData) {
    let response = await axios.get(`https://{DOMAIN}.atlassian.net/rest/api/3/search?fields=comment&maxResults=50&startAt=${startAt}`, {
      headers: {
        "Authorization": `Basic ${BASE64}`
      }
    });
    if (response.data.issues.length === 0) {
      hasMoreData = false;
    } else {
      startAt += 50;
      for (let issue of response.data.issues) {
        let ticket_id = issue.id;
        let commentsResponse = await axios.get(`https://{DOMAIN}.atlassian.net/rest/api/3/issue/${ticket_id}/comment?expand=renderedBody&maxResults=50`, {
          headers: {
            "Authorization": `Basic ${BASE64}`
          }
        });
        for (let comment of commentsResponse.data.comments) {
          console.log(comment);
        }
      }
    }
  }
}
getComments();

```

Before running this code, replace `Email Address` and `API-KEY` with your actual email address and API key, and replace `{DOMAIN}` with your actual domain.

An example of an individual item returned by this API endpoint is:

```json
{
    "id": "1001",
    "self": "http://jira.example.com/rest/api/2/issue/1001/comment",
    "author": {
        "self": "http://jira.example.com/rest/api/2/user?username=johndoe",
        "accountId": "5b109f2f484bbf3b8cd9e7b0",
        "emailAddress": "johndoe@example.com",
        "avatarUrls": {
            "16x16": "http://jira.example.com/secure/useravatar?size=small&ownerId=johndoe",
            "24x24": "http://jira.example.com/secure/useravatar?size=medium&ownerId=johndoe",
            "32x32": "http://jira.example.com/secure/useravatar?size=large&ownerId=johndoe",
            "48x48": "http://jira.example.com/secure/useravatar?size=xlarge&ownerId=johndoe"
        },
        "displayName": "John Doe",
        "active": true,
        "timeZone": "America/Los_Angeles",
        "accountType": "atlassian"
    },
    "body": {
        "version": 1,
        "type": "text",
        "content": [\
            {\
                "type": "paragraph",\
                "content": [\
                    {\
                        "type": "text",\
                        "text": "Great work on this issue!"\
                    }\
                ]\
            }\
        ]
    },
    "renderedBody": "Great work on this issue!",
    "updateAuthor": {
        "self": "http://jira.example.com/rest/api/2/user?username=johndoe",
        "accountId": "5b109f2f484bbf3b8cd9e7b0",
        "emailAddress": "johndoe@example.com",
        "avatarUrls": {
            "16x16": "http://jira.example.com/secure/useravatar?size=small&ownerId=johndoe",
            "24x24": "http://jira.example.com/secure/useravatar?size=medium&ownerId=johndoe",
            "32x32": "http://jira.example.com/secure/useravatar?size=large&ownerId=johndoe",
            "48x48": "http://jira.example.com/secure/useravatar?size=xlarge&ownerId=johndoe"
        },
        "displayName": "John Doe",
        "active": true,
        "timeZone": "America/Los_Angeles",
        "accountType": "atlassian"
    },
    "created": "2019-08-22T10:15:30.000+0000",
    "updated": "2019-08-22T10:15:30.000+0000",
    "jsdPublic": true
}
```

_Related:_ [_A guide to getting projects from Jira via JavaScript_](https://www.merge.dev/blog/jira-api-get-projects-javascript)

## Tips for testing your Jira integration

Let's say you and your team haven't spotted any glitches with the Jira integration. That's great, but keep in mind, it might still encounter snags once it's live in production. These snags can be anything from network latency issues to unexpected user input to conflicts with other software.

Here's what you can do to get ahead of these potential problems:

- **Understand the API specifications**: This is key because knowing the nitty-gritty of the API helps you predict where problems might crop up. With this in mind, dive into the documentation and get familiar with how it's supposed to work.

- **Create a test plan**: This is crucial as it guides your testing process. Think of it as your road map. For instance, if your plan includes testing how the integration handles large data sets or reacts to invalid user inputs, you're less likely to be caught off guard.

- **Test under different conditions**: This step is vital because it ensures your integration holds up under various scenarios. Try mixing it up with different environments or vendors—like testing on both Windows and Linux systems, for example.

- **Check response status codes**: This is a must-do. It's how you'll know if things are running smoothly or if something's gone haywire. Regularly monitoring these codes will give you real-time insights into the health of your integration.

- **Collaboration and communication**: Last but not least, keep in constant touch with your team; sharing insights and flagging issues early on can make a world of difference in managing the integration effectively.

## **Final thoughts**

It's highly probable that your clients utilize a diverse range of ticketing platforms—not just Jira.

To cater to this varied landscape of ticketing tools, you can build to [Merge's Ticketing Unified API](https://www.merge.dev/categories/ticketing-api). Once you’ve built to it, you can offer dozens of ticketing integrations to clients, whether that’s Zendesk, Jira, Asana, GitHub, etc.

‍ _You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fjira-api-javascript-get-comments) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=bd5c1234-8247-4839-b998-a774c2f24411&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c1f82881-cd11-4ff4-b0aa-0ff206597082&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-javascript-get-comments&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=bd5c1234-8247-4839-b998-a774c2f24411&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c1f82881-cd11-4ff4-b0aa-0ff206597082&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-javascript-get-comments&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=17eba85a-11c1-4911-aa63-dcea47296f72&bo=2&sid=e4af49503e8c11f09a36ef0c0c6fb625&vid=e4b018c03e8c11f0bbe7c58933df3a21&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20comments%20from%20Jira%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fjira-api-javascript-get-comments&r=&lt=841&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=503824)