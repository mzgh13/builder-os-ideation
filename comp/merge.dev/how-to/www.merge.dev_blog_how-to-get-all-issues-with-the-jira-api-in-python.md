---
url: "https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python"
title: "How to GET All Issues with the Jira API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#)

Table of contents

[Getting Issues from Jira Using Python](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#getting-issues-from-jira-using-python)

[Accessing Multiple Jira Instances or Other Similar Data Sources](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#accessing-multiple-jira-instances-or-other-similar-data-sources)

[Conclusion](https://www.merge.dev/blog/how-to-get-all-issues-with-the-jira-api-in-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-all-issues-with-the-jira-api-in-python)

##### Just for you

No items found.

# How to GET All Issues with the Jira API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ced5d06bd38a7266a5a_How_to_GET_All_Issues_with_the_Jira_API_in_Python.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Johannes Koch

@Merge

[Jira](https://www.atlassian.com/software/jira) is one of the best-known tools in the software industry for tracking work items. Originally created for bug and issue tracking, it has evolved into a more [general workflow management tool](https://www.atlassian.com/software/jira/guides/use-cases/what-is-jira-used-for). Jira can be used for [IT service management](https://www.atlassian.com/software/jira/service-management), project management, planning, and tracking bugs. It's also flexible enough to let you track custom workflows like [HR management processes or sales processes](https://www.atlassian.com/solutions/work-management).

As an increasing number of people in your organization use Jira to track more things, you'll likely want to use APIs to interact with it to extract data automatically. One of the benefits of Jira is that its REST API lets you get issues from different projects. You can use this data to analyze issues from different projects and create centralized data analytics.

In this article, you'll learn how to use the [Jira REST API](https://developer.atlassian.com/cloud/jira/platform/rest/v3/intro/#authentication) to write issues from Jira into a CSV file by using a simple Python script and by using a Jira webhook with a Python Flask application. You can get the sample code used in this tutorial on the following [GitHub repository](https://github.com/See4Devs/Jira-Python-Webhook).

#### Want to integrate Jira with your product?

Connect your product with Jira—and dozens of other ticketing tools—by simply building to our unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-all-issues-with-the-jira-api-in-python)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## Getting Issues from Jira Using Python

This tutorial shows you how to interact with Jira to extract data from your project and save them in a CSV file.

### Jira API Authentication

The Jira REST API has security measures to protect your data. Its different authentication options depend on the configuration of your Jira instance. A common authentication method is using an [API token](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/), which is what this tutorial uses.

To access your Jira instance with this method, you need to create an API token. [Go to the following URL](https://id.atlassian.com/manage-profile/security/api-tokens), click on **API tokens** , and then click on **Create API token**.

In the pop-up that appears, type `Jira-Python-Token` as the label, and click on **Create**.

[![Create API token screen](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a825427f848ac42b8f9_31gRrMn.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a825427f848ac42b8f9_31gRrMn.webp)

Create API token screen

A new pop-up will appear that contains the token but with it hidden. Click on **Copy**, and save this token somewhere in your notes because you will need it later.

[![Jira API token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a8237f4a8235aaaf371_MjgGqU9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a8237f4a8235aaaf371_MjgGqU9.webp)

Jira API token

Keep the token safe since it can give others access to your Jira instance with your permissions.

[![List API tokens screen](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a826ff5a408d883ff31_pROzeZf.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28a826ff5a408d883ff31_pROzeZf.webp)

List API tokens screen

_Related:_ [_How to get attachments from Jira_](https://www.merge.dev/blog/jira-api-get-attachments-python)

### Preparation

To follow along with this tutorial, you'll need [Python installed](https://www.python.org/downloads/) on your local machine. You'll also need to create a new project in your Jira instance with some issues with which to test your script.

Go to [**Projects > Create Project**](https://support.atlassian.com/jira-software-cloud/docs/create-a-new-project/) and choose a template that you would like to use. For this tutorial, choose **Software Development** as the template and **Kanban**. Next, click on **Use template** and **Select a team managed project**.

[![Use template](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e7e259868f4892c60_pGGMJxU.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e7e259868f4892c60_pGGMJxU.webp)

Use the kanban template

Set **TTO** as the project key and name your project "Team Onboarding".

[![Create Jira project](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e5427f83faf430ab8_0rGMTAh.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e5427f83faf430ab8_0rGMTAh.webp)

Create Jira project

Next, [create a few issues](https://support.atlassian.com/jira-software-cloud/docs/create-an-issue-and-a-sub-task/) in the project.

[![Jira project overview](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e6ff5a402a884c90f_aB70woO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28b0e6ff5a402a884c90f_aB70woO.webp)

Jira project overview

Now that you have your project set up, you'll write some code to interact with Jira using Python.

_Related:_ [_The steps for fetching projects from Jira via Python_](https://www.merge.dev/blog/jira-api-get-projects-python)

### Reading Data from Jira

Open your terminal and install the following Python library using [pip](https://pip.pypa.io/en/stable/installation/).

```“sh” language-none
pip3 install requests
```

You will use the [requests](https://pypi.org/project/requests/) package to access Jira using the [search](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-issue-search/#api-rest-api-3-search-get) REST API endpoint.

Create a new Python file named **JiraBoard.py** and paste the following code into it:

```“python” language-none
# This code sample uses the 'requests' library:
# http://docs.python-requests.org
import requests
from requests.auth import HTTPBasicAuth
import json
import csv

def JiraBoard():
   url = "https://.atlassian.net/rest/api/3/search"

   auth = HTTPBasicAuth("", "")

   headers = {
  	"Accept": "application/json"
   }

   query = {
  	'jql': 'project = TTO'
   }

   response = requests.request(
  	"GET",
  	url,
  	headers=headers,
  	params=query,
  	auth=auth
   )

   data = json.loads(response.text)
   selectedIssues=[]
   #Get all issues and put them into an array
   for issue in data['issues']:
  	#print(issue)
  	selectedIssues.append(issue)

   #Save data from Jira into a csv file
   with open('issues.csv', 'w', newline='') as csvfile:
  	fieldnames = ['expand', 'key', 'id', 'fields', 'self']
  	writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
  	for issue in selectedIssues:
     	writer.writerow(issue)

JiraBoard()

```

The above code does an HTTP GET request using the _requests_ library to the Jira search API. In the header of your request, you specify the type, which is `application/json`, and in the parameters, you put the [Jira query language](https://www.atlassian.com/software/jira/guides/expand-jira/jql) as `jql` with the value of the `project : {project-key}` that you defined when creating the Jira project . Then, you add the authentication using the `HTTPBasicAuth` function that takes as parameters your username, which is your email, and the token that you created in the previous step.

The request result is a `string` stored in the response variable, which is transformed into a JSON format using the `json.load()` method. All issues are added to the `selectedIssues` object, and they are saved into a CSV file named `Issues.csv`. `JiraBoard()` is the function that is called at the end to run all of these steps.

When you run the `JiraBoard.py` code, you should see an `Issues.csv` file created in the same directory as your script. When you open the CSV file, it should have the details of your Jira issues there.

[![CSV Jira issues](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28bea4e35c452ce18be5d_DXMa0y3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28bea4e35c452ce18be5d_DXMa0y3.webp)

CSV of Jira issues

### Jira Webhook

Webhooks are used to synchronize data between two systems to make the data flow between these systems in real time. For example, if you have Freshdesk or Zoho as a CRM, you might want to integrate it with Jira to push issues reported by your customers to your board on Jira for the technical team to investigate.

To create a webhook using Jira, you first need to have a public URL of our application. When you create or update an issue, Jira will push these changes to the webhook URL that you will specify. To do so, you either have to host a Python application on the cloud, or you can expose your application publicly. To keep it simple, you won't be hosting your application on the cloud for this tutorial; you'll use a tool to expose your application publicly.

#### Flask Application

First, create a flask app using the `JiraBoard()` function from the previous step. To start, install the following library:

```“sh” language-none
pip3 install flask
```

Next, create a file called `app.py` and paste the following code into it:

```“python” language-none
from flask import Flask,request,json
from JiraBoard import *
app = Flask(__name__)

@app.route('/')
def home():
	return 'Welcome to Flask Python Application'


@app.route('/webhook')
def webhookJira():
	JiraBoard()
	return "Retrieving issues is completed"


if __name__ == '__main__':
	app.run(debug=True)


```

_Note:_ Make sure that the files `JiraBoard.py` and `app.py` are located in the same directory.

The above code defines a simple Python flask application with two HTTP routes. The first route is the default one, which returns a simple welcome text. The second route is `/webhook`, which will run the function `JiraBoard()` that will collect and save the Jira issues locally.

Open your terminal, and run the following command to run the flask application:

```“sh” language-none
flask run
```

[![Running Flask application](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c5a788cd61761f0b672_qcm1ovY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c5a788cd61761f0b672_qcm1ovY.webp)

Running Flask application

Your application is now running on your localhost, which is [http://127.0.0.1:5000/](http://127.0.0.1:5000/). When you open the URL in your web browser, you should see this home page:

[![Flask application home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c59ef3577b03cec8729_A5cXp3W.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c59ef3577b03cec8729_A5cXp3W.webp)

Flask application home page

Next, go to the webhook URL on your browser, which is [http://127.0.0.1:5000/webhook](http://127.0.0.1:5000/webhook). You should see the message **Retrieving issues is completed**, meaning that the code finished and the `Issues.csv` file has been generated:

[![Flask application webhook page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c5955a0ecbac59a371e_g8PS4kW.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c5955a0ecbac59a371e_g8PS4kW.webp)

Flask application webhook page

[![CSV file generated](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c59922cd6f067b46d4e_7iqdK9H.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28c59922cd6f067b46d4e_7iqdK9H.webp)

CSV file generated

#### Exposing Your Application Publicly

Now that you have your application ready, you need to expose the application publicly so you can use it with the Jira webhook. To do so, you need to set up [ngrock](https://ngrok.com/download) on your machine following the instructions from their website.

After you finish installing ngrock, open your terminal and run the following command:

```“sh” language-none
ngrok http 5000
```

After running the command, you should see the URL that will redirect your localhost:5000 port to a public URL. Check the forwarding field and open the link that ends with `.ngrok.io` in your browser. You should be able to see the application on the public link:

[![ngrock output](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf6099985f0fbbe8b5_yZPmkqe.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf6099985f0fbbe8b5_yZPmkqe.webp)

ngrock output

[![Application exposed publicly](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbfc4086876063725a6_mYVVyx4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbfc4086876063725a6_mYVVyx4.webp)

Application exposed publicly

Next, open `/webhook` using the public URL. The `Issues.csv` file containing your Jira Issues should have been generated.

[![Public webhook route](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf7e2598ccfa8a2e76_txKtCIC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf7e2598ccfa8a2e76_txKtCIC.webp)

Public webhook route

#### Create a Webhook with Request Bin

When a change happens on your Jira board, the change will call a webhook, then the webhook will initiate a workflow that you'll define, which is, in this case, calling your local Flask application. To do so, you will use [RequestBin](https://pipedream.com/), a tool used to create webhooks.

To start, create an account, and log in to the dashboard.

[![RequestBin dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbfef35772a47ec8cef_SHz7iAE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbfef35772a47ec8cef_SHz7iAE.webp)

RequestBin dashboard

Go to the workflow section, click on **New +**, and select the **HTTP/Webhook** option.

[![RequestBin webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf788cd6060df104df_bZOlr2j.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf788cd6060df104df_bZOlr2j.webp)

RequestBin webhook

Next, select **HTTP Requests** and click on **Save and continue**. A unique URL will appear that you'll use to trigger the workflow. Take note of this URL because you'll need it in the next step.

[![Workflow URL](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf757536fa3d141c74_Ul8Qs8J.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cbf757536fa3d141c74_Ul8Qs8J.webp)

Workflow URL

Click on **+** to add the next step, which will indicate what will happen once this workflow is triggered. In this case, you'll add a simple HTTP request to call the Flask application. Select **Send any HTTP Request**, and add the public link of the Flask application generated with ngrock.

[![RequestBin Send HTTP Request](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cc0c408686d013725a7_pML5yLl.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28cc0c408686d013725a7_pML5yLl.webp)

RequestBin Send HTTP Request

Finally, click on **Deploy** so that the workflow is deployed and ready.

#### Set Up Jira

Now you're ready to set up your Jira webhook. To create a webhook on Jira, go to the settings menu in the top right and select **System** from the drop-down menu items:

[![Jira settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d436ff5a4bc8c858586_XUppYZO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d436ff5a4bc8c858586_XUppYZO.webp)

Jira settings

Next, go to **Webhooks** on the left navigation bar, and click on **Create a webhook**:

[![Jira webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43922cd65de0b487ea_9keWjzZ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43922cd65de0b487ea_9keWjzZ.webp)

Jira webhook

Fill in the details: use "Jira Webhook" as the name and the URL you got from RequestBin.

For the configuration on when the webhook should be called, select **created**, **updated**, and **deleted** under **Issue**. Scroll to the bottom and click on **Create**.

[![Jira webhook configuration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43c78d182a5a7e6d7c_KptaEz9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43c78d182a5a7e6d7c_KptaEz9.webp)

Jira webhook configuration

And, congratulations! You're done creating your webhook with Jira.

[![Jira webhook successfully created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d433c5e620660e95e1b_qlp216C.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d433c5e620660e95e1b_qlp216C.webp)

Jira webhook successfully created

#### Testing

Now that you have everything set, go to your Jira board and create or update some issues to test your solution.

If you do, you should see the request intercepted on RequestBin, the workflow triggered, and your Flask application app called. You should also see the `Issues.csv` file with the latest issues you created.

[![Jira dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d4346243ddbc719524c_QyYNezN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d4346243ddbc719524c_QyYNezN.webp)

Jira dashboard

[![RequestBin dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43afe3b6074e2d3c5a_Agtaki8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63e28d43afe3b6074e2d3c5a_Agtaki8.webp)

RequestBin dashboard

_Related:_ [_How to get comments from Jira using Python_](https://www.merge.dev/blog/jira-api-get-comments)

## Accessing Multiple Jira Instances or Other Similar Data Sources

As you increase your Jira usage, especially in a bigger organization, you might want to integrate different Jira instances with each other or connect to other data sources.

For example, if you're using ServiceNow for your IT service management processes, you might want to correlate [ServiceNow incidents](https://www.merge.dev/blog/get-incidents-servicenow-api) with items in your Jira instance. ServiceNow also offers a [REST API](https://docs.servicenow.com/en-US/bundle/tokyo-application-development/page/build/applications/concept/api-rest.html) that you could connect to. However, it would be difficult to maintain both implementations and connections. You'd need to map between different API responses manually as the response structure from the Jira REST API is not the same as the return structure from ServiceNow. Your scripts would also need to talk to at least two endpoints.

This is where tools like [Merge](https://www.merge.dev/) are able to help. Their [unified API](https://docs.merge.dev/get-started/introduction/#unified-api) lets you connect various data sources through setting up the connectivity in Merge. Merge supports various third-party APIs out of the box, especially for [ticketing](https://docs.merge.dev/integrations/ticketing/asana/provider-interactions/) but also for [HR management systems](https://docs.merge.dev/integrations/hris/adp-workforce-now/provider-interactions/).

Interacting with the Merge API is as simple as interacting with the Jira REST API, but you can connect various integrations in the backend. Merge takes care of handling the connection to the backend services and returns results in the same structure across various providers. As an example, the [Ticket](https://docs.merge.dev/ticketing/tickets/#tickets-object) object that the Merge API offers can be mapped to ServiceNow and Jira issues, which makes it easier for your script to handle the responses.

## Conclusion

This article showed you how to interact with and export information from the Jira REST API using Python. You also learned how to set up a Jira webhook for newly created issues in Jira.

As your integration needs grow, [Merge](https://www.merge.dev/) lets you centralize access to different tools and systems through a unified API. Merge comes with hundreds of out-of-the-box integrations with [HR](https://merge.dev/categories/hr-payroll-api), [recruiting](https://merge.dev/categories/ats-recruiting-api), [ticketing](https://merge.dev/categories/ticketing-api), [CRM](https://merge.dev/categories/crm-api), [marketing automation](https://merge.dev/categories/marketing-automation-api), and [accounting](https://merge.dev/categories/accounting-api) platforms to help B2B companies speed up the integration of their systems.

_Learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-all-issues-with-the-jira-api-in-python) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Johannes Koch

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=794e4522-3393-4ad4-a6af-c3d5cabdcfa1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=04a52767-19d6-4157-a1de-6597e2c903c2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-issues-with-the-jira-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=794e4522-3393-4ad4-a6af-c3d5cabdcfa1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=04a52767-19d6-4157-a1de-6597e2c903c2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-issues-with-the-jira-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ea72f7d7-add2-4a2a-b07a-5134b88254e2&bo=2&sid=2a5740d03e8e11f0900d859713dbc518&vid=2a5769103e8e11f0b518b7bbf1448cf9&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20All%20Issues%20with%20the%20Jira%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-issues-with-the-jira-api-in-python&r=&lt=450&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=17877)