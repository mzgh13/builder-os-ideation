---
url: "https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python"
title: "How to fetch users from Okta using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#)

Table of contents

[Authentication configuration in Okta](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#authentication-configuration-in-okta)

[Fetching users from Okta](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#fetching-users-from-okta)

[Conclusion](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-users-from-okta-using-python)

##### Just for you

No items found.

# How to fetch users from Okta using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb151ac179ef5ab3889_How_to_fetch_Users_from_Okta_with_Merge_HRIS_Unified_API_using_Python.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

**_Editor's note_** _: This article is part of a series on building third-party API integrations. Explore Merge if you’re looking to add 180+ integrations across HR, SCIM, payroll, ATS, CRM, accounting, ticketing, marketing automation, and file storage with one_ [_unified API_](https://www.merge.dev/) _._

[Okta](https://www.okta.com/) is a robust and flexible access management tool that offers identity management services. It serves as a consolidated platform for managing employees' identities, encompassing single sign-on, multi-factor authentication, and lifecycle management features. Furthermore, its ability to integrate smoothly with various applications streamlines the HR process and boosts productivity by automating user management tasks.

Integrations with Okta often require pulling user data to other platforms for use cases like auto-provisioning, org chart management, etc. Integrations like these can oftentimes enhance the system's security and efficiency, among [other benefits](https://www.merge.dev/blog/api-integration-benefits).

In this article, we'll walk through how you can build an integration with Okta by successfully authenticating and and fetch users using Python. Buckle up.

## Authentication configuration in Okta

To make authenticated API requests to Okta, you'll need to include an API token in your HTTP header. Okta has a few different options for authentication, but here we will walk through Okta's Basic Authentication. If you need help finding your API key, [we have a help center article with instructions on how to find it](https://help.merge.dev/en/articles/7129484-okta-api-key-authentication).

The header you include in your requests should be in the following format: `Authorization: SSWS {API-KEY}`. This means that you substitute `{API-KEY}` with your actual API token. Be cautious to protect this token and avoid exposing it in public places like GitHub, client-side code, etc.

This API token works as a bearer token which is a method that servers and clients communicate authentication and privileges. This token is generated in your Okta dashboard, specifically in the tokens tab of the API section. Each API request you make will need this token included in the header.

## Fetching users from Okta

The script below uses the requests library to send the GET request to the Okta API. It then parses the response as JSON and adds the users to a list. The script uses a while loop to continue fetching users as long as there is a next link in the response headers. When there is no next link, it means we've fetched all the users and the script breaks out of the loop.

Remember to replace `your-okta-domain` and `your-api-key` with your actual Okta domain and API key.

```python
python
import requests
import json

# Define the base URL
base_url = "https://{DOMAIN}/api/v1/users"

# Define the API Key
api_key = "{API-KEY}"

# Initialize the headers
headers = {
    "Authorization": "SSWS " + api_key,
    "Accept": "application/json",
    "Content-Type": "application/json"
}

# Initialize the URL
url = base_url

# Initialize an empty list to store the users
users = []

# Use a while loop to paginate through the results
while url:

    # Send the GET request
    response = requests.get(url, headers=headers)

    # Parse the response
    users_data = json.loads(response.text)

    # Add the users to the list
    users.extend(users_data)

    # Check for a next link in the response headers
    if 'next' in response.links:
        url = response.links['next']['url']
    else:
        url = None

# Print the users
for user in users:
    print(user)
```

‍

You should see the list of users from Okta as the output.

```python
[\
  {\
    "id": "00ub0oNGTSWTBKOLGLNR",\
    "status": "ACTIVE",\
    "created": "2013-06-24T16:39:18.000Z",\
    "activated": "2013-06-24T16:39:19.000Z",\
    "statusChanged": "2013-06-24T16:39:19.000Z",\
    "lastLogin": "2013-06-24T17:39:19.000Z",\
    "lastUpdated": "2013-07-02T21:36:25.344Z",\
    "passwordChanged": "2013-07-02T21:36:25.344Z",\
    "profile": {\
      "firstName": "Isaac",\
      "lastName": "Brock",\
      "email": "isaac.brock@example.com",\
      "login": "isaac.brock@example.com",\
      "mobilePhone": "555-415-1337"\
    },\
    "credentials": {\
      "password": {},\
      "recovery_question": {\
        "question": "Who's a major player in the cowboy scene?"\
      },\
      "provider": {\
        "type": "OKTA",\
        "name": "OKTA"\
      }\
    },\
    "_links": {\
      "self": {\
        "href": "https://{yourOktaDomain}/api/v1/users/00ub0oNGTSWTBKOLGLNR"\
      }\
    }\
  }\
]
```

‍

## Conclusion

And that's it! You've successfully authenticated and fetched users from Okta.

But what happens when Okta is merely one among many integrations that your team must develop and sustain, and your next customer asks you for a JumpCloud, Azure Active Directory or OneLogin integration?

This is where a [Unified API](https://www.merge.dev/blog/what-is-a-unified-api), such as [Merge](https://merge.dev/), comes into play. At Merge, we’ve built an API that lets you easily integrate once to offer 40+ HRIS, SCIM and Payroll integrations. Our [Unified API](https://merge.dev/categories/hr-payroll-api) has also smoothed out pagination and authentication. _‍_

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-users-from-okta-using-python) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=49e87b68-0f2f-43f6-901b-a22b768e9e8b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2af79bd9-9740-40e9-9b6d-9864db93889b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=49e87b68-0f2f-43f6-901b-a22b768e9e8b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2af79bd9-9740-40e9-9b6d-9864db93889b&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=db9eca54-9ace-498a-8466-e5dddab97453&bo=2&sid=3106c7103e8e11f086daa340ff346835&vid=3106ef003e8e11f0a474bb388482df68&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20users%20from%20Okta%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-python&r=&lt=389&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=530825)