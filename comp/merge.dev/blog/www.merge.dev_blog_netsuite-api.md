---
url: "https://www.merge.dev/blog/netsuite-api"
title: "How to integrate with NetSuite's API in 2025"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/netsuite-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/netsuite-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/netsuite-api#)

Table of contents

[What is a NetSuite API integration?](https://www.merge.dev/blog/netsuite-api#what-is-a-netsuite-api-integration)

[Getting authentication credentials for your NetSuite integration](https://www.merge.dev/blog/netsuite-api#getting-authentication-credentials-for-your-netsuite-integration)

[Best practices for integrating with NetSuite’s API](https://www.merge.dev/blog/netsuite-api#best-practices-for-integrating-with-netsuites-api)

[NetSuite API integration examples](https://www.merge.dev/blog/netsuite-api#netsuite-api-integration-examples)

[Challenges of integrating with NetSuite](https://www.merge.dev/blog/netsuite-api#challenges-of-integrating-with-netsuite)

[Integrate NetSuite and other accounting platforms with your product via Merge’s Unified API](https://www.merge.dev/blog/netsuite-api#integrate-netsuite-and-other-accounting-platforms-with-your-product-via-merges-unified-api)

[NetSuite API integration FAQ](https://www.merge.dev/blog/netsuite-api#netsuite-api-integration-faq)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fnetsuite-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856d29748c10442b0f42ed_JSON.webp)**How to GET invoices in JSON from the Netsuite SOAP API using Python**](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Accounting integrations: examples, benefits, and tools**](https://www.merge.dev/blog/accounting-integration)

# How to integrate with NetSuite's API in 2025

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

NetSuite, a leading ERP system for organizations of all shapes and sizes, typically collects and creates valuable financial data. In addition, it supports key financial processes, whether that’s related to accounts payable, accounts receivable, expense management, and more.

Given the platform’s value, you’ll likely need to integrate your internal instance of NetSuite with your other applications as well as connect customers’ instances with your product.

We’ll break down how you can integrate to NetSuite successfully—regardless of your use case—and highlight impactful examples to help you prioritize your integration efforts.

But to start, let’s align on the definition of a NetSuite API integration.

## **What is a NetSuite API integration?**

It’s any API-based connection to NetSuite that lets you access and interact with data and functionality in the ERP system.

In addition, the integration falls into one of two scenarios: building to an internal instance of NetSuite to automate a workflow(s) within your company, or building to a customer's instance of NetSuite to automate a workflow(s) between your product and their version of the ERP system.

[![Types of NetSuite API integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671088c7ab3b1468f98f46ee_671088a6bfc7588d9c82d006_Types%2520of%2520NetSuite%2520integrations%2520(1).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671088c7ab3b1468f98f46ee_671088a6bfc7588d9c82d006_Types%2520of%2520NetSuite%2520integrations%2520(1).webp)

_Related:_ [_Overview on QuickBooks Online’s API_](https://www.merge.dev/blog/quickbooks-api)

## **Getting authentication credentials for your NetSuite integration**

Before you can start making API requests to NetSuite’s API, you’ll need to get your unique authentication credentials.

Here are the steps you’ll need to take to get these credentials:

1\. Ensure your account has administrator access.

2\. Enable web services and token-based authentication. You can do this by visiting the setup page. Click on company, and then select enable features. You should set up your permissions to the following:

[![Selecting your SuiteScript settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb81acd306430db845b2a_AD_4nXdQna12WDwawxYM1sk_aWWBuNhVRIb8ORdYr-XNTqOrcI2cvuQU2dpMW7ragkjfegZOleBmznjR4NrGNJXmHUkds9VzR5adV2nxVm8hYYI1kaNQ4OYW8pK3jDjfsefI-OHVFhNo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb81acd306430db845b2a_AD_4nXdQna12WDwawxYM1sk_aWWBuNhVRIb8ORdYr-XNTqOrcI2cvuQU2dpMW7ragkjfegZOleBmznjR4NrGNJXmHUkds9VzR5adV2nxVm8hYYI1kaNQ4OYW8pK3jDjfsefI-OHVFhNo.webp)

[![Selecting your SuiteTalk settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb818aa84de39bc7fde16_AD_4nXcyfj1jX-6h8Li-46IxkXs60Aa1rS-BNRZARkZup9CPzJo-uOq3UYWXrxYVC7nkqpJHOmr0CNpium-NbMnA5bQFUjYtW2-JhIKAM2o0g9CLzTGq-xRJVnSjLproCvli6zb5CmrH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb818aa84de39bc7fde16_AD_4nXcyfj1jX-6h8Li-46IxkXs60Aa1rS-BNRZARkZup9CPzJo-uOq3UYWXrxYVC7nkqpJHOmr0CNpium-NbMnA5bQFUjYtW2-JhIKAM2o0g9CLzTGq-xRJVnSjLproCvli6zb5CmrH.webp)

[![Managing your authentication](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb8182cd1296ebd67e079_AD_4nXejj2Dqb1ar8iJPYC4eevt9pQ8OGH5Bl0GCImRnz0tHj2Ntb4QTzN7xUsUyB8dlvBdA2Jgy3Kad2fdAo7kow4lGkiQavrPgkIuGzAaMD6fTiKmh4LDcEBdopaLOz4YoY6P84VEqaQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb8182cd1296ebd67e079_AD_4nXejj2Dqb1ar8iJPYC4eevt9pQ8OGH5Bl0GCImRnz0tHj2Ntb4QTzN7xUsUyB8dlvBdA2Jgy3Kad2fdAo7kow4lGkiQavrPgkIuGzAaMD6fTiKmh4LDcEBdopaLOz4YoY6P84VEqaQ.webp)

3\. Find your Netsuite account ID. This is the combination of letters or numbers that appear before "app.netsuite.com."

4\. Create a role.

5\. Assign a user to that role.

6\. Create an integration to obtain your consumer key and secret.

[![Creating an integration in NetSuite](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb8182e4a0736617e8687_AD_4nXe0lIWl7-wh4uPrMVHqBTNyEH-PmsNjf__GTEfYM4TFCywBNP3M8KKa_EEG4m4zGcshhAt3T7iDdZiQnQrUrYbRUYuuHPUnE8DrffHgPXrw6cdf_JrnHQb7x1RCODVz-gcE6puE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb8182e4a0736617e8687_AD_4nXe0lIWl7-wh4uPrMVHqBTNyEH-PmsNjf__GTEfYM4TFCywBNP3M8KKa_EEG4m4zGcshhAt3T7iDdZiQnQrUrYbRUYuuHPUnE8DrffHgPXrw6cdf_JrnHQb7x1RCODVz-gcE6puE.webp)

7\. Create an access token to get your token ID and secret.

[![Creating an access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb817d4388818b6652e63_AD_4nXdimGSq1Aclzq8KGjdUcyFQ-qcogqCIuwLVrz1ya4RyZq3s91jvIOrdYOcxlLS6aJhulbcCl9iDGRl8adtnry0PA51Oj-WUy7GoPfsbp_jMxTFxTKhRXnvJpYTeoc2sFfSm-qcI_A.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673cb817d4388818b6652e63_AD_4nXdimGSq1Aclzq8KGjdUcyFQ-qcogqCIuwLVrz1ya4RyZq3s91jvIOrdYOcxlLS6aJhulbcCl9iDGRl8adtnry0PA51Oj-WUy7GoPfsbp_jMxTFxTKhRXnvJpYTeoc2sFfSm-qcI_A.webp)

## **Best practices for integrating with NetSuite’s API**

To help you integrate with NetSuite successfully, you can apply these best practices.

#### **Review your integration options carefully**

NetSuite offers [SOAP](https://system.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2024_1/schema/record/account.html) and [REST APIs](https://system.netsuite.com/help/helpcenter/en_US/APIs/REST_API_Browser/record/v1/2024.2/index.html), along with suiteQL.

Each has pros and cons, and understanding them can help you suss out your best option:

- NetSuite has offered SOAP for many years, so it’s highly reliable now. That said, because it’s SOAP, building to it can be highly complex and time consuming

- Their REST API is fairly new, so it offers less functionality. However, given that it’s REST, it’s generally easier to build to

- SuiteQL lets you integrate with data in a RESTful manner, and it lets you build SQL-like queries to access databases directly within NetSuite

#### **Filter requests to avoid timeouts and only access the data you need**

Whether it’s your internal or your customer’s instance of NetSuite, it’ll likely store a significant volume of accounting data.

This means that you'll likely need to apply specific filters within your requests to get responses quickly and avoid timeouts.

For example, say you want to get vendor bills in NetSuite. You can filter by a specific accounting period to only fetch a certain batch of transactions.

Here’s how the request body for the request can look if you use suiteQL:

```python

curl -X "POST" "https://***YOUR-NS-ACCOUNT-ID***.suitetalk.api.netsuite.com/services/rest/query/v1/suiteql/?limit=100&offset=0" \
     -H 'Authorization: OAuth oauth_consumer_key="***YOUR-CONSUMER-KEY***", oauth_nonce="***YOUR-NONCE***", oauth_signature="1bb31e23-4e97-40ba-8ef7-1ca20101fdfb", oauth_signature_method="HMAC-SHA1", oauth_timestamp="***YOUR-TIMESTAMP***", oauth_token="***YOUR-TOKEN***", oauth_version="1.0", realm=***YOUR-NS-ACCOUNT-ID***' \
     -H 'Prefer: transient' \
     -H 'Content-Type: text/plain; charset=utf-8' \
     -H 'Cookie: NS_ROUTING_VERSION=LAGGING' \
     -d $'{
    "q": "SELECT * FROM transaction t WHERE t.postingperiod = '42' AND t.type = \”VendBill\””
}'

```

#### ‍ **Add a custom error message when you potentially hit a rate limit for the SOAP API**

If you’re using NetSuite’s SOAP API, you might not get notified when you’ve hit their rate limit. Instead, you might get something like an “invalid login attempt” error message.

To help address this, you can add custom error wrapping (e.g., “Possible rate limit error”) during a period of high traffic, regardless of the error message you get back from NetSuite. You can also monitor your usage across endpoints and set alerts when you’re close to reaching your rate limit threshold for any given endpoint.

_Related:_ [_How to integrate with Sage Intacct’s API_](https://www.merge.dev/blog/sage-intacct-api)

## **NetSuite API integration examples**

Before you start building NetSuite integrations, it's worth understanding several impactful use cases.

Let’s review a few, starting with internal integrations.

#### **Streamline purchase requisition approvals**

As employees submit purchase requests in NetSuite, the approval process for any may involve multiple stakeholders (e.g., department lead, finance manager, etc.).

To make sure that every approver reviews and signs off (or rejects) a request quickly, you can integrate NetSuite with an application like Slack and build a flow where once a purchase request needs to be reviewed by a certain stakeholder, they would be notified via Slack. Within the Slack message, they can also learn about the request and access a link in NetSuite to review it further and approve/reject it.

[![Sync between NetSuite and Slack](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a27bb88f2dee1cf2bc_AD_4nXdYbCuQ_pQyih3PKvF4tFqBgPDd3jmSH7yr_XJR60VDnCudEgAFvGNdNOEONfKaxmFK1HPeA_vYpIOnhibKEG7XbnXKyN5bGYYIcJ2NhMBZZkbFQqYFk2aK5zDbZG2oJkMK7VwYlmOq5HYMIYrjMmpXDxs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a27bb88f2dee1cf2bc_AD_4nXdYbCuQ_pQyih3PKvF4tFqBgPDd3jmSH7yr_XJR60VDnCudEgAFvGNdNOEONfKaxmFK1HPeA_vYpIOnhibKEG7XbnXKyN5bGYYIcJ2NhMBZZkbFQqYFk2aK5zDbZG2oJkMK7VwYlmOq5HYMIYrjMmpXDxs.webp)

#### **Add financial documents to folders in a file storage application**

As your finance team works in NetSuite, they’re likely to create and manage important documents, such as purchase orders, vendor bills, expense reports, etc.

To help them store these documents in a secure place and access them with ease at a later point, you can integrate NetSuite with a file storage application like Box and build a flow where once a certain type of document gets created, it’s added to an associated folder in Box.

[![Sync between NetSuite and Box](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a38b5d285886f6e488_AD_4nXfIMVTI7LS7ExWAv0rV0wJlE3zyrsajX-JTZAfgpz2zHgNGGda3YjeNMbC1F1IgeBtvUQgv-HcGjVZE5qAV9cBvCWlvV3bTPpgwIOoSBQInAcmOZM_vQvEWnZQqgV-jZkNyl_mNofqxZWNKJKECWm04aggM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a38b5d285886f6e488_AD_4nXfIMVTI7LS7ExWAv0rV0wJlE3zyrsajX-JTZAfgpz2zHgNGGda3YjeNMbC1F1IgeBtvUQgv-HcGjVZE5qAV9cBvCWlvV3bTPpgwIOoSBQInAcmOZM_vQvEWnZQqgV-jZkNyl_mNofqxZWNKJKECWm04aggM.webp)

_Related:_ [_Examples of integrating with Xero_](https://www.merge.dev/blog/xero-api)

#### **Create powerful, customizable financial dashboards**

Say you offer a financial modeling platform that helps customers analyze and forecast their cash flow, expenses, cash balance, and more.

To ensure your users can access accurate, up-to-date information over time across their financial models, you can integrate with their instances of NetSuite and sync relevant data, like balance sheets, income statements, and cash flow statements on a consistent cadence (e.g., every 24 hours).

[![Parallel's Dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a2c710a1acb022f172_AD_4nXfCzn2scffSL50TJtPp8h8-_VS0Z4KV4rjkoyoOyoD2eP_jyykTU4wpAzuwI1ZbhBPaOpfdAILb5KBH73OBomuABYEK8HvSCGEH1dQ1vjhe8DiDewTKlCke2UObHEC2jfaqbLCi58PnImepfH57HtcO2V6E.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671040a2c710a1acb022f172_AD_4nXfCzn2scffSL50TJtPp8h8-_VS0Z4KV4rjkoyoOyoD2eP_jyykTU4wpAzuwI1ZbhBPaOpfdAILb5KBH73OBomuABYEK8HvSCGEH1dQ1vjhe8DiDewTKlCke2UObHEC2jfaqbLCi58PnImepfH57HtcO2V6E.webp)

[_Parallel_](https://www.merge.dev/case-studies/parallel) _, a financial modeling platform for founders, integrates with accounting systems to power their customers’ financial models_

#### **Empower customers to manage their vendor relationships**

Imagine you offer a platform that helps customers buy and manage vendors.

Let’s also assume that you need to help customers keep vendor data up to date in your platform so that they can effectively track upcoming renewals, analyze spend, reconcile transactions, and more. To enable this, you can integrate with their instances of NetSuite and sync a wide range of transaction data from the ERP system every day, like transaction amounts, receipts, descriptions, dates, memos, and payment methods.

[![Dummy data of transaction history for Figma](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a171952bc004207a39f7d4_AD_4nXfOIrAWbrxSaW99oBiNca3GBY9hfbECRJBRa00tGZcWq7YGDusSn9s4ah9Fm84UmIFIIDxTRm1TjbwVfvVCOR5TSsD-4HrTBA3-hc7z6M0wCV7-VfjzNbtnzM1z4qFGvr2FDp9Lo8sjirOwrNl3d5alfjLU.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a171952bc004207a39f7d4_AD_4nXfOIrAWbrxSaW99oBiNca3GBY9hfbECRJBRa00tGZcWq7YGDusSn9s4ah9Fm84UmIFIIDxTRm1TjbwVfvVCOR5TSsD-4HrTBA3-hc7z6M0wCV7-VfjzNbtnzM1z4qFGvr2FDp9Lo8sjirOwrNl3d5alfjLU.webp)

[_BRM_](https://www.merge.dev/case-studies/brm) _, an AI-powered buying platform, offers integrations with NetSuite, Ramp, American Express, and Brex—allowing their users to automatically match transactions across multiple applications_

## **Challenges of integrating with NetSuite**

Unfortunately, integrating with NetSuite is far from easy.

You’ll likely run into a number of challenges that make it difficult to make successful requests, troubleshoot errors, receive responses on time, and more.

Here’s a closer look at some of the issues you might face.

#### **Unclear error messages when you reach your rate limit**

You may not get the 429 Too Many Requests error message when you reach your rate limit. In fact, you might get an alternative error message, which can lead your team to go the wrong path in troubleshooting the issue.

For example, when a request hits a rate limit with their SOAP API, they’ll often just give you an “Invalid Login Attempt” error, as shown below.

```python

  "soapenv:Envelope": {
       "@xmlns:soapenv": "http://schemas.xmlsoap.org/soap/envelope/",
       "@xmlns:xsd": "http://www.w3.org/2001/XMLSchema",
       "@xmlns:xsi": "http://www.w3.org/2001/XMLSchema-instance",
       "soapenv:Body": {
           "soapenv:Fault": {
               "faultcode": "soapenv:Server.userException",
               "faultstring": "Invalid login attempt.",
               "detail": {
                   "platformFaults:invalidCredentialsFault": {
                       "@xmlns:platformFaults": "urn:faults_2024_1.platform.webservices.netsuite.com",
                       "platformFaults:code": "USER_ERROR",
                       "platformFaults:message": "Invalid login attempt."
                   },
                   "ns1:hostname": {
                       "@xmlns:ns1": "http://xml.apache.org/axis/",
                       "#text": "partners117.prod-phx-na9.core.ns.internal"
                   }
               }
           }
       }
   }
}

```

#### **Slow response times**

Your internal instance of NetSuite—or that of your customers—likely has a significant volume of financial data that’s accumulated over the years.

As a result, making requests without highly-specific filters can lead to delayed response times (e.g., 15 minutes). The delays may even exceed the maximum response times that've been set, leading to timeouts.

#### **Complex permissions can easily lead to missing data**

NetSuite has an extensive list of permissions that are needed to access their various transaction types. If you forget to include any one of these permissions, you may not receive certain transactions in the responses—forcing your team to identify the missing permission(s) and make repeated requests.

## **Integrate NetSuite and other accounting platforms with your product via Merge’s Unified API**

Merge has a team dedicated to building deep, reliable, and flexible integrations with complex accounting systems like NetSuite. This removes the burden from your engineers and it ensures that they can avoid all of the challenges highlighted above (as our team has already faced and accounted for them).

In addition, through Merge's [Accounting Unified API](https://www.merge.dev/categories/accounting-api), you can add more than a dozen accounting integrations—including NetSuite—within weeks.

[![A snapshot of the accounting integrations Merge supports](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66f70dceb3790f02454115bc_AD_4nXf8kS0Z-4eG8Ofh8vJHAOqkMx2OSbMUi7XuOUiRtrf0LQpeMsLSAzCSX1GMuwWzD5xPUBwc5RQf_KLFbCBXLwSiaQDjvITVNw23UqwiLBux_LHHkhyW95o1sUYyEquop2TNtRleP7XZw3nx7E4MmBidMyvo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66f70dceb3790f02454115bc_AD_4nXf8kS0Z-4eG8Ofh8vJHAOqkMx2OSbMUi7XuOUiRtrf0LQpeMsLSAzCSX1GMuwWzD5xPUBwc5RQf_KLFbCBXLwSiaQDjvITVNw23UqwiLBux_LHHkhyW95o1sUYyEquop2TNtRleP7XZw3nx7E4MmBidMyvo.webp)

_A snapshot of the accounting integrations Merge supports_

Merge also offers comprehensive, normalized Common Models—which span everything from balance sheets to invoices to journal entries to tracking categories. And the platform provides advanced features for syncing custom data, such as [Remote Data](https://docs.merge.dev/supplemental-data/remote-data/) and [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/).

And finally, the platform offers integration observability features—which include fully-searchable logs, automated issue detection functionality, and holistic performance data—to help your customer-facing teams uncover, diagnose, and resolve integration issues quickly and easily.

[![Merge's automated issue detection functionality](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f8547883d3902fd54bd58e_Q28qNAEHxzETiYJcCdpsDSO5yf0M9m_IFUhuq9XgWvCYRaY3Agjba-JrRL1cDOY3DhorpeLGL8l5Shpgnr2z_MwQSAJITBjJwsfIX6lfqgGTm1cLwPZOovddu1J7ABYxcZo9usM0KbmBBQhBwoaErLs.webp)

Learn more about using Merge to add accounting integrations to your product by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fquickbooks-api).

## **NetSuite API integration FAQ**

In case you have any more questions on NetSuite, we’ve addressed several more below.

#### **What are the benefits of integrating with NetSuite?**

The benefits largely depend on whether you’re implementing internal or customer-facing integrations.

In the case of internal NetSuite integrations, the benefits include the following:

- **Time savings:** Your employees don’t have to re-enter financial data across systems or toggle between different systems to find data **‍**
- **More accurate financial data:** By avoiding data entry, your employees won’t make as many human errors **‍**
- **Happier employees:** Helping employees spend less time copying and pasting information to and from NetSuite allows them to focus on more impactful and interesting work

Customer-facing NetSuite integrations can help your organization in the following ways:

- **Higher customer retention:** By providing more powerful features and capabilities in your product (via your NetSuite integration), you’re more likely to retain customers over time **‍**
- **Improved close rate:** Offering the accounting integration (NetSuite) your prospects need will—all else equal—make them more likely to pick your business **‍**
- **Market growth:** Since enterprise companies around the world use NetSuite, the integration can help you move upmarket and expand to different regions

#### **What are some common NetSuite API endpoints?**

Here are just a few commonly-used ones that support a variety of HTTP methods:

- Invoices: `https://{account_id}.suitetalk.api.netsuite.com/services/rest/record/v1/invoice`
- Credit memos: `https://{account_id}.suitetalk.api.netsuite.com/services/rest/record/v1/creditMemo`
- Issues: `https://{account_id}.suitetalk.api.netsuite.com/services/rest/record/v1/issue`
- Inventory status: `https://{account_id}.suitetalk.api.netsuite.com/services/rest/record/v1/inventoryStatus`
- Sales order: `https://{account_id}.suitetalk.api.netsuite.com/services/rest/record/v1/salesOrder`

#### **What are NetSuite API’s rate limits?**

You’ll have two rate limits that you’ll need to abide by. One is set to a certain number of requests every 24 hours, and the other is set to a smaller number of requests every minute. Your specific rate limits for each timeframe will depend on the plan you’re on and the API licenses you’ve purchased.

It’s also worth noting that you can receive up to 1,000 objects per request, which you can work around through pagination and batches.

_Learn more about_ [_NetSuite’s rate limits_](https://docs.oracle.com/en/cloud/saas/netsuite-openair/nsoa-online-help/article_160070530606.html#subsect_83020344592) _._

#### **Does NetSuite have an API?**

Yes, NetSuite offers both SOAP and REST APIs to help you access a broad range of data and functionality in the ERP system.

You can learn more about their SOAP API (SuiteTalk SOAP) [here](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/chapter_N3412777.html), and you can uncover more information on their REST API [here](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/chapter_N3412777.html).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jon Gitlin is the Managing Editor of Merge's blog. He has several years of experience in the integration and automation space; before Merge, he worked at Workato, an integration platform as a service (iPaaS) solution, where he also managed the company's blog. In his free time he loves to watch soccer matches, go on long runs in parks, and explore local restaurants.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1befc55e-81ff-4a6d-a95a-45b8b310dfc9&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=18bfa0c0-1f4b-4f2e-b007-fcac178635d4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnetsuite-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1befc55e-81ff-4a6d-a95a-45b8b310dfc9&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=18bfa0c0-1f4b-4f2e-b007-fcac178635d4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnetsuite-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=7281b067-d48f-4e74-8f7a-f0fe86d36e06&bo=2&sid=1de146103e8e11f0b174cf8acc0d6a8d&vid=1de252603e8e11f0ac44232983e5cb9b&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20integrate%20with%20NetSuite%27s%20API%20in%202025&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fnetsuite-api&r=&lt=566&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=378979)