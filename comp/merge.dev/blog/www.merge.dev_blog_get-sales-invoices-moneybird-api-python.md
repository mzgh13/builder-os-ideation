---
url: "https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python"
title: "How to fetch sales invoices from the Moneybird API using Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#)

Table of contents

[Authentication‍](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#authentication)

[How to GET sales invoices from Moneybird](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#how-to-get-sales-invoices-from-moneybird)

[Want to connect to more accounting systems?](https://www.merge.dev/blog/get-sales-invoices-moneybird-api-python#want-to-connect-to-more-accounting-systems)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-sales-invoices-moneybird-api-python)

##### Just for you

No items found.

# How to fetch sales invoices from the Moneybird API using Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb2a6710a493b161770_Integration_statistics.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Moneybird is a comprehensive, intuitive, accounting solution, specifically built for entrepreneurs and small and medium-sized businesses. It allows users to create and deliver invoices, receive and pay them, analyze their financials, provide links that allow clients to make payments, and much more.

While you likely want all kinds of data in Moneybird to be accessible elsewhere, sales invoices likely top your list. Syncing sales invoices with a CRM solution can, for instance, help customer-facing employees stay up-to-date on client payments and step in when necessary. And adding sales invoices—alongside other client data—to a business intelligence (BI) platform can help your analysts uncover trends and actionable insights for your go-to-market teams.

To help your team GET sales invoices form Moneybird, we’ll walk you through the steps of building a Python script that can retrieve this data.

## Authentication **‍**

The first step involves configuring authentication.

The Moneybird API uses token-based authentication, which means you need to include a specific header in your requests to the API. The header's format should be `Authorization: Bearer {API-KEY}`, where `{API-KEY}` is the API key that’s specific to your account and is encoded in Base-64. It's essential to have this key set up correctly as it’s used to authenticate your requests and ensure they come from an authorized source.

## **How to GET sales invoices from Moneybird**

The code below collects all your sales invoices from the Moneybird API and stores them in the invoices list. The loop will continue fetching invoices until there are no more pages to retrieve, as indicated by the lack of a 'next' link in the response headers. If there's any error with the request, the code will print out the HTTP status code and break the loop.

Here's the entire Python script:

```python

import requests
import base64
import json

Set your API Key and domain

api_key = "{API-KEY}"
domain = "{DOMAIN}"

Base URL for Moneybird API

base_url = f"https://moneybird.com/api/v2/{domain}/sales_invoices"

Create the header for authentication

auth_header = {
    "Authorization": f"Bearer {api_key}{base64.b64encode(api_key.encode()).decode()}"
}

Initialize variables to hold invoices and the next cursor

invoices = []
next_cursor = None

Fetch invoices from Moneybird API

while True:

# Update the URL with the next cursor if it exists
if next_cursor:
    url = f"{base_url}?page={next_cursor}"
else:
    url = base_url

# Make the GET request to the Moneybird API
response = requests.get(url, headers=auth_header)

# Check for a successful response
if response.status_code == 200:
    # Load the JSON data from the response
    data = json.loads(response.text)

    # Append the invoices to the list
    invoices.extend(data)

    # Check for the next cursor in the Link header
    if 'next' in response.links:
        next_cursor = response.links['next']['url']
    else:
        # If there's no next cursor, we've reached the last page
        break
else:
    print(f"Error: {response.status_code}")
    break

```

_Note: The API key and domain should be replaced with your specific information._

Here’s how an individual item can be returned by this API Endpoint:

```python

{
    "id": "123456",
    "administration_id": 101,
    "contact_id": "654321",
    "contact": {
        "id": "654321",
        "city": "New York",
        "email": "test@test.com",
        "notes": [],
        "phone": "1234567890",
        "country": "USA",
        "version": 1,
        "zipcode": "10001",
        "address1": "123 Test Street",
        "address2": "Apt 1A",
        "lastname": "Doe",
        "sepa_bic": "TESTBIC",
        "attention": "John Doe",
        "email_ubl": false,
        "firstname": "John",
        "sepa_iban": "TESTIBAN",
        "created_at": "2021-01-01T00:00:00Z",
        "tax_number": "123456789",
        "updated_at": "2021-01-02T00:00:00Z",
        "customer_id": "1234",
        "sepa_active": true,
        "bank_account": "1234567890",
        "company_name": "Test Inc.",
        "custom_fields": [],
        "si_identifier": "1234",
        "contact_people": [],
        "delivery_method": "mail",
        "sepa_mandate_id": "1234",
        "credit_card_type": null,
        "tax_number_valid": null,
        "administration_id": 101,
        "sepa_mandate_date": null,
        "credit_card_number": "  ** 1234",
        "sales_invoices_url": "https://example.com/test",
        "sepa_sequence_type": "RCUR",
        "si_identifier_type": null,
        "chamber_of_commerce": "123456",
        "invoice_workflow_id": null,
        "estimate_workflow_id": null,
        "credit_card_reference": "1234",
        "send_invoices_to_email": "invoices@test.com",
        "sepa_iban_account_name": "Test Account",
        "send_estimates_to_email": "estimates@test.com",
        "tax_number_validated_at": null,
        "moneybird_payments_mandate": true,
        "send_invoices_to_attention": "John Doe",
        "send_estimates_to_attention": "John Doe"
    },
    "contact_person_id": "123456",
    "contact_person": {
        "id": "123456",
        "email": "john@test.com",
        "phone": "123456789",
        "version": 1,
        "lastname": "Doe",
        "firstname": "John",
        "created_at": "2022-01-01T00:00:00Z",
        "department": "Sales",
        "updated_at": "2022-01-02T00:00:00Z",
        "administration_id": 101
    },
    "invoice_id": "123456",
    "recurring_sales_invoice_id": null,
    "workflow_id": "123456",
    "document_style_id": "123456",
    "identity_id": "123456",
    "draft_id": null,
    "state": "open",
    "invoice_date": "2022-01-01",
    "due_date": "2022-02-01",
    "payment_conditions": "30 days",
    "payment_reference": "123456",
    "short_payment_reference": "123",
    "reference": "123456",
    "language": "en",
    "currency": "USD",
    "discount": "0",
    "original_sales_invoice_id": null,
    "paused": false,
    "paid_at": null,
    "sent_at": "2022-01-01T00:00:00Z",
    "created_at": "2022-01-01T00:00:00Z",
    "updated_at": "2022-01-02T00:00:00Z",
    "public_view_code": "123456",
    "public_view_code_expires_at": "2023-01-01T00:00:00Z",
    "version": 1,
    "details": [],
    "payments": [],
    "total_paid": "0",
    "total_unpaid": "100",
    "total_unpaid_base": "100",
    "prices_are_incl_tax": true,
    "total_price_excl_tax": "100",
    "total_price_excl_tax_base": "100",
    "total_price_incl_tax": "120",
    "total_price_incl_tax_base": "120",
    "total_discount": "0",
    "marked_dubious_on": null,
    "marked_uncollectible_on": null,
    "reminder_count": 0,
    "next_reminder": "2022-02-15",
    "original_estimate_id": null,
    "url": "https://example.com/invoice/123456",
    "payment_url": "https://example.com/invoice/123456/payment",
    "custom_fields": [],
    "notes": [],
    "attachments": [],
    "events": [],
    "tax_totals": []
}

```

_Related:_ [_Everything you need to know to perform API integration testing_](https://www.merge.dev/blog/api-integration-testing)

## **Want to connect to more accounting systems?**

While collecting sales invoices from Moneybird is, clearly, valuable, you should look to build several other accounting integrations with your product to meet all of your clients’ financial data needs.

Merge, the leading Unified API platform, helps you do just that by offering an [Accounting Unified API](https://merge.dev/categories/accounting-api). Once you connect to the API, you’ll be able to offer integrations with MoneyBird, Sage Intacct, NetSuite, Freshbooks, and several other applications, and not only sync sales invoices but also other business-critical objects and fields.

_Learn more about Merge and its Accounting Unified API by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-sales-invoices-moneybird-api-python) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a111f74e-b9f5-4188-aba7-d2f44b0c5767&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=420a6916-ed9d-42b5-b4d5-f47088342523&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-sales-invoices-moneybird-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a111f74e-b9f5-4188-aba7-d2f44b0c5767&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=420a6916-ed9d-42b5-b4d5-f47088342523&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-sales-invoices-moneybird-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=08255746-542f-42dc-9f86-8e914beadd0b&bo=2&sid=e5b0afd03e8b11f0b6717f7ca4ebda18&vid=e5b128303e8b11f0ad4579f9ab7a61df&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20sales%20invoices%20from%20the%20Moneybird%20API%20using%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-sales-invoices-moneybird-api-python&r=&lt=310&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=57938)