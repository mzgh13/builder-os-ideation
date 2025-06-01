---
url: "https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python"
title: "How to fetch employees from Paylocity using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#)

Table of contents

[Setting Up Authentication for Paylocity API](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#setting-up-authentication-for-paylocity-api)

[FETCH Employees with Merge HRIS Unified API](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#fetch-employees-with-merge-hris-unified-api)

[Leveraging a Unified HRIS API for Efficient Integrations](https://www.merge.dev/blog/how-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python#leveraging-a-unified-hris-api-for-efficient-integrations)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python)

##### Just for you

No items found.

# How to fetch employees from Paylocity using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb0b6c5002162a36205_How_to_fetch_Employees_from_Paylocity_with_Merge_HRIS_Unified_API_using_Python.webp)

No items found.

**_Editor's note_** _: this article is part of a series on building third-party API integrations. Explore Merge if you’re looking to add 180+ integrations across HR and payroll, ATS, CRM, accounting, ticketing, marketing automation, and file storage with one_ [_unified API_](https://www.merge.dev/) _._

Paylocity is an all-inclusive Human Resources Information System (HRIS) that consolidates payroll, benefits, talent management, and other HR-related tasks into a single platform. Utilizing cloud technology, it provides instantaneous data and potent tools for businesses of varying sizes, augmenting efficiency and informed decision-making. Additionally, Paylocity boasts a potent API, enabling developers to weave its features into bespoke applications, allowing for automated extraction of employee information and other HR-centric data.

For a developer, extracting Employee data from a client's Paylocity system can automate HR procedures, curtail manual data input, and maintain data uniformity across several systems. This integration point empowers the developer to obtain real-time, precise employee data, which can subsequently be used to create robust applications, dashboards, or analytics tools that improve decision-making and workflow within the company.

Merge is a Unified API that facilitates developers in adding several integrations, Paylocity included, with a singular API. This article guides you on how to connect to the Paylocity API to acquire a list of Employees using both the Paylocity API and the [Merge HRIS Unified API](https://merge.dev/categories/hr-payroll-api).

## Setting Up Authentication for Paylocity API

When integrating with Paylocity API, one of the first steps you must undertake is configuring your authentication. Paylocity API uses OAuth 2.0 for authentication, specifically the Client Credentials grant type.

To authenticate, you will need to make a request to the token URL, which is `https://api.paylocity.com/IdentityServer/connect/token`. This request should include your `client_id`, `client_secret`, and any other parameters that are required as body parameters.

The header of your request should be formatted in the following way:

```python
"Authorization: Basic {BASE-64}{CLIENT-ID}:{CLIENT-SECRET}{BASE-64}"

```

After successfully exchanging tokens, you can find the `access_token` by following the keys in the response. This token is crucial as it is used to authorize all your subsequent requests to the Paylocity API.

The token's lifespan, or how long it is valid, can be found in the `expires_in` value in the response body. Once your token expires, you can use the `refresh_token` key in the response to get a new one.

Remember, all requests to the Paylocity API must also include the header field `Content-Type: application/x-www-form-urlencoded`. This ensures that the server interprets your request correctly.

```python
import requests
import base64
import json

# Step 1: Getting Access Token
token_url = "https://api.paylocity.com/IdentityServer/connect/token"
client_id = "YOUR_CLIENT_ID"
client_secret = "YOUR_CLIENT_SECRET"
data = {
    "client_id": client_id,
    "client_secret": client_secret,
    "grant_type": "client_credentials",
    "scope": "api"
}

credentials = base64.b64encode(f"{client_id}:{client_secret}".encode("utf-8")).decode("utf-8")
headers = {
    "Authorization": f"Basic {credentials}",
    "Content-Type": "application/x-www-form-urlencoded"
}

response = requests.post(token_url, data=data, headers=headers)
access_token = response.json()['access_token']

# Step 2: Fetching Employees
domain = "YOUR_DOMAIN"
page_number = 0
headers = {
    "Authorization": f"Bearer {access_token}",
    "Content-Type": "application/json"
}

while True:
    employee_url = f"https://api.paylocity.com/api/v2/companies/{domain}/employees?page={page_number}"
    response = requests.get(employee_url, headers=headers)
    employees = response.json()

    if not employees:
        break

    for employee in employees:
        employee_id = employee['employeeId']
        employee_details_url = f"https://api.paylocity.com/api/v2/companies/{domain}/employees/{employee_id}"
        response = requests.get(employee_details_url, headers=headers)
        employee_details = response.json()
        print(employee_details)

    page_number += 1
```

In the above code, replace `YOUR_CLIENT_ID`, `YOUR_CLIENT_SECRET`, and `YOUR_DOMAIN` with your actual client ID, client secret, and domain.

This code first retrieves an access token using your client credentials. It then uses this token to authenticate the API requests. The employees are fetched page by page, and for each employee, additional details are fetched using their employee ID. The loop continues until there are no more employees to fetch (i.e., the response is empty).

An example of an individual item returned by this API Endpoint is:

```json
{
    "ssn": "123-45-6789",
    "gender": "Male",
    "status": {
        "hireDate": "2021-01-01",
        "statusType": "Full-Time",
        "effectiveDate": "2021-01-01",
        "employeeStatus": "Active",
        "terminationDate": "",
        "isEligibleForRehire": true
    },
    "suffix": "Jr",
    "webTime": {
        "chargeRate": 15,
        "badgeNumber": "A123",
        "isTimeLaborEnabled": true
    },
    "currency": "USD",
    "isSmoker": false,
    "lastName": "Doe",
    "taxSetup": {
        "taxForm": "W-4",
        "suiState": "NY"
    },
    "birthDate": "1990-01-01",
    "ethnicity": "Hispanic",
    "firstName": "John",
    "employeeId": "E123",
    "federalTax": {
        "amount": 100,
        "percentage": 15,
        "w4FormYear": 2021,
        "filingStatus": "Single",
        "taxCalculationCode": "Standard"
    },
    "middleName": "F",
    "salutation": "Mr",
    "companyFEIN": "12-3456789",
    "companyName": "ABC Corp",
    "homeAddress": {
        "city": "New York",
        "phone": "123-456-7890",
        "state": "NY",
        "county": "New York",
        "country": "USA",
        "address1": "123 Main St",
        "address2": "Apt 1",
        "postalCode": "10001",
        "mobilePhone": "123-456-7890",
        "emailAddress": "johndoe@example.com"
    },
    "workAddress": {
        "city": "New York",
        "pager": "",
        "phone": "123-456-7890",
        "state": "NY",
        "country": "USA",
        "address1": "123 Broadway",
        "address2": "",
        "location": "HQ",
        "postalCode": "10001",
        "mobilePhone": "123-456-7890",
        "emailAddress": "johndoe@abccorp.com"
    },
    "maritalStatus": "Single",
    "primaryPayRate": {
        "salary": 50000,
        "payType": "Salary",
        "ratePer": "Year",
        "baseRate": 15,
        "payGrade": "A",
        "isAutoPay": true,
        "annualSalary": 50000,
        "changeReason": "Promotion",
        "defaultHours": 40,
        "payFrequency": "Bi-Weekly",
        "effectiveDate": "2021-01-01",
        "beginCheckDate": "2021-02-01"
    },
    "primaryStateTax": {
        "amount": 50,
        "taxCode": "NY",
        "exemptions": 1,
        "percentage": 5,
        "w4FormYear": 2021,
        "exemptions2": 0,
        "filingStatus": "Single",
        "taxCalculationCode": "Standard"
    },
    "customNumberFields": [\
        {\
            "label": "custom1",\
            "value": 10,\
            "category": "custom"\
        }\
    ],
    "departmentPosition": {
        "jobTitle": "Software Engineer",
        "payGroup": "IT",
        "costCenter1": "IT",
        "costCenter2": "Development",
        "costCenter3": "Web",
        "employeeType": "Full-Time",
        "effectiveDate": "2021-01-01",
        "isOvertimeExempt": true,
        "isMinimumWageExempt": true,
        "isSupervisorReviewer": false,
        "isUnionDuesCollected": false,
        "supervisorEmployeeId": "E124",
        "supervisorCompanyNumber": "1",
        "isUnionInitiationCollected": false
    },
    "customBooleanFields": [\
        {\
            "label": "custom1",\
            "value": true,\
            "category": "custom"\
        }\
    ]
}
```

_Related:_ [_Steps for performing API integration in Python_](https://www.merge.dev/blog/api-integration-python)

## FETCH Employees with Merge HRIS Unified API

The Merge API is a great way to pull normalized HRIS data from a variety of HRIS tools, including Paylocity.

When making requests to the Merge API, you will need to pass proper authentication parameters so that you can identify yourself as an authorized user. You'll need to include a Merge API Key (YOUR\_API\_KEY) and a Linked Account Token (END\_USER\_ACCOUNT\_TOKEN) for every request you send to the Merge API.

```python
import time
import HRIS
from HRIS.api import employees_api
from pprint import pprint

configuration = HRIS.Configuration()

# Swap YOUR_API_KEY below with your production key from:
# https://app.merge.dev/keys
configuration.api_key['tokenAuth'] = 'YOUR_API_KEY'
configuration.api_key_prefix['tokenAuth'] = 'Bearer'
```

Once you've authenticated to Merge, you'll next use the API client to make a GET request using the Linked Account Token of the customer whose data you're accessing.

```python
api_client = MergeHRISClient.ApiClient(configuration)

employees_api_instance = employees_api.EmployeesApi(api_client)

x_account_token = 'END_USER_ACCOUNT_TOKEN'
while cursor != None:
    api_response = employees_api_instance.employees_list(x_account_token)
    pprint(api_response)
    cursor = api_response.next
```

The response you get back from the Merge API will include normalized data for any HRIS integration, including Paylocity. To explore the standard response format, check out the API reference at [https://prod.cdn.paylocity.com/developer/index.html#tag/Company-Codes](https://prod.cdn.paylocity.com/developer/index.html#tag/Company-Codes).

```json
{
    "id": "0958cbc6-6040-430a-848e-aafacbadf4ae",
    "remote_id": "19202938",
    "modified_at": "2021-10-16T00:00:00Z",
    "integration_params": {
        "unique_integration_field": "unique_integration_field_value"
    },
    "linked_account_params": {
        "unique_linked_account_field": "unique_linked_account_field_value"
    },
    "field_mappings": {
        "organization_defined_targets": {
            "custom_key": "custom_value"
        },
        "linked_account_defined_targets": {
            "custom_key": "custom_value"
        }
    },
    "employee_number": "2",
    "company": "8d9fd929-436c-4fd4-a48b-0c61f68d6178",
    "first_name": "Greg",
    "last_name": "Hirsch",
    "username": "cousingreg",
    "display_full_name": "Cousin Greg Hirsch",
    "work_email": "greg@merge.dev",
    "personal_email": "greg@gmail.com",
    "mobile_phone_number": "+1234567890",
    "employments": [\
        "17a54124-287f-494d-965e-3c5b330c9a68"\
    ],
    "home_location": "d2f972d0-2526-434b-9409-4c3b468e08f0",
    "work_location": "9efbc633-3387-4306-aa55-e2c635e6bb4f",
    "manager": "0048ea5b-911e-4dff-9364-92070dea62ff",
    "team": "249c9faa-3045-4a31-953b-8f22d3613301",
    "groups": [\
        "21a54124-397f-494d-985e-3c5b330b8a68"\
    ],
    "pay_group": "ad1264e2-39be-4787-b749-f1aade9e3405",
    "ssn": "1234567890",
    "gender": "MALE",
    "ethnicity": "WHITE",
    "marital_status": "SINGLE",
    "date_of_birth": "1990-11-10T00:00:00Z",
    "hire_date": "2020-10-10T00:00:00Z",
    "start_date": "2020-10-11T00:00:00Z",
    "remote_created_at": "2020-10-11T00:00:00Z",
    "employment_status": "INACTIVE",
    "termination_date": "2021-10-12T00:00:00Z",
    "avatar": "http://alturl.com/h2h8m"
}
```

Now that you've accessed data via the Merge HRIS Unified API, you can easily add other integrations on behalf of any of your customers. Check out [Merge Link](https://docs.merge.dev/get-started/link/) to see how to automate your customers authorizing connections on your behalf and generating Linked Account Tokens.

## Leveraging a Unified HRIS API for Efficient Integrations

Suppose you're not well-versed in programming languages such as Python, or perhaps Paylocity is merely one among multiple integrations that you and your team are tasked with developing and managing. This is where a Unified API like [Merge](https://merge.dev/) steps in.

[Merge proposes a solution for HRIS integrations](https://merge.dev/categories/hr-payroll-api) by introducing a single API endpoint that connects to various platforms and services, Paylocity included. This API endpoint serves as a conduit between different platforms, enabling users to communicate with all of them via a single API endpoint.

Merge accomplishes this by utilizing a plugin system that enables it to establish connections to diverse platforms and services. These plugins form a bridge between Merge's API endpoint and the data housed in different HRIS applications. Each plugin is entrusted with managing the distinct communication protocols, APIs, and data structures of the system to which it connects.

When a user sends an API call to Merge, the call is directed to the suitable plugin based on the information given within the call. The plugin then processes the call and delivers the relevant response. This process facilitates users to engage with various systems via a single, Unified API endpoint.

Merge manages these integrations, streamlining authentication with a click-through UI component, and promptly identifying permissioning errors instigated by your customers (such as an incorrect API key). This substantially diminishes the long-term engineering effort associated with an integration product.In this guide, we demonstrated the process of using Python to communicate with the Paylocity API in order to retrieve Employee data.

For those seeking to connect with more than just a single HRIS application, Merge's unified API offers a robust solution. This single API allows you to tap into a multitude of HRIS platforms, Paylocity included, with just one call, thus removing the necessity for multiple separate integrations. This streamlines your integration ecosystem construction process, enabling you to concentrate on enhancing your primary product while simultaneously broadening your potential market.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=80280166-259e-4691-8372-63d86b22d9ae&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=3bc66e36-5b4b-4a26-a916-6cd0eb6df038&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=80280166-259e-4691-8372-63d86b22d9ae&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=3bc66e36-5b4b-4a26-a916-6cd0eb6df038&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=b8274bc2-400e-4975-8564-f2a87c3d5bcb&bo=2&sid=478a9da03e8e11f0a633dde1cc4146b6&vid=478acda03e8e11f0b635ebcef36e1825&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20employees%20from%20Paylocity%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-paylocity-with-merge-hris-unified-api-using-python&r=&lt=397&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=191610)