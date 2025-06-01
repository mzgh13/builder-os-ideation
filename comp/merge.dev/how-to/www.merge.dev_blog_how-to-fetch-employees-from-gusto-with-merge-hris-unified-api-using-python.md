---
url: "https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python"
title: "How to fetch employees from Gusto using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#)

Table of contents

[Obtaining your access token](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#obtaining-your-access-token)

[Steps for fetching employee data from the Gusto API](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#steps-for-fetching-employee-data-from-the-gusto-api)

[Final thoughts](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python)

##### Just for you

No items found.

# How to fetch employees from Gusto using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

No items found.

Gusto, a robust, cloud-based Human Resource Information System (HRIS), is engineered to streamline and automate HR operations. It provides a comprehensive toolkit for payroll, benefits, and HR management, all of which are intricately interconnected to decrease administrative tasks. Moreover, Gusto's API permits [custom integration](https://www.merge.dev/blog/custom-api-integration), facilitating businesses to access employee data and optimize their workflow.

To help you get employee data in Gusto via Python, we'll break down every step you need to follow in this article.

## Obtaining your access token

To initiate this process, users should be directed to the Gusto authorization URL: `https://api.gusto.com/oauth/authorize`. Once the authorization flow is completed, Gusto will redirect the user to the `redirect_url` that was initially provided. Included in this redirect will be the authorization code as a query parameter.

The next step in the process is to exchange the authorization code for an access token. This is done by making a POST request to the Gusto token URL: `https://api.gusto.com/oauth/token`.

This request should include the client ID and client secret that were provided by Gusto, along with the authorization code and other necessary parameters. These should be passed as body parameters in the POST request.

For instance, a Python request might look something like this:

```python
import requests

url = "https://api.gusto.com/oauth/token"
payload = {
    "client_id": "YOUR_CLIENT_ID",
    "client_secret": "YOUR_CLIENT_SECRET",
    "code": "AUTHORIZATION_CODE",
    "grant_type": "authorization_code",
    "redirect_uri": "YOUR_REDIRECT_URL"
}

response = requests.post(url, data=payload)
```

Upon successful completion of the request, the response will include an `access_token`, an `expires_in` value indicating the lifespan of the token, and a `refresh_token`. The `access_token` is used in subsequent API calls to pull employee data, while the `refresh_token` can be used to obtain a new `access_token` once the original has expired.

## Steps for fetching employee data from the Gusto API

First, let's install the necessary package:

```python
pip install requests
```

Next, we will go through the OAuth 2 flow to get the access token.

```python
import requests

# Replace these with your client id and secret
CLIENT_ID = 'YOUR_CLIENT_ID'
CLIENT_SECRET = 'YOUR_CLIENT_SECRET'

def get_access_token():
    token_url = 'https://api.gusto.com/oauth/token'
    auth = (CLIENT_ID, CLIENT_SECRET)
    response = requests.post(token_url, auth=auth)
    response.raise_for_status()
    return response.json()['access_token']

access_token = get_access_token()
```

Then, we'll request the current user's data:

```python
def get_me(access_token):
    url = 'https://api.gusto.com/v1/me'
    headers = {'Authorization': f'Bearer {access_token}'}
    response = requests.get(url, headers=headers)
    response.raise_for_status()
    return response.json()

me = get_me(access_token)
```

Next, we'll loop over the companies that the current user is a payroll admin for, and fetch the employees for each company.

Note: This code fetches all employees for each company the current user is a payroll admin for. It uses the `include` parameter to include all compensations and custom fields for each employee. It also handles pagination by incrementing the page number for each request until an empty page is returned.

```python
def get_employees(access_token, company_id):
    url = f'https://api.gusto.com/v1/companies/{company_id}/employees'
    headers = {'Authorization': f'Bearer {access_token}'}
    params = {'include': 'all_compensations,custom_fields'}
    page = 0
    while True:
        params['page'] = page
        response = requests.get(url, headers=headers, params=params)
        response.raise_for_status()
        data = response.json()
        if not data:
            break
        yield from data
        page += 1

for company in me['roles']['payroll_admin']['companies']:
    for employee in get_employees(access_token, company['uuid']):
        print(employee)
```

An example of an individual item returned by this API Endpoint is:

```json
{
    "uuid": "1a2b3c4d",
    "first_name": "John",
    "middle_initial": "A",
    "last_name": "Doe",
    "email": "john.doe@example.com",
    "company_uuid": "5e6f7g8h",
    "manager_uuid": "9i0j1k2l",
    "version": "1.0",
    "current_employment_status": "employed",
    "onboarding_status": "completed",
    "preferred_first_name": "Johnny",
    "department_uuid": "3m4n5o6p",
    "payment_method": "direct_deposit",
    "department": "Sales",
    "terminated": false,
    "two_percent_shareholder": false,
    "onboarded": true,
    "has_ssn": true,
    "jobs": [\
        {\
            "uuid": "7q8r9s0t",\
            "version": "1.0",\
            "employee_uuid": "1a2b3c4d",\
            "location_uuid": "u2v3w4x5",\
            "current_compensation_uuid": "y6z7a8b9",\
            "payment_unit": "hourly",\
            "primary": true,\
            "two_percent_shareholder": false,\
            "title": "Sales Manager",\
            "compensations": [\
                {\
                    "uuid": "c0d1e2f3",\
                    "employee_uuid": "1a2b3c4d",\
                    "version": "1.0",\
                    "payment_unit": "hourly",\
                    "flsa_status": "exempt",\
                    "adjust_for_minimum_wage": false,\
                    "minimum_wages": [],\
                    "job_uuid": "7q8r9s0t",\
                    "effective_date": "2020-01-01",\
                    "rate": "20.00"\
                }\
            ],\
            "rate": "20.00",\
            "hire_date": "2019-01-01",\
            "location": {\
                "zip": "10001",\
                "city": "New York",\
                "uuid": "u2v3w4x5",\
                "state": "NY",\
                "country": "USA",\
                "inactive": false,\
                "street_1": "123 Main St",\
                "street_2": "Apt 1"\
            }\
        }\
    ],
    "eligible_paid_time_off": [\
        {\
            "name": "Vacation",\
            "policy_name": "Standard Vacation Policy",\
            "policy_uuid": "g4h5i6j7",\
            "accrual_unit": "hours",\
            "accrual_rate": "1.5",\
            "accrual_method": "per_pay_period",\
            "accrual_period": "biweekly",\
            "accrual_balance": "80",\
            "maximum_accrual_balance": "120",\
            "paid_at_termination": true\
        }\
    ],
    "terminations": [],
    "home_address": {
        "zip": "10001",
        "city": "New York",
        "state": "NY",
        "active": true,
        "country": "USA",
        "version": "1.0",
        "street_1": "123 Main St",
        "street_2": "Apt 1",
        "employee_uuid": "1a2b3c4d"
    },
    "garnishments": [],
    "custom_fields": [],
    "date_of_birth": "1980-01-01",
    "ssn": "123-45-6789",
    "phone": "(123) 456-7890",
    "work_email": "john.doe@workexample.com"
}
```

## **Final thoughts**

It’s worth remembering that your clients might be using other HRIS solutions, whether that’s Workday, Namely, UKG, etc.

You can offer customer-facing integrations with all of the HRIS solutions your clients use by connecting to [Merge's HRIS Unified API](https://www.merge.dev/categories/hr-payroll-api).

Learn more about Merge’s Ticketing Unified API, along with the other features and capabilities provided by the platform, by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2c4d38b2-7e01-4bb9-871f-22e8b027c60a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b82c2fc8-1940-415a-afc8-b1711d83cde0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=2c4d38b2-7e01-4bb9-871f-22e8b027c60a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b82c2fc8-1940-415a-afc8-b1711d83cde0&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=6f816e9d-5baf-46fc-9670-235967941d7a&bo=2&sid=5cdcaab03e8d11f08926c7f075ce2538&vid=5cde58403e8d11f0a2033d789d28fbd3&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20employees%20from%20Gusto%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-python&r=&lt=623&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=75896)