---
url: "https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts"
title: "How to set up an admin API user in Salesforce and create contacts"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#prerequisites)

[Authenticate with Salesforce and Obtain Access Token](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#authenticate-with-salesforce-and-obtain-access-token)

[Make HTTP Calls to Create Contacts](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#make-http-calls-to-create-contacts)

[Set Up a Webhook in Salesforce](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#set-up-a-webhook-in-salesforce)

[Conclusion](https://www.merge.dev/blog/how-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts)

##### Just for you

No items found.

# How to set up an admin API user in Salesforce and create contacts

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb2d0411c78c3bc469c_How_to_Set_Up_an_Admin_API_User_in_Salesforce_and_Create_Contacts%25252525281%2525252529.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Michael Nyamande

@Merge

Salesforce is a widely used customer relationship management (CRM) platform that offers a range of features to help businesses manage their customer interactions and data.

One of the key features of Salesforce is its API, which allows developers to integrate the platform with other systems and automate various tasks. It allows businesses to streamline operations and increase efficiency and productivity. However, Salesforce's API can be tricky to work with, especially for those new to the platform.

This article provides a step-by-step guide for setting up admin API access in Salesforce and creating contacts using Python. By the end of this tutorial, you'll have a basic understanding of how to authenticate with the Salesforce API, create contacts using the Admin API, and set up webhooks to respond to different events, such as when a new contact is created.

You can find [the code for this tutorial on GitHub](https://github.com/mikeyny/salesforce-demo).

## **Prerequisites**

To follow along with this tutorial, make sure you have the following:

- Python 3.x
- Salesforce account
- [ngrok](https://ngrok.com/)

You'll need a Salesforce Developer Edition account or a Salesforce Enterprise, Performance, or Unlimited Edition account with API access enabled. You can [sign up for a Salesforce Developer Edition account for free](https://developer.salesforce.com/signup). If you have an existing Enterprise, Performance, or Unlimited Edition account, you can enable API access by contacting your Salesforce administrator.

You'll also need to install the following Python libraries:

- `flask`
- `xmltodict`
- `requests`

You will use `requests` to talk to the Salesforce Admin API, `flask` will help you create a web server for handling your Salesforce webhooks, and `xmltodict` will help you parse the XML data passed by Salesforce via the webhook.

Here is a **requirements.txt** file that you can use to manage your dependencies:

```python
flask
requests
xmltodict
```

You can install these requirements using pip by running the command `pip install -r requirements.txt`.

With these dependencies installed, you're ready to get started with integrating Salesforce into your platform.

## **Authenticate with Salesforce and Obtain Access Token**

To interact with the Salesforce API, you must first handle authentication and generate an API token. Salesforce uses OAuth 2.0 for authentication, and it requires you to register an app with Salesforce and obtain a client ID and secret. You can then use these credentials to obtain an access token, which you'll use to authorize API requests.

Here are the steps to handle authentication and generate an API token:

First, you need to register an app in Salesforce. Go to your Salesforce instance and log in as an administrator. Navigate to **Setup** in the top right corner, and click on **Apps** under **Platform Tools**. In the **Apps** section, click on **App Manager**, then click on the **New Connected App** button.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402df5cb4a363ea807c1e4_image7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402df5cb4a363ea807c1e4_image7.webp)

Fill in the required information, such as the name and email of your app, and select **Enable OAuth Settings**.

Next, you need to enable API access. In the **OAuth Settings** section, add your callback URL or use `https://login.salesforce.com/services/oauth2/success` if you do not have one and select **Full access (full)** for the **Selected OAuth Scopes** field. Then click **Save**. You'll be redirected to a page showing your app details.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402e2ecb4a3606030822c0_image6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402e2ecb4a3606030822c0_image6.webp)

To obtain your consumer key and secret, click on **Manage Consumer Details**, which will redirect you to a page with your details. Copy your consumer key and consumer secret, which you'll use in the following steps.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402e517cefe8809084d928_image1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64402e517cefe8809084d928_image1.webp)

You must also obtain a security token for your account. You can do it by following [the instructions on the Salesforce site](https://help.salesforce.com/s/articleView?id=sf.user_security_token.htm&type=5).

Once you have this information, create a file, name it **credentials.py**, and add the values below:

```python
CONSUMER_KEY = ""   # you obtain this in step 3
CONSUMER_SECRET ="" # you obtain this in step 3
USERNAME = ""  # this is your salesforce username
PASSWORD = ""  # this is your salesforce password
SECURITY_TOKEN= "" # you obtain this in step 4
DOMAIN = "" # This is your salesforce domain, it is in the format https://MyDomainName.my.salesforce.com.
```

You'll need these values to obtain an access token from Salesforce.

_Note:_ Make sure you use the classic experience URL for your `DOMAIN` variable, which is in the format `https://MyDomainName.**develop.my.salesforce.com**` or `https://MyDomainName.**my.salesforce.com**`. Do not use the lightning experience URL, `https://MyDomainName.**develop.lightning.force.com**`, as it does not work with the API.

Lastly, you have to obtain an access token. You'll need to make a request to the Salesforce token endpoint using your client ID and secret. Salesforce provides [many different OAuth authorization flows](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_oauth_flows.htm&type=5) that you can use to obtain the access token. This tutorial will use the [Username-Password authorization flow](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_oauth_username_password_flow.htm&type=5) in Python.

To obtain your access token, create a file, name it **app.py**, and add the following code to it:

```python
import json
import requests
from credentials import *

def generate_token():
    payload = {
        'grant_type': 'password',
        'client_id': CONSUMER_KEY,
        'client_secret' : CONSUMER_SECRET,
        'username' : USERNAME,
        'password' : PASSWORD  + SECURITY_TOKEN
    }
    oauth_endpoint = '/services/oauth2/token'
    response = requests.post(DOMAIN + oauth_endpoint, data=payload)
    return response.json()["access_token"]
```

The code above defines a function, `generate_token`, that calls the Salesforce API and then extracts the access token from the response and returns it. You'll call this function and use the access token it generates to authenticate your API requests to the Salesforce platform in the next step.

## **Make HTTP Calls to Create Contacts**

In this step, you'll make HTTP calls to create contacts on Salesforce via the Admin API.

The Salesforce [contacts schema](https://developer.salesforce.com/docs/atlas.en-us.sfFieldRef.meta/sfFieldRef/salesforce_field_reference_Contact.htm) defines the structure of the data that can be stored for a contact. This schema includes fields such as First Name, Last Name, Email, Phone, Mailing Address, and so forth. When you make an API request to create a contact, you need to include the data for these fields in the request payload.

Below is how to make an `HTTP POST` request to create a contact on Salesforce. Append the following code to your **app.py** file:

```python
access_token = generate_token()

# Define the data for the new contact
contact_data = {
    "FirstName": "John",
    "LastName": "Doe",
    "Email": "johndoe@example.com",
    "Phone": "555-555-5555"
}

# Make the API call to create the contact
response = requests.post(f'{DOMAIN}/services/data/v52.0/sobjects/Contact/',
                        headers={'Authorization': f'Bearer {access_token}',
                                 'Content-Type': 'application/json'},
                        json=contact_data)

# Check the status code of the response
if response.status_code == 201:
    print('Contact created successfully!')
else:
    print(f'Error creating contact: {response.text}')
```

You can run the code using the following command:

```python
python app.py
```

You should get the following output:

```python
Contact created successfully!
```

## **Set Up a Webhook in Salesforce**

Now that you have successfully created a contact in Salesforce, it's also helpful to learn how to respond to events when someone else creates a contact in your Salesforce instance. For example, you might want to sync all contacts created in Salesforce with your mailing list on a tool such as MailChimp. Webhooks are a great way to do this. They're user-defined HTTP callbacks triggered by specific events, such as when a new contact is created.

In this example, you'll set up a webhook in Salesforce to listen for contact creations and trigger a callback to your application. The purpose of this webhook will be to keep your mailing list up-to-date with the latest contact information in Salesforce.

The code below creates your webhook using the `flask` web framework and parses the data using the `xmltodict` library for reading XML. Create a file, name it **webhook.py**, and add the following code to it:

```python
from flask import Flask, request
import json
import os
import xmltodict

app = Flask(__name__)

@app.route('/', methods = ['POST'])
def create_contact_webhook():
    # Convert the XML data to a Python dictionary
    data = request.data
    data_dict = xmltodict.parse(data)

    # Extract the contact information from the dictionary
    email = data_dict['soapenv:Envelope']['soapenv:Body']['notifications']['Notification']['sObject']['sf:Email']
    first_name = data_dict['soapenv:Envelope']['soapenv:Body']['notifications']['Notification']['sObject']['sf:FirstName']
    last_name = data_dict['soapenv:Envelope']['soapenv:Body']['notifications']['Notification']['sObject']['sf:LastName']
    print(email)

    # Call the function to create a new subscriber in Mailchimp
    # You can replace it with any other function you want to carry out when the webhook is received
    # This can be storing the new contact in a database, syncing with a mailing list, or updating an internal system
    # create_mailchimp_subscriber(email, first_name, last_name)

    return "Success", 200

if __name__ == "__main__":
    app.run(debug=True, host="0.0.0.0",port= int(os.environ.get('PORT', 5000)))
```

To test this code, Salesforce requires your webhook to be accessible over the internet. You can do this by deploying your webhook application to your own cloud or PAAS, like [Heroku](https://www.heroku.com/). You can also use [ngrok](https://ngrok.io/) to create a local tunnel to your machine, which is accessible over the internet, and through HTTPS, which is what you'll do in this tutorial.

Download [ngrok](https://ngrok.io/) and run the following command:

```python
python webhook.py
```

Now open a second terminal and run this command:

```python
ngrok http 5000
```

Using ngrok, this command creates an HTTPS tunnel that exposes your application over the internet. You should get the following output:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6440307ced42b8c187c376a1_image8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6440307ced42b8c187c376a1_image8.webp)

Please take note of the URL you get under the **Forwarding** section as you'll later need to tell Salesforce to use it to inform you of new contacts.

Configuring a webhook in Salesforce involves two steps. First, you set up an outbound message to tell Salesforce which message to send to your webhook. Next, you configure a flow, which tells Salesforce what trigger to listen for before executing your action, which in this case is the outbound message.

To set up the outbound message, follow these steps:

- In Salesforce, go to **Setup** \> **Process Automation** \> **Workflow Actions** \> **Outbound Messages**.
- Click on **New Outbound Message** and choose **Contact** from the objects dropdown.
- Enter a name for the outbound message.
- In the **Endpoint URL** field, enter the URL for the webhook that you got from ngrok.
- Select the fields you want to send in the outbound message payload and click **Save**. For the purpose of this tutorial, you can select all fields.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030909989ce2b60a18ae8_image3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030909989ce2b60a18ae8_image3.webp)

To create a flow, follow these steps:

- In Salesforce, go to **Setup** \> **Process Automation** \> **Flows**.
- Click on **New Flow** and choose **Record-Triggered Flow**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030a97cefe8ac86868ab8_image2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030a97cefe8ac86868ab8_image2.webp)

- Select **Contact** as the object that should trigger the flow, and choose **A record is created** as the trigger. You can leave all other fields in their default state and click **Done**.
- Add an action element to the flow, select **Outbound Message** as the category, select the outbound message you created in the previous step in the action filter box, and click **Done**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030c49989cea629a1e555_image4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030c49989cea629a1e555_image4.webp)

- Save your flow by clicking **Save** in the top right corner.
- Activate your flow by clicking the **Activate** button in the top right corner

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030a97cefe8ac86868ab8_image2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/644030a97cefe8ac86868ab8_image2.webp)

Now, create a new contact using either the application you created in the previous step or the Salesforce dashboard. You'll see that your webhook is invoked for each new contact created. You should get an output similar to the one below but with the email address of the new contact:

```python
127.0.0.1 - - [28/Jan/2023 10:09:47] "POST /contact HTTP/1.1" 200 -
test-user@example.com
```

In case you run into any issues, you can review the complete codebase of this tutorial [in this GitHub repo](https://github.com/mikeyny/salesforce-demo).

## **Conclusion**

You now know how to authenticate with the Salesforce Admin API and create contacts using this API through Python. You've also learned how to set up a Salesforce webhook that listens for when contacts are created. In this example, your integration with Salesforce allows you to keep your contact list updated with your external mailing list.

Following these steps can get you started with integrating Salesforce into your B2B platform. However, Salesforce may be just one of many integrations you need to build. This is where Merge can help.

[Merge](https://merge.dev/) offers a [CRM Unified API](https://merge.dev/categories/crm-api) with support for more than 40 CRM systems including [Salesforce](https://merge.dev/integrations/salesforce), [Hubspot](https://merge.dev/integrations/hubspot), and [Microsoft Dynamics](https://merge.dev/integrations/microsoft-dynamics-365-sales). This means you can build integrations for all your needs through a single API, saving you time and reducing complexity. Choosing Merge means you can focus on building your B2B platform while it takes care of all the integrations. [Give Merge a try](https://app.merge.dev/signup) to see how it can streamline your integration process.

Check out our [Guide to CRM Integrations](https://www.merge.dev/blog/ultimate-guide-to-crm-apis) for examples of product integrations, an overview of CRM data schemas, and other useful information to consider as you work with CRM APIs.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Michael Nyamande

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a2849928-51d2-4df0-bd4a-e7c01688498c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=677115a5-c90f-4b19-b0c0-18d9fa0ef130&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a2849928-51d2-4df0-bd4a-e7c01688498c&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=677115a5-c90f-4b19-b0c0-18d9fa0ef130&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=efd3cedc-a631-49f3-b980-d26a0cca9e23&bo=2&sid=c14094603e8c11f095b3052559c39f58&vid=c14333e03e8c11f0adafbfe3c2b80bef&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20set%20up%20an%20admin%20API%20user%20in%20Salesforce%20and%20create%20contacts&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-set-up-an-admin-api-user-in-salesforce-and-create-contacts&r=&lt=540&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=392833)