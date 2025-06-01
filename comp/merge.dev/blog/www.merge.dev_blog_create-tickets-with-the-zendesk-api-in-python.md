---
url: "https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python"
title: "Create Tickets with the Zendesk API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#prerequisites)

[Creating Tickets on the Zendesk Portal](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#creating-tickets-on-the-zendesk-portal)

[Creating a Python Project](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#creating-a-python-project)

[Understanding the Anatomy of a Zendesk Ticket Request](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#understanding-the-anatomy-of-a-zendesk-ticket-request)

[Fetching Tickets](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#fetching-tickets)

[Creating Tickets Using Python](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#creating-tickets-using-python)

[Authentication Errors](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#authentication-errors)

[Conclusion](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-tickets-with-the-zendesk-api-in-python)

##### Just for you

No items found.

# Create Tickets with the Zendesk API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cedd0411c78c3bc80c2_Create_Tickets_with_the_Zendesk_API_in_Python.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Ndafara Tsamba

@Merge

Zendesk is an omnichannel customer service solution that's easy to use and scale. It integrates all channels through which customers reach out to your business, such as email, phone, chat, messenger, and social media, and records client communication as tickets to be resolved.

In addition to customer service management, Zendesk provides sales customer relationship management (CRM) through Zendesk Sell, enhancing productivity and prospect stage visibility for the sales team. It also offers powerful reporting that you can tailor to your business's needs.

In this article, you'll learn how to create tickets with the Zendesk API using Python. This will allow you to integrate and extend your Python projects to use Zendesk. The code used in this article can be found in [this GitHub repository](https://github.com/Ndafara/Zendesk-Tickets-Python).

{{blog-cta-100+}}

## Prerequisites

Before getting to the step-by-step process of creating tickets, first take note of the things you'll need:

**1\. A Zendesk support account with token access enabled**

If you don't have an account, you can [sign up for a free trial](https://www.zendesk.com/register/#step-1).

You need to authorize your API requests to be able to view and make data changes for tasks such as creating tickets in your country. So, log in to your Zendesk account and go to the Admin Center. Select **Apps and Integrations**, then select **Zendesk API** under **APIs**. Enable token access and save the token. You will only be shown the token once, so save it in a safe place.

The screenshot below shows token access enabled with one active API token:

[![Token access](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a5c6a93322b18c06cc3d_EBPkDTn.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a5c6a93322b18c06cc3d_EBPkDTn.webp)

**2\. Python installation**

You'll be using [Python](https://www.python.org/downloads/) version 3.11 or later. Run the command `python --version` to see which Python version number you have:

```“python” language-none
Python 3.11.0
```

‍ **3\. A virtual environment using venv**

Run the command `pip install virtualenv` to install the virtual environment tool.

## Creating Tickets on the Zendesk Portal

Before you create tickets using Python, it's helpful to create a few tickets on the Zendesk portal to help you understand what constitutes a Zendesk ticket.

Log in to the agent dashboard using the URL `https://your_domain.zendesk.com/agent/dashboard`, where your\_domain is the name of your domain.

The screenshot below shows only one ticket with the subject "Sample ticket: Meet the ticket." This is a default ticket that is created the first time you log in to the dashboard:

[![Agent dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6253eba8d438efa0588_wn2Oqyv.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6253eba8d438efa0588_wn2Oqyv.webp)

To create a new ticket, click **Add**. This will open a dialog where you can create a new ticket:

[![New ticket](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626b67c1b5ff2f8b79b_v6mbvhh.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626b67c1b5ff2f8b79b_v6mbvhh.webp)

Fill in the Subject, Body, Requester, Assignee, Type, and Priority fields. Your Requester and Assignee fields will be different from the ones below, as they will contain the user details in your Zendesk account:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1bf6670281e185db91a_Table%201.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1bf6670281e185db91a_Table%201.webp)

The new ticket dialog should now look similar to the following:

[![Portal test ticket](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a62608eed061e4070cd1_zaxZx6O.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a62608eed061e4070cd1_zaxZx6O.webp)

Next, click **Submit as New**. You can also change this button to **Submit as Open**, **Submit as Pending**, or **Submit as Solved**, as shown below:

[![Submit options](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626d82a454f79fddef4_Jh8fE17.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626d82a454f79fddef4_Jh8fE17.webp)

After you click **Submit as New**, the ticket will be added to the dashboard at `https://your_domain.zendesk.com/agent/dashboard`, as shown below:

[![Portal test ticket in dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626fc424a300d70bc0f_b3JMRki.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a626fc424a300d70bc0f_b3JMRki.webp)

Create two or more tickets, but vary their type, priority, and visibility. The tables below offer some examples of the types of tickets you can create:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1eabbb3cd61d7cc7e67_Table%202.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1eabbb3cd61d7cc7e67_Table%202.webp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1f96c41fd28a2277ea3_Table%203.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc1f96c41fd28a2277ea3_Table%203.webp)

To make a private ticket, select **Internal note** in the body instead of **Public reply**, as shown below:

[![Private ticket](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a694411cf822e0e4ce67_uW31dbV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a694411cf822e0e4ce67_uW31dbV.webp)

When you select **Task** as the ticket type, you'll have to provide a due date. In the example below, it's the fifth of December:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc21063cebcd3e55be6d0_Table%204.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc21063cebcd3e55be6d0_Table%204.webp)

The Task ticket will look like this:

[![Task ticket](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6c7d692bcd655d1afdd_CwumOoH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6c7d692bcd655d1afdd_CwumOoH.webp)

Below is a list of all the tickets created for this tutorial, categorized by priority:

[![All tickets](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6c734ee8562bf27f407_Q4hT5UN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e5a6c734ee8562bf27f407_Q4hT5UN.webp)

## Creating a Python Project

Create a new directory and name it `Ticketing_with_Zendesk_API`.

Navigate to the directory and run the following command to create a virtual environment called `ticketing_with_zendesk_api`:

```“python” language-none
python -m venv ticketing_with_zendesk_api
```

After creating the virtual environment, you need to activate it. On Windows, run the following command:

```“python” language-none
ticketing_with_zendesk_api\Scripts\activate
```

To activate the virtual environment on Linux or Mac, run this command:

```“python” language-none
source ticketing_with_zendesk_api/bin/activate
```

Once the virtual environment is activated, install the requests package by running the following command:

```“python” language-none
pip install requests
```

## Understanding the Anatomy of a Zendesk Ticket Request

Before you write the code, it's important to understand the anatomy of a Zendesk ticket request. Tickets in Zendesk are represented as JSON objects, and the following are some of their properties:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc22463cebc25bb5bfdfe_Table%205.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc22463cebc25bb5bfdfe_Table%205.webp)

The full list of properties can be found in the [Zendesk documentation](https://developer.zendesk.com/api-reference/ticketing/tickets/tickets/).

## Fetching Tickets

To fetch tickets, you need to send a GET request to a ticket endpoint. At the time of writing, the published ticket endpoints are as follows:

- GET /api/v2/tickets
- GET /api/v2/organizations/{organization\_id}/tickets
- GET /api/v2/users/{user\_id}/tickets/requested
- GET /api/v2/users/{user\_id}/tickets/ccd
- GET /api/v2/users/{user\_id}/tickets/followed
- GET /api/v2/users/{user\_id}/tickets/assigned
- GET /api/v2/tickets/recent

You'll be using the `/api/v2/tickets` endpoint, which gives you all of the existing tickets.

Create a file in the `Ticketing_with_Zendesk_API` directory with the name `fetch_tickets.py`. You'll use this file to fetch the tickets in your Zendesk account.

Put the following code in the `fetch_tickets.py` file that you created:

```“python” language-none
import requests

# Set credentials
base_url = 'https://your_domain.zendesk.com'
request_endpoint = '/api/v2/tickets'
user = 'your_email' + '/token'
password = 'your_token'

# Request tickets from endpoint
response = requests.get(base_url+request_endpoint, auth=(user, password))

# Check status code
if response.status_code != 200:
    print("Response Code: ",  response.status_code)
    exit()

# Decode JSON response and get tickets
data = response.json()
ticket_list = data['tickets']

# Loop through the tickets and print details
for ticket in ticket_list:
    print(f"Ticket ID: {ticket['id']}")
    print(f"Subject: {ticket['raw_subject']}")
    print(f"Description: {ticket['description']}")
    print(f"Priority: {ticket['priority']}")
    print(f"Due Date: {ticket['due_at']}")
    print()

```

The code starts by importing the requests package, which is a module that allows you to send HTTP requests. Next, it sets the credentials. For the `base_url`, replace `your_domain` with the actual domain name with which you signed up on Zendesk.

It then sets the request\_endpoint with the endpoint that you want to hit on Zendesk. In this instance, it is `/api/v2/tickets`. Next, it sets up the user and the password. These are the authentication details that will be used to communicate with the Zendesk API. Replace `your_email` with the email you used to sign up, and replace `your_token` with the token that you saved earlier.

The code then sends a request to the endpoint using the `requests.get()` method, and you pass in the URL and the authentication details. The full line of code becomes:

```“python” language-none
response = requests.get(base_url+request_endpoint, auth=(user, password))
```

Next, it checks the status\_code of the response. If it is not 200, it means that there was a problem, so it prints the response code that it got and then exits the application.

If it is 200, everything went well, and it proceeds to decode the response to JSON. It then loops through all the tickets, printing each ticket's ID, subject, description, priority, and due date.

To execute the program, run the following command in the terminal from the root directory:

```“python” language-none
python fetch_tickets.py
```

The output of the code should be as follows:

```“python” language-none
Ticket ID: 1
Subject: Sample ticket: Meet the ticket
Description: Hi there,

I'm sending an email because I'm having a problem setting up your new product. Can you help me troubleshoot?

Thanks,
 The Customer

Priority: normal
Due Date: None

Ticket ID: 2
Subject: Portal Test Ticket One
Description: Demonstrating creating a public ticket
Priority: normal
Due Date: None

Ticket ID: 3
Subject: Portal Test Ticket Two
Description: Demonstrating creating a private ticket
Priority: normal
Due Date: None

Ticket ID: 4
Subject: Portal Test Ticket Three
Description: Demonstrating creating a high priority ticket
Priority: high
Due Date: None

Ticket ID: 5
Subject: Portal Test Ticket Four
Description: Demonstrating creating a Task ticket
Priority: normal
Due Date: 2022-12-05T10:00:00Z

```

The output should be consistent with the tickets you have in Zendesk. In this example, it's five tickets.

## Creating Tickets Using Python

You've seen how to create tickets on the portal and then fetch them using Python. You'll now see how to create tickets with Python instead of the portal. Instead of sending a GET request, like you did for fetching, you'll send a POST request, and the published endpoint to send is `/api/v2/tickets`.

In essence, you'll construct your message using the ticket properties mentioned earlier, encode the data into a JSON payload, and then send it.

Create a file named `create_ticket.py` in the `Ticketing_with_Zendesk_API` directory and put in the following code:

```“python” language-none
import requests
import json

# Set the credentials
base_url = "https://your_domain.zendesk.com"
request_endpoint = "/api/v2/tickets"
user = "your_email" + "/token"
password = "your_token"
headers = {"content-type": "application/json"}

# New ticket information
subject = "Python API Test Ticket One"
body = "Demonstrating creating a ticket with the Zendesk API using Python"
type = "question"
priority = "normal"

# Package the data into a dictionary
data = {"ticket": {"subject": subject, "type": type, "priority": priority, "comment": {"body": body}}}

# Encode the data to create a JSON payload
payload = json.dumps(data)

# Send the HTTP post request
response = requests.post(base_url+request_endpoint, data=payload, auth=(user, password), headers=headers)

# Check for HTTP codes other than 201 (Created)
if response.status_code != 201:
    print(f"Response Code: {response.status_code}. There was a problem with the request. Exiting.")
    exit()

print('Successfully created the ticket.')

```

The code starts by importing the requests and json modules. The requests module is used to send your ticket to Zendesk, and the json module is used to encode your data into a payload that the Zendesk API accepts.

It then sets up the credentials as before. Remember to replace `your_domain`, `your_email`, and `your_token` with your actual values. It then sets up the headers. The Zendesk API expects a content type of `application/json`, so that is included here.

Next, it creates the ticket information by using some of the parameters that you have already encountered in this tutorial. This example uses subject, body, type, and priority. It then creates a dictionary that represents what the Zendesk API expects and encodes it into JSON format.

With everything it needs to create the ticket, it sends a POST request using the requests module.

If you get a 201 status code, it means that the ticket was created successfully, and a "Successfully created the ticket" message is printed. If the status code is not 201, there was a problem, so the status code that you got is printed, and it exits the application.

To execute the code, run the following command:

```“python” language-none
python create_ticket.py
```

If everything went well, you'll get a confirmation message that the ticket was successfully created:

```“python” language-none
Successfully created the ticket.
```

To verify that the ticket was created, log in to the agent dashboard at `https://your_domain.zendesk.com/agent/dashboard`, where you should see a ticket with the subject "Python API Test Ticket One."

### Showing a Single Ticket

Instead of listing all the tickets in one output, you can show a specific ticket, but this is only possible if you know the ticket ID of the ticket you want to show. This method works by using a GET request to the published endpoint at `/api/v2/tickets/{ticket_id}` and then replacing `ticket_id` with your ticket ID.

Create a file called `show_ticket.py` and put in the following code:

```“python” language-none
import requests

# Set the credentials
base_url = 'https://your_domain.zendesk.com'
ticket_id = 6
request_endpoint = '/api/v2/tickets/' + str(ticket_id)
user = 'your_email' + '/token'
password = 'your_token'

# Request ticket from endpoint
response = requests.get(base_url+request_endpoint, auth=(user, password))

# Check status code
if response.status_code != 200:
    print(f"Response Code: {response.status_code}. There was a problem with the request. Exiting.")
    exit()

# Decode JSON response and get the ticket
data = response.json()
ticket_data = data['ticket']

print(f"Ticket ID: {ticket_data['id']}")
print(f"Subject: {ticket_data['raw_subject']}")
print(f"Description: {ticket_data['description']}")
print(f"Priority: {ticket_data['priority']}")
print(f"Type: {ticket_data['type']}")
print()

```

To execute the code, run the following command:

```“python” language-none
python show_ticket.py

```

The output of the execution should be as follows:

```“python” language-none
Ticket ID: 6
Subject: Python API Test Ticket One
Description: Demonstrating creating a ticket with the Zendesk API using Python
Priority: normal
Type: question

```

The subject is "Python API Test Ticket One," which matches the one you created using the API in Python.

## Authentication Errors

Things don't always work as intended, and you could encounter some authentication errors. Below are some of the authentication errors with their response codes that you might encounter:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc2361167b688cdfc63e8_Table%206.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/640fc2361167b688cdfc63e8_Table%206.webp)

These errors can be fixed by checking if you are authorized to perform API calls. If you're authorized, check whether you're using the correct user and token details.

You can find the full list of errors you can encounter in the [Zendesk developer documentation](https://developer.zendesk.com/api-reference/introduction/requests/#status-codes).

## Conclusion

In this article, you learned how to create and show tickets with the Zendesk API in Python.

Doing this manually for each integration you use can be tedious, though. If you have to integrate several tools, consider [Merge](https://merge.dev/), a Unified API for hundreds of integrations that include [Zendesk](https://merge.dev/integrations/zendesk), [Freshdesk](https://merge.dev/integrations/freshdesk), [Salesforce Service Cloud](https://merge.dev/integrations/salesforce-service-cloud), and other [helpdesk and ticketing apps](https://merge.dev/categories/ticketing-api).

Instead of learning each API, you only have to know how Merge works to interact with the different APIs that it supports. And if you don't see the integration you need, let Merge know, and they'll add it fast—at no extra charge to you.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-tickets-with-the-zendesk-api-in-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Ndafara Tsamba

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d1bbebd1-d9e9-47ca-8752-3b36fa69a10f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a5ba574f-662c-4876-89db-476e675e0e81&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-tickets-with-the-zendesk-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d1bbebd1-d9e9-47ca-8752-3b36fa69a10f&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a5ba574f-662c-4876-89db-476e675e0e81&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-tickets-with-the-zendesk-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=33d3c96a-d5a9-45ad-afb6-fef977f0f320&bo=2&sid=27d9abe03e8c11f0889e01f0b8427e16&vid=27d9c0e03e8c11f0bb0ec1dbc41d86c5&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Create%20Tickets%20with%20the%20Zendesk%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-tickets-with-the-zendesk-api-in-python&r=&lt=1182&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=649660)