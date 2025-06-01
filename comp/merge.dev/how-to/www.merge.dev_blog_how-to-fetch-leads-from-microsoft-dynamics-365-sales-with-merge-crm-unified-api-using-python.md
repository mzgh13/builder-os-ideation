---
url: "https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python"
title: "How to fetch leads from Microsoft Dynamics 365 Sales using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python#)

Table of contents

[How to pull leads from Microsoft Dynamics 365](https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python#how-to-pull-leads-from-microsoft-dynamics-365)

[Final thoughts](https://www.merge.dev/blog/how-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python)

##### Just for you

No items found.

# How to fetch leads from Microsoft Dynamics 365 Sales using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae9309b17fd57b5701_How_to_Fetch_Leads_from_Microsoft_Dynamics_365_Sales_with_Merge_CRM_Unified_API.webp)

No items found.

Microsoft Dynamics 365 Sales offers a robust customer relationship management (CRM) system, enabling businesses to understand their customers' needs more accurately, engage accounts more intelligently, and secure more deals.

While there's a variety of data worth pulling from Microsoft Dynamics 365 Sales, leads are likely at or near the top of your list.

To help you get leads from the CRM in Python, we'll breakdown each step you need to follow.

_Related:_ [_Marketing automation integration examples_](https://www.merge.dev/blog/marketing-automation-integration)

### Authentication

Before you can pull leads from the Microsoft Dynamics 365 Sales API, you need to authenticate with the service. You can this through an OAuth 2.0 Authorization Code grant type.

First, set up an OAuth flow with Microsoft Dynamics 365 Sales. Users should navigate to the authorization URL, https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize, to authorize. Once the user completes the authorization flow, Microsoft Dynamics 365 Sales will navigate the user to your provided `redirect_url` and include the authorization code as a query parameter, `code`. This code can be exchanged for an access token.

Include the scopes `https://{DOMAIN}.dynamics.com/.default offline_access` in the scope parameter in the authorization URL. For the token URL, use the `client ID` and secret provided by Microsoft Dynamics 365 Sales.

To request the access token, hit the token URL, `https://login.microsoftonline.com/organizations/oauth2/v2.0/token`. Pass `client_id`, `client_secret`, and other parameters into the URL as body parameters. The header format should be `Content-Type: application/x-www-form-urlencoded` for the token URL.

The access token can be found in the `access_token` key in the response of the token URL. Use the `expires_in` value in the response body of the token URL to determine the lifespan of the token. The refresh token can be found in the `refresh_token key` in the response. Use the token URL to refresh the access token when it expires.

## How to pull leads from Microsoft Dynamics 365

**‍** First, define your Microsoft Dynamics 365 Sales domain:

```python
DOMAIN = 'YOUR_DOMAIN'
```

Then define your Microsoft Dynamics 365 Sales client id and secret:

```python
CLIENT_ID = 'YOUR_CLIENT_ID'
CLIENT_SECRET = 'YOUR_CLIENT_SECRET'
```

Establish your redirect url:

```python
REDIRECT_URL = 'YOUR_REDIRECT_URL'
```

Designate your authorization url and scopes:

```python
AUTH_URL = 'https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize'
SCOPES = f'https://{DOMAIN}.dynamics.com/.default offline_access'
```

Specify your token url:

```python
TOKEN_URL = 'https://login.microsoftonline.com/organizations/oauth2/v2.0/token'

```

Exchange the authorization code for an access token:

```python
def get_access_token(code):
    headers = {'Content-Type': 'application/x-www-form-urlencoded'}
    data = {
        'client_id': CLIENT_ID,
        'client_secret': CLIENT_SECRET,
        'code': code,
        'redirect_uri': REDIRECT_URL,
        'grant_type': 'authorization_code',
        'scope': SCOPES
    }
    response = requests.post(TOKEN_URL, headers=headers, data=data)
    if response.status_code == 200:
        return response.json().get('access_token')
    else:
        return None
```

Retrieve the Leads from Microsoft Dynamics 365 Sales

```python
def get_leads(access_token):
    headers = {'Authorization': 'Bearer ' + access_token}
    response = requests.get(f'https://{DOMAIN}.dynamics.com/api/data/v9.0/leads', headers=headers)
    if response.status_code == 200:
        return response.json()
    else:
        return None
```

Get the authorization code:

‍ **Note**: In a real world scenario, this would be the result of a user action to authorize the application.

```python
code = 'YOUR_AUTHORIZATION_CODE'
```

Get the access token using the authorization code:

```python
access_token = get_access_token(code)
```

Fetch the leads using the access token:

```python
leads = get_leads(access_token)
print(leads)
```

Replace `'YOUR_DOMAIN'`, `'YOUR_CLIENT_ID'`, `'YOUR_CLIENT_SECRET'`, `'YOUR_REDIRECT_URL'` and `'YOUR_AUTHORIZATION_CODE'` with your actual values.

This script first exchanges an authorization code for an access token. It then uses that access token to authenticate a request to the Microsoft Dynamics 365 Sales leads endpoint and retrieve leads data. The results are then printed to the console.

You should see the list of Leads from Microsoft Dynamics 365 Sales as the output.

```python
{
    "@odata.context": "https://services.odata.org/V4/(S(4h1gie24gh0cc1gv4wtobl1r))/TripPinServiceRW/",
    "value": [\
        {\
            "@odata.etag": "W/\"08D7D405123456789\"",\
            "mobilephone": "+1 123 456 7890",\
            "address1_country": "United States",\
            "merged": false,\
            "prioritycode": 1,\
            "confirminterest": false,\
            "exchangerate": 1.5,\
            "_parentaccountid_value": "12345678-1234-1234-1234-1234567890",\
            "decisionmaker": true,\
            "modifiedon": "2021-09-18T20:30:00Z",\
            "revenue_base": 50000.0,\
            "_owninguser_value": "1234567a-1234-1234-1234-1234567890",\
            "address1_shippingmethodcode": 1,\
            "address1_composite": "123 Main St, City, State 12345",\
            "lastname": "Doe",\
            "donotpostalmail": false,\
            "numberofemployees": 100,\
            "donotphone": false,\
            "preferredcontactmethodcode": 2,\
            "_ownerid_value": "1234567b-1234-1234-1234-1234567890",\
            "sic": "1234",\
            "firstname": "John",\
            "evaluatefit": false,\
            "yomifullname": "John Doe",\
            "address2_addresstypecode": 2,\
            "donotemail": false,\
            "address2_shippingmethodcode": 2,\
            "fullname": "John Doe",\
            "address1_addressid": "1234567c-1234-1234-1234-1234567890",\
            "msdyn_gdproptout": false,\
            "statuscode": 1,\
            "createdon": "2021-09-18T20:30:00Z",\
            "address1_stateorprovince": "State",\
            "_msdyn_predictivescoreid_value": "1234567d-1234-1234-1234-1234567890",\
            "companyname": "Company Name",\
            "donotfax": false,\
            "leadsourcecode": 1,\
            "jobtitle": "Developer",\
            "versionnumber": 123456789,\
            "address1_line1": "123 Main St",\
            "emailaddress1": "johndoe@example.com",\
            "telephone1": "+1 123 456 7890",\
            "donotsendmm": false,\
            "leadqualitycode": 1,\
            "_transactioncurrencyid_value": "1234567e-1234-1234-1234-1234567890",\
            "subject": "Introduction",\
            "address1_addresstypecode": 1,\
            "donotbulkemail": false,\
            "_modifiedby_value": "1234567f-1234-1234-1234-1234567890",\
            "followemail": true,\
            "leadid": "1234567g-1234-1234-1234-1234567890",\
            "_createdby_value": "1234567h-1234-1234-1234-1234567890",\
            "websiteurl": "https://www.example.com",\
            "address1_city": "City",\
            "salesstagecode": 1,\
            "_msdyn_leadkpiid_value": "1234567i-1234-1234-1234-1234567890",\
            "revenue": 50000.0,\
            "purchasetimeframe": 1,\
            "participatesinworkflow": true,\
            "statecode": 1,\
            "_owningbusinessunit_value": "1234567j-1234-1234-1234-1234567890",\
            "address2_addressid": "1234567k-1234-1234-1234-1234567890",\
            "address1_postalcode": "12345",\
            "telephone3": "+1 123 456 7891",\
            "businesscardattributes": null,\
            "address1_upszone": "Zone 1",\
            "address2_city": "City 2",\
            "_slainvokedid_value": "1234567l-1234-1234-1234-1234567890",\
            "address1_postofficebox": "PO Box 123",\
            "importsequencenumber": 1,\
            "utcconversiontimezonecode": 1,\
            "schedulefollowup_qualify": null,\
            "overriddencreatedon": null,\
            "stageid": null,\
            "msdyn_leadscore": null,\
            "address1_latitude": 36.1699,\
            "address1_utcoffset": -8,\
            "yomifirstname": "John",\
            "estimatedclosedate": null,\
            "_masterid_value": null,\
            "lastonholdtime": null,\
            "address2_fax": null,\
            "address2_line1": "456 Secondary St",\
            "address1_telephone3": "+1 123 456 7892",\
            "address1_telephone2": "+1 123 456 7891",\
            "address1_telephone1": "+1 123 456 7890",\
            "address2_postofficebox": "PO Box 456",\
            "emailaddress2": "jdoe@example.com",\
            "address2_latitude": 40.7128,\
            "processid": null,\
            "emailaddress3": "john.doe@example.com",\
            "address2_composite": "456 Secondary St, City 2, State 2 67890",\
            "salesstage": null,\
            "traversedpath": null,\
            "qualificationcomments": null,\
            "address2_line2": "Apt 456",\
            "teamsfollowed": null,\
            "budgetamount": 10000.0,\
            "address2_stateorprovince": "State 2",\
            "address2_postalcode": "67890",\
            "estimatedamount": null,\
            "entityimage_url": null,\
            "initialcommunication": null,\
            "msdyn_scorehistory": null,\
            "timezoneruleversionnumber": null,\
            "estimatedamount_base": null,\
            "address2_telephone3": "+1 123 456 7893",\
            "need": null,\
            "address2_telephone2": "+1 123 456 7892",\
            "address2_telephone1": "+1 123 456 7891",\
            "address2_upszone": "Zone 2",\
            "_owningteam_value": null,\
            "budgetstatus": null,\
            "address2_line3": "Unit 456",\
            "timespentbymeonemailandmeetings": null,\
            "businesscard": null,\
            "address2_longitude": 74.006,\
            "_modifiedonbehalfby_value": null,\
            "address1_line2": "Apt 123",\
            "address1_county": "County",\
            "schedulefollowup_prospect": null,\
            "msdyn_leadscoretrend": null,\
            "address1_fax": "+1 123 456 7893",\
            "_createdonbehalfby_value": null,\
            "_accountid_value": null,\
            "address2_name": "Secondary Address",\
            "msdyn_leadgrade": null,\
            "msdyn_scorereasons": null,\
            "address2_utcoffset": -5,\
            "_campaignid_value": null,\
            "_slaid_value": null,\
            "fax": null,\
            "address2_county": "County 2",\
            "_qualifyingopportunityid_value": null,\
            "msdyn_salesassignmentresult": null,\
            "address1_line3": "Unit 123",\
            "_parentcontactid_value": null,\
            "industrycode": null,\
            "purchaseprocess": 1,\
            "onholdtime": null,\
            "entityimage_timestamp": null,\
            "_customerid_value": null,\
            "entityimageid": null,\
            "lastusedincampaign": null,\
            "_msdyn_segmentid_value": null,\
            "_originatingcaseid_value": null,\
            "telephone2": "+1 123 456 7891",\
            "yomilastname": "Doe",\
            "description": null,\
            "_relatedobjectid_value": null,\
            "_contactid_value": null,\
            "yomimiddlename": null,\
            "budgetamount_base": 10000.0,\
            "address1_name": "Main Address",\
            "yomicompanyname": null,\
            "address1_longitude": 115.1728,\
            "entityimage": null,\
            "middlename": null,\
            "estimatedvalue": null,\
            "salutation": null,\
            "pager": null,\
            "address2_country": "United States"\
        }\
    ]
}
```

## **Final thoughts**

It's highly probable that your clients utilize a diverse range of CRM systems—not just Microsoft Dynamics 365 Sales.

To cater to this varied landscape of CRM tools, you can build to [Merge's CRM Unified API](https://www.merge.dev/categories/crm-api). Once you’ve built to it, you can offer dozens of CRM integrations to clients, whether that’s Salesforce, HubSpot, ActiveCampaign, etc.

‍ _You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=4d774f39-cb2e-4916-936f-e487250f78cd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1eed0379-de64-40a9-a75b-f3ac96e61a9e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=4d774f39-cb2e-4916-936f-e487250f78cd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1eed0379-de64-40a9-a75b-f3ac96e61a9e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=568a8798-b921-42a0-afd3-4126d2e87af1&bo=2&sid=406816c03e8e11f0afd0df7a0def7bdd&vid=406857503e8e11f0b6769f450d5a4d4a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20leads%20from%20Microsoft%20Dynamics%20365%20Sales%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-leads-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-using-python&r=&lt=402&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=459903)