---
url: "https://www.merge.dev/blog/how-to-fetch-deal-pipelines-from-hubspot-using-python"
title: "How to fetch deal pipelines from HubSpot using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-deal-pipelines-from-hubspot-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-deal-pipelines-from-hubspot-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-deal-pipelines-from-hubspot-using-python#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-deal-pipelines-from-hubspot-using-python)

##### Just for you

No items found.

# How to fetch deal pipelines from HubSpot using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e81d81421ed2a7cc5c13_HubSpot.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

**HubSpot** is a Customer Relationship Management (CRM) solution for marketing, sales, and customer service needs. It equips teams with tools for everything from social media marketing and content management to lead capture and reporting. It's essentially a comprehensive toolkit to help businesses attract, engage with, and delight customers more effectively.

HubSpot also offers an [**API**](https://developers.hubspot.com/docs/api/overview?__hstc=229663683.44368bb01274ad1e4705a503de8eb8c5.1748743251694.1748743251694.1748743251694.1&__hssc=229663683.1.1748743251694&__hsfp=3707738794) that developers can leverage to integrate its suite of services into their applications. This integration facilitates the extraction of data for analysis or customization, enhancing what sales, marketing, and customer success can do.

In our experience, an integration developers find useful involves pulling **Deal Pipelines** from a customer's HubSpot system. This extraction can provide valuable insights into the customer's sales process, opening up more data-driven decision making. You can also use this integration to boost overall efficiency of marketing operations.

In this article, we’re going to dive into the following key areas:

- Setting up secure authentication for the HubSpot API
- Extracting structured data from HubSpot, specifically using fetch requests to retrieve Deal Pipelines
- Connecting with many third-party CRM platforms using a single API

### Authentication

Hubspot's API supports two methods of authentication: OAuth and Basic Authentication. We will walk through the Basic Authentication method, which is accomplished using an **API key --** a unique identifier that authorizes your application to access the HubSpot data.

This API key is included in the header of your HTTP request in the format `Authorization: Bearer {API-KEY}`, where `{API-KEY}` is the actual key provided by HubSpot.

### Fetching deal pipelines with the Hubspot API

Now let's jump into actually getting Deal Pipelines from Hubspot!

This Python script uses the `requests` library to send a **GET** request to the mentioned API endpoint. The API key is included in the header.

```python

import requests
import json

# Define the API endpoint and API key
api_endpoint = 'https://api.hubapi.com/crm/crm-pipelines/v1/pipelines/deals'
api_key = 'Your_HubSpot_API_Key'

# Define the header for the request
header = {
    'Authorization': f'Bearer {api_key}'
}

# Function to fetch deal pipelines
def fetch_deal_pipelines(url, header):
    response = requests.get(url, headers=header)
    data = json.loads(response.text)

    # Extract the deal pipelines
    deal_pipelines = data['results']

    # Check if there is a next page
    next_cursor = data['paging'].get('next', {}).get('link', '')
    if next_cursor:
        deal_pipelines += fetch_deal_pipelines(next_cursor, header)

    return deal_pipelines

# Fetch the deal pipelines
deal_pipelines = fetch_deal_pipelines(api_endpoint, header)

```

The function `fetch_deal_pipelines` sends a **GET** request to the provided URL and parses the JSON response to extract the deal pipelines. It also checks for the existence of a next page using the cursor in the response. If a next page exists, it recursively fetches the deal pipelines from the next page by calling itself with the next page's URL. The deal pipelines from all pages are concatenated and returned.

For reference, this is example of an individual item returned by this API Endpoint:

```json
{
    "label": "Sales Pipeline",
    "active": true,
    "stages": [\
        {\
            "label": "Appointment Scheduled",\
            "active": true,\
            "stageId": "123456789",\
            "metadata": {\
                "isClosed": "false",\
                "probability": "25"\
            },\
            "createdAt": 1631597558,\
            "updatedAt": 1631597558,\
            "displayOrder": 1\
        },\
        {\
            "label": "Qualified To Buy",\
            "active": true,\
            "stageId": "987654321",\
            "metadata": {\
                "isClosed": "false",\
                "probability": "50"\
            },\
            "createdAt": 1631599000,\
            "updatedAt": 1631599000,\
            "displayOrder": 2\
        }\
    ],
    "default": true,
    "createdAt": 1631597558,
    "updatedAt": 1631597558,
    "objectType": "DEAL_PIPELINE",
    "pipelineId": "1234567890",
    "displayOrder": 0,
    "objectTypeId": "DEAL"
}
```

### Leverage a unified CRM API for seamless integrations

In this article, we walked through the process of leveraging Python to connect with HubSpot and retrieve deal pipelines. But what if your clients use a variety of CRM systems?

You can integrate your product with all of your clients' CRM solutions to sync deal pipelines—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's CRM Unified API to offer 20+ CRM integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-deal-pipelines-from-hubspot-using-python) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)

Shensi Ding

CEO and co-founder

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5856bfb-a46c-4add-ab83-3cb83e5e36f0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=15b96246-39ed-4fdc-933c-828a0449f885&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-deal-pipelines-from-hubspot-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c5856bfb-a46c-4add-ab83-3cb83e5e36f0&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=15b96246-39ed-4fdc-933c-828a0449f885&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-deal-pipelines-from-hubspot-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=be06070a-8026-48d5-9324-69e3959b54ff&bo=2&sid=3d7342603e8c11f08048f1711ecc2753&vid=3d73b5103e8c11f0bc89870fc9f62d85&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20deal%20pipelines%20from%20HubSpot%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-deal-pipelines-from-hubspot-using-python&r=&lt=675&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=935499)