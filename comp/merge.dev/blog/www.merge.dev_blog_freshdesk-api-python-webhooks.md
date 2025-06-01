---
url: "https://www.merge.dev/blog/freshdesk-api-python-webhooks"
title: "How to Use the Freshdesk API with Python and Webhooks"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/freshdesk-api-python-webhooks#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/freshdesk-api-python-webhooks#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/freshdesk-api-python-webhooks#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/freshdesk-api-python-webhooks#prerequisites)

[Setting Up Your Freshdesk Account](https://www.merge.dev/blog/freshdesk-api-python-webhooks#setting-up-your-freshdesk-account)

[Fetching Freshdesk Tickets Using the requests.get Method](https://www.merge.dev/blog/freshdesk-api-python-webhooks#fetching-freshdesk-tickets-using-the-requestsget-method)

[Creating a Freshdesk Ticket Using the requests.post Method](https://www.merge.dev/blog/freshdesk-api-python-webhooks#creating-a-freshdesk-ticket-using-the-requestspost-method)

[Updating a Freshdesk Ticket Using the requests.put Method](https://www.merge.dev/blog/freshdesk-api-python-webhooks#updating-a-freshdesk-ticket-using-the-requestsput-method)

[Creating a Webhook with Freshdesk and Pipedream](https://www.merge.dev/blog/freshdesk-api-python-webhooks#creating-a-webhook-with-freshdesk-and-pipedream)

[Conclusion](https://www.merge.dev/blog/freshdesk-api-python-webhooks#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffreshdesk-api-python-webhooks)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735d06bd38a725e808_Freshservice_API_Key.webp)**How to get your Freshservice API key (4 steps)**](https://www.merge.dev/blog/freshservice-api-key)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7198dcb1a5cce5147a_Freshservice_API_key.webp)**5 ticket APIs worth building to**](https://www.merge.dev/blog/ticket-api)

# How to Use the Freshdesk API with Python and Webhooks

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856caeeb21529aacad9a0d_How_to_use_the_Freshdesk_API_with_Python_and_Webhooks.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Lucien Chemaly

@Merge

[Freshdesk](https://www.freshworks.com/freshdesk/) is cloud-based customer support software that features a ticketing system, automated workflows, a knowledge base, and self-service portals. It also includes analytics and reporting tools to track customer satisfaction and improve customer service. Freshdesk is designed for businesses of all sizes, but it's particularly well suited for small- and medium-sized businesses looking for an affordable and easy-to-use customer service platform.

One of the main reasons you might have to integrate with Freshdesk is to improve workflows and streamline communication by, for example, automating support tasks. It could also be to give the business better insight into customers by analyzing customer support data or combining it with data from other sources.

This article shows you how to use the Freshdesk API and Python to retrieve and generate tickets on Freshdesk. You'll also learn how to use a webhook with Freshdesk to get updates of changes to tickets. You can find the code for this tutorial in [this GitHub repository](https://github.com/See4Devs/freshdesk-python).

#### Add ticketing integrations to your product with ease

Learn how Merge can help you add dozens of ticketing integrations to your product—including Freshdesk—through a single, unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffreshdesk-api-python-webhooks)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Prerequisites**

To follow along with this tutorial, you need the following installed on your machine:

- [Python 3.11.1](https://www.python.org/downloads/)
- The Python package installer [pip](https://pip.pypa.io/en/stable/installation/)

Once you have these installed, go to your terminal or shell and install the requests and json libraries using these commands:

```python
pip3 install requests
pip3 install json
```

‍ _Note:_ You might have already installed this library with Python. To avoid any issues, though, make sure it's installed before proceeding to the next step.

_Related:_ [_A guide to using webhooks for internal and customer-facing integrations_](https://www.merge.dev/blog/webhooks-integration)

## **Setting Up Your Freshdesk Account**

You'll also need to set up your Freshdesk account for this tutorial.

### **Create a Freshdesk Account**

If you don't have a Freshdesk account, you can sign up for a free trial on [the Freshdesk website](https://www.freshdesk.com/).

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426faef8d0688a57fd3143f_image12.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426faef8d0688a57fd3143f_image12.webp)

You'll need to complete a registration form and activate your account through a verification email, and then log in to Freshdesk using your email address and password.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb4a14c8bd25bd02105d_image9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb4a14c8bd25bd02105d_image9.webp)

_Related:_ [_REST APIs versus webhooks_](https://www.merge.dev/blog/rest-api-vs-webhooks)

### **Create Tickets**

Next, you need to create some tickets that you'll be using later in this tutorial. If you don't know the Freshdesk platform well, use this exercise to familiarize yourself with its features.

To create a new ticket, click on **New** then **New Ticket** in the top right corner of the page. Fill out the form with the necessary information, including the subject, description, and priority level. Click on **Create** to submit the ticket.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb6a9cc9d5beb9bece42_image15.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb6a9cc9d5beb9bece42_image15.webp)

To edit a ticket, click on the ticket in the list of tickets in the Freshdesk dashboard, then click on the **Edit** pen. Make whatever changes you want to in the form and click on **Save**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb8778ce68407dcccc7e_image22.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fb8778ce68407dcccc7e_image22.webp)

To delete a ticket, click on the ticket in the list of tickets in the Freshdesk dashboard. Click on **Delete** to remove the ticket permanently.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fbb3faf5d556c18bbbe4_image26.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fbb3faf5d556c18bbbe4_image26.webp)

You'll need four to five tickets for later in this tutorial. Create them now with whatever details you wish to put.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fbfea36fc6434da635b2_image25.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fbfea36fc6434da635b2_image25.webp)

_Related:_ [_When to use polling over webhooks_](https://merge.dev/blog/webhooks-vs-polling)

### **Get Your Freshdesk API Key**

The last thing you need from Freshdesk is your API key, which you'll use for authenticating requests made to your Freshdesk account.

Click on your profile image on the top right corner, then navigate to **Profile Settings**. Click on **View API Key** to view your key.

Copy and keep this key somewhere safe because you'll need it in a later section.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fc251ef2a4463719b33e_image10.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fc251ef2a4463719b33e_image10.webp)

## **Fetching Freshdesk Tickets Using the requests.get Method**

The first thing you'll be doing in this tutorial is to fetch the tickets you just created using Python's `request.get` method.

You might want to use this method to fetch ticket data programmatically to process and analyze your ticket data for analytics purposes or if you want to integrate data from Freshdesk tickets with other applications. It gives you greater control over your ticket management processes and allows you to use data more effectively.

Create a file named **get\_freshdesk\_ticket.py** and add the following code to it:

```python
#Importing the necessary libraries
import requests
import json

#Set the API endpoint and API Key
base_url = "https://yourcompany.freshdesk.com/api/v2"
api_key = "your_api_key"
password = "your_freshdesk_password"
url = base_url + "/tickets"

#Http request to freshdesk
response = requests.get(url, auth = (api_key, password))

if response.status_code == 200:
    tickets = json.loads(response.content)
    for ticket in tickets:
        print(ticket)
else:
    print("Failed to fetch tickets.")
```

In the code above, you start by importing the needed libraries, namely `requests`, which lets you make the HTTP call, and `json`, for transforming your response from text to json format.

You then specify the credentials and URL related to your Freshdesk account. You need to replace `yourcompany` with the company name you used when you signed up for Freshdesk. You can get it from the Freshdesk URL on your browser. Replace `your_api_key` with the key you got from the previous step and `your_freshdesk_password` with the password of your Freshdesk account.

Next, you call the Freshdesk endpoint using the `request.get()` method, and finally, if the result is successful, you display the tickets by using a `for` loop and `print()`.

Run the code from your terminal or command line using the following command:

```python
python3 get_freshdesk_tickets.py
```

You should see the tickets you created on Freshdesk as the output:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fd3efaf5d50c7c8d1d83_image7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fd3efaf5d50c7c8d1d83_image7.webp)

## **Creating a Freshdesk Ticket Using the requests.post Method**

Next, you'll be creating a ticket using the `requests.post` method.

You might want to create tickets programmatically if you want to automate the process of creating tickets in real time based on events or to integrate with other systems. It lets you manage the ticket-creation process efficiently.

Create a file named **create\_freshdesk\_ticket.py** and add the following code to it:

```python
#Importing the necessary libraries
import requests
import json

#Set the API endpoint and API Key
base_url = "https://yourcompany.freshdesk.com/api/v2"
api_key = "your_api_key"
password = "your_freshdesk_password"
url = base_url + "/tickets"

headers = {
   "Content-Type": "application/json"
}

ticket = {
   'subject' : 'Tutorial Ticket',
   'description' : 'Ticket tutorial details',
   'email' : 'tutorial@python.com',
   'priority' : 1,
   'status' : 2
}

response = requests.post(url, auth = (api_key, password), data=json.dumps(ticket), headers = headers)

if response.status_code == 201:
   print("Ticket created successfully.")
else:
   print("Failed to create a ticket.")
```

This code follows a similar structure to that of the previous example. You again start by importing the needed libraries, namely `requests`, which lets you make the HTTP call, and `json`, for transforming your data from the `dict` object type to json format.

You also again specify the credentials and the URL that are related to your Freshdesk account. Remember to replace `yourcompany`, `your_api_key`, and `your_freshdesk_password` with the details from your Freshdesk account.

But because you're creating a ticket, you now define the header type, which is json, and the ticket details. You then call the Freshdesk endpoint using the `request.post()` method. Finally, if the result is successful, the ticket is created.

Run the code from your terminal or command line using the following command:

```python
python3 create_freshdesk_ticket.py
```

You should see "Ticket created successfully" as the output.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fe0cbef80312d72d0166_image16.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fe0cbef80312d72d0166_image16.webp)

Go to the Freshdesk portal to check whether the ticket has been created correctly.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fe22237698798a2a6522_image24.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fe22237698798a2a6522_image24.webp)

_Related:_ [_Common webhook events_](https://www.merge.dev/blog/webhook-events)

## **Updating a Freshdesk Ticket Using the requests.put Method**

Next, you'll be updating a Freshdesk ticket using `requests.put`. It lets you make changes to existing tickets, such as updating the status, adding notes, or modifying the details. Programmatically updating tickets lets you integrate Freshdesk with other systems to keep data consistent across multiple platforms.

Create a file named **update\_freshdesk\_ticket.py** and add the following code to it:

```python
#Importing the necessary libraries
import requests
import json

#Set the API endpoint and API Key
base_url = "https://yourcompany.freshdesk.com/api/v2"
api_key = "your_api_key"
password = "your_freshdesk_password"
#ticket ID - You get this ID from the freshdesk portal
ticketID="12"
url = base_url + "/tickets/"+ticketID

headers = {
   "Content-Type": "application/json"
}

ticket = {
   'description' : 'This is a new updated description',
}

response = requests.put(url, auth = (api_key, password), data=json.dumps(ticket), headers = headers)

if response.status_code == 200:
   print("Ticket updated successfully.")
else:
   print("Failed to update a ticket.")
```

As before, replace `yourcompany`, `your_api_key`, and `your_freshdesk_password` with the details from your Freshdesk account.

In the code above, you again start by importing the `requests` and `json` libraries and specifying the credentials and URL related to your Freshdesk account.

You then need to define the ticket ID of the ticket you want to change. You can get it from Freshdesk portal by opening the ticket and checking the ticket ID in the URL or by checking the ticket information.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fefbacd6f5274506f31c_image5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426fefbacd6f5274506f31c_image5.webp)

In this example, the ticket ID is `12`. Change this value to the ticket ID of one of yours.

Next, you define the header type, which is `json`, and the new ticket details. You then call the Freshdesk endpoint using the `request.put()` method. Finally, if the result is successful, the ticket is updated.

Run the code from your terminal or command line using the following command:

```python
python3 update_freshdesk_ticket.py
```

You should see "Ticket updated successfully" as the output.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ff7cb7504106fb200a54_image13.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ff7cb7504106fb200a54_image13.webp)

Go to your Freshdesk dashboard to check that the ticket has been updated correctly.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ff8f237698d9be2c7d9d_image3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ff8f237698d9be2c7d9d_image3.webp)

## **Creating a Webhook with Freshdesk and Pipedream**

Lastly, you'll be setting up a webhook to get updates of when changes occur to Freshdesk tickets. Webhooks allow Freshdesk to communicate with external systems in real time by sending HTTP POST requests when specific events occur.

You'll also be using [Pipedream](https://pipedream.com/), a tool that streamlines webhook handling for developers, with a serverless platform to receive webhooks from any compatible service and process data via a low-code interface or code editor.

### **Creating a Webhook with Pipedream**

To create a webhook, go to [Pipedream](https://pipedream.com/), create an account, and sign in. Go to the **Workflows** section on the left navigation bar then click on **New +**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffadd08a781b1a08ad23_image23.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffadd08a781b1a08ad23_image23.webp)

Select **HTTP / Webhook** and choose **HTTP Requests (Most Popular)**. Rename your workflow to `Freshdesk-Webhook` and then click on **Save and continue**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffd2e8e24c74a3d29a67_image18.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffd2e8e24c74a3d29a67_image18.webp)

Copy the URL of your webhook and click on **Generate Test Event** and then **Send HTTP Request**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffecc656bf19a75305c2_image8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6426ffecc656bf19a75305c2_image8.webp)

Click **Continue**.

To deploy the webhook, you need to add at least one action. After this webhook is called, what will happen? For the purpose of this tutorial, you'll add a simple `print` function using Python.

Choose **Python** from the list and then select the **Hello, World!** option.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700152cb09533798f803b_image20.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700152cb09533798f803b_image20.webp)

