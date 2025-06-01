---
url: "https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples"
title: "How to Pull Employee Data from the BambooHR API (with examples)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#)

Table of contents

[BambooHR Developer API](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#bamboohr-developer-api)

[Pulling Employee Data from the BambooHR API](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#pulling-employee-data-from-the-bamboohr-api)

[Conclusion](https://www.merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples)

##### Just for you

No items found.

# How to Pull Employee Data from the BambooHR API (with examples)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856d2a5d5f07ea064916f3_Bamboo_Integration_Tutorial.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Sooter Saalu

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 40+ HRIS integrations with one_ [_HR API_](https://merge.dev/category/hr-payroll-api).

‍

BambooHR is a cloud-hosted solution for human resources (HR). It enables management, monitoring, and optimization across various HR functions, such as employee performance, employee satisfaction, recruitment, onboarding, payment, benefits, and employee vacation periods. It provides a holistic solution for typical HR challenges and helps HR professionals manage their work by providing a single source for employee data.

BambooHR provides an [API](https://documentation.bamboohr.com/docs) for its services, allowing users to programmatically access and update records on the platform.

The [BambooHR API](https://www.merge.dev/integrations/bamboohr) can be used to retrieve and amend employee and company data, generate files and reports from these data points, as well as to manage time tracking, goals, and tasks in the workspace.

This article provides a demonstration of how to pull employee data from the BambooHR API, using Python code, Postman requests, and the functionality available from Merge.dev.

#### Integrate with every HRIS through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of HRIS solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## BambooHR Developer API

The [BambooHR developer API](https://documentation.bamboohr.com/docs/api-details) is a RESTful API that utilizes HTTPS requests to access or modify all the available resources on the platform, such as employee data or company reports. Each request you make to the BambooHR API goes through authentication and authorization: the former checks to see if you have the necessary credentials to access the BambooHR domain, while the latter checks to see your permission level, which determines the data you are allowed to view and edit.

Your API requests will be made to a URL that begins with

`https://api.bamboohr.com/api/gateway.php/{company subdomain name}/`, with further additions made depending on the data being queried. The domain/subdomain name is your self-input tag for your BambooHR environment.

For the purposes of this article, a trial BambooHR account environment was created by registering on the [BambooHR](https://www.bamboohr.com/) platform.

[BambooHR authentication](https://documentation.bamboohr.com/docs/getting-started#authentication) is easily done. Simply log in to your registered/created BambooHR environment and go to the **Account** option under **Settings**, then **API Keys**, where you can generate and delete keys.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91bd_62d72647a64a7ac4b3e2679c_BambooHR_API_Keys.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91bd_62d72647a64a7ac4b3e2679c_BambooHR_API_Keys.webp)

Using the **Access Levels** option under **Settings**, you can set permission levels for your users to full access, no access, or some preset permission levels: employee, manager, or custom. Remember that the API key inherits the permission set of the user. If a user doesn’t have access to X field, then the API key they generate won’t have access to that field either.

Requests to the BambooHR developer API can return responses in JSON or XML; BambooHR provides functionality to choose the specific response format needed.

**Note:** BambooHR restricts access to the API if an unknown API key is repeatedly used in a request. While the API is restricted, all requests will return a “403 Forbidden” response.

Utilizing the BambooHR developer API, users can query and update employee data and files, company files and reports, time off and benefits, time and goal tracking, and training, among other services.

Want to use OAuth Bamboo allows for this if you have a partnership.

_Related:_ [_Examples of HR APIs_](https://www.merge.dev/blog/hr-api)

### Employee Data and Files

You can access and update your employee records, either in bulk or by individual employee. BambooHR has various API endpoints for its services; use the endpoint `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/` for querying a specific employee. Your self-input company name is the domain (for example, Touchstone), and the id is the unique numerical value for the specific employee. The particular data output from this request is dependent on the self-input query parameters based on the BambooHR API fields.

For example, sending a request to the endpoint `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/?fields=firstName%2ClastName` outputs the specific employee’s first name and last name, while the endpoint `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/?fields=firstName%2ClastName%2C%20birthday` adds in the employee’s birth date. You can also make use of the list of [field names](https://documentation.bamboohr.com/docs/list-of-field-names) for valid query parameters.

The API endpoint `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/files/{fileId}` retrieves specific employee files, where the added `fileId` corresponds to the specific employee file needed.

There are two methods to retrieve employee data in bulk from the API. The first method, getting the [employee directory](https://documentation.bamboohr.com/reference/get-employees-directory-1), can be restricted in the user account settings, leading to a “403 Forbidden” response. So it’s recommended instead to generate a [custom report](https://documentation.bamboohr.com/reference/request-custom-report-1) when bulk employee data is needed.

You can explore the mechanics of other use cases for the BambooHR API in the [documentation](https://documentation.bamboohr.com/reference). The page showcases the endpoints needed for the requests, the required parameters for those requests, and sample code in Shell, as well as four other software languages.

_Related:_ [_An example of an employee API_](https://www.merge.dev/blog/employee-api)

## Pulling Employee Data from the BambooHR API

Your employee data is arguably your most important resource on the BambooHR platform, and you might need to connect, aggregate, or visualize this data for better analysis. This article demonstrates pulling employee data from the BambooHR developer API using the following three methods: Python, Postman, and Merge.

[Authentication on BambooHR](https://documentation.bamboohr.com/docs/getting-started#authentication) is a requirement common to all methods. At this point, you should have your registered BambooHR domain and an authenticated BambooHR API key for this domain.

### Python

Using the requests library in Python, you can make API calls to BambooHR. As mentioned earlier, the BambooHR API utilizes a basic HTTPS authentication using the user API keys. This means that the API key needs to be encoded in base64 before being sent in the API call. The requests library has functionality for basic authentication encoding.

Here’s the code for pulling a single employee’s data from the BambooHR developer API:

```python
# First, install the requests library if needed
pip install -U requests

# Next, import the package
import requests

# Declare the API endpoint
‘’’
The domain is touchstone, the employee id is 4, and the requested BambooHR API fields (Query parameter) are the employee’s first name, last name, age, gender, job title, company department, and division:
‘’’
url = "https://api.bamboohr.com/api/gateway.php/touchstone/v1/employees/4/?fields=firstName%2ClastName%2Cage%2Cgender%2CjobTitle%2Cdepartment%2Cdivision"

Note that the directory endpoint only includes currently active employees - this means some blank ones will show up. In order to track changes, you would use the /employees/changed to get all terminated and active employees.

Additionally, note that all fields have to be included in query parameters, so you’ll need to confirm exactly what fields you need when making API requests.

# Adding in the headers for our request
‘’’
The only header needed for this request is the accepted format for the API response. As said earlier, this can be JSON or XML for this request:
‘’’

headers = {
    "Accept": "application/json"
}

# Making the API call
‘’’
The requests library has a basic authentication option so you can input your API key directly into the function. Only the API key is required in the username space for authentication, and the password variable can be a random string.
‘’’
response = requests.request("GET", url, headers=headers, auth=('xxxxxxAPIxxxxKEYxxx', 'pass'))

# Showcasing the response from the API call
print(response.text)
```

This will show you results similar to the following.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c0_62d726b4552cfc0593b9ec4d_Results_of_the_API_call_-_Python_Single_Employee.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c0_62d726b4552cfc0593b9ec4d_Results_of_the_API_call_-_Python_Single_Employee.webp)

The same methodology can be used to [pull bulk employee data from BambooHR using custom reports](https://documentation.bamboohr.com/reference/request-custom-report-1):

```python
import requests

# Custom Report Endpoint
‘’’
The required query parameter here is the format for the report; supported formats include CSV, PDF, XLS, XML, and JSON:
‘’’
url = "https://api.bamboohr.com/api/gateway.php/touchstone/v1/reports/custom?format=JSON"

# Body parameters
‘’’
For custom reports, parameters include the title of the report, date filters for the data, and, finally, the BambooHR API fields requested. These parameters are not hard requirements:
‘’’
payload = {"fields": ["firstName", "lastName", "age", "gender", "jobTitle", "department", "division"]}

headers = {
    "Content-Type": "application/json"
}

response = requests.request("POST", url, json=payload, headers=headers,auth=('xxxxxxAPIxxxxKEYxxx', 'pass'))

print(response.text)
```

This will show you results similar to the following.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d7d656def1c5da91af_62d726f3b5d0e5707ca2664f_Results_of_the_API_Call_-_Python_Bulk_Data.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d7d656def1c5da91af_62d726f3b5d0e5707ca2664f_Results_of_the_API_Call_-_Python_Bulk_Data.webp)

### Postman

[Postman](https://www.postman.com/) is an API platform for building and using APIs. It provides an easy interface to interact with APIs. You can pull employee data with Postman using the same information you used earlier with Python: the endpoints, API key, and various parameters.

First, you can create a new collection to categorize the requests you will be making. This helps ease authentication when requests use the same authorizations.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91cc_62d7271c9e685f5eccebbcdd_Create_New_in_Postman.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91cc_62d7271c9e685f5eccebbcdd_Create_New_in_Postman.webp)

Next, click on your created **Collection** and select the **Basic Auth** option in the authorization pane, then input your API key in the username space.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91cf_62d7274c6844a16d2041e16f_s0FSc5K.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91cf_62d7274c6844a16d2041e16f_s0FSc5K.webp)

Create a request within your **Collection**. Your first API call with Postman will involve pulling data for a single employee. Select the **Basic Auth** option under **Authorization** in your request, and it should inherit the inputted key from your collection. Then, input the API endpoint in the request URL space. As before, the standard endpoint for this call is `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}`.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9dad656def1c5da92a7_62d727683b2065e0fbb51574_cwAeb4Q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9dad656def1c5da92a7_62d727683b2065e0fbb51574_cwAeb4Q.webp)

Our last step for this call is to go to the **Params** tab and fill out the necessary query parameters. The key is **fields**, and the value is all the needed field names separated by commas. Sending this request should give similar results to the following.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9dad656def1c5da92a4_62d7278d47d9d05320a8756a_egLJMoY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9dad656def1c5da92a4_62d7278d47d9d05320a8756a_egLJMoY.webp)

The response is XML formatted by default, but this can be changed by editing the **Accept** parameter under the **Headers** tab, changing the default `/` for `application/json`.

The same steps can be undertaken for pulling bulk employee data from BambooHR using custom reports in Postman.

Create a new request under your created collection, select the basic auth option, input the needed endpoint, `https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/reports/custom`, which utilizes the HTTPS Post method instead of the GET, and select the right method ( **POST**) from the dropdown.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91d5_62d728f3f637981473e9fc22_URJ4pny.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91d5_62d728f3f637981473e9fc22_URJ4pny.webp)

Next, add in the format variable under the **Params** tab.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91fc_62d72ae12ddff415172cdd9e_vhBaver.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91fc_62d72ae12ddff415172cdd9e_vhBaver.webp)

Add a **Content-Type** parameter under the **Headers** tab.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91f9_62d72b17b65a595c883d1faf_S9Wtnzy.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91f9_62d72b17b65a595c883d1faf_S9Wtnzy.webp)

Finally, add in the BambooHR API fields needed under the **Body** tab. You can input these variables in the raw JSON format as below.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91ff_62d72b556844a1cf974521cd_OUfb87s.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91ff_62d72b556844a1cf974521cd_OUfb87s.webp)

This will show you results similar to the following.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c8_62d72b7b99c98d1d65a65f90_XkaRCx3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c8_62d72b7b99c98d1d65a65f90_XkaRCx3.webp)

### How To Pull Employees with Merge

[Merge](https://www.merge.dev/) is an API integration platform that eases the process of collating data from several API sources, allowing for querying and updating using a central API link.

To pull data from the BambooHR API using Merge, your first step is to register on the Merge platform, then connect BambooHR to the Merge platform. Merge provides an easy process to integrate other platforms on the website.

From your Merge homepage, go to **Linked Accounts**, then **Test Linked Accounts**, and add a “Test Account”. Choose BambooHR under **Human Resource Information System**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da924f_62d72bcb552cfc12a1bd1df6_9OcZDpV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da924f_62d72bcb552cfc12a1bd1df6_9OcZDpV.webp)

Log in to your BambooHR domain, and it should be integrated under your Merge linked accounts.

**Test Linked Accounts** is useful for trying out the Merge functionalities and looking for connection bugs. You can elevate your test linked account to a production account by checking the option on your test linked account settings.

Merge shows its utility when collating data from multiple integrations and domains. This collated data can be accessed from one API: the **Merge Unified API**. To utilize the Merge Unified API, you will need an account token and an API key. You can get your account token by clicking your created linked account. The **Account Token** can be found below.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c5_62d72c3caae1ba07d954c5a0_4D6nEwt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91c5_62d72c3caae1ba07d954c5a0_4D6nEwt.webp)

The API key can be found by clicking the **Configuration** option on the menu and then the **API Keys** tab.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91d2_62d72c6ea64a7a0aa2eaafd8_spGoxRT.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91d2_62d72c6ea64a7a0aa2eaafd8_spGoxRT.webp)

**Note**: A test API key was created for the test linked accounts demonstrated in this article. Test linked accounts require manual synchronization of your data, but their usage is not billed by Merge.

You can use the endpoint `https://api.merge.dev/api/hris/v1/employees` to pull bulk employee data from your integrated BambooHR domain on Merge, with request headers for the authentication key `Authorization: Bearer YOUR_API_KEY` and your account token `X-Account-Token: END_USER_ACCOUNT_TOKEN`.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91f6_62d72ca03b20651732bab6c8_LIqisX8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f9d9d656def1c5da91f6_62d72ca03b20651732bab6c8_LIqisX8.webp)

This utilizes the [Merge Common Model](https://app.merge.dev/configuration/common-models/hris%20%20https://app.merge.dev/configuration/common-models/hris) for employee data; this is a default configuration of data parameters that showcases the data available on employees across platforms. This model can be edited according to your needs and queried from a single endpoint without any additional parameters or editing.

If you want to pull custom fields that your customer has set up, you’re able to use Merge’s GET `/meta/fields` endpoint to pull.

This endpoint and all others are well documented in the [Merge API documentation](https://www.merge.dev/docs/hris/overview), where you can explore the common data models across the human resources, accounting, and recruiting categories as well as information on getting additional data.

Merge helps you integrate data from multiple sources feeding into a single API link for the eventual user.

## Conclusion

In this article, you learned how to query and access BambooHR’s API using Python, Postman, and Merge, exploring the mechanics of each method and how they work.

[Merge](https://www.merge.dev/) is a single RESTful API platform that allows easy integration of clients across [human resources](https://merge.dev/categories/hr-payroll-api), [applicant tracking](https://merge.dev/categories/ats-recruiting-api), [accounting](https://merge.dev/categories/accounting-api), [CRM](https://merge.dev/categories/crm-api), [file storage](https://merge.dev/categories/file-storage-api), and [ticketing](https://merge.dev/categories/ticketing-api) system categories. It provides a unified platform link for seamless management of your company’s assets and data resources.

And check out our [Guide to ATS Integrations](https://www.merge.dev/blog/guide-to-ats-api-integrations) if you're looking to add integrations to [BambooHR](https://merge.dev/integrations/bamboohr), [Workday](https://merge.dev/integrations/workday), [Taleo](https://merge.dev/integrations/oracle-taleo), [SuccessFactors](https://merge.dev/integrations/sap-successfactors), and more.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Sooter Saalu

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d6a0bf92-8d0e-4f98-b07c-604f4638b98f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b927ad09-16f5-4493-960f-b05eab6c63fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d6a0bf92-8d0e-4f98-b07c-604f4638b98f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b927ad09-16f5-4493-960f-b05eab6c63fc&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=6c670e4f-0f73-4e25-bd97-a3fd4d8c36ff&bo=2&sid=52dbe4a03e8c11f0bca1b55641761f3b&vid=52dcbf003e8c11f0b50e390237858325&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20Pull%20Employee%20Data%20from%20the%20BambooHR%20API%20(with%20examples)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-pull-employee-data-from-the-bamboohr-api-with-examples&r=&lt=457&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=950522)