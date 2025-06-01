---
url: "https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api"
title: "How to add users with the Okta SCIM API"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#prerequisites)

[Set Up an Okta Developer Account](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#set-up-an-okta-developer-account)

[Create Okta API Tokens](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#create-okta-api-tokens)

[Create Users with Okta's User API](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#create-users-with-oktas-user-api)

[Retrieve User Data with Okta's User API](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#retrieve-user-data-with-oktas-user-api)

[Conclusion](https://www.merge.dev/blog/how-to-add-users-with-the-okta-scim-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-add-users-with-the-okta-scim-api)

##### Just for you

No items found.

# How to add users with the Okta SCIM API

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb3b6c5002162a363ca_How_to_Add_Users_with_the_Okta_SCIM_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Furqan Butt

@Merge

Okta SCIM is a popular directory and system for cross-domain identity management (SCIM) software that provides extensive REST APIs for managing user operations like creating, reading, updating, and deleting users.

Integrating Okta with existing systems is a treat for developers because of its API-first architecture and its support for all popular languages, with [more than a dozen language-specific SDKs](https://developer.okta.com/code/#front-end).

This article illustrates how to integrate with the Okta API in Python. You'll learn how to set up a basic Okta integration by authenticating with the API and then creating and reading users in a Python application.

The source code for this tutorial can be found [in this GitHub repo](https://github.com/furqanshahid85-python/okta-create-get-user-api.git).

## Prerequisites

Since you'll be using Python to interact with the Okta API in this tutorial, make sure you have a [recent version of Python working on your device](https://www.python.org/downloads/).

## Set Up an Okta Developer Account

Before you can begin, you need to create an Okta developer account. It's free to use and allows you to explore Okta's features.

Head to the [developer sign-up page](https://developer.okta.com/signup/) to create your developer account. You can create a new account or use your Google or GitHub account to sign up.

[![Sign up to Okta Developer account](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540eac4130b64f36869d92_Ddqymr8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540eac4130b64f36869d92_Ddqymr8.webp)

## Create Okta API Tokens

To access the Okta User APIs to manage users in Python, you first need to create an API token that allows access to these REST endpoints.

Sign in to your Okta Developer account. In the **Okta Admin Console**, expand the **Security** tab on the left and click on **API**.

[![1. Creating API token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed84130b6b11886e1a0_hI2skhd.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed84130b6b11886e1a0_hI2skhd.webp)

Click on the **Tokens** tab and then on **Create token**. Provide a suitable token name.

[![2. Creating API token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed8193f2e765f468d87_RBpS2uC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed8193f2e765f468d87_RBpS2uC.webp)

Your API token is now created. Copy the token value and save it in a file or environment variable on your system since you'll need this value to access the APIs.

[![3. Creating API token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed8c7aa0b447360715f_MkF7oQe.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540ed8c7aa0b447360715f_MkF7oQe.webp)

## Create Users with Okta's User API

Okta's User API provides different user-related operations for creating, getting, listing, and updating users that you can use to manage your organization's users.

When it comes to creating users, the User API allows you to use different operations to create users with different sets of attributes. The [options available](https://developer.okta.com/docs/reference/api/users/#create-user) are as follows:

- Create User without Credentials
- Create User with Recovery Question
- Create User with Password
- Create User with Imported Hashed Password
- Create User with Password Import Inline Hook
- Create User with Password & Recovery Question
- Create User with Authentication Provider
- Create User in Group
- Create User with Non-Default User Type

You can read more about how to make requests to each of them in the [Okta documentation](https://developer.okta.com/docs/reference/api/users/#create-user).

To create a user, first open your favorite text editor and create a Python file. Name it **create\_users.py**.

Install the requests module in Python, which you'll use to make HTTP requests:

```python
pip install requests

```

Create two variables, `api_token` and `domain`, which are required when making requests to Okta APIs. Assign the token value you saved earlier to the `api_token variable`. Copy the domain value from the Okta developer account's admin console and assign it to the domain variable:

[![Okta domain](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540f113ac794c66324afdd_IBbN7qx.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64540f113ac794c66324afdd_IBbN7qx.webp)

Here's the code for the above:

```python
import  requests
import  json

api_token = "00srPC-9frt19RvBcClkZv9WFN45Ma3fWNbffmA0aE"
domain = "dev-38008485.okta.com"

```

Now that you have the API token and domain values, you can make requests to the Okta User API to create users.

After creating the required API token and domain variables, it's time to create the headers object. The headers object below specifies some custom headers that are needed to be passed for making the POST request to create a user. The `authorization SSWS token` header is mandatory because Okta API uses it to authenticate an incoming request:

```python
headers = {
	"Accept": "application/json",
	"Content-Type": "application/json",
	"Authorization": f"SSWS {api_token}"
}

```

Next, you need to create the body object that is passed in the POST request. The body object below specifies different profile attributes for the user you'll create. The credentials object is used to specify the password for the newly created user. The `activate=true` query parameter specifies that the newly created user is also marked as active:

```python
body = {
	"profile": {
		"firstName": "alex",
		"lastName": "jones",
		"email": "alex.jones@example.com",
		"login": "alex.jones@example.com",
		"mobilePhone": "888-777-1234"
	},
	"credentials": {
		"password": {"value": "Str0ngp@s$word"}
		}
}

```

The code block below has you making a POST request to `/users` to create a new user. It uses the domain variable specified earlier, and the headers and body objects are passed with the request:

```python
url = f"https://{domain}/api/v1/users?activate=true"
response = requests.post(url=url, headers=headers, data=json.dumps(body))
print(response.status_code)
print(response.content)

```

The entire code is as follows:

```python
import  requests
import  json

api_token = "00srPC-9frt19RvBcClkZv9WFN45Ma3fWNbffmA0aE"
domain = "dev-38008485.okta.com"
headers = {
	"Accept": "application/json",
	"Content-Type": "application/json",
	"Authorization": f"SSWS {api_token}"
}
body = {
	"profile": {
		"firstName": "alex",
		"lastName": "jones",
		"email": "alex.jones@example.com",
		"login": "alex.jones@example.com",
		"mobilePhone": "888-777-1234"
	},
	"credentials": {
		"password": {"value": "Str0ngp@s$word"}
		}
}
url = f"https://{domain}/api/v1/users?activate=true"
response = requests.post(url=url, headers=headers, data=json.dumps(body))
print(response.status_code)
print(response.content)

```

Execute the code by running the following command in your terminal:

```python
python create_users.py

```

On successfully executing the code, you'll get the following output:

[![Request response](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645410823f331fbad1e45bb4_qpj9h0U.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645410823f331fbad1e45bb4_qpj9h0U.webp)

You can verify whether the user has been successfully created in the **Okta Admin Console** by going to **Directory** \> **People**:

[![New user success](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64541082ac78476a17ec35e0_3oxl5dZ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64541082ac78476a17ec35e0_3oxl5dZ.webp)

## Retrieve User Data with Okta's User API

You can also use the Okta User API to get a user's data. You can get a list of all the users or retrieve a single user. The [Get User](https://developer.okta.com/docs/reference/api/users/#get-user) resource provides a list of operations to retrieve a single user's data with any of the following resources:

- Get Current User
- Get a User with an ID
- Get User with Login
- Get User with Login Shortname

You can read more about these [in the Okta documentation](https://developer.okta.com/docs/reference/api/users/#get-user).

As you did before, create a Python file and call it **get\_user.py**.

You'll again need to use the api\_token and domain variables that you created previously.

The following code block shows how to get a user's data using the user login:

```python
import  requests
import  json

api_token = "00srPC-9frt19RvBcClkZv9WFN45Ma3fWNbffmA0aE"
domain = "dev-38008485.okta.com"
headers = {
	"Accept": "application/json",
	"Content-Type": "application/json",
	"Authorization": f"SSWS {api_token}"
}

url = f"https://{domain}/api/v1/users/alex.jones@example.com"
response = requests.get(url=url, headers=headers)
print(response.status_code)
print(response.content)

```

In the code above, /user/login returns the user data for the given login query parameter. Unlike the POST request, there is no body parameter to be passed for making a GET request.

Run the following command to execute the code:

```python
python get_user.py

```

Once the code is successfully executed, you should get the following response object:

```python
{
"id": "00u7rd1gibWfx9Oym5d7",
"status": "ACTIVE",
"created": "2022-12-26T14:50:55.000Z",
"activated": "2022-12-26T14:50:55.000Z",
"statusChanged": "2022-12-26T14:50:55.000Z",
"lastLogin": null,
"lastUpdated": "2022-12-26T14:50:55.000Z",
"passwordChanged": "2022-12-26T14:50:55.000Z",
"type": {
"id": "oty7cgjnwghNn2vMu5d7"
},
"profile": {
"firstName": "alex",
"lastName": "jones",
"mobilePhone": "888-777-1234",
"secondEmail": null,
"login": "alex.jones@example.com",
"email": "alex.jones@example.com"
},
"credentials": {
"password": {},
"emails": [\
{\
"value": "alex.jones@example.com",\
"status": "VERIFIED",\
"type": "PRIMARY"\
}\
],
"provider": {
"type": "OKTA",
"name": "OKTA"
}
},
"_links": {
"suspend": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/lifecycle/suspend",
"method": "POST"
},
"schema": {
"href": "https://dev-38008485.okta.com/api/v1/meta/schemas/user/osc7cgjnwghNn2vMu5d7"
},
"resetPassword": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/lifecycle/reset_password",
"method": "POST"
},
"forgotPassword": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/credentials/forgot_password",
"method": "POST"
},
"expirePassword": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/lifecycle/expire_password",
"method": "POST"
},
"changeRecoveryQuestion": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/credentials/change_recovery_question",
"method": "POST"
},
"self": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7"
},
"resetFactors": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/lifecycle/reset_factors",
"method": "POST"
},
"type": {
"href": "https://dev-38008485.okta.com/api/v1/meta/types/user/oty7cgjnwghNn2vMu5d7"
},
"changePassword": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/credentials/change_password",
"method": "POST"
},
"deactivate": {
"href": "https://dev-38008485.okta.com/api/v1/users/00u7rd1gibWfx9Oym5d7/lifecycle/deactivate",
"method": "POST"
}
}
}

```

Similarly to using the Get User operation to retrieve a single user's data, you can use the `"https://{domain}/api/v1/users"` endpoint of the Okta User API to retrieve all users. The list user endpoint searches for users with user properties specified in the search query parameter.

You can read more about filtering users with search parameters [in the Okta documentation](https://developer.okta.com/docs/reference/api/users/#list-users).

## Conclusion

In this article, you learned how to access Okta APIs via API tokens to create new users and get user details in Python.

Okta's User API lets you create users with different user attributes and security credentials like passwords or security questions. It also makes it easy to get user details for either a single user or a list of users.

Even though Okta makes integration relatively easy for developers, creating custom integrations can become cumbersome when you're working with several applications. [Merge's](https://merge.dev/) single Unified API lets you integrate with over sixty HR, accounting, and identity platforms, including Okta, and access data from them over a single API. It lets you focus on building your core product instead of having to develop custom integrations for third-party platforms, saving you effort, time, and money.

Learn more about Merge's Unified API from the [official documentation](https://docs.merge.dev/hris/overview) or sign up for a [free account](https://app.merge.dev/signup).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Furqan Butt

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=86f2dc8e-c17e-4a75-b134-38591bb65e2b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=9e591e90-4348-49fa-b8b8-14496d2e2798&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-users-with-the-okta-scim-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=86f2dc8e-c17e-4a75-b134-38591bb65e2b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=9e591e90-4348-49fa-b8b8-14496d2e2798&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-users-with-the-okta-scim-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=cb030222-b2cf-4548-a196-4c4822b4bce6&bo=2&sid=3783be803e8e11f0a2b44525c0133578&vid=3783fe203e8e11f08af557d8ada4fc41&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20add%20users%20with%20the%20Okta%20SCIM%20API&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-users-with-the-okta-scim-api&r=&lt=448&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=189791)