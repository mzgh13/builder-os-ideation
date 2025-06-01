---
url: "https://www.merge.dev/blog/get-all-issues-github-api-python"
title: "How to get all issues with the GitHub API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-all-issues-github-api-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-all-issues-github-api-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-all-issues-github-api-python#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/get-all-issues-github-api-python#prerequisites)

[Generating a GitHub auth token](https://www.merge.dev/blog/get-all-issues-github-api-python#generating-a-github-auth-token)

[Fetching all GitHub issues](https://www.merge.dev/blog/get-all-issues-github-api-python#fetching-all-github-issues)

[Setting up a webhook endpoint](https://www.merge.dev/blog/get-all-issues-github-api-python#setting-up-a-webhook-endpoint)

[Build to multiple ticketing applications through a single API with Merge](https://www.merge.dev/blog/get-all-issues-github-api-python#build-to-multiple-ticketing-applications-through-a-single-api-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-all-issues-github-api-python)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7198dcb1a5cce5147a_Freshservice_API_key.webp)**5 ticket APIs worth building to**](https://www.merge.dev/blog/ticket-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7000295f40b50711b2_API_key_guide.webp)**How to get tickets from Jira using Python**](https://www.merge.dev/blog/how-to-get-tickets-from-jira-using-python)

# How to get all issues with the GitHub API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7241fab85507bb23f5_SharePoint_API_key.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Kumar Harsh

@Merge

GitHub is widely used by developers from companies of all sizes to manage issues, code, projects, and more.

To help users better access and integrate its services, GitHub offers a [REST API](https://docs.github.com/en/rest) that allows you to access your GitHub data through your applications and services as and when you need it. And while there are a variety of valuable endpoints provided in GitHub's API, [issues](https://docs.github.com/en/rest/issues/issues) is one of the most valuable; it lets you sync issues with internal bug tracking systems, use issue data to trigger project management tasks, identify common issues, and more.

We'll help you leverage this endpoint effectively by breaking down how you can access all issues in a given GitHub repository using Python. You'll also learn how to set up a webhook that automatically receives all new issues created on a GitHub repository.

#### Add ticketing integrations to your product with ease

Learn how Merge can help you add dozens of ticketing integrations to your product—including GitHub—through a single, unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-all-issues-github-api-python)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## Prerequisites

You'll need these things to follow along:

- A [GitHub account](https://github.com/join) to generate a token that enables you to access the GitHub API
- A GitHub repo with closed and open issues
- A copy of [Python](https://www.python.org/) installed on your system
- [ngrok](https://ngrok.com/) for creating a public URL for a webhook

If you don't have a GitHub repo on your account that has a few issues in both closed and open states, you can either create one manually or use a public repo, such as [this one](https://github.com/krharsh17/sample-repo).

_Related:_ [_A guide to retrieving repositories in GitHub_](https://www.merge.dev/blog/github-get-repositories)

## Generating a GitHub auth token

Once you're ready to start, head over to the [Settings page](https://github.com/settings/tokens) on your GitHub account and generate a new classic auth token by clicking on the **Generate new token** drop-down and selecting **Generate new token (classic).**

You might be asked to provide your GitHub password to verify your identity.

On the next page, name your token to recognize it later and select its scope. Since you're looking to access public information in this tutorial, you don't need to select any scopes. Once done, click on the green **Generate token** button at the bottom:

[![Creating the token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0dc94272a9ba843aa2_tfAsLyS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0dc94272a9ba843aa2_tfAsLyS.webp)

Once the token is created, you'll be shown its value. Make sure to copy and store it in a safe place.

## Fetching all GitHub issues

To create the app for this tutorial, create a new directory with two files in it named appy.py and templates/index.html using the following commands:

```python

mkdir github-issues
cd github-issues
touch app.py
mkdir templates
touch templates/index.html

```

The app.py file holds your Flask app's code, and the templates/index.html file defines a basic HTML template that you'll use to render the list of issues.

Paste the following in the templates/index.html file:

```html

<!DOCTYPE html>
<html>
<head>
  <title>GitHub Issue Tracker</title>
</head>
<body>
  <h1>GitHub Issue Tracker</h1>
  <form action="/fetch_issues" method="GET">
    <label for="repo_url">Enter GitHub repo URL:</label>
    <input type="text" id="repo_url" name="repo_url">
    <button type="submit">Fetch Issues</button>
  </form>
  <h2>All Issues</h2>
  <ul>
    {% for issue in issues %}
    <li>
      <a href="{{ issue.html_url }}">{{ issue.title }}</a> - {{ issue.state }}
    </li>
    {% endfor %}
  </ul>
</body>
</html>

```

‍

This HTML file defines an input box, a button that lets you enter the URL of the repo whose issues have to be fetched, and a list at the bottom where the fetched issues are listed.

Next, paste the following code into the app.py file:

```python

import requests
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/fetch_issues')
def fetch_issues():
    repo_url = request.args.get('repo_url')

    split_url = repo_url.split("/")
    owner = split_url[3]
    repo = split_url[4]

    response = requests.get(f'https://api.github.com/search/issues?q=repo:{owner}/{repo}+is:issue&per_page=100',
            headers={
                'X-GitHub-Api-Version': '2022-11-28',
                'Authorization': 'Bearer '
                })

    if response.status_code == 200:
        issues = response.json()["items"]
    else:
        issues = []

    return render_template('index.html', issues=issues)

if __name__ == '__main__':
    app.run(debug=True)

```

This code defines two endpoints—a home page route (/) to render the HTML web page and another route to fetch the issues for a particular GitHub repo and render the populated template.

The /fetch\_issues endpoint makes a request to the GitHub Search endpoint to look up all issues of a given repo and return one hundred items per page. If you're handling a repo with a large number of issues, you need to take care of [API pagination](https://www.merge.dev/blog/rest-api-pagination) yourself since the GitHub API limits the maximum number of items in this response to a hundred.

Note that the [GitHub Search API](https://docs.github.com/en/rest/search/search?apiVersion=2022-11-28) has been used here instead of the Issues API. This is because the [Issues API](https://docs.github.com/en/rest/issues/issues?apiVersion=2022-11-28) also returns [pull requests in the response](https://docs.github.com/en/rest/issues/issues?apiVersion=2022-11-28) as GitHub treats issues and pull requests the same internally. If you'd like to experiment, you can try replacing the GitHub API URL with `https://api.github.com/repos/{owner}/{repo}/issues?state=all&per_page=100` to test out the Issues API.

Before you run this code, you need to run the following commands to create a virtual environment in the directory, activate it, and install the required packages ( `requests and Flask):`

```python

python3 -m venv env
source env/bin/activate

pip3 install requests Flask

```

`‍` You can now run the app using the following command: ` python3app.py` You can access the app at http://17.0.0.1:5000. Here's how the page looks when you enter the URL `https://github.com/krharsh17/sample-repo.git in the input box:`

[![Demo app for fetching all issues](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d76f8e136c155c345_mxLG3Yt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d76f8e136c155c345_mxLG3Yt.webp)

You can put in any repo's URL to list its issues. You can also develop this code further to make integrations that rely on this data.

## Setting up a webhook endpoint

GitHub also allows you to set up webhooks to get notified when a new issue is created on one of your repos. To do that, you need to make some changes to the Flask app you've created.

Start by adding the following to the templates/index.html file to render the list of issues received through the webhook.

```html

<!DOCTYPE html>
<html>
<head>
    <title>GitHub Issue Tracker</title>
    <script src="https://unpkg.com/htmx.org@1.9.10"></script>
</head>
<body>
    <h1>GitHub Issue Tracker</h1>

    <form action="/fetch_issues" method="GET">
        <label for="repo_url">Enter GitHub repo URL:</label>
        <input type="text" id="repo_url" name="repo_url">
        <button type="submit">Fetch Issues</button>
    </form>

    <h2>All Issues</h2>
    <ul>
        {% for issue in issues %}
        <li>
            <a href="{{ issue.html_url }}">{{ issue.title }}</a> - {{ issue.state }}
        </li>
        {% endfor %}
    </ul>

    <!-- Add the following tags -->
    <h2>New Issues from Webhook</h2>
    <ul hx-get="/webhook" hx-trigger="every 2s"></ul>
</body>
</html>

```

The ul tag makes use of [HTMX](https://htmx.org/) to make AJAX GET requests to a /webhook endpoint in the app and load the latest list of issues received from the webhook. The attribute sets the requests to be sent every two seconds to poll the backend for the latest list of issues.

On the backend, you need to add the following code in the app.py file:

```python

webhook_issues = []  # Store new issues received through webhook

@app.route('/webhook', methods=['POST', 'GET'])
def webhook():

    if (request.method == 'POST'):
        data = request.json
        issue = data.get('issue')

        if issue:
            webhook_issues.append(issue)

        return 'Webhook received'
    elif (request.method == 'GET'):
        print(webhook_issues)
        response_html = ""
        for issue in webhook_issues:
            print(issue)
            response_html += f'{issue["title"]} - {issue["state"]}'
        return response_html

```

This defines the endpoint that handles both equests. When you run the app, the GitHub webhook sends requests to this endpoint, and it stores the incoming issues' payload through it, too. At the same time, the front end makes use of the  endpoint to fetch the stored issues.

For the GitHub webhook to send requests to your Flask app, you need to generate a remote URL for your app. You can do that through an HTTP tunneling service like [ngrok](https://ngrok.com/download). Run ngrok using the following command: `ngrok http 127.0.0.1:5000`

This command starts HTTP tunneling and creates a remote URL for you that looks something like this: `https://23fd-223-179-156-103.ngrok-free.app. You'll use this URL with the/webhook path to create a webhook for your repo.` ‍

Navigate to your repo's home page and click on **Settings**:

[![Navigating to settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d59b43638156884cc_aBe40yr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d59b43638156884cc_aBe40yr.webp)

On the **Settings** page, click on **Webhooks** under the **Code and automation** subsection on the left of the page:

[![Navigating to webhooks](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d2897a750781b1f77_fddeKSq.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d2897a750781b1f77_fddeKSq.webp)

Click on the **Add webhook** button at the top right of this page:

[![Adding a new webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d7cbf572b21fac000_YqWWzF2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d7cbf572b21fac000_YqWWzF2.webp)

In the new form that opens, enter the payload URL and configure other options:

[![New webhook form](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d7df1465081429bc2_Qlaw5Cf.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d7df1465081429bc2_Qlaw5Cf.webp)

After you've entered the payload URL (/webhook), set the content type as application/json, select **Let me select individual events** under **Which events would you like to trigger this webhook**, and check the box next to **Issues** under the events list:

[![Selecting issue events](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0db0ba49222595bb0a_Aj9HMiI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0db0ba49222595bb0a_Aj9HMiI.webp)

Make sure the **Active** checkbox is checked at the bottom and click on the **Add webhook** button:

[![Create the webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0de1143fbca334b8d7_GhzNBUE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0de1143fbca334b8d7_GhzNBUE.webp)

Once created, GitHub automatically sends a test request to your webhook URL to test it out:

[![Hook created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d59665d1f200cdedb_IETa6pN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0d59665d1f200cdedb_IETa6pN.webp)

If your app is running, you'll see a line of output in its logs similar to the following, indicating that the request was received:

`127.0.0.1 - - [31/Jan/2024 13:59:13] "GET /webhook HTTP/1.1" 200 -
127.0.0.1 - - [31/Jan/2024 13:59:14] "POST /webhook HTTP/1.1" 200 -  # This one
`

This means that you've set everything up correctly.

You can now try creating a new issue in your repo to see how it is automatically populated on the web page:

[![Issue received through webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0de5bd4a7fe0326e86_MoXefLt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65cb8a0de5bd4a7fe0326e86_MoXefLt.webp)

Note: You can find the code for the complete app built in this tutorial [in this repo](https://github.com/krharsh17/github-issues-api.git).

## Build to multiple ticketing applications through a single API with Merge

As you can tell, the process of implementing this integration is relatively complex and time intensive. This is only exacerbated when you expand this out to the other ticketing applications you'd like to integrate with.

To help you integrate with all the ticketing tools your clients and prospects use quickly and easily, you can build to [Merge's Ticketing Unified API](https://www.merge.dev/categories/ticketing-api).

You'll also be able to oversee and address clients' integration issues via [Merge's Integration Observability features](https://www.merge.dev/features/integration-observability) and lean on Merge's team of partner engineers for any integration maintenance-related work.

Learn more about how Merge can help you integrate with several ticketing tools by [scheduling a demo with one of Merge's integrations experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-all-issues-github-api-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Kumar Harsh

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fcfc8f1b-3292-4516-90e6-fd5e2059a736&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b756218d-84c8-45a6-b7a8-cd3376bbcaef&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-all-issues-github-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fcfc8f1b-3292-4516-90e6-fd5e2059a736&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b756218d-84c8-45a6-b7a8-cd3376bbcaef&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-all-issues-github-api-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=2c6ac86a-5cd0-4365-b9fc-f8246352bae1&bo=2&sid=9370c8303e8c11f0976771615dff11f0&vid=937115003e8c11f09edb03f59a1deed9&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20all%20issues%20with%20the%20GitHub%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-all-issues-github-api-python&r=&lt=1168&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=28726)