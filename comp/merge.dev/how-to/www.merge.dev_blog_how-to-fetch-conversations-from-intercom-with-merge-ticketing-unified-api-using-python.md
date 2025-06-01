---
url: "https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python"
title: "How to fetch conversations from Intercom using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#)

Table of contents

[Intercom API's authentication configuration](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#intercom-apis-authentication-configuration)

[GET conversations from Intercom's API](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#get-conversations-from-intercoms-api)

[Conclusion](https://www.merge.dev/blog/how-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python)

##### Just for you

No items found.

# How to fetch conversations from Intercom using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb351ac179ef5ab3a6f_25.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

_Editor's note: This article is part of a series on building third-party API integrations. Explore Merge if you’re looking to add 180+ integrations across HR, SCIM, payroll, ATS, CRM, accounting, ticketing, marketing automation, and file storage with one_ [_unified API_](https://www.merge.dev/) _._

[Intercom](http://www.intercom.com/) is a powerful customer communication platform that equips organizations with an array of tools for effective customer engagement and interaction. It combines functionalities such as live chat, help desk support, and customer engagement, enabling businesses to deliver personalized customer service and foster enhanced relationships. Additionally, [Intercom provides an Application Programming Interface (API)](https://developers.intercom.com/docs/references/introduction) for businesses to access, integrate, and manipulate their Intercom data, encompassing conversations, users, and companies.

For developers aiming to extract Conversations from a client's Intercom system, they can do so to analyze customer dialogues, optimize customer service, and gain valuable insights into customer behaviors and preferences. The Intercom API serves as an integration point allowing developers to programmatically retrieve, manage, and manipulate these Conversations. This facilitates a more efficient, data-centric approach to improving customer experience and satisfaction.

## Intercom API's authentication configuration

Intercom supports two forms of authentication -- OAuth and Basic Authentication. In this article, we will walk you through the Basic Auth method.

First, you need to find your API key. This token can be found in your Intercom settings under `Access Token Management`.

Every request you make must include this access token in the `Authorization` header field. The format will look like this: `Authorization: Bearer YOUR_ACCESS_TOKEN`.

In addition to this, all requests to Intercom must include the header field `Accept: application/json`. This specifies that the client wants the response data in JSON format. Make sure to include these header fields in all of your API requests to ensure successful communication with the Intercom API.

## GET conversations from Intercom's API

Now let's get coding.

In this script below, we are making a GET request to Intercom's Conversations API endpoint. We are using the `requests` library to send the HTTP request and the `json` library to parse the JSON response.

The function `get_conversations` sends a GET request to the provided URL and returns the parsed JSON response. The function `extract_conversations` extracts the conversations from the response. We first call `get_conversations` with the initial URL and extracts the conversations from the response.

```python
python
import requests
import json

url = 'https://api.intercom.io/conversations'
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {API_KEY}',
}

def get_conversations(url):
    response = requests.get(url, headers=headers)
    data = json.loads(response.text)
    return data

def extract_conversations(data):
    conversations = data['conversations']
    return conversations

data = get_conversations(url)
conversations = extract_conversations(data)

```

‍

Now, we start paginating through Intercom's response. The function `get_next_page` checks if there is a next page URL in the response and returns it if there is one -- otherwise it returns `None`. Then we enter a loop where it keeps calling `get_conversations` with the next page URL and extracting the conversations until there are no more pages. Finally, we print all the conversation!

```python
def get_next_page(data):
    if data['pages']['next']:
        return data['pages']['next']
    else:
        return None

next_page = get_next_page(data)
while next_page:
    data = get_conversations(next_page)
    conversations += extract_conversations(data)
    next_page = get_next_page(data)

for conversation in conversations:
    print(conversation)

```

‍

Congrats! Now you should see the list of Conversations from Intercom as the output.

```python
{
  "type": "conversation.list",
  "pages": {
    "type": "pages",
    "page": 1,
    "per_page": 20,
    "total_pages": 1
  },
  "total_count": 1,
  "conversations": [\
    {\
      "type": "conversation",\
      "id": "455",\
      "created_at": 1698402964,\
      "updated_at": 1698402964,\
      "waiting_since": null,\
      "snoozed_until": null,\
      "source": {\
        "type": "conversation",\
        "id": "403918332",\
        "delivered_as": "admin_initiated",\
        "subject": "",\
        "body": "this is the message body",\
        "author": {\
          "type": "admin",\
          "id": "991267877",\
          "name": "Ciaran142 Lee",\
          "email": "admin142@email.com"\
        },\
        "attachments": [],\
        "url": null,\
        "redacted": false\
      },\
      "contacts": {\
        "type": "contact.list",\
        "contacts": [\
          {\
            "type": "contact",\
            "id": "653b92937e1c8b2e793e3678",\
            "external_id": "70"\
          }\
        ]\
      },\
      "first_contact_reply": null,\
      "admin_assignee_id": null,\
      "team_assignee_id": null,\
      "open": false,\
      "state": "closed",\
      "read": false,\
      "tags": {\
        "type": "tag.list",\
        "tags": []\
      },\
      "priority": "not_priority",\
      "sla_applied": null,\
      "statistics": null,\
      "conversation_rating": null,\
      "teammates": null,\
      "title": null,\
      "custom_attributes": {},\
      "topics": {},\
      "ticket": null,\
      "linked_objects": {\
        "type": "list",\
        "data": [],\
        "total_count": 0,\
        "has_more": false\
      }\
    }\
  ]
}
```

‍

## Conclusion

Wasn't that fun? Now you can keep building!

Unfortunately, Intercom is probably only one of many integrations in the help desk / ticketing space that your team must integrate with.

This is where a [Unified API](https://www.merge.dev/blog/what-is-a-unified-api), such as [Merge](https://merge.dev/), comes into play. At Merge, we’ve built an API that lets you easily integrate once to offer 30+ Ticketing, Project Management and Helpdesk integrations. Our [Unified API](https://merge.dev/categories/hr-payroll-api) fully normalizes authentication, pagination, rate limits and response bodies. _‍_

_Learn more about Merge by_ [_scheduling a demo!_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=78541407-e7da-42e4-9d7f-df5b041cfa62&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=03781d43-29d0-43fc-ac30-c5ee6671580f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=78541407-e7da-42e4-9d7f-df5b041cfa62&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=03781d43-29d0-43fc-ac30-c5ee6671580f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=02fc8be7-d7b0-4b38-be14-8548d2d3f51d&bo=2&sid=4b1e70703e8d11f0af654d1e7aedca63&vid=4b1e7c503e8d11f09aaf83f091ccbca5&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20conversations%20from%20Intercom%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-conversations-from-intercom-with-merge-ticketing-unified-api-using-python&r=&lt=388&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=118692)