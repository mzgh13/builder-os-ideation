---
url: "https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript"
title: "How to fetch employees from Gusto using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#)

Table of contents

[Authenticating with Gusto API](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#authenticating-with-gusto-api)

[FETCH Employees with Merge HRIS Unified API](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#fetch-employees-with-merge-hris-unified-api)

[Leveraging a Unified HRIS API for Efficient Integrations](https://www.merge.dev/blog/how-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript#leveraging-a-unified-hris-api-for-efficient-integrations)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript)

##### Just for you

No items found.

# How to fetch employees from Gusto using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

No items found.

**_Editor's note_** _: this article is part of a series on building third-party API integrations. Explore Merge if you’re looking to add 180+ integrations across HR and payroll, ATS, CRM, accounting, ticketing, marketing automation, and file storage with one_ [_unified API_](https://www.merge.dev/) _._

Gusto serves as a robust Human Resources Information System (HRIS), aiding enterprises in the effective management and streamlining of their HR workflows. It delivers a broad spectrum of features encompassing payroll management, benefits administration, and time tracking, all of which are readily accessible through an intuitive portal. Gusto also offers an API, enabling developers to incorporate Gusto's HR functionalities into their bespoke applications and systems.

Developers may want to extract employee data from a client's Gusto system for the purpose of integrating HR data into other business applications such as project management tools, payroll software, or analytics platforms. This integration point facilitates a smooth flow of data, minimizing manual input and paving the way for more precise and efficient operations across systems.

Merge offers its Unified API as a tool that enables developers to incorporate hundreds of integrations, Gusto included, with a single API. This article guides you through the process of connecting to the Gusto API to retrieve a list of Employees, using both the Gusto API and the [Merge HRIS Unified API](https://merge.dev/categories/hr-payroll-api).

## Authenticating with Gusto API

To connect and interact with the Gusto API, you will need to setup an OAuth 2.0 authentication flow. This is a standard protocol for authorization and allows you to access user data in a secure manner.

Gusto uses the Authorization Code grant type. To start off, the users need to navigate to the authorization URL at `https://api.gusto.com/oauth/authorize`. After successfully completing the authorization process, Gusto will redirect the user back to the `redirect_url` you've provided. The authorization code will be included as a query parameter named `code`.

Once you have the authorization code, you can exchange it for an access token. To do this, make a POST request to the token URL `https://api.gusto.com/oauth/token` and pass the `client_id`, `client_secret`, and other required parameters in the body of the request.

Here's what a request might look like:

```javascript
const axios = require('axios');
const params = new URLSearchParams();
params.append('client_id', 'yourClientId');
params.append('client_secret', 'yourClientSecret');
params.append('code', 'authorizationCode');
params.append('grant_type', 'authorization_code');
params.append('redirect_uri', 'yourRedirectUri');

axios.post('https://api.gusto.com/oauth/token', params)
.then((response) => {
    console.log(response.data);
}).catch((error) => {
    console.error(error);
});
```

The response will contain the `access_token`, `expires_in` (the lifespan of the token in seconds), and `refresh_token`. The `access_token` is what you'll use to authenticate your requests to the Gusto API.

When the `access_token` is about to expire, you should use the `refresh_token` to obtain a new one. This can be done by making a POST request to the same token URL as above, but this time with a `grant_type` of `refresh_token` and passing the `refresh_token` as a parameter.

Remember to store these tokens securely and never expose them in client-side code or version control systems.

```javascript
const axios = require('axios');
let accessToken = 'your_access_token'; // replace this with your actual access token

// Step 1: Fetch the user's roles
axios.get('https://api.gusto.com/v1/me', {
  headers: {
    'Authorization': `Bearer ${accessToken}`
  }
}).then(response => {
  let userRoles = response.data['roles'];

  // Step 2: Loop over the user's roles
  userRoles['payroll_admin']['companies'].forEach(company => {
    let companyId = company['uuid'];

    // Step 3: Fetch the employees for each company
    axios.get(`https://api.gusto.com/v1/companies/${companyId}/employees`, {
      params: {
        include: 'all_compensations,custom_fields'
      },
      headers: {
        'Authorization': `Bearer ${accessToken}`
      }
    }).then(response => {
      console.log(response.data);
    }).catch(error => {
      console.error(error);
    });
  });
}).catch(error => {
  console.error(error);
});
```

This script uses the `axios` library to perform HTTP requests. It first fetches the user's roles from the Gusto API, loops over the companies the user is a payroll admin for, and finally fetches and logs the employees for each company.

The `Authorization` header is set to `Bearer ${accessToken}`, where `${accessToken}` is replaced by your actual access token.

The `include` parameter is set to `all_compensations,custom_fields` to include all compensation and custom field data in the employee response.

Remember, this is a basic example and does not include error handling or pagination. In a production environment, you would want to implement additional checks and handle potential exceptions properly. Also, you would need to handle pagination to ensure you get all the employees if there are more than can be returned in a single response.

To refresh the access token, you would need to hit the token URL again with the `refresh_token` that you received in the original response.

An example of an individual item returned by this API Endpoint is:

```json
{
    "uuid": "123456",
    "first_name": "John",
    "middle_initial": "P",
    "last_name": "Doe",
    "email": "john.doe@example.com",
    "company_uuid": "abcdef",
    "manager_uuid": "def456",
    "version": "1.0",
    "current_employment_status": "active",
    "onboarding_status": "completed",
    "preferred_first_name": "Johnny",
    "department_uuid": "dep123",
    "payment_method": "direct deposit",
    "department": "Sales",
    "terminated": false,
    "two_percent_shareholder": false,
    "onboarded": true,
    "has_ssn": true,
    "jobs": [\
        {\
            "uuid": "job789",\
            "version": "1.0",\
            "employee_uuid": "123456",\
            "location_uuid": "loc456",\
            "current_compensation_uuid": "comp123",\
            "payment_unit": "hourly",\
            "primary": true,\
            "two_percent_shareholder": false,\
            "title": "Sales Manager",\
            "compensations": [\
                {\
                    "uuid": "comp456",\
                    "employee_uuid": "123456",\
                    "version": "1.0",\
                    "payment_unit": "hourly",\
                    "flsa_status": "exempt",\
                    "adjust_for_minimum_wage": false,\
                    "minimum_wages": [],\
                    "job_uuid": "job789",\
                    "effective_date": "2022-01-01",\
                    "rate": "$20.00"\
                }\
            ],\
            "rate": "$20.00",\
            "hire_date": "2022-01-01",\
            "location": {\
                "zip": "90210",\
                "city": "Beverly Hills",\
                "uuid": "loc456",\
                "state": "CA",\
                "country": "USA",\
                "inactive": false,\
                "street_1": "123 Main St",\
                "street_2": "Suite 200"\
            }\
        }\
    ],
    "eligible_paid_time_off": [\
        {\
            "name": "Vacation",\
            "policy_name": "vacation policy",\
            "policy_uuid": "pol123",\
            "accrual_unit": "hours",\
            "accrual_rate": "1.5",\
            "accrual_method": "per pay period",\
            "accrual_period": "biweekly",\
            "accrual_balance": "80",\
            "maximum_accrual_balance": "200",\
            "paid_at_termination": true\
        }\
    ],
    "terminations": [],
    "home_address": {
        "zip": "90210",
        "city": "Beverly Hills",
        "state": "CA",
        "active": true,
        "country": "USA",
        "version": "1.0",
        "street_1": "123 Main St",
        "street_2": "Suite 200",
        "employee_uuid": "123456"
    },
    "garnishments": [],
    "custom_fields": [],
    "date_of_birth": "1990-01-01",
    "ssn": "123-45-6789",
    "phone": "(123) 456-7890",
    "work_email": "john.doe@company.com"
}
```

_Related:_ [_A guide to automating user provisioning and deprovisioning processes_](https://www.merge.dev/blog/automated-provisioning-and-deprovisioning)

## FETCH Employees with Merge HRIS Unified API

The Merge API is a great way to pull normalized HRIS data from a variety of HRIS tools, including Gusto.

When making requests to the Merge API, you will need to pass proper authentication parameters so that you can identify yourself as an authorized user. You'll need to include a Merge API Key (YOUR\_API\_KEY) and a Linked Account Token (END\_USER\_ACCOUNT\_TOKEN) for every request you send to the Merge API.

```javascript
import fetch from 'node-fetch'

