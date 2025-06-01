---
url: "https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python"
title: "How to Make a GET Request for All Commits from the GitLab API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python#)

Table of contents

[Getting Commits from the GitLab API in Python](https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python#getting-commits-from-the-gitlab-api-in-python)

[Conclusion](https://www.merge.dev/blog/how-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python)

##### Just for you

No items found.

# How to Make a GET Request for All Commits from the GitLab API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cece8bfa24cca7942da_How_to_Retrieve_All_Commits_Using_the_GitLab_API_in_Python.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Marshall Chikari

@Merge

GitLab is a popular ticketing and developer tool system that lets you create and label issues and set assignees. It lets you collaborate, discuss, and plan, and it provides a better way of tracking work among teams.

In this tutorial, you'll learn how to set up a basic GitLab issues integration by authenticating with the GitLab API and pulling and getting all commits from the [commits API](https://docs.gitlab.com/ee/api/commits.html) using Python. You might use such a list of commits for maintaining an audit trail of changes or compiling a list of changes for release notes by looking at the comments from the commits.

You can find the complete code of this tutorial [here](https://gitlab.com/gitnyasha/gitlab-python).

## Getting Commits from the GitLab API in Python

GitLab's paid version provides out-of-the-box reports that lets you export a list of merge commits in the group to CSV. However, even if you're using the free version, you can get a list of all commits using the GitLab API, which is what you'll learn in this article.

The sections below will show you how to create a repository on GitLab, set up a Python project, generate a personal access token, and commit changes from your Python project when you make HTTP calls on the API. You'll export the results to a CSV file for easy reading.

If you do not have a GitLab account yet, [sign up for one](https://gitlab.com/) first.

### Create a Repository

To start, create a repository in your GitLab account. Once you're logged in, click the **New project** button:

[![GitLab page showing new project button](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb787ff1c6b61455c950_YL3ZW3h.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb787ff1c6b61455c950_YL3ZW3h.webp)

### Set Up a Python Code Project

Create a blank project and name it `gitlab-python`, for example. Leave all options as they are and click **Create project**. Because you want to push changes from your Python program to this repository, click **Clone** to download the repository to your machine.

If you open the project with VS Code, your workspace should look like below:

[![VS Code workspace](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb7884e82a29a8b51cd7_8Ryq0Ef.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb7884e82a29a8b51cd7_8Ryq0Ef.webp)

Next, set up a Python project. For this tutorial, you will simply create a Python file that makes an HTTP GET request to the GitLab API when you run it from the terminal. Create a file inside the workspace or inside the folder of your project that you cloned from GitLab. Name it `main.py`.

### Commit Changes to the Repository

To stage the file you created, run `git add main.py`. Next, run `git commit -m "created the python file"` to commit your changes.

Lastly, push the changes from your local repository to a remote one on GitLab by running `git push -uf origin main`. If it asks for a username and password, enter your GitLab username and password.

If you've performed this step successfully, you should see the Python file on your GitLab repository when you refresh the page, as in the image below:

[![Python file pushed to GitLab](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb97e87f680fa24fa6dc_e4fbqnV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb97e87f680fa24fa6dc_e4fbqnV.webp)

### Handle Authentication and Generate a GitLab Access Token

GitLab provides various ways to authenticate with the GitLab API: OAuth2 tokens, project access tokens, group access tokens, session cookie, GitLab CI/CD job tokens (specific endpoints only), and personal access tokens.

In this tutorial, you'll use personal access tokens, but you can find out more about the other options in the [GitLab documentation](https://docs.gitlab.com/ee/api/#authentication).

To generate a personal access token, select your avatar in the top-right corner of the GitLab page, select **Edit Profile**, and select **Access Tokens** on the left sidebar. You should see a page like the one below:

[![GitLab user settings page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb98cc77fe108e4e8043_mTyFCgV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bb98cc77fe108e4e8043_mTyFCgV.webp)

Enter a token name and [an optional expiry date](https://stackoverflow.com/questions/7030694/why-do-access-tokens-expire/7035926#7035926).

Next, select the desired scopes. In this case, choose **read\_api** as you only want to get commits from GitLab.

After that, click **Create personal access token**, which will generate your token. You should see a page like below with the message "Your new personal access token has been created":

[![Generated GitLab access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bbc05a83a462fde39924_ZP8wZ5g.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bbc05a83a462fde39924_ZP8wZ5g.webp)

Copy the generated token and store it somewhere safe. You'll use it later to authenticate with the API.

### Make HTTP Calls to Get Commits from GitLab

Since you will use your access token to authenticate with the API, you don't want to expose it to the public. Create two files: an `.env` to store your access key and a `.gitignore`, which will reference files that will not be pushed to GitLab.

In the `.env` file, add a single `ACCESS_TOKEN=your_personal_access_token_from_gitlab` and save. In your `.gitignore` file, add `.env` and save.

Next, inside your `main.py` file, import the following dependencies:

```“python” language-none
import http.client
import csv
import json
from os import environ
from dotenv import load_dotenv

load_dotenv()

```

The first dependency will be used to make the request on the API, the second dependency is for converting the results into CSV format, the third is to convert the results into JSON first before converting to CSV, and the last ones are for getting the access token from the `.env` file.

Before adding code to actually make an HTTP request, first install the module `dotenv` on your machine using the `pip install python-dotenv` command in your terminal. Add the code below to your `main.py` file:

```“python” language-none
def get_data():
    conn = http.client.HTTPSConnection("gitlab.com")

    headersList = {
        "PRIVATE-TOKEN": environ.get('ACCESS_TOKEN')
    }

    payload = ""

    conn.request("GET", "/api/v4/projects/[your project id]/repository/commits",
                 payload, headersList)
    response = conn.getresponse()
    result = response.read()

    return json.loads(result.decode("utf-8"))

```

The code above makes an authenticated HTTP request to the GitLab API by including the header `PRIVATE-TOKEN`, which is the access token from the `.env` file. The results are returned in JSON format. You can find your project id in the project repository under the project name, copy it, and replace \[your project id\] with your actual project id like in the image below:

[![Image showing GitLab project ID](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bc70912257470dd93547_ZobxT2h.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bc70912257470dd93547_ZobxT2h.webp)

Now commit the changes you've made by running the following commands in your terminal:

```“python” language-none
git add .
git commit -m "make http request to gitlab api"
git push origin main

```

To convert the results you got from the `get_data()` method, create another method called `generate_csv()` and add the following code:

```“python” language-none
def generate_csv(data):
    with open('gitlab-python.csv', 'w', newline='') as csvfile:
        fieldnames = ['id', 'short_id', 'created_at', 'parent_ids', 'title', 'message', 'author_name', 'author_email',\
                      'authored_date', 'committer_name', 'committer_email', 'committed_date', 'trailers', 'web_url']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
        writer.writeheader()
        for i in data:
            writer.writerow(i)

```

The method above takes data, creates a file in the project named `gitlab-python.csv` if it's not already there, and populates the CSV file with the data from the request. The fieldnames variable contains the headings of the data, which you will get from the API results.

Next, push changes to the remote repository by running the Git commands as you have done before. The complete code for making a request to the GitLab API to get all the commits is shown below:

```“python” language-none
import http.client
import csv
import json
from os import environ
from dotenv import load_dotenv

load_dotenv()

def get_data():
    conn = http.client.HTTPSConnection("gitlab.com")

    headersList = {
        "PRIVATE-TOKEN": environ.get('ACCESS_TOKEN')
    }

    payload = ""

    conn.request("GET", "/api/v4/projects//repository/commits",
                 payload, headersList)
    response = conn.getresponse()
    result = response.read()

    return json.loads(result.decode("utf-8"))

def generate_csv(data):
    with open('gitlab-python.csv', 'w', newline='') as csvfile:
        fieldnames = ['id', 'short_id', 'created_at', 'parent_ids', 'title', 'message', 'author_name', 'author_email',\
                      'authored_date', 'committer_name', 'committer_email', 'committed_date', 'trailers', 'web_url']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
        writer.writeheader()
        for i in data:
            writer.writerow(i)

generate_csv(get_data())

```

Run the Python script in your terminal using the python `main.py` command. Notice that a file is generated inside the project folder named `gitlab-python.csv`. Open it to see whether the request was successful. You should see the history of the commits you made earlier, as shown below:

[![VS Code workspace of a Python project](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bcffb1f04c04b7261016_BTBL84v.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63f7bcffb1f04c04b7261016_BTBL84v.webp)

## Conclusion

In this tutorial, you learned how to get a list of commits from the GitLab API using Python. You can find the complete code of this tutorial [here](https://gitlab.com/gitnyasha/gitlab-python).

If you need to integrate with multiple APIs, consider [Merge's unified API](https://merge.dev/). It lets you integrate to tools like [GitLab](https://merge.dev/integrations/gitlab) and hundreds of other [ticketing](https://merge.dev/categories/ticketing-api), [HR](https://merge.dev/categories/hr-payroll-api), [recruiting](https://merge.dev/categories/ats-recruiting-api), and [accounting](https://merge.dev/categories/accounting-api) platforms.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Marshall Chikari

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=f38a0e49-1dc7-4945-9ccb-cbcd4765c152&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=eb764191-7436-4b29-b7d1-d90fb78132e4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=f38a0e49-1dc7-4945-9ccb-cbcd4765c152&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=eb764191-7436-4b29-b7d1-d90fb78132e4&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=2fae440b-723e-4f3f-bbc7-2a13c79c5863&bo=2&sid=2b3a02903e8c11f091237f011d1c0976&vid=2b3a8a703e8c11f0b4ecf7ab7bba3c2c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20Make%20a%20GET%20Request%20for%20All%20Commits%20from%20the%20GitLab%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-make-a-get-request-for-all-commits-from-the-gitlab-api-in-python&r=&lt=2220&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=41754)