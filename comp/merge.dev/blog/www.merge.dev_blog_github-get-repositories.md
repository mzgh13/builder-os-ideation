---
url: "https://www.merge.dev/blog/github-get-repositories"
title: "How to GET repositories using the GitHub API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/github-get-repositories#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/github-get-repositories#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/github-get-repositories#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/github-get-repositories#prerequisites)

[Authenticating to the GitHub Repositories API](https://www.merge.dev/blog/github-get-repositories#authenticating-to-the-github-repositories-api)

[Generating a fine-grained personal access token](https://www.merge.dev/blog/github-get-repositories#generating-a-fine-grained-personal-access-token)

[Fetching repositories from the GitHub API in Python](https://www.merge.dev/blog/github-get-repositories#fetching-repositories-from-the-github-api-in-python)

[Final thoughts](https://www.merge.dev/blog/github-get-repositories#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgithub-get-repositories)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7241fab85507bb23f5_SharePoint_API_key.webp)**How to get all issues with the GitHub API in Python**](https://www.merge.dev/blog/get-all-issues-github-api-python)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cedd0411c78c3bc80c2_Create_Tickets_with_the_Zendesk_API_in_Python.webp)**Create Tickets with the Zendesk API in Python**](https://www.merge.dev/blog/create-tickets-with-the-zendesk-api-in-python)

# How to GET repositories using the GitHub API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7de0a9323838512e363_Autoprovisioning.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387dd3f0d4cd41792b7_62eff905d64065369cc3c90b_Paul_S..webp)

Paul Spangfort

Software Engineer

@Merge

GitHub allows you to find all kinds of resources and code on their platform, which includes the source code for entire websites, applications, servers, and games.

The source code on GitHub is most commonly stored in “repositories”. As a result, it can be useful to fetch and read information on specific GitHub repositories.

In this article, we’ll walk through how you can do just that. This includes how you can generate the credentials needed for making authenticated HTTP requests to GitHub’s Repositories API endpoint, and writing the code for retrieving the information using Python.

## **Prerequisites**

To follow along this guide you’ll need:

- A valid [GitHub account](https://github.com/login)
- Python version 3.10 or later
- The python requests library installed in your environment (like your laptop)

## **Authenticating to the GitHub Repositories API**

There are 3 options you can use to authenticate to the GitHub Repositories API endpoint:

### **1\. Fine-grained personal access tokens**

Fine-grained personal access tokens function similarly to bearer tokens, but they provide certain security advantages. More specifically, a fine-grained personal access token allows you to easily configure the resources it can access as well as revoke access if and when needed.

Note: We’ll be using this token for our walkthrough. You can learn more about generating a fine-grained personal access token in [GitHub’s docs](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token).

### **2\. Github user access token**

In GitHub, a user access token functions much like an OAuth token. Unlike a normal OAuth token however, GitHub’s user access tokens also have fine-grained permissions.

_Learn more about_ [_generating a user access token_](https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app) _._

### **3\. App installation access tokens**

If you want to authorize HTTP requests on behalf of a GitHub application, you can use an app installation access token.

This is useful for installing applications in your repositories that can, for example, help keep the versions of any installed packages up to date automatically.

_Learn more about_ [_authenticating as a GitHub App installation_](https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app-installation) _._

## **Generating a fine-grained personal access token**

There are many public repositories on GitHub that we can fetch high-level information on. However, if you want access to detailed information on a repository or information about a private repository, you’ll need to make sure you have some form of authentication that has permission to read that data.

You can do the latter by generating a fine-grained personal access token. Here’s how:

1. [Verify your GitHub account’s email address](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/verifying-your-email-address) (if it hasn't been verified yet).

2. In the upper-right corner of any page, click your profile photo, then click **Settings.**

[![Accessing Settings in your GitHub profile](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439ea3fbb07e572e6345_eBlt9ukxnDS80x8FJ8W4P7jT91fX1T7YO_RBInBHOsYl29lJasCJv83y72kaBpiwY6EFrNOvzlA92uRx3OsUV3sheQLnDevXltVFgso1wjVpn5dlxXtb40hK1sHd12DCMe1i8CnV7rhBdr4W1mQr6d0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439ea3fbb07e572e6345_eBlt9ukxnDS80x8FJ8W4P7jT91fX1T7YO_RBInBHOsYl29lJasCJv83y72kaBpiwY6EFrNOvzlA92uRx3OsUV3sheQLnDevXltVFgso1wjVpn5dlxXtb40hK1sHd12DCMe1i8CnV7rhBdr4W1mQr6d0.webp)

‍

3\. In the left sidebar, click **Developer settings.**

[![Accessing "Developer settings" in your GitHub profile](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439ed6f2485e1685c850_LGnqGbCbnM3U4tRGElrkepNewIwCvjeXAoZSNZiCHhNR8dcnJ99kuFGiGv9acj320hcwFsZFSBAB1_6enVVViObwUZh1j9KpMcQ_aOL2wORGL0zsZyDMpPZ79VkWUJOwUO1xvBSXzfM4Trim_ZMKVLE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439ed6f2485e1685c850_LGnqGbCbnM3U4tRGElrkepNewIwCvjeXAoZSNZiCHhNR8dcnJ99kuFGiGv9acj320hcwFsZFSBAB1_6enVVViObwUZh1j9KpMcQ_aOL2wORGL0zsZyDMpPZ79VkWUJOwUO1xvBSXzfM4Trim_ZMKVLE.webp)

4\. In the left sidebar, under **Personal access tokens**, click **Fine-grained tokens.**

**‍**

[![Accessing fine-grained tokens in your GitHub profile](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef462b1f364b468d245b60_Screenshot%202024-03-11%20at%201.57.40%E2%80%AFPM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef462b1f364b468d245b60_Screenshot%202024-03-11%20at%201.57.40%E2%80%AFPM.webp)

5\. Click **Generate new token.** 6\. Under **Token name**, enter a name for the token.

7\. Under **Expiration**, select an expiration for the token.

8\. (Optional) Under **Description**, add a note to describe the purpose of the token.

[![Adding a description to describe a token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e5eebe84a2e1c9d85_gbYBK9s2qGIZfNEiZGfhOISyBqiqfnfDFg2Y7WUcvhWgi98ojvXDwVk6mYKxIghzGpuBpItZUhXrd-AWuookjIbY7KW7S8113dNfejBNcemwxLeOlwvZS8-wob6c6xIapC5QLgIoQ8Iw7uQegtIrvXU.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e5eebe84a2e1c9d85_gbYBK9s2qGIZfNEiZGfhOISyBqiqfnfDFg2Y7WUcvhWgi98ojvXDwVk6mYKxIghzGpuBpItZUhXrd-AWuookjIbY7KW7S8113dNfejBNcemwxLeOlwvZS8-wob6c6xIapC5QLgIoQ8Iw7uQegtIrvXU.webp)

9\. Under **Resource owner**, select a resource owner. The token will only be able to access resources owned by the selected resource owner. Organizations that you are a member of will not appear unless the organization opted in to fine-grained personal access tokens. You can learn more aboutsetting a personal access token policy for your organization [here.](https://docs.github.com/en/organizations/managing-programmatic-access-to-your-organization/setting-a-personal-access-token-policy-for-your-organization)

10\. Under **Repository access**, select which repositories you want the token to access. You should choose the minimal repository access that meets your needs. Tokens always include read-only access to all public repositories on GitHub.

11\. If you selected **Only select repositories** in the previous step, under the **Select repositories** dropdown, select the repositories you want the token to access.

[![Selecting repositories in GitHub](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e4b9f0b4d5a67ea24_kBwPDEWG6G6rbF9UoInk13RGnwHuR7pK6erPTBlTpd16QMNHGnBiWpcG5dxMkiH5MpafuDqTHbR0k3t-HfIZX0OFv9yG07XoqfhAs7yX040sZsHLGL0v3sYaS1cwzfjLDh1pbxWYqAnGIGu1e7a4N3w.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e4b9f0b4d5a67ea24_kBwPDEWG6G6rbF9UoInk13RGnwHuR7pK6erPTBlTpd16QMNHGnBiWpcG5dxMkiH5MpafuDqTHbR0k3t-HfIZX0OFv9yG07XoqfhAs7yX040sZsHLGL0v3sYaS1cwzfjLDh1pbxWYqAnGIGu1e7a4N3w.webp)

12\. Under **Permissions**, select which permissions to grant the token. Depending on which resource owner and which repository access you specified, there are repository, organization, and account permissions. You should choose the minimal permissions necessary for your needs. In this example, I’ll be generating a token that has read-only access to the contents of my selected repository.

[![Selecting permissions ](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e41c0927ee421709e_PFv_8dN_ZD6Q46OAHUSH8ldwQop1mfWm2CHmPuTrm9x8ZI2MKFTYrlzouxWxtU9kV2MAGCtfh0T4qnJqzZOU2H981Wu7q7RYeJShBIU--eiac37LSz0QFzk-rS7o4r3wxcNp8wHjer-QYK9qdla4Raw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65ef439e41c0927ee421709e_PFv_8dN_ZD6Q46OAHUSH8ldwQop1mfWm2CHmPuTrm9x8ZI2MKFTYrlzouxWxtU9kV2MAGCtfh0T4qnJqzZOU2H981Wu7q7RYeJShBIU--eiac37LSz0QFzk-rS7o4r3wxcNp8wHjer-QYK9qdla4Raw.webp)

13\. Click **Generate token.**

Note that you must save the token after you generate it, as there will be no way to access it after it has been created and shown to you.

We are now ready to take our access token and make some authenticated requests!

**NOTE**: Not all GitHub endpoints can be accessed using fine-grained personal access tokens. Please refer to GitHub’s documentation about which [**Endpoints are available for fine-grained personal access tokens**](https://docs.github.com/en/rest/authentication/endpoints-available-for-fine-grained-personal-access-tokens?apiVersion=2022-11-28).

## **Fetching repositories from the GitHub API in Python**

Let’s go through two example requests we can make to GitHub’s repositories endpoint, one without authentication, and one using our new personal access token.

### **Making an unauthenticated request**

Many organizations on GitHub have a public list of repositories that we can fetch information about without authenticating our request.

In this example, let’s see what repositories the Netflix organization stores on GitHub.

First we’ll import the necessary requests package and construct the URL that we want to make a request to (see [GitHub’s list organization repositories documentation for more information](https://docs.github.com/en/rest/repos/repos?apiVersion=2022-11-28#list-organization-repositories)).

```python

import requests
# At the top we can construct the request we want to make
GITHUB_BASE_URL = 'https://api.github.com'
org_name = 'Netflix'
organization_repositories_url = f"{GITHUB_BASE_URL}/orgs/{org_name}/repos"

```

After that, we can use our requests library to make a GET request to the URL we constructed to fetch information about Netflix’s repositories.

```python

# Make the API request. Note the .get() function, which corresponds to the HTTP method of our request
response = requests.get(organization_repositories_url)

# If status_code is 200 we made a successful request!
if response.status_code == 200:
    repositories = response.json()
    # After this add code to do fun and useful things with the repository information!

# If status_code is not 200, something is wrong with our request
else:
    print(f"Failed to retrieve repositories. Status code: {response.status_code}")

```

### **Making an authenticated request**

This time, let’s make a request to the individual repository that we set our personal access token to have access to.

Similarly to before, we’ll first construct the URL that we want to make the request to, and this time we’ll also set up the headers for our request, which will contain our personal access token in the “Authorization” key.

```python

# At the top we can construct the request we want to make
GITHUB_BASE_URL = 'https://api.github.com'
user_name = 'pspangfort-merge'
repo_name = 'storybook-hackathon'

repository_url = f"{GITHUB_BASE_URL}/repos/{user_name}/{repo_name}"

personal_access_token = ""

headers = {
    'Authorization': f"Bearer {personal_access_token}" }

```

After this, we can pass in the headers to our request and make an authenticated request to the GitHub API.

```python

headers = { 'Authorization': f"Bearer {personal_access_token}" }
# Make the API request. Note the .get() function, which corresponds to the HTTP method of our request
response = requests.get(repository_url, headers=headers)

# If status_code is 200 we made a successful request!
if response.status_code == 200:
    repositories = response.json()
    # After this add code to do fun and useful things with the repository information!

# If status_code is not 200, something is wrong with our request
else:
    print(f"Failed to retrieve repositories. Status code: {response.status_code}")

```

We’ve now successfully made an authenticated request to the GitHub API and retrieved (hopefully) useful information.

## **Final thoughts**

The process of building to the GitHub API may seem manageable, but your clients likely want you to [provide product integrations](https://www.merge.dev/blog/product-integrations) with countless other tools.

To meet customer demand for integrations at scale and without straining your engineering resources, you can use Merge, the leading unified API solution.

Merge offers a single API that lets you provide hundreds of integrations to your product, whether that’s CRM, ticketing, accounting, and so on.

Merge also provides Integration Observability tooling to help your customer-facing employees manage your integrations and maintenance support on behalf of your engineers—all but ensuring that you can offer reliable and performant integrations.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgithub-get-repositories).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Paul Spangfort

Software Engineer

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=64c372da-df88-4099-8975-4ad36a46195c&bo=2&sid=d7c70a303e8d11f09657ede0b0eb3721&vid=d7c803503e8d11f09eaa4f4ac99f3fcb&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20repositories%20using%20the%20GitHub%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgithub-get-repositories&r=&lt=695&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=158961)