Click **Test** and then **Deploy**.

And, congratulations, your webhook is created!

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64270033acd6f509d207bad6_image4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64270033acd6f509d207bad6_image4.webp)

### **Setting Up a Webhook with Freshdesk**

Now that your webhook is created with Pipedream, you need to configure Freshdesk.

In your Freshdesk account, navigate to **Admin**, select **Workflows**, and choose **Automations**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427004acfbbca3c095d5fc0_image14.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427004acfbbca3c095d5fc0_image14.webp)

Next, toggle **Ticket Updates** and scroll down to the option **Create new ticket via Webhook, on replies to closed tickets**. Toggle the activation button, which will turn the toggle button green.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427005fd08a7864150975ae_image17.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427005fd08a7864150975ae_image17.webp)

After activating the webhook option, click on **Create new ticket via Webhook, on replies to closed tickets**.

You need to define the settings for which action will trigger a call to the webhook. For this example, you'll trigger a call if there is any update on any ticket that's not closed. To do so, update the information to match the following:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700862cb095d4be901f0d_image21.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700862cb095d4be901f0d_image21.webp)

Now you need to update the URL to match the one you previously created with Pipedream. Add your Pipedream URL and untoggle **Requires authentication**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427009eb83da60d2bc80b80_image1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6427009eb83da60d2bc80b80_image1.webp)