let conf = new Configuration({
    apiKey: "YOUR_API_KEY",
    accessToken: "END_USER_ACCOUNT_TOKEN",
    fetchApi: fetch
});
```

Once you've authenticated to Merge, you'll next use the API client to make a GET request using the Linked Account Token of the customer whose data you're accessing.

```javascript
const employeesApi = new merge_sdk.HRIS.EmployeesApi(conf);

let response = await employeesApi.employeesList({}).catch((reason) => {
    console.log(reason);
});
console.log(response);
```

The response you get back from the Merge API will include normalized data for any HRIS integration, including Gusto. To explore the standard response format, check out the API reference at [https://docs.gusto.com/](https://docs.gusto.com/).

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

What if JavaScript or other programming languages are not your strong suit? Or what if Gusto is merely one among many integrations you and your team are tasked with developing and managing?

That's where the power of a Unified API like [Merge](https://merge.dev/) comes into play.

Merge provides an [HRIS integration API](https://merge.dev/categories/hr-payroll-api) that offers a single API endpoint that links to multiple platforms and services, Gusto included. This API endpoint functions as a conduit between various platforms, enabling users to engage with all of them through one centralized API endpoint.

Merge achieves this through the utilization of a plugin system, which enables it to link with different platforms and services. These plugins act as intermediaries, connecting Merge’s API endpoint with data from various HRIS applications. Each plugin is tasked with managing the specific communication protocols, APIs, and data structures of the system to which it is connected.

When a user initiates an API call to Merge, the call is directed to the relevant plugin based on the data provided in the call. The plugin then processes the call and delivers the corresponding response. This approach enables users to engage with all the different systems via a single, Unified API endpoint.

Merge oversees these integrations, streamlining authentication with a one-click UI component, and proactively identifying permissioning errors caused by your customers, such as an incorrect API key. This significantly alleviates the engineering effort associated with an integration product over its lifetime. In this piece, we've guided you on how to leverage JavaScript to access Employee data from Gusto.

Should your requirements involve integration with multiple Human Resource Information Systems (HRIS), consider utilizing Merge's unified API. This powerful tool enables you to tap into a variety of HRIS platforms, Gusto included, through a solitary call. This eradicates the necessity for numerous integrations, streamlining the construction of an integrated ecosystem. By doing so, you can concentrate on refining your core product and broadening your accessible market.

To get started with Merge, you can [sign up for free](https://merge.dev/) or [request a demo](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6e05c377-d3b1-49bf-af9a-e9127015542f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2e616ed7-29de-4def-90b8-3ae0dfcdecb8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6e05c377-d3b1-49bf-af9a-e9127015542f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2e616ed7-29de-4def-90b8-3ae0dfcdecb8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=7e07a0cd-bcd4-491d-95d3-345492257f67&bo=2&sid=0fb382103e8e11f09c2c23f3d09f59f2&vid=0fb3ccc03e8e11f09107d9597ce9775c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20employees%20from%20Gusto%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-employees-from-gusto-with-merge-hris-unified-api-using-javascript&r=&lt=471&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=485882)