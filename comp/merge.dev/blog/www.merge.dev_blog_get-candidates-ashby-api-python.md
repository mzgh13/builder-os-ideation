---
url: "https://www.merge.dev/blog/get-candidates-ashby-api-python"
title: "How to get all candidates with the Ashby API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-candidates-ashby-api-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-candidates-ashby-api-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-candidates-ashby-api-python#)

Table of contents

[Authentication in Ashby](https://www.merge.dev/blog/get-candidates-ashby-api-python#authentication-in-ashby)

[How to GET candidates from Ashby‍](https://www.merge.dev/blog/get-candidates-ashby-api-python#how-to-get-candidates-from-ashby)

[Want to connect to more ATS platforms?](https://www.merge.dev/blog/get-candidates-ashby-api-python#want-to-connect-to-more-ats-platforms)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-candidates-ashby-api-python)

##### Just for you

No items found.

# How to get all candidates with the Ashby API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Ashby, an all-in-one applicant tracking system (ATS), helps recruiting teams of all sizes gather, organize, and analyze large quantities of job applications. In addition, the software helps recruiting teams manage the full candidate life cycle to help organizations land target candidates more easily and with greater success.

Ashby also offers [APIs](https://developers.ashbyhq.com/), which empowers developers to access any of the data stored in the platform—as well as add information to the system.

Perhaps no object (and associated fields) is more valuable in Ashby than _candidates_. To help you retrieve either all candidates or individual ones, we’ll walk you through the process of using a Python script to connect to the relevant API endpoint and fetch the candidates in Ashby.

## **Authentication in Ashby**

You'll need to include a specific header in your requests. This header should be in the format `Authorization: Basic {API-KEY}`. Moreover, all interactions with Ashby's API require another header field, specifically `Content-Type: application/json`.

## **How to GET candidates from Ashby** ‍

The script below fetches candidates from the Ashby API. It does this by first encoding the API key in Base64 format and preparing the headers for the request. Then, it hits the endpoint `'https://api.ashbyhq.com/candidate.list'` repeatedly until there's no more data available. The next cursor is extracted from the response and included in the next request. Finally, all the candidates are printed out.

Here’s how the script should look (in addition to the header):

```python

import requests
import base64
import json
API_KEY = 'your_ashby_api_key'
BASE_64 = base64.b64encode(bytes(API_KEY, 'utf-8')).decode('utf-8')
headers = {
    'Authorization': 'Basic ' + BASE_64 + ':' + BASE_64,
    'Content-Type': 'application/json',
}
url = 'https://api.ashbyhq.com/candidate.list'
next_cursor = None
more_data_available = True
candidates = []
while more_data_available:
    data = {'cursor': next_cursor} if next_cursor else None
    response = requests.post(url, headers=headers, json=data)
    response_json = response.json()
    candidates.extend(response_json['results'])
    more_data_available = response_json['moreDataAvailable']
    next_cursor = response_json['nextCursor']
for candidate in candidates:
    print(candidate)

```

_Note: Remember to replace 'your\_ashby\_api\_key' with your actual API key._

Here’s an example of an individual item returned by this API Endpoint:

```python

{
    "id": "1",
    "name": "John Doe",
    "primaryEmailAddress": {
        "value": "johndoe@example.com",
        "type": "work",
        "isPrimary": true
    },
    "emailAddresses": [\
        {\
            "value": "johndoe@example.com",\
            "type": "work",\
            "isPrimary": true\
        },\
        {\
            "value": "johndoe2@example.com",\
            "type": "home",\
            "isPrimary": false\
        }\
    ],
    "phoneNumbers": [\
        {\
            "value": "1234567890",\
            "type": "mobile",\
            "isPrimary": true\
        },\
        {\
            "value": "0987654321",\
            "type": "home",\
            "isPrimary": false\
        }\
    ],
    "socialLinks": [\
        {\
            "url": "https://www.linkedin.com/in/johndoe",\
            "type": "LinkedIn",\
            "isPrimary": true\
        },\
        {\
            "url": "https://www.twitter.com/johndoe",\
            "type": "Twitter",\
            "isPrimary": false\
        }\
    ],
    "tags": [\
        {\
            "id": "1",\
            "title": "Engineer",\
            "isArchived": false\
        },\
        {\
            "id": "2",\
            "title": "Experienced",\
            "isArchived": false\
        }\
    ],
    "position": "Software Engineer",
    "company": "ABC Corp",
    "school": "XYZ University",
    "applicationIds": [\
        "app1",\
        "app2",\
        "app3"\
    ]
}

```

_Related:_ [_Tips for conducting API integration testing_](https://www.merge.dev/blog/api-integration-testing)

## **Want to connect to more ATS platforms?**

Merge, the leading unified API solution, lets you connect your product to Ashby and dozens of other ATSs, such as Lever, Greenhouse, and Jobvite, through its [ATS Unified API](https://merge.dev/categories/ats-recruiting-api). This allows your product to offer more capabilities and richer analytics, as well as simply sync the data your clients need with little friction.

To learn how you can fetch candidates—along with a variety of other types of data—from dozens of ATS solutions, you can [schedule a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-candidates-ashby-api-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=35dbe50a-8a9b-4970-a0a7-d04dd78970a4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8d518ef3-3d8c-4603-8aa9-77ddf2274c3b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-candidates-ashby-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=35dbe50a-8a9b-4970-a0a7-d04dd78970a4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=8d518ef3-3d8c-4603-8aa9-77ddf2274c3b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-candidates-ashby-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=111bfede-b38b-45b5-b10c-a0f2a39aa3f7&bo=2&sid=6b9d37703e8c11f0bcd7cd5b9691edee&vid=6b9d52203e8c11f09c1bef6c48db44b4&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20all%20candidates%20with%20the%20Ashby%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-candidates-ashby-api-python&r=&lt=823&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=161486)