For testing purposes, you won't add a key for authenticating with the webhook. However, if you're working with live applications, you need to create your own keys to protect your webhook from DDoS attacks.

Scroll down and click **Preview and save** and then **Save** to make the changes.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700b1b750419cee20fe2c_image19.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700b1b750419cee20fe2c_image19.webp)

Now you are all set.

To test whether everything works, update one of your Freshdesk tickets. For example, change the status from **Pending** to **Resolved** and click **Update**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700c4c656bff5e953673f_image2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700c4c656bff5e953673f_image2.webp)

Your Pipedream webhook dashboard should show the details of your ticket.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700d82cb0954380908156_image11.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/642700d82cb0954380908156_image11.webp)

## **Conclusion**

In this article, you learned how to use Python to interact with Freshdesk to fetch, create, and update tickets. You also learned how to use a [webhook](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira) with Freshdesk to get real-time updates of when changes occur on Freshdesk tickets.

If you need to build and maintain several integrations, you can build one integration with [Merge](https://merge.dev/) and connect with hundreds of platforms—including [Freshdesk](https://merge.dev/integrations/freshdesk), [Zendesk](https://merge.dev/integrations/zendesk), and [Salesforce Service Cloud](https://merge.dev/integrations/salesforce-service-cloud)—through a [Helpdesk and Ticketing Unified API](https://merge.dev/categories/ticketing-api). Instead of building and maintaining integrations with various tools and services, Merge allows you to easily implement new technologies and stay up-to-date with industry trends, all while staying focused on your core operations.

_Learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffreshdesk-api-python-webhooks) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1ee669d7-1bcc-4791-a544-e098831036a4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6bf7a34b-9dc4-457b-8014-f1f68589a261&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffreshdesk-api-python-webhooks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1ee669d7-1bcc-4791-a544-e098831036a4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6bf7a34b-9dc4-457b-8014-f1f68589a261&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffreshdesk-api-python-webhooks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=aa999247-ce21-45a1-b1ee-5f3bfe1ad7e1&bo=2&sid=0d875a003e8c11f086640f543b4101d9&vid=0d8772103e8c11f0aecb75c12ca23a83&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20Use%20the%20Freshdesk%20API%20with%20Python%20and%20Webhooks&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffreshdesk-api-python-webhooks&r=&lt=567&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=787257)