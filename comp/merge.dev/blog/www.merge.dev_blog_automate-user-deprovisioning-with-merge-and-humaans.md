---
url: "https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans"
title: "How to automate user deprovisioning with Merge's Unified API and Humaans"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#)

Table of contents

[How Does the Merge API Work?](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#how-does-the-merge-api-work)

[Triggering User Deprovisioning with Merge's Unified API](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#triggering-user-deprovisioning-with-merges-unified-api)

[Final thoughts](https://www.merge.dev/blog/automate-user-deprovisioning-with-merge-and-humaans#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomate-user-deprovisioning-with-merge-and-humaans)

##### Just for you

No items found.

# How to automate user deprovisioning with Merge's Unified API and Humaans

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Amr Abdou

@Merge

Building integrations with multiple systems is complex and time-consuming.

However, a unified API solution like [Merge](https://merge.dev/) makes it easier to link various platforms. Merge, the leading unified API solution, offers a web-based interface that lets you develop integrations using a single data model. It allows you to sync and normalize data from multiple integrated systems and perform CRUD operations using a standardized data model.

Merge also lets you create webhooks to notify your software of events that happen on other integrated systems. This enables you to automate tasks such as user deprovisioning that can take long hours to do manually.

In this article, you'll learn more about how Merge's unified API simplifies integration development and maintenance, and you'll see how to use it to automate user deprovisioning in an [HRIS system](https://merge.dev/categories/hr-payroll-api) like [Humaans](https://merge.dev/integrations/humaans) in Python.

{{blog-cta-100+}}

## How Does the Merge API Work?

Merge's unified API uses a single data model to fetch, update, and delete data from different integrations, including CRM systems, application tracking systems (ATSs), ticking systems, marketing automation systems, file storage applications, and more. Data from integrations of the same category is constantly synced and normalized, enabling you to build multiple integrations using unified objects and making it easier to reuse code.

To build an integration using Merge, you start by linking an account of a supported platform from Merge's web-based interface. Merge then syncs and normalizes in the background, making it available for access using Merge's standardized data model and a single authentication method.

## Triggering User Deprovisioning with Merge's Unified API

User deprovisioning is the process of revoking access privileges and permissions for an employee who is no longer associated with an organization.

When a user is deprovisioned in the company account of an HRIS like [Humaans](https://humaans.io/), you can notify your internal system by sending a POST request to an endpoint that you define on your Merge dashboard. By including the [Employee](https://docs.merge.dev/hris/employees/) object, which is used across all HRIS integrations in Merge, you can program your application to carry out permission revocation or account deactivation in your internal system and other integrated systems.

Let's see what that looks like.

### Prerequisites

This demonstration is in Python, so you need to have the latest Python version installed on your machine. This tutorial uses version 3.9.

You also need a Merge account and a Humaans account. You can sign up for a [free Merge account](https://app.merge.dev/signup). If you are not a Humaans customer, you can sign up for a [free trial](https://app.humaans.io/signup).

_Note that this process is very similar for different HRISs, so you can adapt these steps for the HRIS of your choice._

### Create a Link Between Merge and Humaans

To create a link between Merge and Humaans, you need to generate a Humaans access token from your Humaans account.

Log in to your [Humaans account](https://app.humaans.io/), open the dropdown menu next to your name at the top left corner, and click **API Access Tokens**:

[![Create a Humaans access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794d9c35c80a9200b26_XnIi7Kp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794d9c35c80a9200b26_XnIi7Kp.webp)

Give the access token a label in the pop-up, then click **Create Access Token**. Copy this token so you can use it in the next step.

[![Create a Humaans access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7968a565e357b6ba25c_w6qKLgi.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7968a565e357b6ba25c_w6qKLgi.webp)

Then, navigate to your [Merge dashboard](https://app.merge.dev/get-started/sync-sandbox-data), scroll down, and click **Open Merge Link**. A pop-up will show all the integration options available. Select **Human Resources Information System** and then **Humaans**:

[![Create a Merge link](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f79420b0997a88968ba7_GL2A0AG.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f79420b0997a88968ba7_GL2A0AG.webp)

In the API key field, paste the Humaans access token and click **Submit**:

[![Add the access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7949ec7ec8842e03362_IaNlnsg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7949ec7ec8842e03362_IaNlnsg.webp)

Merge will start syncing your data in the background. Once the syncing is done, you will get a message that confirms the link has been created.

### Set Up the Development Environment

In this project, you’ll use the flask module to create a development server that makes an endpoint that’ll receive the webhook request from Merge.

First, create a new folder for this project, navigate to the folder in your terminal window, and create a virtual environment by running this command:

```python
python3 -m venv .venv
```

In the same terminal window, activate the virtual environment by running this command:

```python
. .venv/bin/activate
```

And run this command to install Flask:

```python
pip install Flask
```

### Create a Python App

In the project folder, create a file named `deprovisioning_webhook.py` and paste this code in it:

```python

# Importing Flask and json modules
from flask import Flask, request
from datetime import datetime, timedelta, timezone
import json

# Flask constructor takes the name of the current module (__name__) as argument.
app = Flask(__name__)

# ‘/' URL is bound with home() function.
@app.route('/')
# ‘/’ URL is bound with hello_world() function.
def home():
    return "Empty page!"

# ‘/humaansDeprovisioning’ URL is bound with humaansDeprovisioning() function.
@app.route('/humaans-deprovisioning',methods=['POST'])
def humaansDeprovisioning():
    data = request.json

    # Print The webhook data object to the terminal
    json_formatted_str = json.dumps(data, indent=2)
    print(json_formatted_str)

    # Create a datetime object in the current time
    current_date = datetime.now(tz=timezone(timedelta(hours=0)))
    # Get the Termination date from the webhook object & convert it to datetime format
    termination_date = datetime.strptime(data["data"]["termination_date"], "%Y-%m-%dT%H:%M:%S%z")

    # Compare date to determine if the employment is terminated
    if termination_date < current_date:
        print("Employment terminated. Execute user deprovisioning logic")
        print(f"Name: {data['data']['display_full_name']}")
        print(f"User ID: {data['data']['id']}")
        print(f"Termination date: {termination_date}")

    return ''

# main driver function
if __name__ == '__main__':
    # run the application
    app.run()

```

‍

This code starts by importing three modules: \`flask\` to create a server and receive webhooks, \`datetime\` to handle and compare dates, and \`json\` to print the JSON response in a readable format.

It uses the `` `@app.route('/humaans-deprovisioning',methods=['POST'])` `` decorator to bind the `` `/humaans-deprovisioning` `` URL to the `` `humaansDeprovisioning()` `` function. The `` `humaansDeprovisioning()` `` function retrieves the JSON data from the request using `` `request.json` ``. This JSON object will be the webhook post request received from Merge.

The function then prints the JSON data to the console. It also retrieves the current date and time and the termination date from the JSON data. It compares the termination date with the current date to determine if the employment is terminated. If it is, it prints information about the user and the termination date to the console.

Finally, the ` __name__ == '__main__': ` condition ensures that the Flask application is only run if the script is executed directly, then the `app.run()` function is called to start the Flask development server and run the application.

### Create a Webhook in Merge

Before adding a new webhook to your Merge account, you need a live URL for your local server. You can create one using [ngrok](https://ngrok.com/). [Create an ngrok account](https://ngrok.com/) and follow their setup guide.

After installing ngrok, open a new terminal window, navigate to the project folder, and run ngrok http 5000. Copy the live URL from this terminal window.

Next, navigate back to your Merge dashboard, open the **Advanced** page from the left sidebar menu, then click the **Webhooks** tab. In the webhooks page, click **Add Webhook** and paste the ngrok URL in the format {YOUR-NGROK-URL}/humaans-deprovisioning to the **Webhook URL** field:

[![Add a webhook URL](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794dd99a1a5dc02c557_UswgE3t.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794dd99a1a5dc02c557_UswgE3t.webp)

Scroll down and configure the webhook to send you a POST request when employee data is updated in any integrated HRIS platform. The settings to select are **Send me instances of select data types when they're created, updated, or deleted**, the **Employee** data under **Selected Data Types**, and the **Updated** event to emit a webhook, as in the following image:

[![Add a webhook in Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794aa987a260c6d6cbc_4GIQn9C.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794aa987a260c6d6cbc_4GIQn9C.webp)

### Test the App

Before you mimic a deprovisioning event on Humaans, make sure that your ngrok URL is still live and your Python application is running.

Next, go to the [Humaans dashboard](https://app.humaans.io/) and open an employee profile from the **People** view. From the left sidebar, click **Offboarding**, select an employment end date and a reason for it, then click **Confirm and Schedule Offboarding**.

[![Offboarding using Humaans](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7942cf0b85540551944_24jpK17.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f7942cf0b85540551944_24jpK17.webp)

You will not receive the update instantly because every Merge integration is synced periodically. You can speed up the process by going to the [Test Linked Accounts](https://app.merge.dev/linked-accounts/test-accounts), clicking the Humaans link page, then clicking **Resync All**:

[![Merge integration sync all](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f79420b0997a88968bb7_S4XgBFm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f79420b0997a88968bb7_S4XgBFm.webp)

After the sync is done, check the terminal window where the Python script is running. You will see the webhook post request with the updated employee data, as shown below:

[![Merge webhook POST request](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794aa987a260c6d6ccc_b19AI4D.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d4f794aa987a260c6d6ccc_b19AI4D.webp)

## Final thoughts

As you’ve seen in this article, using Merge's unified API helps you overcome many difficulties that come with such work by providing a single programming interface for more than a hundred integrations, including HRIS platforms like Humaans. You saw how to use Merge to create webhooks that alert your application to changes in HRIS users' statuses, detect deprovisioning events, and process the results.

Sign up for a [free Merge account](https://app.merge.dev/signup) to save time building integrations and focus on building your application. And if you’d like to see the platform in action, schedule a demo with one of our integration experts.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Amr Abdou

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=896fa3c8-74c8-48da-8c3a-8a93ab31863b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=fee65e71-31e9-44c6-8b77-3e2bede1df25&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-deprovisioning-with-merge-and-humaans&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=896fa3c8-74c8-48da-8c3a-8a93ab31863b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=fee65e71-31e9-44c6-8b77-3e2bede1df25&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-deprovisioning-with-merge-and-humaans&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f17e892a-cb04-4013-9103-612cd4c62d97&bo=2&sid=4d6b25303e8c11f094b601378688c433&vid=4d6b85a03e8c11f0a781196d9861a6ba&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20automate%20user%20deprovisioning%20with%20Merge%27s%20Unified%20API%20and%20Humaans&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-deprovisioning-with-merge-and-humaans&r=&lt=1243&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=876556)