---
url: "https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python"
title: "How to fetch opportunities from Microsoft Dynamics 365 Sales with Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python#)

Table of contents

[Authenticating with Microsoft Dynamics 365 Sales API](https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python#authenticating-with-microsoft-dynamics-365-sales-api)

[Final thoughts](https://www.merge.dev/blog/how-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python)

##### Just for you

No items found.

# How to fetch opportunities from Microsoft Dynamics 365 Sales with Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb10b382a09b6075231_How_to_Fetch_Opportunities_from_Microsoft_Dynamics_365_Sales_with_Merge_CRM_Unified_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Microsoft Dynamics 365 Sales offers a robust customer relationship management (CRM) system, enabling businesses to understand their customers' needs more accurately, engage accounts more intelligently, and secure more deals.

While there's a variety of data worth pulling from Microsoft Dynamics 365 Sales, opportunities are likely at or near the top of your list.

To help you get opportunities from the CRM in Python, we'll breakdown each step you need to follow.

## Authenticating with Microsoft Dynamics 365 Sales API

To interact with the Microsoft Dynamics 365 Sales API, you will need to authenticate your application using OAuth 2.0. The authentication process follows the Authorization Code grant type and involves several steps:

1. **Set up an OAuth flow with Microsoft Dynamics 365 Sales**: After this setup, direct your users to the authorization URL, which is `https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize`. The users need to authorize from this URL.
2. **Redirect URL and Authorization Code**: Upon successful authorization, Microsoft Dynamics 365 Sales will navigate the user back to the `redirect_url` you provided. Included in the redirection will be the `code` as a query parameter. This is the authorization code that you will later exchange for an access token.
3. **Scopes**: Include the `https://{DOMAIN}.dynamics.com/.default offline_access` scopes in your request. Scopes define the level of access that your application requires.
4. **Accessing the Token URL**: Use the client ID and secret provided by Microsoft Dynamics 365 Sales to hit the token URL `https://login.microsoftonline.com/organizations/oauth2/v2.0/token` and request an access token. The `client_id`, `client_secret`, and other parameters should be passed into the URL as body parameters.
5. **Header Format**: Make sure to use the `Content-Type: application/x-www-form-urlencoded` header format for the token URL.
6. **Accessing the Access Token**: The access token will be made available in the `access_token` key in the response from the token URL.
7. **Token Expiry**: You can find the validity of the token in the expires\_in value in the response body of the token URL.
8. **Refresh Token**: The refresh token will be available in the refresh\_token key in the response. This token can be used to refresh your access token when it expires.

By following the steps above, you can successfully authenticate and interact with the Microsoft Dynamics 365 Sales API.

```python
python import requests from requests.auth import HTTPBasicAuth import json

```

You will need to use your own `client_id` and `client_secret`.

**Replace {DOMAIN} with your Microsoft Dynamics 365 Domain**

```python
CLIENT_ID = 'your_client_id'
CLIENT_SECRET = 'your_client_secret'
REDIRECT_URI = 'your_redirect_uri'
TOKEN_URL = 'https://login.microsoftonline.com/organizations/oauth2/v2.0/token'
AUTH_URL = 'https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize'
SCOPE = 'https://{DOMAIN}.dynamics.com/.default offline_access'
API_URL = 'https://{DOMAIN}.dynamics.com/api/data/v9.0/opportunities'
```

**Get the Authorization Code**

```python
auth_response = requests.get(
    AUTH_URL,
    params={
        'client_id': CLIENT_ID,
        'response_type': 'code',
        'redirect_uri': REDIRECT_URI,
        'scope': SCOPE
    }
)
```

**Extract Authorization Code**

```python
auth_code = auth_response.json()['code']

```

**Get the Access Token**

```python
token_response = requests.post(
    TOKEN_URL,
    headers={
        'Content-Type': 'application/x-www-form-urlencoded'
    },
    data={
        'client_id': CLIENT_ID,
        'client_secret': CLIENT_SECRET,
        'code': auth_code,
        'redirect_uri': REDIRECT_URI,
        'grant_type': 'authorization_code'
    }
)
```

**Extract Access Token**

```python
access_token = token_response.json()['access_token']

```

**Extract Refresh Token**

```python
refresh_token = token_response.json()['refresh_token']

```

**Fetch Opportunities**

```python
api_response = requests.get(
    API_URL,
    headers={
        'Authorization': f'Bearer {access_token}'
    }
)
```

**Print Opportunities**

```python
print(json.dumps(api_response.json(), indent=4))

```

This script initiates the OAuth 2 flow by fetching an authorization code, exchanging it for an access token, and then using that access token to authenticate a request to the Microsoft Dynamics 365 Sales API. The script prints out the JSON response from the API, which includes the Opportunities data.

You should see the list of Opportunities from Microsoft Dynamics 365 Sales as the output.

```python
{
    "@odata.context": "https://services.odata.org/V4/(S(sapj4y0e5v))/TripPinServiceRW/",
    "value": [\
        {\
            "@odata.etag": "W/\"08D7D40891852C0F\"",\
            "prioritycode": 1,\
            "completeinternalreview": true,\
            "stepname": "Step 1",\
            "filedebrief": false,\
            "estimatedclosedate": "2022-12-25",\
            "_pricelevelid_value": "8f5c9e9f-3bb0-4ce9-851c-2f538c8b1b27",\
            "totalamount": 5000,\
            "confirminterest": true,\
            "captureproposalfeedback": false,\
            "exchangerate": 1.3,\
            "opportunityid": "d9a9a9da-1daa-4daa-adaa-2daa3daa4daa",\
            "_parentcontactid_value": "a1b2c3d4-e5f6-a7b8-c9d0-e1f2a3b4c5d6",\
            "identifycompetitors": true,\
            "_parentaccountid_value": "b1c2d3e4-f5a6-b7c8-d9e0-b1c2d3e4f5a6",\
            "name": "New Opportunity",\
            "decisionmaker": false,\
            "totallineitemamount": 4500,\
            "isrevenuesystemcalculated": true,\
            "modifiedon": "2022-02-15T18:25:43Z",\
            "_owninguser_value": "c1d2e3f4-a5b6-c7d8-e9f0-c1d2e3f4a5b6",\
            "skippricecalculation": 0,\
            "presentproposal": true,\
            "proposedsolution": "Proposed Solution Details",\
            "totaldiscountamount": 500,\
            "_ownerid_value": "d1e2f3a4-b5c6-d7e8-f9a0-d1e2f3a4b5c6",\
            "sendthankyounote": true,\
            "identifycustomercontacts": true,\
            "evaluatefit": true,\
            "totalamountlessfreight": 4800,\
            "totallineitemdiscountamount": 200,\
            "totalamountlessfreight_base": 4800,\
            "msdyn_gdproptout": false,\
            "statuscode": 1,\
            "createdon": "2022-02-15T18:25:43Z",\
            "versionnumber": 1,\
            "emailaddress": "contact@example.com",\
            "customerneed": "Customer needs details",\
            "_msdyn_predictivescoreid_value": "e1f2a3b4-c5d6-e7f8-a9b0-c1d2e3f4a5b6",\
            "totaltax_base": 100,\
            "totallineitemamount_base": 4500,\
            "estimatedvalue": 5000,\
            "totalamount_base": 5000,\
            "developproposal": true,\
            "purchaseprocess": 1,\
            "description": "Opportunity description",\
            "_msdyn_opportunitykpiid_value": "f1a2b3c4-d5e6-f7a8-b9c0-d1e2f3a4b5c6",\
            "resolvefeedback": true,\
            "totaltax": 100,\
            "totaldiscountamount_base": 500,\
            "_transactioncurrencyid_value": "g1h2i3j4-k5l6-g7h8-i9j0-g1h2i3j4k5l6",\
            "estimatedvalue_base": 5000,\
            "msdyn_forecastcategory": 1,\
            "_modifiedby_value": "h1i2j3k4-l5m6-h7i8-j9k0-h1i2j3k4l5m6",\
            "presentfinalproposal": true,\
            "_createdby_value": "i1j2k3l4-m5n6-i7j8-k9l0-i1j2k3l4m5n6",\
            "timezoneruleversionnumber": 4,\
            "currentsituation": "Current situation details",\
            "pricingerrorcode": 0,\
            "salesstagecode": 1,\
            "totallineitemdiscountamount_base": 200,\
            "purchasetimeframe": 1,\
            "identifypursuitteam": true,\
            "closeprobability": 0.8,\
            "participatesinworkflow": false,\
            "statecode": 0,\
            "_owningbusinessunit_value": "j1k2l3m4-n5o6-j7k8-l9m0-j1k2l3m4n5o6",\
            "pursuitdecision": true,\
            "opportunityratingcode": 1,\
            "_customerid_value": "k1l2m3n4-o5p6-k7l8-m9n0-k1l2m3n4o5p6",\
            "completefinalproposal": true,\
            "msdyn_opportunityscore": null,\
            "msdyn_scorehistory": null,\
            "actualvalue_base": 5000,\
            "msdyn_opportunityscoretrend": null,\
            "_msdyn_segmentid_value": null,\
            "budgetstatus": null,\
            "_accountid_value": null,\
            "finaldecisiondate": "2022-12-25",\
            "msdyn_similaropportunities": null,\
            "_slainvokedid_value": null,\
            "msdyn_opportunitygrade": null,\
            "quotecomments": null,\
            "timeline": null,\
            "qualificationcomments": null,\
            "_contactid_value": null,\
            "_campaignid_value": null,\
            "stageid": null,\
            "lastonholdtime": null,\
            "need": null,\
            "stepid": null,\
            "processid": null,\
            "onholdtime": null,\
            "freightamount": null,\
            "discountamount": null,\
            "discountpercentage": null,\
            "_owningteam_value": null,\
            "_slaid_value": null,\
            "freightamount_base": null,\
            "msdyn_scorereasons": null,\
            "discountamount_base": null,\
            "overriddencreatedon": null,\
            "teamsfollowed": null,\
            "traversedpath": null,\
            "importsequencenumber": null,\
            "initialcommunication": null,\
            "schedulefollowup_qualify": null,\
            "_createdonbehalfby_value": null,\
            "_originatingleadid_value": null,\
            "customerpainpoints": null,\
            "scheduleproposalmeeting": null,\
            "schedulefollowup_prospect": null,\
            "utcconversiontimezonecode": null,\
            "timespentbymeonemailandmeetings": null\
        }\
    ]
}
```

_Related:_ [_Benefits of marketing automation integration_](https://www.merge.dev/blog/marketing-automation-integration)

## **Final thoughts**

It's highly probable that your clients utilize a diverse range of CRM systems—not just Microsoft Dynamics 365 Sales.

To cater to this varied landscape of CRM tools, you can build to [Merge's CRM Unified API](https://www.merge.dev/categories/crm-api). Once you’ve built to it, you can offer dozens of CRM integrations to clients, whether that’s Salesforce, HubSpot, ActiveCampaign, etc.

‍ _You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python) _._

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

[iframe](https://app.qualified.com/w/1/faa5v4dWtZ1a9fXx/messenger?uuid=43929036-e512-4b2c-99d5-8866319849c6)

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b0313dc1-1fe4-412d-93d8-7e7c8beede2e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=080c3257-2420-4670-a42a-1be3fbf95169&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b0313dc1-1fe4-412d-93d8-7e7c8beede2e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=080c3257-2420-4670-a42a-1be3fbf95169&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743148015&cv=11&fst=1748743148015&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python&_ng=1&hn=www.googleadservices.com&frm=0&tiba=How%20to%20fetch%20opportunities%20from%20Microsoft%20Dynamics%20365%20Sales%20with%20Python&npa=0&pscdl=noapi&auid=1184850441.1748743148&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)[iframe](https://td.doubleclick.net/td/rul/331218389?random=1748743148208&cv=11&fst=1748743148208&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200&gcd=13l3l3l3l1l1&dma=0&tag_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351869~103351871~104481633~104481635~104559073~104559075~104612245~104612247&u_w=1280&u_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python&_ng=1&hn=www.googleadservices.com&frm=0&tiba=How%20to%20fetch%20opportunities%20from%20Microsoft%20Dynamics%20365%20Sales%20with%20Python&did=dZTQ1Zm&gdid=dZTQ1Zm&npa=0&pscdl=noapi&auid=1184850441.1748743148&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=851ac030-bbf6-40bc-8800-ee5d6f2cbe01&bo=2&sid=00f1c7203e8c11f0a0224f433e827f22&vid=00f1f2503e8c11f086970f6ed2517530&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20opportunities%20from%20Microsoft%20Dynamics%20365%20Sales%20with%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-opportunities-from-microsoft-dynamics-365-sales-with-merge-crm-unified-api-with-python&r=&lt=615&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=996348)