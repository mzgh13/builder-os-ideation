---
url: "https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python"
title: "How to GET invoices in JSON from the Netsuite SOAP API using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#)

Table of contents

[What is Netsuite?](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#what-is-netsuite)

[What is the Netsuite Developer API?](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#what-is-the-netsuite-developer-api)

[How to Understand Netsuite’s Documentation Like a Pro](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#how-to-understand-netsuites-documentation-like-a-pro)

[How to Build a Sample SOAP Envelope for Netsuite](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#how-to-build-a-sample-soap-envelope-for-netsuite)

[Required fields for creating a Netsuite Envelope](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#required-fields-for-creating-a-netsuite-envelope)

[Sending the SOAP Envelope to Netsuite to pull invoices via API](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#sending-the-soap-envelope-to-netsuite-to-pull-invoices-via-api)

[Building your Netsuite (and other accounting) integrations with Merge](https://www.merge.dev/blog/how-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python#building-your-netsuite-and-other-accounting-integrations-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python)

##### Just for you

No items found.

# How to GET invoices in JSON from the Netsuite SOAP API using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856d29748c10442b0f42ed_JSON.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53853af779c6de1fabd7_62eff9857d098c1325724163_ria.webp)

Ria Garg

Platform

@Merge

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538484e0976358929031_62eff2f406d84893e1c8be19_aaron.webp)

Aaron Lu

Growth Marketing

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 12+ Accounting integrations with one_ [_Accounting API_](https://merge.dev/category/accounting-api).

## What is Netsuite?

[Oracle Netsuite](https://www.netsuite.com/portal/home.shtml) is a popular accounting software used by SMBs (small and medium businesses) and mid-market companies. Netsuite provides a unified view of a business by bringing together finance, supply chain, HR, and e-commerce services into a single system. It’s able to serve a large variety of different industries and can be customized to accommodate a wide array of business processes.

In this article, you’ll learn how to understand Oracle Netsuite’s documentation, how to configure user permissions to begin an integration, and how to build a sample SOAP envelope with Netsuite’s API in order to GET invoices.

## What is the Netsuite Developer API?

For tools and software that act as the basis of corporate accounting and resource planning or HR workflows, an integration with Netsuite provides a powerful source of truth.

The way to build an integration with Netsuite is through the Netsuite Developer API. Here’s what you need to know to get started using the Netsuite API.

_Related:_ [_A guide to integrating with NetSuite_](https://www.merge.dev/blog/netsuite-api)

## How to Understand Netsuite’s Documentation Like a Pro

### How do you begin to integrate with Netsuite?

To begin integrating with Netsuite, you need a user role with the proper administrative permissions. In your Netsuite portal, the first thing you’ll need to do is go to your portal >> Setup >> Users/Roles >> Manage Roles.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3674_62d72dcf77dcaf6c4ae70247_Netsuite%2520Manage%2520Docs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3674_62d72dcf77dcaf6c4ae70247_Netsuite%2520Manage%2520Docs.webp)

Inside Role management, add a Role with full access to all transaction types. For the purposes of this article we’ll be pulling information from the SOAP API, so you’ll need to give the role permissions to “SOAP Web Services.”

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3671_62d72e3e0a6dc9b90bd35eeb_SOAP_Web_Services.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3671_62d72e3e0a6dc9b90bd35eeb_SOAP_Web_Services.webp)

Under the setup, tab go to “Integrations” then “Manage Integrations” and hit “New”. Look at the “Integration” page screenshot for guidance on how to fill out the form. We will use Token Based Authentication.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c367a_62d72e9ca4024324e119eb9f_Part_Two_of_Token_Based_Authentication.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c367a_62d72e9ca4024324e119eb9f_Part_Two_of_Token_Based_Authentication.webp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3684_62d72ec91d7a2d0322de00d4_Token_Based_Authentication_Screen%2520(1).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3684_62d72ec91d7a2d0322de00d4_Token_Based_Authentication_Screen%2520(1).webp)

After saving your new integration, you should receive a Consumer Key and Consumer Secret.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c367d_62d72edb2672d618e44322f2_Integrations_later.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c367d_62d72edb2672d618e44322f2_Integrations_later.webp)

To create the Token ID and SECRET go to "Manage Access Tokens" in your Netsuite instance.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3677_62d72efa846fe71f78e7900c_settings.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3677_62d72efa846fe71f78e7900c_settings.webp)

Create a New Access Token with the Role just created.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3681_62d72f0de148792bc5cdb03b_access1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3681_62d72f0de148792bc5cdb03b_access1.webp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3687_62d72f2816544a3740211f99_access2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67108a7f90caab900d9c3687_62d72f2816544a3740211f99_access2.webp)

Creating the Access token will give you the Token ID and Secret, which along with the Consumer Key and Secret will give you all the permissions you need to access the Netsuite SOAP service.

### What Netsuite data models are relevant to a general accounting use case?

When building integrations with any Accounting API Provider, including Oracle Netsuite, one key field that almost always needs to be pulled is [Invoices](https://merge.dev/docs/accounting/invoices). Other relevant data models include Journal Entries, Tracking Categories, Contacts, Accounts, and Line Items.

Invoices are important because they signal a client’s obligation to pay for a given set of goods or services.

In the next section of this article,  you will learn how to pull invoices from Netsuite’s SOAP API with Python to receive a JSON response.

## How to Build a Sample SOAP Envelope for Netsuite

Here’s an example SOAP Envelope you would send to Netsuite to pull invoices from a certain timeframe (in this example, we’ll be pulling all invoices after 2021-01-01). We’ll deconstruct the Envelope below.

```python
<?xml version='1.0' encoding='utf-8'?>
<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
   <soap-env:Header>
       <tokenPassport >
           <account xmlns:ns1="urn:core_2020_2.platform.webservices.netsuite.com">{Domain}</account>
           <consumerKey xmlns:ns2="urn:core_2020_2.platform.webservices.netsuite.com">{Username}</consumerKey>
           <token xmlns:ns3="urn:core_2020_2.platform.webservices.netsuite.com">{TOKEN_ID}</token>
           <nonce xmlns:ns4="urn:core_2020_2.platform.webservices.netsuite.com">{nonce}</nonce>
           <timestamp xmlns:ns5="urn:core_2020_2.platform.webservices.netsuite.com">{timestamp}</timestamp>
           <signature xmlns:ns6="urn:core_2020_2.platform.webservices.netsuite.com" algorithm="HMAC-SHA256">{signature}</signature>
       </tokenPassport>
       <searchPreferences xmlns:ns7="urn:messages_2020_2.platform.webservices.netsuite.com">
           <bodyFieldsOnly>true</bodyFieldsOnly>
           <returnSearchColumns>true</returnSearchColumns>
           <pageSize>1000</pageSize>
       </searchPreferences>
   </soap-env:Header>
   <soap-env:Body>
    <search >
           <searchRecord xsi:type="ns8:TransactionSearchAdvanced" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns8="urn:sales_2020_2.transactions.webservices.netsuite.com">
               <criteria >
                   <basic>
                       <type operator="anyOf" >
                           <searchValue>_invoice</searchValue>
                       </type>
                       <lastModifiedDate operator="after">
                           <searchValue >2021-01-01T00:00:00-07:00</searchValue>
                       </lastModifiedDate>
                   </basic>
               </criteria>
               <columns >
                   <basic>
                       <internalId/>
                       <transactionNumber/>
                       <quantity/>
                       <amount/>
                       <amountRemaining/>
                       <memo/>
                       <currency/>
                       <dateCreated/>
                       <dueDate/>
                       <entity/>
                       <tranDate/>
                       <discountAmount/>
                       <lastModifiedDate/>
                       <rate/>
                       <item/>
                       <account/>
                       <class/>
                       <line/>
                   </basic>
               </columns>
           </searchRecord>
       </search>
   </soap-env:Body>
</soap-env:Envelope>
```

## Required fields for creating a Netsuite Envelope

Before actually sending off the SOAP request, we’ll need to get the fields required to build the SOAP header. These fields include your (or your customer’s) `account Domain`, `Username`, `Token_ID`, `nonce`, `timestamp`, and `signature`.

**Consumer Key (Username) and Token ID:** The Consumer Key and Token ID will come from the **integration registration,** which you receive in the above section.

**Account Domain (or Account ID):** If you don’t already know your Account ID you can pull it from your unique Netsuite URL. Go to your Netsuite instance and the digits that prefix “app.netsuite.com” is your Account ID.

**Nonce:** The nonce is a 10-digit random code that is often generated with encryption libraries. In Python, there are several libraries you could use to generate it including [secrets](https://docs.python.org/3/library/secrets.html) or [osrandom](https://pynative.com/cryptographically-secure-random-data-in-python/).  For this tutorial, we’ll just use the secrets module.

**Timestamp:** Generate a current timestamp in millisecond format. It is important the timestamp is created at the time of the request. We’ll use the time library to pull in the current time.

**Signature:**

```python
timestamp: str = str(int(timezone.now().timestamp()))
       nonce: str = secrets.token_hex(20)
       base_str: str = "&".join([account_id, consumer_key, token_id, nonce, timestamp])
       key: str = "&".join([consumer_secret, token_secret])
       digest: bytes = hmac.new(str.encode(key), msg=str.encode(base_str), digestmod=hashlib.sha256).digest()
       signature: str = base64.b64encode(digest).decode()
```

To create the signature, we’ll make a hash from the nonce and timestamp just generated and your auth tokens.. Create a base string by concatenating your auth fields together, as shown in the code snippet, and create a key by concatenating your `Token Secret` and `Consumer Secret` **.** With your key and base string, generate a hash using the HmacSHA256 library, which will be your signature.

Note that in this SOAP header, we also have a set of search preferences we can fill out including body fields, search columns, and page size. We’ll set the former two to true as the fields and search columns are all we’ll need from the request. The page size is set to 1000: the maximum allowed size.

```python
<soap-env:Header>
       <tokenPassport >
           <account xmlns:ns1="urn:core_2020_2.platform.webservices.netsuite.com">{Domain}</account>
           <consumerKey xmlns:ns2="urn:core_2020_2.platform.webservices.netsuite.com">{Username}</consumerKey>
           <token xmlns:ns3="urn:core_2020_2.platform.webservices.netsuite.com">{TOKEN_ID}</token>
           <nonce xmlns:ns4="urn:core_2020_2.platform.webservices.netsuite.com">{nonce}</nonce>
           <timestamp xmlns:ns5="urn:core_2020_2.platform.webservices.netsuite.com">{timestamp}</timestamp>
           <signature xmlns:ns6="urn:core_2020_2.platform.webservices.netsuite.com" algorithm="HMAC-SHA256">{signature}</signature>
       </tokenPassport>
       <searchPreferences xmlns:ns7="urn:messages_2020_2.platform.webservices.netsuite.com">
           <bodyFieldsOnly>true</bodyFieldsOnly>
           <returnSearchColumns>true</returnSearchColumns>
           <pageSize>1000</pageSize>
       </searchPreferences>
   </soap-env:Header>
```

Now that we’ve constructed our SOAP Header, we’ll move on to the Body, where we’ll create the request.

### Constructing Your Netsuite API Request Body

The `searchRecord` field is the object for specifying the search record types for searching records based on specific search criteria. To pull invoices, we will query transactions records here: `xmlns:ns8="urn:sales_2020_2.transactions.webservices.netsuite.com`.

There are several other items we can pull from Netsuite, and you’ll be able to find the namespace values and models of ones you can pull from here: [https://www.netsuite.com/help/helpcenter/en\_US/srbrowser/Browser2016\_1/schema/record/invoice.html](https://www.netsuite.com/help/helpcenter/en_US/srbrowser/Browser2016_1/schema/record/invoice.html)

To further narrow down the search, add some criteria like below, including the search value which is the object we’re searching for (invoices), and a timeframe from which we wish to make our request. In this case, we’re pulling all invoices that occur after 2021-01-01.

```python
<soap-env:Body>
    <search >
           <searchRecord xsi:type="ns8:TransactionSearchAdvanced" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns8="urn:sales_2020_2.transactions.webservices.netsuite.com">
               <criteria >
                   <basic>
                       <type operator="anyOf" >
                           <searchValue>_invoice</searchValue>
                       </type>
                       <lastModifiedDate operator="after">
                           <searchValue >2021-01-01T00:00:00-07:00</searchValue>
                       </lastModifiedDate>
                   </basic>
               </criteria>
               <columns >
                   <basic>
                       <internalId/>
                       <transactionNumber/>
                       <quantity/>
                       <amount/>
                       <amountRemaining/>
                       <memo/>
                       <currency/>
                       <dateCreated/>
                       <dueDate/>
                       <entity/>
                       <tranDate/>
                       <discountAmount/>
                       <lastModifiedDate/>
                       <rate/>
                       <item/>
                       <account/>
                       <class/>
                       <line/>
                   </basic>
               </columns>
           </searchRecord>
       </search>
   </soap-env:Body>
```

To make the request in Python, we’ll wrap the request in a string and create variables for the header values that you’ll need to fill out with your information.

```python
request body =
f"""<soap-env:Envelope xmlns:soap-env="http://schemas.xmlsoap.org/soap/envelope/">
  <soap-env:Header>
      <tokenPassport >
          <account xmlns:ns1="urn:core_2020_2.platform.webservices.netsuite.com">{Domain}</account>
          <consumerKey xmlns:ns2="urn:core_2020_2.platform.webservices.netsuite.com">{Username}</consumerKey>
          <token xmlns:ns3="urn:core_2020_2.platform.webservices.netsuite.com">{TOKEN_ID}</token>
          <nonce xmlns:ns4="urn:core_2020_2.platform.webservices.netsuite.com">{nonce}</nonce>
          <timestamp xmlns:ns5="urn:core_2020_2.platform.webservices.netsuite.com">{timestamp}</timestamp>
          <signature xmlns:ns6="urn:core_2020_2.platform.webservices.netsuite.com" algorithm="HMAC-SHA256">{signature}</signature>
      </tokenPassport>
      <searchPreferences xmlns:ns7="urn:messages_2020_2.platform.webservices.netsuite.com">
          <bodyFieldsOnly>true</bodyFieldsOnly>
          <returnSearchColumns>true</returnSearchColumns>
          <pageSize>1000</pageSize>
      </searchPreferences>
  </soap-env:Header>
  <soap-env:Body>
   <search >
          <searchRecord xsi:type="ns8:TransactionSearchAdvanced" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns8="urn:sales_2020_2.transactions.webservices.netsuite.com">
              <criteria >
                  <basic>
                      <type operator="anyOf" >
                          <searchValue>_invoice</searchValue>
                      </type>
                      <lastModifiedDate operator="after">
                          <searchValue >2021-01-01T00:00:00-07:00</searchValue>
                      </lastModifiedDate>
                  </basic>
              </criteria>
              <columns >
                  <basic>
                      <internalId/>
                      <transactionNumber/>
                      <quantity/>
                      <amount/>
                      <amountRemaining/>
                      <memo/>
                      <currency/>
                      <dateCreated/>
                      <dueDate/>
                      <entity/>
                      <tranDate/>
                      <discountAmount/>
                      <lastModifiedDate/>
                      <rate/>
                      <item/>
                      <account/>
                      <class/>
                      <line/>
                  </basic>
              </columns>
          </searchRecord>
      </search>
  </soap-env:Body>
</soap-env:Envelope>"""
```

## Sending the SOAP Envelope to Netsuite to pull invoices via API

The rest of the steps for pulling invoices is the same as our previous SOAP example [here](https://www.merge.dev/blog/marketing/how-to-get-employees-from-the-workday-api-with-python), where we create a request and parse the response form the request.

```python
	response = requests.request(method="POST", url=url, data=request_body)
parsed_response = json.loads(parse(response.content))
```

Like before, we pass in our SOAP envelope as a request body, and instead of receiving XML which is standard in soap, we receive a parsed JSON object that’s much simpler to work with!

```python
	{
   "soapenv:Envelope": {
       "@xmlns:soapenv": "http://schemas.xmlsoap.org/soap/envelope/",
       "@xmlns:xsd": "http://www.w3.org/2001/XMLSchema",
       "@xmlns:xsi": "http://www.w3.org/2001/XMLSchema-instance",
       "soapenv:Header": {
           "platformMsgs:documentInfo": {
               "@xmlns:platformMsgs": "urn:messages_2020_2.platform.webservices.netsuite.com",
               "platformMsgs:nsId": "WEBSERVICES_7600508_04082022182110359418257319_d3406a8646b75"
           }
       },
       "soapenv:Body": {
           "searchResponse": {
               "@xmlns": "",
               "platformCore:searchResult": {
                   "@xmlns:platformCore": "urn:core_2020_2.platform.webservices.netsuite.com",
                   "platformCore:status": {
                       "@isSuccess": "true"
                   },
                   "platformCore:totalRecords": "13",
                   "platformCore:pageSize": "1000",
                   "platformCore:totalPages": "1",
                   "platformCore:pageIndex": "1",
                   "platformCore:searchId": "WEBSERVICES_7600508_04082022182110359418257319_d3406a8646b75",
                   "platformCore:searchRowList": {
                       "platformCore:searchRow": [\
                           {\
                               "@xsi:type": "tranSales:TransactionSearchRow",\
                               "@xmlns:tranSales": "urn:sales_2020_2.transactions.webservices.netsuite.com",\
                               "tranSales:basic": {\
                                   "@xmlns:platformCommon": "urn:common_2020_2.platform.webservices.netsuite.com",\
                                   "platformCommon:account": {\
                                       "platformCore:searchValue": {\
                                           "@internalId": "119"\
                                       }\
                                   },\
                                   "platformCommon:amount": {\
                                       "platformCore:searchValue": "4520.0"\
                                   },\
                                   "platformCommon:amountRemaining": {\
                                       "platformCore:searchValue": "20.0"\
                                   },\
                                   "platformCommon:class": {\
                                       "platformCore:searchValue": {\
                                           "@internalId": "1"\
                                       }\
                                   },\
                                   "platformCommon:dueDate": {\
                                       "platformCore:searchValue": "2022-01-05T00:00:00.000-08:00"\
                                   },\
                                   "platformCommon:entity": {\
                                       "platformCore:searchValue": {\
                                           "@internalId": "10"\
                                       }\
                                   },\
                                   "platformCommon:internalId": {\
                                       "platformCore:searchValue": {\
                                           "@internalId": "113"\
                                       }\
                                   },\
                                   "platformCommon:lastModifiedDate": {\
                                       "platformCore:searchValue": "2022-04-06T11:22:00.000-07:00"\
                                   },\
                                   "platformCommon:line": {\
                                       "platformCore:searchValue": "0"\
                                   },\
                                   "platformCommon:memo": {\
                                       "platformCore:searchValue": "memoline"\
                                   },\
                                   "platformCommon:tranDate": {\
                                       "platformCore:searchValue": "2021-12-06T00:00:00.000-08:00"\
                                   },\
                                   "platformCommon:transactionNumber": {\
                                       "platformCore:searchValue": "CUSTINVC1"\
                                   }\
                               }\
                           }\
                       ]
                   }
               }
           }
       }
   }
}
```

We’ve shortened our response here to a more manageable bite, but in the body section, we’re able to see the fields we’re interested in pulling under the section which includes the amount, amount remaining, and the due dates as shown below. There will also be additional fields relevant to the invoice such as modified date, memos, and general transaction information.

```python
     "platformCommon:amount": {
                                       "platformCore:searchValue": "4520.0"
                                   },
                                   "platformCommon:amountRemaining": {
                                       "platformCore:searchValue": "20.0"
                                   },
                                   "platformCommon:class": {
                                       "platformCore:searchValue": {
                                           "@internalId": "1"
                                       }
                                   },
                                   "platformCommon:dueDate": {
                                       "platformCore:searchValue": "2022-01-05T00:00:00.000-08:00"
                                   },
```

With this data at the tip of your fingers, you’re able to utilize all the data inside your or your customer's NetSuite instances.

## Building your Netsuite (and other accounting) integrations with Merge

With Merge, offering an integration with Netsuite (or any other accounting platform) inside your product becomes a trivial task.

All your developers need to do is add our drop-in [Merge Link component](https://www.merge.dev/docs/guides/merge-link/get-started) to your front end, and integrate it with [Merge’s Unified API](https://www.merge.dev/docs/sdk) in your backend. We provide SDKs in NodeJS, C#/ .NET, Python, and Ruby to make your development process easy., though if there’s a specific language you need, you can get in touch with us through Intercom to request it. You’re also able to make [requests to the Merge API](https://www.merge.dev/docs/basics/authentication).

To test with Merge, we have a [public postman space](https://www.merge.dev/docs/guides/testing-via-postman) that allows you to get a cleaned version of the JSON we’ve shown above with Merge’s API, you no longer need to do any additional work of normalizing the soap response and will receive responses in a standard format that is consistent across all accounting API providers, whether they use SOAP or a REST architecture.

Looking to integrate multiple accounting providers beyond Netsuite? Merge’s [Unified Accounting API](https://merge.dev/categories/accounting-api) provides easy, REST-based API integration with platforms like [Netsuite](https://merge.dev/integrations/netsuite), [Quickbooks](https://merge.dev/integrations/quickbooks-online), [Sage Intaact](https://merge.dev/integrations/sage-intacct), and more.

Merge’s Unified API returns standardized data across all platforms, and handles the long-term of integration maintenance for you. One integration with Merge is all you’ll need to pull and push accounting data on behalf of your customers.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Ria Garg

Platform

@Merge

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Aaron Lu

Growth Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=f4e7cd46-6194-4fd1-b1cf-a02b9756b141&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=46fdf11c-a50f-4706-a217-f64877787c32&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=f4e7cd46-6194-4fd1-b1cf-a02b9756b141&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=46fdf11c-a50f-4706-a217-f64877787c32&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=d4f2aa00-3dea-4400-abc9-13b6ded0bdd4&bo=2&sid=309639003e8c11f0bd616ff100c0787b&vid=30963b903e8c11f0b227b75e5968b03a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20invoices%20in%20JSON%20from%20the%20Netsuite%20SOAP%20API%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-invoices-in-json-from-the-netsuite-soap-api-using-python&r=&lt=413&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=195262)