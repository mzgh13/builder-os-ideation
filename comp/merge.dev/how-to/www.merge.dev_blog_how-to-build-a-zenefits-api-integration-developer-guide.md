---
url: "https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide"
title: "How to Build a Zenefits API Integration: Developer Guide"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#)

Table of contents

[Integration with the Zenefits API Through Merge](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#integration-with-the-zenefits-api-through-merge)

[Set Up Webhooks](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#set-up-webhooks)

[Conclusion](https://www.merge.dev/blog/how-to-build-a-zenefits-api-integration-developer-guide#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-a-zenefits-api-integration-developer-guide)

##### Just for you

No items found.

# How to Build a Zenefits API Integration: Developer Guide

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cf025b20320c1db5a98_Zenefits_API_Integration_Logo.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Anshuman Bhardwaj

@Merge

[Zenefits](https://www.zenefits.com/) is a popular HRIS with features that range from onboarding and exiting, payroll, benefits, and time tracking. As you’re building out your own app’s integration support, providing users an easy way to sync their Zenefits data with your own app can drive more sales.

One of the easiest ways to provide a Zenefits integration for your app or platform is to build an integration through Merge. Merge is a Unified API for B2B integrations, and provides a seamless way for all your app to connect to Zenefits and 40+ other HR, Payroll, and Directory platforms.

In this guide, you’ll learn about the easiest way to set up a Zenefits integration, retrieve the access key from the dashboard to authenticate appropriately with the Merge API, and integrate it with your users’ Zenefits account. You’ll then use the Merge API to collect information from companies and employees that are using your Zenefits account. Lastly, you’ll set up webhooks to stay up-to-date with data updates and secure your webhook endpoint with signature hashing.

Let’s get started.

## Integration with the Zenefits API Through Merge

Before starting, you’ll want to make sure you have the following setup. This will allow you to test your integration to make sure it works for your users.

- Have access to an existing [Zenefits](https://www.zenefits.com/) account.
- [Sign up](https://app.merge.dev/signup) for a free account on Merge and access to their API keys.

_Related:_ [_A guide to choosing between polling and webhooks_](https://merge.dev/blog/webhooks-vs-polling)

### Authenticate with the Merge API

The Merge Unified API is accessed via two forms of authentication.

The first, a **Production Access Key** authorizes you as a user of Merge.

The second, a **Linked Account Token**, authorizes that your API requests are being made on behalf of a specific user.

You collect your **Production Access Key** from the Merge dashboard to authenticate using the Merge API.

Follow the steps below to get the access key:

1\. Open the [Merge dashboard](https://app.merge.dev/).

2\. Click on **Configuration** on the left sidebar.

3\. Click on the **API Keys** tab of the configuration page.

4\. Copy the **Production Access Key** from the Organization Secrets section of the page and save it for later.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a96d3ef1491bf8c314a4_Znenefits.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a96d3ef1491bf8c314a4_Znenefits.png)

We’ll walk through how to create a Linked Account Token, next.

### Create a Linked Account Token via Zenefits

Next, we’ll want to set up your link\_token in Zenefits.

1\. Open the [Zenefits dashboard](https://secure.zenefits.com/dashboard/#/)) in your web browser.

2\. Click on the hamburger icon on the top navigation bar to open the sidebar.

3\. Click on **Company Profile**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a96d3ef1491bf8c314a4_Znenefits.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a96d3ef1491bf8c314a4_Znenefits.png)

4\. On the **Company Profile** page, click on **Custom Integrations**.

5\. Click on the **Add Token** button to create a new REST API token. Make sure to tick all the checkboxes in the form.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5dd38773b3ec117188bd1_CreateToken.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5dd38773b3ec117188bd1_CreateToken.png)

Once ready, the new token will show in the list as a secret. Click on the eye icon to see the token, and save it somewhere safe for use later.

### Link Your Zenefits Account with Merge

1\. Open your [Merge dashboard](https://app.merge.dev/).

2\. Click on **Linked Accounts** in the left sidebar.

3\. Select the **Test Linked Accounts** tab on the Linked Accounts page.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5dd57b33ae23cc5eed8a0_jpWp8hI.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5dd57b33ae23cc5eed8a0_jpWp8hI.png)

4\. Follow the steps shown in the video below to link your Zenefits account with Merge:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5deb221ff1245471c8263_ezgif-3-09e05869ac.gif)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5deb221ff1245471c8263_ezgif-3-09e05869ac.gif)

5\. Click on the newly linked Zenefits account in the table.

6\. Copy the **Account Token** from the Overview section. Later in this tutorial, the account token will be sent as a header called X-Account-Token to authorize your Merge API requests to collect end users’ data from your Zenefits account.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5ddadeeb6432060d638d4_Copy_Account_Token.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5ddadeeb6432060d638d4_Copy_Account_Token.png)

### Convert to Production Account

To use the Merge API in production applications, convert the linked account to production by clicking on the **Settings** tab and clicking on **Convert to Production Linked Account**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5ddc7b33ae2c65eeef480_Convert_to_Production.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5ddc7b33ae2c65eeef480_Convert_to_Production.png)

Now that you have the access-key and account-token, you can use the Merge API to access the data from your Zenefits account.

### Make Requests to Zenefits Using the Merge API

The following examples use the node-fetch npm package to make HTTP calls to the Merge HRIS API.

Run npm install --save node-fetch@2 to install the package.

#### Get Companies’ Details

All information about how common models work with the Merge HRIS Unified API is stored in our documentation. You can view it [here](https://merge.dev/docs/hris/overview/).

Use the /companies endpoint of the Merge API to get the list of companies available in your Zenefits account:

```javascript
// require fetch from node-fetch
const fetch = require("node-fetch");

// create new headers object
let requestHeaders = new fetch.Headers();

// replace with the Merge production access key
requestHeaders.append("Authorization", "Bearer <access-key>");

// replace with the Zenefits account token copied from Merge
requestHeaders.append("X-Account-Token", "<account-token>");

const requestOptions = {
  method: 'GET',
  headers: requestHeaders
};

fetch("https://api.merge.dev/api/hris/v1/companies", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

#### Get a List of Employees

Use the /employees endpoint of the Merge API to get a list of all employees available in your Zenefits account:

```javascript
// require fetch from node-fetch
const fetch = require("node-fetch");

// create new headers object
let requestHeaders = new fetch.Headers();

// replace with the Merge production access key
requestHeaders.append("Authorization", "Bearer <access-key>");

// replace with the Zenefits account token copied from Merge
requestHeaders.append("X-Account-Token", "<account-token>");

const requestOptions = {
  method: 'GET',
  headers: requestHeaders
};

fetch("https://api.merge.dev/api/hris/v1/employees", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

#### Get Employee Details by ID

Use the /employees/:employeeId endpoint of the Merge API to get the information of a given employee using their employee ID from your Zenefits account:

```javascript
// require fetch from node-fetch
const fetch = require("node-fetch");

// create new headers object
let requestHeaders = new fetch.Headers();

// replace with the Merge production access key
requestHeaders.append("Authorization", "Bearer <access-key>");

// replace with the Zenefits account token copied from Merge
requestHeaders.append("X-Account-Token", "<account-token>");

const requestOptions = {
  method: 'GET',
  headers: requestHeaders
};

// replace the :employeeId in the URL with an employee id copied from response of previous request
fetch("https://api.merge.dev/api/hris/v1/employees/d79f64ff-335f-44ae-a9ab-d257acc31e3a", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

### Make Requests to Zenefits Using Merge SDKs

You can also use the Merge SDKs to get data from Zenefits. The following examples use Merge’s Node/TS SDK, and you can choose to view a full list of the SDKs that Merge provides [here](https://merge.dev/docs/sdk/).

#### Install the SDK

Run npm install --save @mergeapi/merge-hris-node to install the Merge SDK in your project.

#### Get Companies’ Details

Use the companiesList method to get a list of companies available in your Zenefits account:

```javascript
// require the modules from Merge SDK
const { CompaniesApi, HttpBearerAuth} = require("@mergeapi/merge-hris-node");

// create a new http auth provider
const auth = new HttpBearerAuth();
auth.accessToken =  "<access-key>" // replace with the Merge production access key

// create a CompaniesApi instance
const companyApi = new CompaniesApi();

// provide access key for authentication with Merge
companyApi.setDefaultAuthentication(auth);

// replace with the Zenefits account token copied from Merge
const xAccountToken = "<account-token>"

// request the list of companies from Merge
companyApi.companiesList(xAccountToken).then(({ body }) => {
    console.log('Companies list', body)
})
```

#### Get a List of Employees

Use the employeesList method to get a list of all employees available in your Zenefits account:

```javascript
// require the modules from Merge SDK
const { EmployeesApi, HttpBearerAuth} = require("@mergeapi/merge-hris-node");

// create a new http auth provider
const auth = new HttpBearerAuth();

// replace with the Merge production access key
auth.accessToken =  "<access-key>"

// create a EmployeesApi instance
const employeeApi = new EmployeesApi();

// provide access key for authentication with Merge
employeeApi.setDefaultAuthentication(auth);

// replace with the Zenefits account token copied from Merge
const xAccountToken = "<account-token>"

// request the list of employees from Merge
employeeApi.employeesList(xAccountToken).then(({body}) => {
    console.log('Employees list', body)
})
```

#### Get Employee Details by ID

Use the employeesRetrieve method to get the information of a given employee using their employee ID from your Zenefits account. Provide the employeeId as the second parameter when invoking the employeesRetrieve method:

```javascript
// require the modules from Merge SDK
const { EmployeesApi, HttpBearerAuth} = require("@mergeapi/merge-hris-node");

// create a new http auth provider
const auth = new HttpBearerAuth();

// replace with the Merge production access key
auth.accessToken =  "<access-key>"

// create a EmployeesApi instance
const employeeApi = new EmployeesApi();

// provide access key for authentication with Merge
employeeApi.setDefaultAuthentication(auth);

// replace with the Zenefits account token copied from Merge
const xAccountToken = "<account-token>"

// copied from the response of previous example
const employeeId = '96567b3c-a856-4d3e-a9d6-85cd7c7ffc2d'

// request the data of employee with a given employeeId
employeeApi.employeesRetrieve(xAccountToken, employeeId).then(({body}) => {
    console.log('Employee details', body)
})
```

## Set Up Webhooks

Keeping yourself up-to-date with the latest data from Merge has synced from your users’ Zenefits account might be difficult over time. That’s why Merge allows you to subscribe to their webhooks to receive updates rather than continuously checking on them. Merge’s webhooks will make POST requests to the API endpoint you registered and provide data in the request body.

Follow the steps below to set up a webhook in Merge:

1\. Open the [Webhooks configuration page](https://app.merge.dev/configuration/webhooks/) on your Merge dashboard, and click on **Add webhook** button.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a99385742fd33eab6f5b_Add_Webhook.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a99385742fd33eab6f5b_Add_Webhook.png)

2\. Input the Webhook URL that will be called by a POST request by Merge, select the subscription type, either sync notifications or data changes, and click the **Add webhook** button.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a99385742fd33eab6f5b_Add_Webhook.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a99385742fd33eab6f5b_Add_Webhook.png)

That’s it. The webhook will automatically report the latest data to your API endpoint, as shown below.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a9e0e7a1c5d1aff178c2_Webhook.site.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5a9e0e7a1c5d1aff178c2_Webhook.site.png)

### Secure Your Webhook

Securing your webhook endpoint is critical to prevent malicious requests from coming through. You can hash the request body content with the signature copied from the Merge dashboard. To verify the request’s authenticity, compare the hashed request body with the value of the X-Merge-Webhook-Signature header Merge sends with each request.

To copy your webhook signature, open the [Webhooks configuration page](https://app.merge.dev/configuration/webhooks/) on your Merge dashboard and copy the token from the **Security** section to use later.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5aa083ef1493c0bc31aa1_Webhook_Sceurity.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/62f5aa083ef1493c0bc31aa1_Webhook_Sceurity.png)

The example below shows how to secure your webhook in Node.js and Express.

Run npm i --save express to install Express.

```javascript
const express = require("express");
const crypto = require("crypto");
const server = express();
const PORT = 8080;

server.post("/webhook", (request, response) => {
    const b64_encoded = crypto.createHmac("sha256", "<webhook-signature-copied-from-merge>").update(request.body).digest("base64");
    const sentByMerge = b64_encoded == request.headers["X-Merge-Webhook-Signature"]
    if(!sentByMerge) {
        response.status(400).send('Invalid request!')
    } else {
        // do your operation
    }
});

// start the server at <http://localhost>:{PORT}
server.listen(PORT, () => {
    console.log(`server is running at port: ${PORT}`);
});
```

## Conclusion

In this guide, you learned to set up a Merge account, retrieve the access key from your Merge dashboard, and integrate it with your Zenefits account. Using Merge’s Unified API, you also worked through different ways to access company and employee information from your Zenefits account. Lastly, you set up webhooks to stay up-to-date with data updates, including securing your webhook endpoint.

You can read more about the Merge HRIS API on our [documentation](https://merge.dev/docs/hris/overview/) page, which explains all domains and endpoints.

[Merge’s](https://merge.dev/) unified API for payroll, HR, recruiting, accounting, and ticketing solutions helps you build HR integrations with Zenefits and more than thirty-two other integrations through a single API. You can link as many integrations—even from different providers—to your Merge account and access all the data with one API.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Anshuman Bhardwaj

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