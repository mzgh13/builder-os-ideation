---
url: "https://www.merge.dev/blog/create-a-deal-in-pipedrive"
title: "How to create a deal in Pipedrive with a Unified API"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/create-a-deal-in-pipedrive#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/create-a-deal-in-pipedrive#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/create-a-deal-in-pipedrive#)

Table of contents

[Using Merge to Automate Tasks on Pipedrive](https://www.merge.dev/blog/create-a-deal-in-pipedrive#using-merge-to-automate-tasks-on-pipedrive)

[Creating a Deal in Pipedrive with Merge's Unified API](https://www.merge.dev/blog/create-a-deal-in-pipedrive#creating-a-deal-in-pipedrive-with-merges-unified-api)

[Conclusion](https://www.merge.dev/blog/create-a-deal-in-pipedrive#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-a-deal-in-pipedrive)

##### Just for you

No items found.

# How to create a deal in Pipedrive with a Unified API

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cadbbb5568970b2d91a_8.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Ndafara Tsamba

@Merge

Customer relationship management (CRM) systems help companies manage customer relationships, from leads through opportunities to sales and beyond. They typically include features for storing and tracking customer contact information, managing sales leads, tracking sales opportunities, and providing customer support.

A unified API like that of [Merge](https://merge.dev/) can help you integrate various CRM systems with each other and into your applications and workflows. For instance, as a software developer for a technology company, you might want the sales team in your organization to be able to create deals in a CRM like [Pipedrive](https://www.pipedrive.com/) as soon as they finish meetings with potential customers. You can use the Merge Unified API to create the deal so that you can automate the process and save time.

In this article, you will learn more about how Merge's unified API can help you automate tasks in CRMs, and you'll see how to use it to create a deal in Pipedrive.

## Using Merge to Automate Tasks on Pipedrive

Pipedrive is a popular cloud-based CRM software that provides a user-friendly and intuitive interface that enables sales teams to track leads, manage deals, and close sales efficiently.

If you want to automate any tasks on Pipedrive as part of an integration with other tools, you could use Pipedrive's API. However, it would involve some development effort and maintenance overhead since this will likely not be the only tool and API you work with. Different tools' APIs have varying data models, endpoints, and authentication mechanisms. Relying on individual APIs could make it challenging to manage data consistency and scalability across multiple platforms, resulting in more complex code and potential issues during updates or changes to the integration.

Merge's unified API addresses the challenges of integrating with multiple platforms by providing a single, standardized interface to access data and functionality from various APIs.

Merge allows you to streamline the integration process, reducing development effort and maintenance overhead as you no longer need to manage multiple APIs with varying data models and endpoints. In addition to a more efficient and robust integration process, Merge also simplifies updates and changes to the integration, saving you significant time and effort.

_Related:_ [_How to GET tasks from Pipedrive_](https://www.merge.dev/blog/fetch-tasks-pipedrive-using-python)

## Creating a Deal in Pipedrive with Merge's Unified API

Let's see how you can use Merge's unified API to create a deal in Pipedrive.

You will be using the Python CRM SDK, but the Merge SDK is also available in other languages such as Ruby, Java, and Node TypeScript.

### Prerequisites

To follow along, you will need the following:

- A [Pipedrive account](https://www.pipedrive.com/en/register)

[![Pipedrive sign-in](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79117322d9c42ab935_3rXRjXx.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79117322d9c42ab935_3rXRjXx.webp)

- A [Merge account](https://app.merge.dev/signup)
- A Python installation. Be sure to use [version 3.11](https://www.python.org/downloads/) or later.
- A virtual environment using [venv](https://www.python.org/downloads/). Run the command pip install virtualenv to install the virtual environment tool.

### Link Pipedrive with Merge

For Merge to interact with Pipedrive, you have to link your Pipedrive account with Merge.

Log in to your Merge account, select **Linked Accounts**, and click **Test Linked Accounts** since you don't want to use production for a tutorial.

If you're using Merge for the first time, you'll see that there are no linked accounts.

[![No linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a8931d53b2b0f860_l412HrV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a8931d53b2b0f860_l412HrV.webp)

Click on the **Launch Test Link** button.

[![Launch Test Link](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79bd8f55060f6fc83f_kJ6sROZ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79bd8f55060f6fc83f_kJ6sROZ.webp)

This will open the **Select Category** dialog. Choose **Customer Relationship Management**.

[![Customer Relationship Management](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a5c909b541974a30_MnTpbwp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a5c909b541974a30_MnTpbwp.webp)

In the **Select Integration** dialog, select Pipedrive.

[![Select Pipedrive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79200bb47ed908aa95_pB5ynPC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79200bb47ed908aa95_pB5ynPC.webp)

Merge will then start setting up the integration.

[![Setting up integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79474c7388467ae3ff_JeY8QlW.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79474c7388467ae3ff_JeY8QlW.webp)

You'll have to provide consent for Merge to read the data in your Pipedrive account. Click **Continue**.

[![Access request to Pipedrive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a5c909b541974a42_jtLWNbB.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79a5c909b541974a42_jtLWNbB.webp)

Next, you'll have to specify how you want to authenticate with Pipedrive. Keep the default choice of **I want to use my API Key or Access Token** to authenticate and click **Next**.

[![Authenticate with Pipedrive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ac48b7bda0a14e748_mzaQiG3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ac48b7bda0a14e748_mzaQiG3.webp)

Merge gives you detailed instructions on how to get the API Key from your Pipedrive account.

[![Get API key from Pipedrive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79474c7388467ae411_NWEaCDE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f79474c7388467ae411_NWEaCDE.webp)

Log in to your Pipedrive account and click on your account name in the top right corner and then on **Personal Preferences**.

[![Pipedrive Personal Preferences](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a5de5ffc5a496dcc9_f6OieYx.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a5de5ffc5a496dcc9_f6OieYx.webp)

In the **Personal Preferences** page, select the **API** tab and copy the API key provided.

[![API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc875_1MxwlNI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc875_1MxwlNI.webp)

Back in Merge, paste the API key you copied and click on **Submit**.

[![Submit API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a200bb47ed908aaa7_AldiFl2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a200bb47ed908aaa7_AldiFl2.webp)

Provide your Pipedrive subdomain and click on **Submit**.

[![Pipedrive subdomain](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a90d9986a1d5ecdde_IrQByQC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a90d9986a1d5ecdde_IrQByQC.webp)

Merge will continue to set up the integration.

[![Setting up integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc851_kVE7aUK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc851_kVE7aUK.webp)

You will get a confirmation message upon a successful setup.

[![Successful setup](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7aa5c909b541974a63_ERxIFED.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7aa5c909b541974a63_ERxIFED.webp)

When you click **Finish Setup**, you should see Pipedrive on your linked accounts.

[![Pipedrive linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc863_oX7hUGl.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7abd8f55060f6fc863_oX7hUGl.webp)

### Get Merge API Key and Account Token

To make calls to Merge using the SDK, you will need to get a test access key and account token.

To get the key, select **API Keys** in the left-hand pane of your Merge screen. Because you are using the testing environment, copy and keep the test key under **Test Access Keys**. You will use this later in your code.

[![Access keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ae2c18c9e6f91803f_fNdix7B.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ae2c18c9e6f91803f_fNdix7B.webp)

To get the account token, click **Linked Accounts** on the left-hand pane of your Merge screen. Click on the integration for which you want to get the account token—in this case, Pipedrive. You can find the account token towards the right of the screen. Copy and keep it too for your code.

[![Account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a200bb47ed908aab9_vpwGQz3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a200bb47ed908aab9_vpwGQz3.webp)

### Enable Read-Write Permissions on the Common Model

You will be using the common model provided by Merge, and the permissions here are set to **read** by default. Creating a deal is a write, though, so you have to enable the write permissions on the opportunity model.

On your Merge dashboard, click **Common Models** on the left and then **CRM**. Click on the **Opportunity** model, and then enable **Read+Write**.

[![Common models](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a9003987434051299_2o1sH7I.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7a9003987434051299_2o1sH7I.webp)

### Create an Opportunity in Pipedrive Using the Merge CRM SDK

You're now ready to create a deal—or an _opportunity_ as it's called in Pipedrive—using the Merge CRM SDK in Python.

Start by creating a new directory and name it CreateOpportunityInPipedrive.

In the directory, run the following command to create a virtual environment called creatingOpportunityInPipedrive: `python -m venv creatingOpportunityInPipedrive`

After creating the virtual environment, you need to activate it. If you are on Windows, run the following command: `creatingOpportunityInPipedrive\Scripts\activate`

If you are on Linux or Mac, run the following command: `source creatingOpportunityInPipedrive/bin/activate`

Once the virtual environment is activated, install the Merge CRM SDK by running the following command: `pip install --upgrade MergePythonClient`

The Merge Python library provides access to the Merge API from Python. This tutorial uses version 0.2.5+ of the Merge Python Client.

You will get the following output if the installation was successful:

```python

...output_ommitted...
Successfully installed MergePythonClient-0.2.5 anyio-4.0.0 certifi-2023.7.22 exceptiongroup-1.1.3 h11-0.14.0 httpcore-0.18.0 httpx-0.25.0 idna-3.4 pydantic-1.10.12 sniffio-1.3.0 typing-extensions-4.7.1

```

After installing the Merge Python Client, create a file called **opportunities.py** and paste the following code in it:

```python

import merge
from merge.client import Merge
from merge.resources.crm.types import OpportunityRequest

client = Merge(api_key="YOUR_API_TOKEN", account_token="YOUR_ACCOUNT_TOKEN")

new_opportunity = client.crm.opportunities.create(model=OpportunityRequest(
    name="Unified API Solution",
    description="Needs a Unified API for various Integrations!",
    amount=50000,
    integration_params={
        "key": None,
        },
    linked_account_params={
        "key": None,
    },
    )
)

print(new_opportunity)

```

This code creates an opportunity with name, description, and amount fields. You can also include [other fields](https://github.com/merge-api/merge-crm-python/blob/main/docs/Opportunity.md) such as last\_activity\_date, close\_date, and stage.

Don't forget to replace YOUR\_API\_TOKEN and YOUR\_ACCOUNT\_TOKEN with your actual values.

As you can see below, there are currently no opportunities in Pipedrive.

[![No current deals](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ac48b7bda0a14e75a_gItEMPC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7ac48b7bda0a14e75a_gItEMPC.webp)

Run the following command to execute the script: `python opportunities.py`

If everything executes well, a deal will be created in Pipedrive, and you will get the following output, which shows that there are no errors or warnings:

```python

model=Opportunity(name='Unified API Solution',
            description=None, amount=50000,
            owner='f2a9bde1-7e57-4420-b406-5defa210d69f',
            account=None,
            stage='1270534c-553c-4415-8032-46b3e6a7b646',
            status=,
            last_activity_at=None,
            close_date=None,
            remote_created_at=datetime.datetime(2023, 9, 11, 21, 32, 28, tzinfo=datetime.timezone.utc), remote_was_deleted=False,
            id='0585ce0e-a89a-4200-913c-472c90f480bb',
            remote_id='1',
            modified_at=datetime.datetime(2023, 9, 11, 21, 32, 28, 313978, tzinfo=datetime.timezone.utc), field_mappings=None,
            remote_data=None, remote_fields=None)
warnings=[]
errors=[]
logs=None

```

If you now go back to Pipedrive, you will see that there is now one deal with the title Unified API Solution and a value of 50,000 in the currency of your Pipedrive account.

[![Pipedrive deals](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7aa5c909b541974a81_qJGoxaM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65021f7aa5c909b541974a81_qJGoxaM.webp)

## Conclusion

In this article, you saw how you can use Merge's unified API to automate creating a deal in Pipedrive.

This isn't the only use case for Merge's unified API. It can also help you automate other CRM tasks and integrate your CRM systems with other applications in your organization. Its simplicity and flexibility help improve your efficiency to save time and costs.

Sign up for [free](https://app.merge.dev/signup) to explore Merge's full potential.

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=1c3965fb-a5c1-42a3-a798-29cae2d0bba0&bo=2&sid=2df4d3103e8d11f0b685a7dc312b5824&vid=2df569b03e8d11f08f999376cb5080d9&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20create%20a%20deal%20in%20Pipedrive%20with%20a%20Unified%20API&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-a-deal-in-pipedrive&r=&lt=479&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=583107)