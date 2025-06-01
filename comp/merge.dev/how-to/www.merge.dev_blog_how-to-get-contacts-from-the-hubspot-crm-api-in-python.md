---
url: "https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python"
title: "How to GET contacts from the HubSpot CRM API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#)

Table of contents

[Setting Up Your HubSpot Account](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#setting-up-your-hubspot-account)

[Using Python with HubSpot](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#using-python-with-hubspot)

[Prerequisites](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#prerequisites)

[Managing Integrations with Merge's Unified API](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#managing-integrations-with-merges-unified-api)

[Conclusion](https://www.merge.dev/blog/how-to-get-contacts-from-the-hubspot-crm-api-in-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-contacts-from-the-hubspot-crm-api-in-python)

##### Just for you

No items found.

# How to GET contacts from the HubSpot CRM API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cec51ac179ef5ab8142_SaaS_integration_strategy.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Lucien Chemaly

@Merge

HubSpot is an all-in-one CRM platform with a comprehensive suite of tools and resources that helps businesses to connect their marketing, sales, and service efforts. Its integrated approach as well as its user-friendliness, flexibility, and top-notch customer service make HubSpot a popular choice among businesses of all sizes.

Developers may need to integrate with HubSpot to access and manage customer data, such as contacts, to personalize and automate marketing efforts. For example, a developer could use the HubSpot API to retrieve contact information and use it to trigger personalized email campaigns based on a contact's behavior on the company's website.

This article shows you how to use the Python programming to manage contacts on HubSpot. It offers detailed steps to efficiently access, retrieve, and generate contacts on the HubSpot platform using Python.

The code used in this tutorial can be found in [this GitHub repository](https://github.com/See4Devs/hubspot-python).

## Setting Up Your HubSpot Account

Before getting started on the tutorial, you need to get your HubSpot account set up.

If you don't have a HubSpot account, sign up for a free or demo account on the [HubSpot website](https://www.hubspot.com/?__hstc=229663683.401df6f512dcef59c0992c56e0b2f820.1748743587199.1748743587199.1748743587199.1&__hssc=229663683.1.1748743587199&__hsfp=3707738794).

[![HubSpot sign up](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a4127f7008ad793915c_t3lgaGw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a4127f7008ad793915c_t3lgaGw.webp)

Follow the instructions to sign up. Once your account is created, you'll be logged in to HubSpot. If you already have an account, simply log in.

[![HubSpot login](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a429bb37824d0300a67_9VXeuE6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a429bb37824d0300a67_9VXeuE6.webp)

### Create Contacts

Next, you need to create several contacts to be used later in this tutorial. Use this exercise to also familiarize yourself with the HubSpot platform.

To create a new contact, navigate to **Contacts** from the top navigation bar, then click on **Create contact** in the top right corner of the page. Fill out the form with the necessary information, including first name, last name, and email. Click on the **Create** button to submit the contact.

[![HubSpot creating a contact](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a6027f700e35e93c27d_eZHgdxO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a6027f700e35e93c27d_eZHgdxO.webp)

To delete a contact, click on the contact in the list of contacts in the HubSpot dashboard. Click on **Actions** and then **Delete** to remove the contact permanently.

[![HubSpot deleting a contact](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a60a7db575b4ec208d9_9fvI98K.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a60a7db575b4ec208d9_9fvI98K.webp)

Create four to five contacts with whatever details you wish to use later in this tutorial.

[![Hubspot contacts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a609bb37836b2303a72_UQ1mUTN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a609bb37836b2303a72_UQ1mUTN.webp)

### Create a HubSpot App and Generate an Application Token

Lastly, you need to create a HubSpot app to get a token for authenticating requests made to your HubSpot account, which you'll use later in the tutorial.

Click on **Settings** in the top navigation bar, then navigate to the **Private Apps** section under **Integrations**. Click on **Create a private app** and fill in the information required.

[![HubSpot application](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7df261340f98f95186_X1ZOyYn.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7df261340f98f95186_X1ZOyYn.webp)

Next, toggle to **Scopes**, search for **contacts**, then check all the boxes for **Read** and **Write** related to contacts. This will give your application permission to have access to your contacts.

[![HubSpot application permissions](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7d8e348816d4ebea72_dIWLukF.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7d8e348816d4ebea72_dIWLukF.webp)

Lastly, click on **Create app** in the top right corner.

You should get a prompt that states **Your private app was created**. This prompt contains your application token. Click on **Copy** and save the token somewhere safe because you'll use it later.

[![HubSpot application token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7da7db57a557c22e21_uXGw851.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95a7da7db57a557c22e21_uXGw851.webp)

## Using Python with HubSpot

With all the setup out of the way, you can now start the tutorial.

## Prerequisites

To follow along with this tutorial, you need the following installed on your machine:

- [Python 3.11.1](https://www.python.org/downloads/)
- The Python package installer [pip](https://pip.pypa.io/en/stable/installation/)

Once you have these installed, go to your terminal or shell and install the _requests_ library using the following command:

```“python” language-none
pip3 install requests
```

_Note:_ You might have already installed this library with Python. To avoid any issues, it's best to make sure it's installed before proceeding to the next step.

### Getting HubSpot Contacts Using the requests.get Method

Create a file named `get_hubspot_contacts.py` and add the following code to it:

```“python” language-none
import requests

# Set the API endpoint and headers
endpoint = "https://api.hubapi.com/contacts/v1/lists/all/contacts/all"
headers = {"Authorization": "Bearer Your_Token"}

# Make a GET request to the API
response = requests.get(endpoint, headers=headers)

# Parse the JSON data from the response
data = response.json()

# Loop through the contacts and print their information
for contact in data["contacts"]:
   print(contact)

```

Replace `Your_Token` with the token you got from the previous step.

In the code above, you start by importing the needed library, requests, to make the HTTP call. You then specify the endpoint URL and the headers that are related to your HubSpot account. Next, you call the HubSpot endpoint using the `request.get()` method, and finally, if the result is successful, you display the contacts by using a `for loop` and the `print()` function.

Run the code from the terminal or command line using the following command:

```“python” language-none
python3 get_hubspot_contacts.py
```

You should see the contacts you created on HubSpot as the output.

[![Fetching HubSpot contacts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b178e3488da46ec4f4a_QxaVanX.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b178e3488da46ec4f4a_QxaVanX.webp)

### Creating HubSpot Contacts Using the requests.post Method

Create a file named `create_hubspot_contact.py` and add the following code to it:

```“python” language-none
import requests

# Set the API endpoint
url = "https://api.hubapi.com/crm/v3/objects/contacts"

# Set the request headers
headers = {
   "Content-Type": "application/json",
   "Authorization": "Bearer Your_Token"
}

# Set the contact information
contact = {
   "properties": {
       "email": "example@python.com",
       "firstname": "Tutorial",
       "lastname": "Test1"
   }
}

# Send the request
response = requests.post(url, json=contact, headers=headers)

if response.status_code == 201:
   print("Contact Created Successfully")
else:
   print("Failed To Create Contact")

```

Replace `Your_Token` with the token you got earlier.

In the code above, you again start by importing the needed library, requests, to make the HTTP call, and then you specify the endpoint URL and the headers that are related to your HubSpot account. Next, you define the contact information that you want to create, after which you call the HubSpot endpoint using the `request.post()` method. If the result is successful, you should see the contact created on your HubSpot contacts.

Run the code from the terminal or command line using the following command:

```“python” language-none
python3 create_hubspot_contact.py
```

You should see "Contact Created Successfully" as the output.

[![Creating HubSpot contact](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b75f26134d7c5fa1cfb_Hpc3vJJ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b75f26134d7c5fa1cfb_Hpc3vJJ.webp)

If you check the HubSpot portal, you should see your newly created contact.

[![HubSpot contact created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b75d08717758799522c_7tXu2io.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95b75d08717758799522c_7tXu2io.webp)

### Creating a Webhook Using Python to Fetch HubSpot Contacts

If you want to automate the process of retrieving new or updated contact information and integrating it with other systems or applications, using a webhook with Python to fetch HubSpot contacts can be useful.

In this section, you'll use [Flask](https://flask.palletsprojects.com/en/2.2.x/) to create an endpoint that will serve as an API, or webhook, to call to get contacts. Flask is a lightweight Python framework used to create APIs.

Install the Flask library with the following command:

```“python” language-none
pip3 install flask
```

Next, create a file named `app.py` and add the following code to it:

```“python” language-none
from flask import Flask
import requests

app = Flask(__name__)

@app.route("/contacts", methods=["GET"])
def get_contacts():
   # Set the API endpoint and headers
   endpoint = "https://api.hubapi.com/contacts/v1/lists/all/contacts/all"
   headers = {"Authorization": "Bearer Your_Token"}

   # Make a GET request to the API
   response = requests.get(endpoint, headers=headers)

   # Parse the JSON data from the response
   data = response.json()

   return data

if __name__ == "__main__":
   app.run(debug=True)

```

Remember to replace `Your_Token` with the token you got earlier.

In the code above, you start by importing the `requests` library to make the HTTP call and the `flask` library to create and run your endpoint. You then define the route for the HTTP GET request of the endpoint, which is `/contacts`. The route calls the `get_contacts()` function, which calls the HubSpot endpoint and returns the contacts. This route defines the endpoint URL and the headers related to your HubSpot account.

Run the code from the terminal or command line using the following command:

```“python” language-none
flask run
```

[![Flask app running](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95c0e9f0d061face36dcd_r9tc65V.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95c0e9f0d061face36dcd_r9tc65V.webp)

Next, open your browser and paste in the following URL: [http://localhost:5000/contacts](http://localhost:5000/contacts). You should see the contacts displayed in your browser.

[![HubSpot contacts in browser](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95c0e81d12df4fac718cf_ObaaYMM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f95c0e81d12df4fac718cf_ObaaYMM.webp)

## Managing Integrations with Merge's Unified API

But what if you are not proficient in programming languages like Python? Or what if HubSpot is just one of several integrations you and your team need to build and maintain?

That's where a tool like [Merge](https://merge.dev/) can help.

Merge offers a unified API for all suites of integrations by providing a single API endpoint that connects to multiple platforms and services—including [HubSpot](https://merge.dev/integrations/hubspot). The API endpoint acts as a bridge between the different platforms and services, allowing users to interact with all of them using a single API call.

To achieve this, Merge uses a system of plugins that allows it to connect to different platforms and services. These plugins act as a bridge between the Merge API endpoint and the various platforms and services. Each plugin is responsible for handling the specific communication protocols, APIs, and data structures of the platform or service it connects to.

When a user makes an API call to Merge, the call is routed to the appropriate plugin based on the information provided in the call. The plugin then processes the call and returns the appropriate response. This allows users to interact with all the different platforms and services through a single, unified API endpoint.

Merge also allows developers to build custom plugins to connect to new platforms and services, which can be added to the API endpoint. This means that Merge is constantly expanding its integration capabilities and support for new platforms and services.

## Conclusion

This article showed you how to use Python to interact with the HubSpot CRM to fetch and create contacts. You learned how to create a webhook to automatically retrieve HubSpot contacts when the endpoint is accessed.

You also learned how the Merge [CRM Unified API](https://merge.dev/categories/crm-api) allows you to connect with hundreds platforms, including [HubSpot](https://merge.dev/integrations/hubspot) and [Salesforce](https://merge.dev/integrations/salesforce), through a single call, eliminating the need for multiple integrations. Simplifying the process of integrating with various tools and services allows you to focus on your core product, leading to increased efficiency and improved bottom line.

Check out our [Guide to CRM Integrations](https://www.merge.dev/blog/ultimate-guide-to-crm-apis) for examples of product integrations, an overview of CRM data schemas, and other useful information to consider as you work with CRM APIs.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-contacts-from-the-hubspot-crm-api-in-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lucien Chemaly

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c710e6ef-0900-413d-ab21-2118fdfe4298&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=cfe55687-7963-48a4-8e73-4bb874407675&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-contacts-from-the-hubspot-crm-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c710e6ef-0900-413d-ab21-2118fdfe4298&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=cfe55687-7963-48a4-8e73-4bb874407675&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-contacts-from-the-hubspot-crm-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f33a2e92-812f-45dd-bda5-154293df9bb3&bo=2&sid=06aa99703e8d11f084ee47da02c64ee4&vid=06aa87e03e8d11f084176fbb7908cfad&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20contacts%20from%20the%20HubSpot%20CRM%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-contacts-from-the-hubspot-crm-api-in-python&r=&lt=682&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=286845)