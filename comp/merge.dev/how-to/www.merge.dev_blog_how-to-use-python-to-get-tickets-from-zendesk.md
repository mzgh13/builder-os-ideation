---
url: "https://www.merge.dev/blog/how-to-use-python-to-get-tickets-from-zendesk"
title: "How to use python to get tickets from Zendesk"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-use-python-to-get-tickets-from-zendesk#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-use-python-to-get-tickets-from-zendesk#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-use-python-to-get-tickets-from-zendesk#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-use-python-to-get-tickets-from-zendesk)

##### Just for you

No items found.

# How to use python to get tickets from Zendesk

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67191e669cffba5b25f571c5_Merge%20VIP%20Dinner-og.jpg)

No items found.

_This tutorial is part of a series on building product integrations._

Zendesk is more than just a ticketing system – it's a unified platform that many businesses use to categorize, manage, respond to, and solve customer inquiries and complaints. The platform simplifies the customer support process by transforming all incoming requests from different channels into tickets, which are easier for support teams to track and handle.

Zendesk's API functionalities makes it easy for developers to integrate with other systems and programmatically pull ticket data for analysis or to meet other business use cases like building custom dashboards, conducting in-depth analytics, automating workflows, etc.

In this tutorial, we’ll cover:

- How to establish authentication for the Zendesk API
- How to pull normalized data from Zendesk by making get requests to retrieve tickets . This normalized method will enable you to manage your data more effectively.
- How to use a single API endpoint to connect with hundreds of third-party ticketing systems. This will streamline your operations and enable better integration across various platforms.

_Related:_ [_How to GET GitHub repositories_](https://www.merge.dev/blog/github-get-repositories)

### Authentication

To authenticate with the Zendesk API you need a specific header format for the HTTP requests. The header needs to include an **authorization field**, using the Basic access authentication method. The string following 'Basic' should be a Base64 encoded string that represents your email address (used for the Zendesk account), followed by '/token:', and ending with your API key. **The entire string should be encoded in Base64**.

**_Note_** _: the '/token:' part is a literal string - it doesn't change._

Make sure that your email and API key are correct, and that you properly encode the whole string. This authentication method provides a secure way to interact with the Zendesk API.

Here’s a simple Python function to generate the required authentication header:

```python

import base64

def generate_auth_header(email, api_key):
    token = email + '/token:' + api_key
    token_bytes = token.encode('ascii')
    base64_bytes = base64.b64encode(token_bytes)
    base64_token = base64_bytes.decode('ascii')
    return 'Basic ' + base64_token

```

Replace **'email'** and ' **api\_key**' with your actual email address and Zendesk API key respectively. The function will return the complete authorization header value.

```python

import requests
import base64
import json

# define your email and API-key
email = 'YOUR_EMAIL'
api_key = 'YOUR_API_KEY'

# domain of your Zendesk account
domain = 'YOUR_DOMAIN'

# base64 encode your authentication
auth = base64.b64encode(bytes(f'{email}/token:{api_key}', 'utf-8')).decode('ascii')

# set the header for the request
headers = {
    'Authorization': f'Basic {auth}'
}

# start the url for the request
url = f'https://{domain}.zendesk.com/api/v2/search/export?query=type:ticket&filter[type]=ticket'

while True:
    response = requests.get(url, headers=headers)
    data = response.json()

    # get the tickets from the response
    tickets = data['results']

    # process the tickets as you need
    for ticket in tickets:
        print(ticket)

    # check if there is a next page of results
    if not data['meta']['has_more']:
        break

    # if there is a next page, update the url
    url = data['links']['next']

```

### How to get tickets from Zendesk

This Python script uses the `requests` library to make HTTP requests to the Zendesk API. The script begins by defining the email, API key, and domain of your Zendesk account.

The email and API key are used to create a `Basic Auth` header for the requests to the API. The domain is used to construct the URL for the requests.

The script then enters a loop. In each iteration of the loop, the script makes a **GET** request to the Zendesk API to get a page of tickets. Tickets are extracted from the response and printed out.

Then, the script checks if there are more pages of tickets to get. If there are, the script updates the URL for the next request with the URL of the next page of tickets. If not, the script breaks out of the loop.

For reference, here’s an example of an individual item returned by this API Endpoint:

```json
{
    "url": "https://zendesk_api/ticket/123",
    "id": 123,
    "via": {
        "channel": "email",
        "source": {
            "from": {
                "name": "User",
                "address": "user@example.com"
            },
            "to": {
                "name": "Support",
                "address": "support@example.com"
            }
        }
    },
    "created_at": "2022-01-01T00:00:00Z",
    "updated_at": "2022-01-01T01:00:00Z",
    "type": "question",
    "subject": "Need help with product",
    "raw_subject": "Need help with product",
    "description": "I am having trouble with this product, can you assist?",
    "priority": "high",
    "status": "open",
    "requester_id": 1,
    "submitter_id": 2,
    "assignee_id": 3,
    "group_id": 4,
    "collaborator_ids": [\
        5,\
        6\
    ],
    "follower_ids": [\
        7,\
        8\
    ],
    "email_cc_ids": [\
        9,\
        10\
    ],
    "has_incidents": false,
    "is_public": true,
    "tags": [\
        "product",\
        "help"\
    ],
    "custom_fields": [\
        {\
            "field_id": 1,\
            "value": "custom_value"\
        }\
    ],
    "sharing_agreement_ids": [\
        1,\
        2\
    ],
    "fields": [\
        {\
            "field_id": 1,\
            "value": "custom_value"\
        }\
    ],
    "followup_ids": [\
        1,\
        2\
    ],
    "ticket_form_id": 1,
    "brand_id": 1,
    "allow_channelback": false,
    "allow_attachments": true,
    "result_type": "ticket"
}
```

_Related:_ [_What you need to know about reading API documentation_](https://www.merge.dev/blog/how-to-read-api-documentation)

### Use a unified ticketing API to integrate at scale

In this article, we walked through the process of getting tickets from Zendesk using Python. But what if your clients use a variety of ticketing systems?

You can integrate your product with all of your clients' ticketing solutions to sync tasks—among other types of data—by leveraging Merge, the leading Unified API solution.

Simply build to Merge's Ticketing and Project Management Unified API to offer 30+ ticketing integrations. You'll also be able to access Merge's robust [Integrations Management](https://www.merge.dev/features/integrations-management) features to identify and troubleshoot issues quickly and successfully.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-use-python-to-get-tickets-from-zendesk) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e3fdf8a0-3752-45e2-a912-36f37e26ffbb&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5ca59b98-2153-491f-a832-a89f5acc18d2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tickets-from-zendesk&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e3fdf8a0-3752-45e2-a912-36f37e26ffbb&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5ca59b98-2153-491f-a832-a89f5acc18d2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tickets-from-zendesk&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=70394184-2d37-4b82-9dbe-2b4a6e7aab68&bo=2&sid=f278b1f03e8b11f0919673c40dac3976&vid=f278c3a03e8b11f0bab79313ae872b61&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20use%20python%20to%20get%20tickets%20from%20Zendesk&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-use-python-to-get-tickets-from-zendesk&r=&lt=521&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=907793)