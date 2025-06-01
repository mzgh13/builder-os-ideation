---
url: "https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python"
title: "How to GET employees from the Workday API with Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#)

Table of contents

[Understanding Workday’s SOAP API](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#understanding-workdays-soap-api)

[Authentication and permissions with the Workday API](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#authentication-and-permissions-with-the-workday-api)

[How to GET employees from the Workday API in Python](https://www.merge.dev/blog/how-to-get-employees-from-the-workday-api-with-python#how-to-get-employees-from-the-workday-api-in-python)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-employees-from-the-workday-api-with-python)

##### Just for you

No items found.

# How to GET employees from the Workday API with Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb2b0b7764b66a5aa8b6b8_Dan%20Rothman%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538316bd609b4c800381_62eff2ae1cef2850ec2d43ad_dan-rothman.webp)

Dan Rothman

Engineering

@Merge

If you’re building a direct integration with Workday, one of the most basic things you’ll want to do is pull employees from the Workday API. The following article covers how you can start interacting with Workday’s SOAP API.

As a note from the authors (who’ve built an entire Workday integration), we truly believe the quickest way to get a Workday integration is via a unified API provider, such as Merge.

In this article, we'll cover how to understand Workday's SOAP API, how to set proper permissions in Workday, and how to write a GET request to Workday's SOAP API in Python.

## Understanding Workday’s SOAP API

While most modern applications structure their APIs with a REST architecture, Workday employs an architecture known as SOAP. SOAP stands for Simple Object Access Protocol, and returns information with the following format:

```markup
<xsd:simpleType name="Assignable_RoleReferenceEnumeration">
 <xsd:restriction base="xsd:string">
  <xsd:annotation>
   <xsd:appinfo>
    <wd:enumeration value="WID"/>
    <wd:enumeration value="Organization_Role_ID"/>
   </xsd:appinfo>
  </xsd:annotation>
 </xsd:restriction>
</xsd:simpleType>
```

## Authentication and permissions with the Workday API

### Getting permissions for Workday HRIS and ATS

In order to begin receiving SOAP responses from Workday, you need to create an Integrated System User (ISU) with the proper permissions. Workday configures their permissions on a field level, so you’ll need to grant yourself access to a number of fields to get things up and running.

**Please note** that the following steps will need to be accomplished by a **Workday user with administrative access**.

1. Access the **Create Integration System User task** through Workday’s search bar and create a **new user**
2. Add the new user to the list of **System Users** in order to guarantee the password you created does not expire
3. Access the **Create Security Group task** and create a new **User-Based Security Group**
4. Add the **Integration System User** you’ve created to the group and save your progress

After step four, you’ll need to follow different processes depending on which [Workday API endpoints](https://www.merge.dev/blog/workday-api-integration) you wish to pull data from.

### Accessing the Workday HRIS API

1. Search Workday for **Public Web Services**
2. Open the report
3. Hover over **Human Resources** and click the three dots to access the menu
4. Click **Web Service**, then **View WSDL**
5. Navigate to the bottom of the WSDL page to find the **hostname**
6. Look for the Username, Password, Tenant Name `https://wd5-services1.workday.com/TENANT_NAME`, and Endpoint URL. Save these somewhere secure for later

### Accessing the Workday ATS API

1. Navigate to the **Domain Security Policy** tab under **Web Service**
2. Search for **Recruiting Web Services**
3. Add permissions to the **User’s Security Group** for the endpoints you’ll be accessing (for example Get\_Applicants, Get\_Job\_Postings, etc.)
4. Look for the Username, Password, Tenant Name `https://wd5-services1.workday.com/TENANT_NAME`, and Endpoint URL under the **User’s Security Group.** Save these somewhere secure for later.

#### Integrate with every HRIS through Merge

Learn how Merge's Unified API lets you integrate your product with dozens of HRIS solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-employees-from-the-workday-api-with-python)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## How to GET employees from the Workday API in Python

### Set up your request file

Open up a new Python file, and call it workday\_requester.py

Import `json`, `requests`, and `xmltodict` from parse.

As we mentioned above, the Workday API returns responses in XML. You, like most developers, are probably used to a dictionary. `xmltodict` lets us parse the response by returning an ordered dictionary that we can then turn into a dictionary.

```python
import requests
from xmltodict import parse
```

Create and store the tenant\_name, your username, password, and url from Step 4 as variables.

```python
tenant_name = "tenant"
username = f"ISU_USERNAME@{tenant_name}"
password = "PASSWORD"

# Exact URL may vary
url = f"https://services1.myworkday.com/ccx/service/{tenant_name}/Human_Resources/v36.2"
```

### Construct your SOAP request body

Below is an example of the request body you would use to fetch employees using the Get Workers Endpoint. You’ll need to tweak this request body to fit the API endpoint you’d like to call.

**Note** that to deal with pagination, you need to set a page number for the request as well. Save this as a variable.

```python
page_number = 1
```

SOAP requests contain 2-4 blocks. You can think of a block as similar structure HTML, which requires both an opening and closing tag. The SOAP blocks are Envelope, Header, Body, and Fault. For a basic SOAP request, only the Envelope and Body are required.

To get employees, we’ll need to use the Envelope, Header, and Body blocks.

To help you think about the structure of SOAP, you can think of a SOAP Request as a "package," the Envelope is being the "packaging," the Header is the "Sent from Address," and the Body is the "letter/contents" of the package.

We’ll first create the Envelope with a namespace attribute `xmlns:soapenv=”https://schemas.xmlsoap.org/soap/envelope/”`.

Our opening Envelope block will look something like this:

```markup
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:bsvc="urn:com.workday/bsvc">
```

The other two blocks (the Header and Body) will be wrapped inside this Envelope.

The Header will contain our API access credentials and the security needed to access it. Alone, the header will look like this:

```markup
<soapenv:Header>
  <wsse:Security soapenv:mustUnderstand="1" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
    <wsse:UsernameToken>
      <wsse:Username>{username}</wsse:Username>
      <wsse:Password Type="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordText">{password}</wsse:Password>
    </wsse:UsernameToken>
  </wsse:Security>
</soapenv:Header>
```

The bulk of our actual request will be in the Body. There, we will define the parameters and data we’d like to fetch.

For our example, we’re making a `Get_Workers_Request`, and because we’re also using pagination we’ll want to pass page\_number as a parameter.

To call a different endpoint, change the bsvc payload in the SOAP body to the endpoint of your choosing.

```markup
<bsvc:Get_Workers_Request>
</bsvc:Get_Workers_Request>
```

**Note** how we’re leaving out `soapenv:Fault`, which would generally be used to catch error codes when your SOAP API call is incomplete.

Look at the example below to see how the Envelope, Header, and Body all fit together in a SOAP request.

```

```

### Pull and format your Workday API employee request

We’ll then want to make the call by calling requests with the URL and request body. In a traditional REST API call we would use `method=”GET”`, but with SOAP we’ll be calling `POST` to the `Get_Workers_Request` endpoint to access this data.

In order to make the resulting response more readable, we can use json.loads and the  parse method to convert the response to a dictionary.

```python
parsed_response = jsonloads(parse(response.content))
```

The resulting response will look similar to this:

```python
{
	'env:Envelope': {
		'@xmlns:env': 'http://schemas.xmlsoap.org/soap/envelope/',
		'env:Body': {
			'wd:Get_Workers_Response': {
				'@xmlns:wd': 'urn:com.workday/bsvc',
				'@wd:version': 'v37.0',
				'wd:Response_Filter': {
					'wd:Page': '1',
					'wd:Count': '100'
				},
				'wd:Response_Results': {
					'wd:Total_Results': '100',
					'wd:Total_Pages': '1',
					'wd:Page_Results': '1000',
					'wd:Page': '1'
				},
				'wd:Response_Data': {
					'wd:Worker': {
						'wd:Worker_Reference': {
							'wd:ID': [{\
									'@wd:type': 'WID',\
									'#text': '2000000000'\
								},\
								{\
									'@wd:type': 'Employee_ID',\
									'#text': '100001'\
								}\
							]
						},
						'wd:Worker_Descriptor': 'Daniel Rothman',
						'wd:Worker_Data': {
							'wd:Worker_ID': '100001',
							'wd:User_ID': 'Daniel.Rothman'
						}
					}
				}
			}
		}
	}
}
```

We’ve shortened the response here, but the response will likely include fields like the employees contact information, hire date, weekly hours and more!

And that’s it! You’ve successfully pulled the employees object from the Workday API.

At Merge, we’ve built a [Unified API](https://www.merge.dev/blog/what-is-a-unified-api) that lets you easily pull from Workday using REST (no SOAP required). Our [HRIS Unified API](https://merge.dev/categories/hr-payroll-api) has also smoothed out pagination and authentication. We offer over 180+ integrations, including [Workday](https://merge.dev/integrations/workday), [BambooHR](https://merge.dev/integrations/bamboohr), and [UKG](https://merge.dev/integrations/ukg-pro).

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-employees-from-the-workday-api-with-python) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb2b0b7764b66a5aa8b6b8_Dan%20Rothman%20-%20Merge.png)

Dan Rothman

Engineering

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ac8508bc-690c-47e4-85ed-a4ca86a92b2b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b6a97814-1337-4f1f-a16c-b70dbea0242e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-employees-from-the-workday-api-with-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ac8508bc-690c-47e4-85ed-a4ca86a92b2b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b6a97814-1337-4f1f-a16c-b70dbea0242e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-employees-from-the-workday-api-with-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=76638444-0209-4cc2-b495-df27d2bdb155&bo=2&sid=305d0c603e8e11f09315a9aeddd18d05&vid=305da0e03e8e11f0ac69df7585df0995&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20employees%20from%20the%20Workday%20API%20with%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-employees-from-the-workday-api-with-python&r=&lt=460&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=245511)