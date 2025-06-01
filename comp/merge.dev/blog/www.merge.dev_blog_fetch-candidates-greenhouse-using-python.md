---
url: "https://www.merge.dev/blog/fetch-candidates-greenhouse-using-python"
title: "How to fetch candidates from Greenhouse using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/fetch-candidates-greenhouse-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/fetch-candidates-greenhouse-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/fetch-candidates-greenhouse-using-python#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffetch-candidates-greenhouse-using-python)

##### Just for you

No items found.

# How to fetch candidates from Greenhouse using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Greenhouse, a prominent applicant tracking system (ATS), lets you organize and manage candidate details, job postings, applications, interviews, hiring decisions, and more.

Given all the information Greenhouse collects and stores, as well as tasks it lets you perform, you likely have many reasons to connect your product to the application via [its APIs](https://support.greenhouse.io/hc/en-us/articles/10568627186203-Greenhouse-API-overview). That said, candidates likely top your data wants from Greenhouse.

We’ll help you collect candidates from the Greenhouse API by walking you through the steps of setting up a functioning script in Python.

### **1\. Configure authentication**

Greenhouse uses Basic Authentication over HTTPS, which requires an API key.

Include a header in your requests in the format Authorization: `Basic {BASE-64}{API-KEY}:{BASE-64}`. This API key is unique to your instance and provides you with the necessary permissions to access and manipulate your data. The API key should be Base64 encoded before being passed in the header.

It’s worth noting that all API requests must be made over HTTPS. Requests made over plain HTTP will fail. API requests without authentication will also fail. You’ll also want to include the following: ```` ```python import requests import base64````

### **2\. Define the API key and encode it using BASE-64**

You’ll need to use the following code: `api_key = 'your_api_key' base64_api_key = base64.b64encode(api_key.encode()).decode()`

### **3\. Set up the headers for the request**

Here’s how it should look: `headers = { "Authorization": f"Basic {base64_api_key}:{base64_api_key}", "Content-Type": "application/json" }`

### **4\. Define the initial endpoint**

In this case, the endpoint is https://harvest.greenhouse.io/v1/candidates.

### **5\. Initialize an empty list to store the candidates**

This can be as simple as the following: candidates = \[\]

### **6\. Loop until the endpoint is empty (i.e., we've reached the last page)**

Here’s the code that facilitates this logic:

```python
while endpoint: response = requests.get(endpoint, headers=headers) response.raise_for_status() # Raise exception if the request failed data = response.json() candidates.extend(data) endpoint = response.headers.get('link', '').split('next')[-1]
```

### **An example of a response**

At this point, candidates should contain all the data.

To recap, this Python script sends a GET request to the API endpoint defined above, fetches candidates' data, and stores it in the candidates list. The script uses basic authentication with the API key provided and iterates through all pages of the data using Greenhouse's cursor-based pagination. Moreover, the response.raise\_for\_status()line will raise an HTTP error if one occurred, which can be helpful for debugging.

After the script finishes, ``thecandidates` `` variable contains the candidates data, which can be processed as needed. An example of an individual item returned by this API endpoint can look as follows:

```python

{
    "id": "1627289354398",
    "tags": [\
        "developer",\
        "newyork",\
        "remote"\
    ],
    "title": "Software Developer",
    "company": "Tech Solutions",
    "addresses": [\
        {\
            "type": "home",\
            "value": "123 Main St, New York, NY"\
        }\
    ],
    "can_email": true,
    "last_name": "Smith",
    "recruiter": {
        "id": "1627289354399",
        "name": "John Doe",
        "last_name": "Doe",
        "first_name": "John"
    },
    "created_at": "2021-07-26T14:22:34Z",
    "educations": [\
        {\
            "id": "1627289354400",\
            "degree": "Bachelor of Science in Computer Science",\
            "discipline": "Computer Science",\
            "school_name": "Harvard University"\
        }\
    ],
    "first_name": "John",
    "is_private": false,
    "updated_at": "2021-07-26T14:22:34Z",
    "coordinator": {
        "id": "1627289354401",
        "name": "Jane Doe",
        "last_name": "Doe",
        "first_name": "Jane"
    },
    "applications": [\
        {\
            "id": "1627289354402",\
            "jobs": [\
                {\
                    "id": "1627289354403",\
                    "name": "Software Developer"\
                }\
            ],\
            "source": {\
                "id": "1627289354404",\
                "public_name": "LinkedIn"\
            },\
            "status": "Active",\
            "prospect": false,\
            "applied_at": "2021-07-26T14:22:34Z",\
            "credited_to": {\
                "id": "1627289354405",\
                "name": "John Doe",\
                "last_name": "Doe",\
                "first_name": "John"\
            },\
            "candidate_id": "1627289354398",\
            "current_stage": {\
                "id": "1627289354406",\
                "name": "Screening"\
            },\
            "last_activity_at": "2021-07-26T14:22:34Z"\
        }\
    ],
    "last_activity": "2021-07-26T14:22:34Z",
    "phone_numbers": [\
        {\
            "type": "home",\
            "value": "1627289354407"\
        }\
    ],
    "email_addresses": [\
        {\
            "type": "home",\
            "value": "johnsmith@example.com"\
        }\
    ],
    "website_addresses": [\
        {\
            "type": "LinkedIn",\
            "value": "https://linkedin.com/in/johnsmith"\
        }\
    ],
    "social_media_addresses": [\
        {\
            "value": "https://twitter.com/johnsmith"\
        }\
    ]
}

```

### **Want to integrate with more ATS systems?**

For those striving to connect their product with multiple ATS applications, Merge's [ATS Unified API](https://merge.dev/categories/ats-recruiting-api) offers an ideal solution.

It enables access to a broad range of ATS platforms, such as Greenhouse, with just a single call. This eliminates the necessity for numerous integrations, thereby streamlining your system integration process. By doing so, you can dedicate more time and resources towards enhancing your primary product, all while broadening your potential market reach.

To learn more about Merge, you can [request a demo](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffetch-candidates-greenhouse-using-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5f7175a5-4dfb-4ca1-b631-6770aaf4fe5b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=739ca9fc-a29c-4c96-b832-7cd7a7b5beb1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-candidates-greenhouse-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=5f7175a5-4dfb-4ca1-b631-6770aaf4fe5b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=739ca9fc-a29c-4c96-b832-7cd7a7b5beb1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-candidates-greenhouse-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=3f98369d-3e77-4fc7-a339-ca8c00abf1c5&bo=2&sid=5cc006403e8c11f096b4a3b97a54034b&vid=5cc01c903e8c11f097327d10d104096c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20candidates%20from%20Greenhouse%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffetch-candidates-greenhouse-using-python&r=&lt=750&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=799993)