---
url: "https://www.merge.dev/blog/how-to-get-employees-from-hris-merge"
title: "How to get employees from any HRIS with Merge"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#)

Table of contents

[Using Public APIs to Get Employee Data](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#using-public-apis-to-get-employee-data)

[Using Merge to Access HRIS Data](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#using-merge-to-access-hris-data)

[Setting Up Merge with BambooHR](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#setting-up-merge-with-bamboohr)

[Conclusion](https://www.merge.dev/blog/how-to-get-employees-from-hris-merge#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-employees-from-hris-merge)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**‍A guide to integrating with Workday’s API**](https://www.merge.dev/blog/workday-api-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadc1bfb5f5db30164e_Guide_to_HRIS_APIs.webp)**Guide to HRIS integrations**](https://www.merge.dev/blog/guide-to-hris-api-integrations)

# How to get employees from any HRIS with Merge

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae748c10442b0eba79_653701f158e63264e2e77528_How_to_get_employees_from_any_HRIS_with_Merge.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Amr Abdou

@Merge

‍

If you're building internal systems and applications like training programs, payment processing systems, and performance-tracking apps, you'll often need to integrate with multiple human resources information systems (HRISs) to fetch, update, and sync employee data.

Most modern HRISs offer public APIs to allow developers to integrate with them. However, these APIs are not uniform across platforms, which makes integrating with multiple HRISs complex and hard to maintain. A Unified API such as Merge can reduce the complexity of your application and save time and costs by letting you get employee data from multiple HRISs using a single API.

This article compares getting employee data using several public HRIS APIs with a Unified API like Merge. It explains why a Unified API is more time- and cost-effective and allows you to build a simpler, more secure application. It also covers cases where you need to stick to the vendor's public API and shows you what it's like to use Merge to integrate with a popular HRIS like [BambooHR](https://merge.dev/integrations/bamboohr).

_Related:_ [_What, exactly, is HR integration?_](https://www.merge.dev/blog/hr-integration)

## Using Public APIs to Get Employee Data

Your first option for getting employee data from multiple HRISs would be to use the vendors' public APIs. The challenge is that these APIs vary in many core aspects like protocols, authentication methods, object schema, data format, and endpoints.

Let's consider how the APIs of two of the most commonly-used, cloud-based, HRIS solutions, [Workday](https://merge.dev/integrations/workday) and [BambooHR](https://merge.dev/integrations/bamboohr), differ.

Workday has a SOAP API architecture that uses XML to exchange messages. To [get employee data using the Workday API](https://merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python), you need to:

- authenticate requests by creating an integrated system user (ISU) and giving it the required permissions;
- send requests and receive responses in XML format;
- send a POST request to the Get\_Workers\_Request endpoint; and
- handle responses according to their employee object schema.

On the other hand, BambooHR has a RESTful API, which is the most common standard for modern APIs. To [get employee data using BambooHR API](https://merge.dev/blog/how-to-pull-employee-data-from-the-bamboohr-api-with-examples), you need to:

- use HTTP requests;
- authenticate them using API Keys;
- exchange data in JSON format;
- send a GET request to the https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id} endpoint; and
- handle responses according to their specified object schema.

Integrating with only these two HRIS APIs will require extra time and, thus, costs. This process adds to the complexity of your solution.

First, you will need to spend time learning how to interact with each API and go through different sets of documentation created in different styles. The integrations themselves require you to use different authentication methods, perform data normalization and create custom SQL queries to process different data models, and use different endpoints and HTTP requests to pull the same type of data.

Even after building the integration, you will need to maintain it. You will have to keep up with two sets of API updates, revisit the API documentation with each update, update your code as regularly as needed, and ensure that you comply with any changes in the vendors' terms of service.

There are cases where there's no way around the complexity of integrating with multiple APIs. For instance, you might be building integrations with systems that don't serve the same purpose, such as integrating an internal system with HRIS and accounting cloud platforms.

However, if you need to integrate with multiple systems for the same purpose, a Unified API solution can be cost-effective and offer time savings.

## Using Merge to Access HRIS Data

Let's see what it would look like to use Merge's Unified API to get employee data from HRISs like Workday or Bamboo HR.

Merge provides a single programming interface to fetch, update, and sync data from multiple APIs. Its Unified API uses a single authentication method, standardized data schemes, and a single set of unified endpoints to send requests to all integrations across all HRIS platforms.

To start, Merge saves you the hassle of learning how to interact with several APIs and going through different sets of documentation. You only need to use one set of well-written and beautifully designed [documentation](https://docs.merge.dev/get-started/introduction/) and you create links with the relevant HRIS vendors using a single web-based UI.

Compared to integrating with multiple vendor APIs, a Unified API also shortens development time and reduces the complexity and code size of your integration. You only need to use one authentication method to send all API requests. It lets you use a unified schema for common data objects such as [employee](https://docs.merge.dev/hris/employees/#employees-object), [company](https://docs.merge.dev/hris/companies/#companies-object), and [location](https://docs.merge.dev/hris/locations/#locations-object). ou can also use object relationships and nesting for complex schemas.

You don't even have to worry about data normalization since you will be using a standardized data model for all integrations. Using one authentication method and standard endpoints across all integrations not only reduces complexity but also improves security.

Unified APIs can also improve the performance of your integration. It normalizes and syncs data at a frequency of your choice and then stores data to make it accessible through the API's standard endpoints.

Maintaining your integrations is also less time-consuming and costly. If a vendor updates their API, Merge updates its integration with them. Your integration with Merge remains unaffected. This means you don't have to frequently dive into the documentation of multiple APIs, update your integration to comply with each API update, explore new features, or remove deprecated and revoked functions.

Lastly, unlike most HRIS vendors, Merge provides [SDKs](https://docs.merge.dev/sdk/) for many programming languages. Merge's HRIS SDKs are available in many popular programming languages, including Python, Ruby, Go, Java, Elixir, and C#.

_Related:_ [_What is an employee API?_](https://www.merge.dev/blog/employee-api)

## Setting Up Merge with BambooHR

What is it like to use Merge to integrate with an HRIS such as BambooHR?The steps for setting up the integration and fetching employee data are the same no matter which HRIS you integrate with:

- Create a link between Merge and the HRIS.
- Get authentication tokens.
- Fetch employee data.

For illustrative purposes, we'll use BambooHR.

You'll need to have a Merge account and gain access to a BambooHR Sandbox to follow along. You can sign up for free accounts with [Merge](https://app.merge.dev/signup) and [BambooHR](https://www.bamboohr.com/signup/). The BambooHR account comes with demo data that you can use for testing.

The code sample that follows is written in Node. To run it, you need to have [Node](https://nodejs.org/en/download) installed along with [npm](https://nodejs.org/en/download).

### Create a Link Between Merge and the HRIS

Navigate to your [Merge dashboard](https://app.merge.dev/get-started/sync-sandbox-data) in your browser. If your account is newly created, you will see a **Get Started** page to help you create your first integration. Scroll down and click **Open Merge Link**. If you don't see the **Get Started** page in your dashboard, you can create a new link from the [**Test Linked Accounts**](https://app.merge.dev/linked-accounts/test-accounts) page.

[![Merge Get Started dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7968a565e357b6ba25c_w6qKLgi.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7968a565e357b6ba25c_w6qKLgi.webp)

In the pop-up that shows all the integration options available, select **Human Resources Information System** and then **BambooHR**:

[![Merge create link](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb64ef4f337db5c43cae_j6Wnd2y.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb64ef4f337db5c43cae_j6Wnd2y.webp)

Merge will start creating the link and syncing your data in the background. The link will take a few minutes or more depending on the size of your data. Once it is done, you will get a message that confirms the link is created:

[![Merge link created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb64960c05b1ed802de5_s3FGBvp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb64960c05b1ed802de5_s3FGBvp.webp)

#### Get Authentication Tokens

To authenticate every Merge API request, you need two keys: an _access key_ and an _account token_.

To get the access key, open the **API Keys** page from the left-side menu and copy the default key listed under the **Test Access Keys**.

[![Get Merge test access keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb641b32bb180e3f2fa5_IYTMtiB.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb641b32bb180e3f2fa5_IYTMtiB.webp)

The _account token_ is specific to every Merge link. To get the account token for your BambooHR integration, open the **Linked Accounts** page from the left-side menu. This page shows both the production and testing linked accounts. Click **Test Linked Accounts** on the top menu and then click on the BambooHR link that you created in the previous step:

[![View Merge test link accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb6437fd2fb50bd13b50_gXP2xDd.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb6437fd2fb50bd13b50_gXP2xDd.webp)

From the BambooHR link page, copy the _account token_:

[![Get Merge link account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb640d9c2e294a446f90_SF2A21k.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb640d9c2e294a446f90_SF2A21k.webp)

#### Fetch Employee Data

To send API requests to Merge endpoints, you will use the axios package.

Navigate to your project folder in your terminal, and run the following command:

```python
 npm install axios
```

In the same folder, create a file named **getEmployees.js**, open it, and paste in this code:

```python

const axios = require('axios');

const API_ACCESS_KEY = 'API ACCESS KEY HERE';
const BAMBOOHR_TOKEN = 'BAMBOOHR TOKEN HERE';

// Authorization Header
let config = {
    headers: {
        'Authorization': 'Bearer ' + API_ACCESS_KEY, // Test Access key
        'X-Account-Token': BAMBOOHR_TOKEN // BambooHR Key
    },
};

// Get Employees Request
axios.get('https://api.merge.dev/api/hris/v1/employees', config)
.then((result) => {
    console.log(result.data);
}).catch((error) => {
    console.log(error.response);
});

```

In this code, the axios library is imported at the first line, followed by declaring the `API_ACCESS_KEY` and `BAMBOOHR_TOKEN` variables. Then, the config variable is declared to hold the authorization headers. The axios.get function sends a GET request to the https://api.merge.dev/api/hris/v1/employees endpoint, which is the endpoint that can be used to get employee data from all HRIS integrations.

Before running the code, replace API ACCESS KEY HERE with your access key and BAMBOOHR TOKEN HERE with your BambooHR access token to authenticate requests.

To run the code, go to the terminal window and run the following command:

```python
node getEmployees.js
```

After the request execution, the response will look like this:

[![Merge employee object response](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb6471131fb70ede2582_JiZddRm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dabb6471131fb70ede2582_JiZddRm.webp)

The response data object includes pagination parameters and an array of the employees' data.

This [employee object](https://docs.merge.dev/hris/employees/) is unified across all the HRIS integrations supported by Merge, which means you can use these same steps to integrate your application with all the other HRIS vendors that Merge integrates with.

## Conclusion

Integrating with multiple HRIS APIs to get employee data is complex, time-consuming, and costly.

Though unavoidable in some cases—like when you're integrating with systems that don't serve the same purpose in your app or where the HRIS you need to integrate with is not supported by any Unified API—, using a unified API like Merge is more time- and cost-effective and results in a simpler, more secure solution.

[Merge](https://merge.dev/) provides a single programming interface to get data from more than fifty HRIS APIs, including Workday, BambooHR, ADP, Gusto, UKG Pro, and Hibob. You also get access to hundreds of integrations with accounting, ticketing, marketing automation, and file-storage platforms.

As you saw, getting employee data from a popular HRIS such as BambooHR requires only three straightforward steps. Merge also offers [webhooks](https://docs.merge.dev/basics/webhooks/overview/) that you can use to be notified of changes in data in HRIS platforms and trigger automated workflows.

Sign up for a [free Merge account](https://app.merge.dev/signup) to see how Merge helps reduce the time you spend on creating and maintaining integrations.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Amr Abdou

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