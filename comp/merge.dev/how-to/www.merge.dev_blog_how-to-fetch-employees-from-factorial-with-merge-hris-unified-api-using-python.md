---
url: "https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python"
title: "How to fetch employees from Factorial using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#)

Table of contents

[Authentication configuration](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#authentication-configuration)

[How to get employees from Factorial](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#how-to-get-employees-from-factorial)

[Final thoughts](https://www.merge.dev/blog/how-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python)

##### Just for you

No items found.

# How to fetch employees from Factorial using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cafa8b22be11998ca9d_How_to_Fetch_Employees_from_Factorial_with_Merge_HRIS_Unified_API.webp)

No items found.

Factorial is an advanced HRIS solution that's engineered to optimize and automate critical HR tasks such as employee data management, time tracking, and benefits administration. The platform also incorporates an API, empowering developers to extract vital employee data into their own systems or applications for personalized management and reporting.

To help you get employees from Factorial using Python, we'll cover every step you need to follow below.

## Authentication configuration

Before you can pull data from the Factorial API, you need to set up OAuth 2.0 authentication. This integration uses the authorization code grant type.

Firstly, direct your users to the authorization URL `https://api.factorialhr.com/oauth/authorize` to start the OAuth flow. Once the user completes the authorization flow, the Factorial API will redirect the user to the redirect URL that you provided. The redirect URL will include the authorization code as a query parameter, `code`, which you will then use to request an access token.

To request the access token, you need to hit the token URL `https://api.factorialhr.com/oauth/token` using your client ID and secret provided by Factorial. Include these credentials, along with other required parameters, in the URL as query parameters.

The request header should follow this format: `Authorization: Bearer {ACCESS-TOKEN}`.

Here's where to find important information in the token URL response:

- The `access token` is in the access\_token key.
- The `expires_in` value tells you how long the token will last.
- The refresh token is in the `refresh_token` key.

## How to get employees from Factorial

The code below will help you pull employee data from the Factorial API by setting up an OAuth flow, getting an access token and using it to make an authorized request to the Factorial API.

First, define your client ID, client secret, and redirect URL:

```python
client_id = 'your-client-id'
client_secret = 'your-client-secret'
redirect_url = 'your-redirect-url'
```

Then establish the authorization URL and token URL:

```python
auth_url = 'https://api.factorialhr.com/oauth/authorize'
token_url = 'https://api.factorialhr.com/oauth/token'
```

Once the user navigates to the authorization URL and authorizes, they're sent to the redirect URL with code as a query parameter. Get the authorization code from the query parameter:

```python
auth_code = 'auth-code-from-query-param'
```

Request the access token:

```python
payload = {
    'client_id': client_id,
    'client_secret': client_secret,
    'code': auth_code,
    'redirect_uri': redirect_url,
    'grant_type': 'authorization_code'
}
response = requests.post(token_url, data=payload)
token_response = response.json()
```

Get the access token and refresh token from the response:

```python
access_token = token_response['access_token']
refresh_token = token_response['refresh_token']
```

Use the access token to make authorized API requests:

```python
headers = {'Authorization': 'Bearer ' + access_token}
response = requests.get('https://api.factorialhr.com/api/v1/employees', headers=headers)
```

Print the response:

```python
print(response.json())
```

Remember to replace `'your-client-id'`, `'your-client-secret'`, `'your-redirect-url'`, and `'auth-code-from-query-param'` with your actual Client ID, Client Secret, Redirect URL, and Authorization code respectively.

You should see the list of employees from Factorial as the output.

```python
[\
    {\
        "id": 101,\
        "birthday_on": "1990-01-01",\
        "manager_id": 201,\
        "timeoff_manager_id": 301,\
        "regular_access_starts_on": "2022-01-01",\
        "avatar": "https://example.com/avatar.jpg",\
        "identifier": "EMP101",\
        "identifier_type": "Employee ID",\
        "phone_number": "+1-555-555-5555",\
        "gender": "Male",\
        "nationality": "American",\
        "bank_number": "1234567890",\
        "country": "United States",\
        "city": "New York",\
        "state": "New York",\
        "postal_code": "10001",\
        "address_line_1": "123 5th Avenue",\
        "address_line_2": "Suite 101",\
        "social_security_number": "123-45-6789",\
        "email": "employee101@example.com",\
        "full_name": "John Doe",\
        "first_name": "John",\
        "last_name": "Doe",\
        "role": "Software Engineer",\
        "start_date": "2022-01-01",\
        "hiring": {\
            "base_compensation_amount_in_cents": 7000000,\
            "base_compensation_type": "Salary"\
        },\
        "location_id": 401,\
        "team_ids": [\
            501,\
            502,\
            503\
        ],\
        "company_holiday_ids": [\
            601,\
            602\
        ]\
    }\
]
```

## **Final thoughts**

It’s worth remembering that your clients might be using other HRIS solutions, whether that’s Workday, Namely, UKG, etc.

You can offer customer-facing integrations with all of the HRIS solutions your clients use by connecting to [Merge's HRIS Unified API](https://www.merge.dev/categories/hr-payroll-api).

Learn more about Merge’s Ticketing Unified API, along with the other features and capabilities provided by the platform, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3a593708-54c8-4873-873d-54fd7160f8ce&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f378936a-eccf-43e6-9e56-3cd4744228d1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3a593708-54c8-4873-873d-54fd7160f8ce&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=f378936a-eccf-43e6-9e56-3cd4744228d1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=8e788a60-e542-4f99-9f48-5564e9204bab&bo=2&sid=5dd827f03e8d11f0a7be69757f55b477&vid=5dd8bb603e8d11f0855649e7b8186ed0&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20employees%20from%20Factorial%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-factorial-with-merge-hris-unified-api-using-python&r=&lt=433&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=119254)