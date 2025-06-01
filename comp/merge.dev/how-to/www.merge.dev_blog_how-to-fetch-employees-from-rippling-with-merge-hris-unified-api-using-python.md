---
url: "https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python"
title: "How to fetch employees from Rippling using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#)

Table of contents

[Authentication configuration](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#authentication-configuration)

[How to get employees](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#how-to-get-employees)

[Final thoughts](https://www.merge.dev/blog/how-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python)

##### Just for you

No items found.

# How to fetch employees from Rippling using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb1d0411c78c3bc45bc_How_to_Fetch_Employees_from_Rippling_with_Merge_HRIS_Unified_API.webp)

No items found.

Rippling stands as a potent HRIS that helps businesses manage payroll, benefits, employee onboarding, and more. Given all its use cases, it likely stores rich data on employees.

We'll help you retrieve employee data from Rippling's API (using Python) by breaking down every step you need to follow.

## Authentication configuration

To pull employee data from Rippling API, you first need to authenticate your application. Rippling uses the OAuth 2.0 protocol for authentication and authorization.

In the header of each HTTP request, include an authorization token in the following format: `Authorization: Bearer {API-KEY}`. This `{API-KEY}` is your unique application key provided by Rippling. Make sure to replace `{API-KEY}` with your actual API key.

It's important to note that all API requests must be made over HTTPS. Calls made over plain HTTP will fail. Also, you must authenticate for all API requests. Also, remember to keep your API key secure. Do not share your secret API key in publicly accessible areas such GitHub, client-side code, and so forth.

_Related:_ [_Recruiting integrations worth building_](https://www.merge.dev/blog/recruiting-integration)

## How to get employees

The Python code below fetches employees from Rippling API using `requests` library. It uses a generator to yield employee data as it is fetched from the API. The function `fetch_employees` takes an API key and a limit as arguments and fetches employee data in a paginated manner using an offset.

Moreover, the code fetches data from the API endpoint using a GET request. It includes an authorization header in the format ``Authorization: Bearer {API-KEY}` ``. The function fetches data in pages of size `limit` and increments the offset by `limit` after each request to fetch the next page. It stops fetching when it encounters an empty page.

```python
python
import requests
import json

```

Here'e an example of a response from the request.

```python
[\
    {\
        "id": "1234",\
        "dob": "1980-01-01",\
        "ssn": "123-45-6789",\
        "name": "John Doe",\
        "level": "5",\
        "phone": "+123456789",\
        "photo": "https://example.com/photo.jpg",\
        "teams": [],\
        "title": "Software Engineer",\
        "gender": "Male",\
        "userId": "5678",\
        "lastName": "Doe",\
        "createdAt": "2021-01-01",\
        "firstName": "John",\
        "isManager": true,\
        "roleState": "Active",\
        "updatedAt": "2021-06-01",\
        "workEmail": "john.doe@example.com",\
        "department": "Engineering",\
        "flsaStatus": "Exempt",\
        "smallPhoto": "https://example.com/smallphoto.jpg",\
        "phoneNumber": "+123456789",\
        "compensation": {\
            "currency": "USD",\
            "salaryUnit": "Yearly",\
            "annualSalary": "100000",\
            "signingBonus": "5000",\
            "bonusSchedule": "Quarterly",\
            "salaryPerUnit": "25000",\
            "equityNumShares": 1000,\
            "relocationReimbursement": "2000"\
        },\
        "customFields": {},\
        "filingStatus": "Single",\
        "workLocation": {\
            "zip": "12345",\
            "city": "San Francisco",\
            "phone": "+123456789",\
            "state": "CA",\
            "country": "US",\
            "streetLine1": "123 Main St",\
            "streetLine2": "",\
            "steLocationCode": {\
                "psdCode": "",\
                "cityCode": "1",\
                "stateCode": "2",\
                "countyCode": "3",\
                "schoolCode": "",\
                "isOverridden": false,\
                "locationCode": "123",\
                "municipalityCode": "",\
                "transitDistrictCode": ""\
            },\
            "_smartystreets_validity": "Valid"\
        },\
        "workSchedule": {\
            "FRIDAY": {\
                "hours": "8"\
            },\
            "MONDAY": {\
                "hours": "8"\
            },\
            "SUNDAY": {\
                "hours": 0\
            },\
            "TUESDAY": {\
                "hours": "8"\
            },\
            "SATURDAY": {\
                "hours": 0\
            },\
            "THURSDAY": {\
                "hours": "8"\
            },\
            "WEDNESDAY": {\
                "hours": "8"\
            }\
        },\
        "payScheduleId": "123",\
        "personalEmail": "john.doe@gmail.com",\
        "employeeNumber": 12345,\
        "employmentType": "Full-time",\
        "workLocationId": "456",\
        "isInternational": false,\
        "identifiedGender": "Male",\
        "preferredLastName": "Doe",\
        "preferredFirstName": "John",\
        "workLocationNickname": "Main Office",\
        "companyEmploymentType": {\
            "id": "789",\
            "label": "Full-time",\
            "company": "ABC Corp",\
            "isHourly": false,\
            "createdAt": "2021-01-01",\
            "isDeleted": false,\
            "updatedAt": "2021-06-01",\
            "isFullTime": true,\
            "isPartTime": false,\
            "isSalaried": true,\
            "displayName": "Full-time",\
            "isTemporary": false,\
            "isContractor": false,\
            "external_on_changes": [],\
            "possible_new_employment_types": []\
        }\
    }\
]
```

_Related:_ [_What you need to know to perform API integration in Python_](https://www.merge.dev/blog/api-integration-python)

## **Final thoughts**

Your clients likely use a wide range of HRIS platforms—not just Rippling.

To cater to the varied landscape of HRIS tools, you can build to [Merge's HRIS Unified API](https://www.merge.dev/categories/hr-payroll-api). Once you’ve built to it, you can offer dozens of ticketing integrations to clients, whether that’s Workday, Namely, UKG, etc.

‍ _You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=04a6cd48-38f9-4c33-be45-e161ba381acd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bea62550-1a62-4457-a340-adc4d13c6ed1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=04a6cd48-38f9-4c33-be45-e161ba381acd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=bea62550-1a62-4457-a340-adc4d13c6ed1&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=77d73b7b-87ff-4947-ac2f-88d8dbf8aa70&bo=2&sid=4cfef2c03e8e11f0904f270d0b623b48&vid=4cffbaf03e8e11f08b9663da32a3f2ca&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20employees%20from%20Rippling%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-rippling-with-merge-hris-unified-api-using-python&r=&lt=342&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=414974)