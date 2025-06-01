---
url: "https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through"
title: "Building a SOAP API Integration When You Already Know REST: The Full Walk-Through"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#)

Table of contents

[A SOAP API Example](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#a-soap-api-example)

[Implementing a SOAP API Integration with Python](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#implementing-a-soap-api-integration-with-python)

[Conclusion](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through)

##### Just for you

No items found.

# Building a SOAP API Integration When You Already Know REST: The Full Walk-Through

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856d2aa6710a493b1693a4_SOAP_API_Integration_Tutorial.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Oluseun Falodun

@Merge

Though RESTful APIs are preferred by many organizations these days for their flexibility, some legacy enterprises, platforms, and systems still use SOAP APIs. SOAP is an older protocol and exchanges data formatted as XML. SOAP is also language and platform agnostic and focuses on remotely accessing and manipulating objects.

A number of human resources, application tracking, accounting software, and payment-solution platforms still rely on the SOAP protocol, including [Sage X3](https://developer.sage.com/x3/soap-guide/), [Salesforce](https://developer.salesforce.com/docs/atlas.en-us.api.meta/api/sforce_api_quickstart_intro.htm), [Workday](https://www.workday.com/), and [PayPal](https://developer.paypal.com/api/nvp-soap/soap/). This poses a challenge for REST API–based organizations that need to integrate with SOAP-based platforms.

In this tutorial, you’ll learn how to put your REST skills to use for integrating your platform with SOAP APIs.

#### Add 100s of integrations to your product via Merge

Learn how Merge's Unified API can help you add hundreds of integrations across software categories—from ticketing to HRIS to accounting applications.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## A SOAP API Example

One of the most popular enterprise management platforms using SOAP APIs is [Workday](https://www.workday.com/), which provides payroll, human resources, and applicant-tracking services to developers. Its API incorporates WSDL, REST, and SOAP protocols.

If you compare SOAP to REST, integrating with SOAP APIs is not so different from how your organization already uses REST APIs. You’ll make calls to test the Workday human resources web services by carrying out some basic CRUD operations. (This tutorial assumes you already have a Workday user ID and password.)

Following is a high-level overview of the process:

- Check the Workday [Web Service Description Language (WSDL)](https://www.w3.org/TR/wsdl.html#_wsdl) document to see how to call your required web service.
- Extract and interpret the WSDL XML request schema for the required service endpoint.
- Configure the SOAP request header and body structure to add API URL and authentication using your Workday user ID and password.
- Make HTTP connection and call using [Postman](https://www.postman.com/), [SoapUI](https://www.soapui.org/), and Python (or other languages like Java, PHP, or Ruby).

## Implementing a SOAP API Integration with Python

Since many organizations use Python for automating communication between APIs and for API integration, let's use it for this tutorial.

Python’s popular [Requests library](https://docs.python-requests.org/en/latest/) allows developers to make HTTP request calls to a specific URL. You may already use this library to implement REST API calls and integration with Python, but you can also use it to call SOAP services.

There are more robust libraries like [suds](https://pypi.org/project/suds/) and [Zeep](https://pypi.org/project/zeep/) for interacting with SOAP APIs in Python. For simplicity, though, let’s stick with the Requests library.

### Checking WSDL Requirements

WSDL is an XML format for calling a web service that describes the available endpoints, the structure of requests, and the responses to expect. WSDL is a standard format for SOAP API documentation or specification, much like for REST APIs.

You’ll first need to check the WSDL requirements in Workday’s [documentation](https://community.workday.com/sites/default/files/file-hosting/productionapi/index.html).

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be1eb2d5cf56ffefbd4db_62d72ce0228c8df34cace1fc_Workday.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be1eb2d5cf56ffefbd4db_62d72ce0228c8df34cace1fc_Workday.webp)

You can see the available Workday API services, including the **Human\_Resources** Web services you’ll be using. Click on the **Human\_Resources** link to see the list of specific CRUD operations available and their associated descriptions.

For this tutorial, you’ll be making GET and POST calls to the endpoint using the `Get_Employee` operation to fetch employee data and the `Add_Vaccination` operation to create a vaccination record resource for an employee.

WSDL’s are for SOAP web services what Swagger/OpenAPI schemas are for REST-based web services. The JSON contents of Merge API’s OpenAPI schema for HRIS at [https://api.merge.dev/api/hris/v1/schema](https://api.merge.dev/api/hris/v1/schema) contain many of the same objects as the XML contents of the Workday WSDL, albeit for different HRIS services.

### Extracting WSDL XML Request Schema

In the Workday Human Resources services, you’ll see a simple XML sample of the SOAP message body for retrieving employee information from Workday:

```python
	<bsvc:Employee_Get xmlns:bsvc="urn:com.workday/bsvc" bsvc:As_Of_Date="2008-09-29" bsvc:As_Of_Moment="2014-09-18T23:18:33" bsvc:version="string">
<bsvc:Employee_Reference>
<bsvc:Integration_ID_Reference bsvc:Descriptor="string">
<bsvc:ID bsvc:System_ID="string">string</bsvc:ID>
</bsvc:Integration_ID_Reference>
</bsvc:Employee_Reference>
</bsvc:Employee_Get>
```

Developers often use tools and environments that can read a WSDL file to find methods and syntaxes for writing the SOAP message payload. [SoapUI](https://www.soapui.org/) is one such tool. The image below shows the SoapUI interface after the **Human\_Resources** WSDL file was imported into the SoapUI tool:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be1ec2d5cf56ffefbd510_62d72d1218ca34fe9cf2ea54_SOAP%2520UI%2520Tool.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671be1ec2d5cf56ffefbd510_62d72d1218ca34fe9cf2ea54_SOAP%2520UI%2520Tool.webp)

Note that a typical SOAP request message structure has some parallels with a REST API request structure. As seen in the above screenshot, the SOAP request contains the following elements:

- A SOAP envelope element, which serves as the root element defining the XML document
- An optional SOAP header element—like a RESTful header— contains specific information like SOAP API authentication, cookie, and user agent
- The SOAP body element containing the actual message (data/payload) for the endpoint
- An optional SOAP Fault element for keeping errors and status data for the message

For more information on the SOAP standard syntax structure, check [the W3 Consortium documentation on SOAP binding for HTTP](https://www.w3.org/TR/wsdl.html#_soap-b).

SoapUI automatically adds the required elements to the body syntax provided on the Workday website. Next, we’ll configure your request message to point to your organization’s Workday URL—either provided by the platform or available in documentation—with relevant authentication.

### Configuring SOAP Request Authentication

If the API call you want to make requires authentication, those details can easily be bundled with the `SOAP:Header` element. Workday APIs use [WS-Security](https://en.wikipedia.org/wiki/WS-Security) for SOAP API authentication. By using the WSDL endpoint to connect directly to the server, you can add a username field and password to obtain access.

Say your company’s WSDL endpoint URL for Workday is `https://MY-COMPANYINSTANCE.workday.com/ccx/service/MY-COMPANYNAME/Human_Resources` and your username is `UserName@MY-COMPANY`. You can send a fetch request to get the details of an employee in your organization with the system ID `Gil Feig` from 2019 to date with a version of the message snippet above.

Below, the header and the SOAP body elements have been modified and wrapped inside a SOAP envelope.

```python
	<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:bsvc="urn:com.workday/bsvc">
   <soapenv:Header>
  <wsse:Security soapenv:mustUnderstand="1" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
    <wsse:UsernameToken wsu:Id="bogus">
      <wsse:Username>UserName@MY-COMPANY</wsse:Username>
      <wsse:Password Type="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordText">[PASSWORD HERE]</wsse:Password>
      <wsse:Nonce EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">bogus</wsse:Nonce>
      <wsu:Created>2000-10-02T21:12:28.365Z</wsu:Created>
    </wsse:UsernameToken>
  </wsse:Security>
</soapenv:Header>
   <soapenv:Body>
      <bsvc:Employee_Get bsvc:As_Of_Date="2019-01-01" bsvc:As_Of_Moment="2022-03-01" bsvc:version="1.1">
         <bsvc:Employee_Reference>
            <bsvc:Integration_ID_Reference bsvc:Descriptor="?">
               <bsvc:ID bsvc:System_ID="?">Fly Ash</bsvc:ID>
            </bsvc:Integration_ID_Reference>
         </bsvc:Employee_Reference>
      </bsvc:Employee_Get>
   </soapenv:Body>
</soapenv:Envelope>
```

Next, we’ll write a Python script to send the request.

### Making an HTTP Request

Combining all the above steps in a Python script, your client can make a request to the Workday API server and get a response. For your Workday instance, the script to **fetch** an employee data will look like this:

```python
	import requests
# Workday SOAP Human_Resources request URL
url = "https://MY-COMPANYINSTANCE.workday.com/ccx/service/MY-COMPANYNAME/Human_Resources"

# Request Header
headers = {'content-type': 'application/soap+xml'}

# structured XML for Get_Employee Fly Ash
payload = """<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:bsvc="urn:com.workday/bsvc">
   <soapenv:Header>
  <wsse:Security soapenv:mustUnderstand="1" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
    <wsse:UsernameToken wsu:Id="bogus">
      <wsse:Username>UserName@MY-COMPANY</wsse:Username>
      <wsse:Password Type="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordText">[PASSWORD HERE]</wsse:Password>
      <wsse:Nonce EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">bogus</wsse:Nonce>
      <wsu:Created>2000-10-02T21:12:28.365Z</wsu:Created>
    </wsse:UsernameToken>
  </wsse:Security>
</soapenv:Header>
   <soapenv:Body>
      <bsvc:Employee_Get bsvc:As_Of_Date="2019-01-01" bsvc:As_Of_Moment="2022-03-01" bsvc:version="1.1">
         <bsvc:Employee_Reference>
            <bsvc:Integration_ID_Reference bsvc:Descriptor="?">
               <bsvc:ID bsvc:System_ID="?">Fly Ash</bsvc:ID>
            </bsvc:Integration_ID_Reference>
         </bsvc:Employee_Reference>
      </bsvc:Employee_Get>
 </soapenv:Body>
</soapenv:Envelope>
"""
#  Request
response = requests.request("POST", url, data=payload, headers=headers)

# prints the response
print(response.text)
print(response)
```

You should get a response from the server specifying employee data as an XML response body wrapped in a SOAP envelope, formatted [this way](https://community.workday.com/sites/default/files/file-hosting/productionapi/Human_Resources/v38.0/samples/Employee.xml), and an HTTP 200 response code.

You’ll note some differences here between REST and SOAP APIs. In contrast to REST API response bodies that can hold different data formats like JSON, stylesheets, PNG, and documents, SOAP APIs only return XML data in the response.

In addition, REST makes use of HTTP verbs like GET, POST, PATCH, PUT, and DELETE to send requests for CRUD operations. The HTTP GET method allows for caching of the response data coming from web services. When SOAP uses HTTP protocol as its transfer mechanism, requests are mostly sent via the HTTP POST method. As a result, there is no caching done at the HTTP level for SOAP HTTP requests.

To complete your integration, use your preferred tool to parse the XML data in the server response and build your solution on top of the [API connection](https://www.merge.dev/blog/api-connection).

### Making a Request to Create a Resource

Now you’ll send a POST request to the SOAP API endpoint to create a new resource on the server-side. You’ll add a vaccination record for an employee using the same technique you used to make the GET request but with a different request body, per the SOAP request specification in the [WSDL file](https://community.workday.com/sites/default/files/file-hosting/productionapi/Human_Resources/v38.0/Add_Vaccination.html).

```python
	import requests
# SOAP request URL
url = "https://MY-COMPANYINSTANCE.workday.com/ccx/service/MY-COMPANYNAME/Human_Resources"

# Request Header
headers = {'content-type': 'application/soap+xml'}

# structured XML for Get_Employee Fly Ash
payload = """<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:bsvc="urn:com.workday/bsvc">
  <soapenv:Header>
  <wsse:Security soapenv:mustUnderstand="1" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
    <wsse:UsernameToken wsu:Id="bogus">
      <wsse:Username>UserName@MY-COMPANY</wsse:Username>
      <wsse:Password Type="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordText">[PASSWORD HERE]</wsse:Password>
      <wsse:Nonce EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">bogus</wsse:Nonce>
      <wsu:Created>2000-10-02T21:12:28.365Z</wsu:Created>
    </wsse:UsernameToken>
  </wsse:Security>
</soapenv:Header>
   <soapenv:Body>
...
...
...
   </soapenv:Body>
</soapenv:Envelope>
"""
# POST request
response = requests.request("POST", url, data=payload, headers = headers)

# prints the response
print(response.text)
print(response)
```

As before, the response will return an XML body wrapped in a SOAP envelope.

## Conclusion

SOAP APIs may seem like a challenge to work with, but even if you’re more familiar with REST APIs, you can still integrate your platform with a SOAP API platform. This added flexibility will increase your organization’s ability to work with legacy platforms as well as add some needed skills to your toolbox.

If you’d like an easier way to accomplish such an integration, though, consider [Merge](https://www.merge.dev/). Even if the original platform uses SOAP, Merge’s RESTful API platform offers a unified way to integrate all of your company’s systems, from human resources and payroll to recruiting and accounting. We provide authentication, logs, issue detection, and automated alerts to help your business save resources. You can [sign up for a free trial](https://app.merge.dev/signup) or [request a demo](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Oluseun Falodun

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3f6a1af0-1c55-4fa2-a191-c3b6674cf3d6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=af94187c-297f-4b2a-ba05-36d8e53279e2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3f6a1af0-1c55-4fa2-a191-c3b6674cf3d6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=af94187c-297f-4b2a-ba05-36d8e53279e2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=4033395d-ca7b-48a3-8fa8-a175fa7b18a8&bo=2&sid=14f5b2203e8c11f08c45011b669119e2&vid=14f5e5703e8c11f0848879f09b3a0a30&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Building%20a%20SOAP%20API%20Integration%20When%20You%20Already%20Know%20REST%3A%20The%20Full%20Walk-Through&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbuilding-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through&r=&lt=730&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=213186)