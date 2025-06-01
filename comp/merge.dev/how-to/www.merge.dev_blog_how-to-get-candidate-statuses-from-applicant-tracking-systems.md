---
url: "https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems"
title: "How to get candidate statuses from applicant tracking systems"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#)

Table of contents

[What Is Merge?](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#what-is-merge)

[How to Integrate Data from Multiple ATS Platforms with Merge](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#how-to-integrate-data-from-multiple-ats-platforms-with-merge)

[Conclusion](https://www.merge.dev/blog/how-to-get-candidate-statuses-from-applicant-tracking-systems#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-candidate-statuses-from-applicant-tracking-systems)

##### Just for you

No items found.

# How to get candidate statuses from applicant tracking systems

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb12a8b75b1b6143393_Marketing_Automation_-_How_to_GET_Lists_with_the_Klaviyo_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Sooter Saalu

@Merge

Applicant tracking systems (ATSs), also known as recruiting systems, help increase efficiency, reduce your administrative burden, enhance candidates' experiences, improve compliance with hiring rules, and build a talent pipeline for future hiring needs.

However, you can only realize these benefits if your ATS has access to the relevant data for the entire hiring workflow.

This can prove challenging, as organizations often use different systems and data storages for some categories of data, creating [data silos](https://www.techtarget.com/searchdatamanagement/definition/data-silo). For example, you may have candidates who have applied through different platforms, each with its own candidate status classification. Tracking the progress of these candidates across your hiring process and optimizing your recruitment strategy would be convoluted and challenging without unifying the information.

In this tutorial, you'll see how you can get candidates and the relevant fields to update their candidate status from three popular ATSs— [Workable](https://workable.com/), [BambooHR](https://bamboohr.com/), and [ApplicantStack](https://www.applicantstack.com/)— by using [Merge](https://merge.dev/).

_Note:_ this article uses three ATSs because they offer free trial accounts. Merge also offers integrations to [more than thirty other recruiting systems](https://merge.dev/categories/ats-recruiting-api), including [Greenhouse](https://www.merge.dev/integrations/greenhouse), [Lever](http://merge.dev/integrations/lever), and more. You can adapt the steps in this tutorial to the ATSs you work with.

## What Is Merge?

Before we get into the tutorial, let's consider what Merge is and how it can help you unify your applicant data.

Using Merge, you can build to a single API (Merge) and gain access to hundreds of integrations that span across ATSs, HRISs, CRMs, file storage solutions, and more.

To simplify the development and management of your unified solution, Merge provides an intuitive user interface, comprehensive dashboard, and [multiple SDKs](https://docs.merge.dev/sdk/) in various programming languages, such as Python, Ruby, and Java.

Its single, central API link and programming interface lets you link your third-party accounts and access, query, and update your data, eliminating the need for separate API calls. Merge intelligently integrates your data sources to ensure that data is synced harmoniously, and it uses common data models that have been standardized across platforms.

By providing centralized data access to all associated data sources, accompanied by standardized data models and customizable synchronization, Merge enables you to merge data from multiple ATS platforms, resulting in easier reporting, streamlined maintenance, and reduced complexity and effort. It also helps you eliminate data silos, enhance data integrity, and embrace a unified approach to promote efficient, data-driven decision-making.

## How to Integrate Data from Multiple ATS Platforms with Merge

Let's explore how you can use Merge to integrate with multiple ATS platforms.

In the sections that follow, you’ll first link accounts for three popular ATS platforms to Merge—Workable, ApplicantStack, and BambooHR—and authenticate them using API tokens. You’ll then query the Merge Unified API using its [Python client](https://github.com/merge-api/merge-python-client) to retrieve candidate status information.

Remember that you can use the same steps below to integrate with [any of the other ATS platforms](https://merge.dev/categories/ats-recruiting-api) available via Merge.

### Prerequisites

To follow along with this tutorial, you will need the following:

- Trial accounts for [Workable](https://www.workable.com/free-trial), [BambooHR](https://www.bamboohr.com/signup/), [ApplicantStack](https://www.applicantstack.com/start-free-trial/), and of course, [Merge](https://app.merge.dev/signup)
- [Python](https://wiki.python.org/moin/BeginnersGuide/Download) installed to work with the [Merge Python client](https://github.com/merge-api/merge-python-client)
- A [virtual environment](https://docs.python.org/3/library/venv.html) created and configured to execute all the commands in this tutorial

### Link ATS Accounts to Merge

This section is adapted from [Merge's well-documented process](https://docs.merge.dev/get-started/linked-account/) for integrations that takes into account the unique features of each platform.

From your [Merge Dashboard](https://app.merge.dev/login), click on **Linked Accounts** on the left panel under **Overview**.

[![Linked Accounts on Merge home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661648ecf1f7ad62dbd58_TIr0GXK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661648ecf1f7ad62dbd58_TIr0GXK.webp)

On the **Linked Accounts** page, you’ll see **Production Linked Accounts** and **Test Linked Accounts**. Test accounts let you explore Merge's features and the linking process, so you'll be using it for this tutorial.

Click on **Test Linked Accounts**, then **Launch Test Link** to start up Merge's simple wizard for linking accounts and integrating platforms. You’ll first see the various categories offered on Merge, from **Human Resource Information System** to **File Storage**.

[![Available integrations on Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164755b87ff22a49732_cl7ptKa.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164755b87ff22a49732_cl7ptKa.webp)

Select **Applicant Tracking System** to see all the available integrations under this category.

The process that follows is similar for all platforms, but let's start with Workable. Scroll down and click on the Workable icon. You will be given a breakdown of the types of data Merge will be able to access from your Workable account.

[![Workable authorization request](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164d7e1caa1d5ba8a12_kUQVUc1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164d7e1caa1d5ba8a12_kUQVUc1.webp)

Click **Continue**. You will be offered two methods for authenticating your account with Workable. The recommended method is to use an access token, which offers an additional layer of security and guarantees a more secure and streamlined authentication process. Alternatively, you can choose to authenticate through the Workable website's login process.

For the access token option, you will need to enter your Workable subdomain. For example, if your domain is touchstone.workable.com, your subdomain will be touchstone.

After that, you will be given detailed instructions on how to generate an access token on your Workable account.

[![Workable access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66165dcce6f0a168f4152_nA1R48O.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66165dcce6f0a168f4152_nA1R48O.webp)

Complete the steps, copy your access token into the space provided, and continue with the Merge wizard.

The last step in the wizard gives you the chance to set data permissions and tweak your integration to Merge to your organization's data management policies and preferences.

For the purpose of this tutorial, go ahead and click **Finish**. Your [Workable integration](https://www.merge.dev/integrations/workable) will now be set up.

[![Workable last step](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661642a51793f6b044f79_QIeY0jZ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661642a51793f6b044f79_QIeY0jZ.webp)

Because the process for integrating into a platform from Merge is standardized, the steps are very similar for other platforms. You can therefore repeat the steps above for BambooHR and ApplicantStack to end up with three test accounts.

[![Test accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164370c8c8743ff4c72_YbJbvaC.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d66164370c8c8743ff4c72_YbJbvaC.webp)

### How to Get Data Using Merge

Now that you have successfully integrated your ATS platforms with Merge, you'll pull data from the integrations using the [Merge Python client](https://github.com/merge-api/merge-python-client), which allows you to generate standardized data from the Merge API.

To begin, go into your virtual environment and execute the following command to install the Merge client in your Python virtual environment.

```python
pip install --upgrade MergePythonClient
```

‍ _Note:_ This tutorial was written based on version 0.2.1 of the Merge Python Client. You can use the following command to check the version you have installed:

```python
pip show MergePythonClient
```

Next, generate an API key on Merge, which will be used to authenticate requests for your Merge account.

[![Merge test API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661642a51793f6b044f89_M923znG.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661642a51793f6b044f89_M923znG.webp)

Lastly, you need tokens from your test accounts. You can get these by clicking on the test account and copying the token on the right.

[![Test account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661645b81aadb9ddaab30_StktnqS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d661645b81aadb9ddaab30_StktnqS.webp)

You can use the Merge Python client to generate data on the candidates from your ATS platforms. Merge will format the data to output information about the candidates (name, last interaction, email address) and their application (job they are applying for, current stage).

Create a new Python file and copy the following code into the file:

````python

```python

## Importing python packages

import merge
from merge.client import Merge
from pprint import pprint

## Add in your Merge API-Key and account token
merge_client = Merge(
    api_key="{Merge-API-Key}",
    account_token="{Test-Account-Token}")

try:
    # the 'candidates' resource offers several functions and parameters
    # See [client.py](https://github.com/merge-api/merge-python-client/blob/main/src/merge/resources/ats/resources/candidates/client.py) for a list of all supported configuration parameters.
    api_response = merge_client.ats.candidates.list()
    pprint(api_response)
except Exception as e:
    print("Exception when calling CandidatesApi->candidates_list: %s\n" % e)

```

````

This code generates a list of your candidates and the information surrounding their application.

Before executing the Python file, be sure to replace {Merge-API-Key} with your actual Merge API key and {Test-Account-Token} with the token of your test account obtained previously.

Save the file and execute it on your Python virtual environment to get similar results:

```python
PaginatedCandidateList(next=None, previous=None, results=[Candidate(id='ca34777c-c819-4c87-91f1-57a1e48544d1', remote_id='a446sgwjuu0j', first_name='Michael', last_name='Turner', company=None, title=None, remote_created_at='2023-06-07T17:26:00Z', remote_updated_at=None, last_interaction_at=None, is_private=None, can_email=None, locations=['Atlanta'], phone_numbers=[PhoneNumber(value='924-555-7845', phone_number_type=None, modified_at='2023-06-07T16:32:45.337198Z')], email_addresses=[EmailAddress(value='michael.turner@applicantstack.com', email_address_type=None, modified_at='2023-06-07T16:32:45.216174Z')],……\
```\
\
To benefit from the full range of features from your unified data, you can also use the Merge client to connect Merge to the backend of your solution.\
\
## Conclusion\
\
Unifying your data from multiple ATS platforms with Merge allows you to overcome the challenges of scattered data and get the full benefits of these systems.\
\
In this article, you learned how you can use Merge to unify data from multiple ATS platforms—namely Workable, BambooHR, and ApplicantStack—to streamline reporting, simplify maintenance, and reduce the complexity of your solution.\
\
Merge provides a comprehensive unified API platform that empowers you to access, query, and update data from various third-party data sources across HRISs, ATSs, ticketing systems, CRMs, file storage categories, and more. In addition, Merge can consolidate your data into [common models](https://merge.dev/features/common-models), allowing you to have standardized fields across platforms and gain a holistic view of your data.\
\
To get started with Merge, you can [sign up for a free account](https://app.merge.dev/signup) and/or schedule a [demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-candidate-statuses-from-applicant-tracking-systems).\
\
“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”\
\
![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)\
\
Name\
\
Position\
\
Position\
\
![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)\
\
Sooter Saalu\
\
@Merge\
\
## Read more\
\
[Software scalability: design, strategies and best practices](https://www.merge.dev/blog/software-scalability)\
\
![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)\
\
### Software scalability: design, strategies and best practices\
\
Insights\
\
[How to integrate with the SharePoint API via Python](https://www.merge.dev/blog/sharepoint-api-python)\
\
![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)\
\
### How to integrate with the SharePoint API via Python\
\
Engineering\
\
[How to build integrations for AI agents](https://www.merge.dev/blog/ai-agent-integrations)\
\
![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)\
\
### How to build integrations for AI agents\
\
AI\
\
## Subscribe to the Merge Blog\
\
Get stories from Merge straight to your inbox\
\
[Subscribe](https://www.merge.dev/get-in-touch?utm_btn=dr-page-root)\
\
![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67a0696c88fcb6b1a1d8ad6f_CTA%20Background%20Logo.svg)\
\
![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)\
\
### Get our best content every week\
\
Our weekly newsletter provides the best practices you need to build high performing product integrations.\
\
Your email\
\
Thank you! Your submission has been received!\
\
Oops! Something went wrong while submitting the form.\
\
But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_\
\
But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_\
\
But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_\
\
But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_\
\
Qualified\
\
## Looking to add integrations to your product?\
\
Simply and securely add 100s of customer-facing integrations with one API\
\
Get a demoChat with an expertDownload product integrations eBook\
\
![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d538c74f-ea27-4743-80a3-7d348db0aaa6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=785a3b66-dd04-4279-a28f-d73a5782149e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-candidate-statuses-from-applicant-tracking-systems&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d538c74f-ea27-4743-80a3-7d348db0aaa6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=785a3b66-dd04-4279-a28f-d73a5782149e&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-candidate-statuses-from-applicant-tracking-systems&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)\
\
![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=8953a2ce-5914-447f-95c8-5cfeb656d474&bo=2&sid=d7f7c8c03e8d11f0a0aca1275debb903&vid=d7f7c5603e8d11f091d37b98b29aa5a8&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20candidate%20statuses%20from%20applicant%20tracking%20systems&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-candidate-statuses-from-applicant-tracking-systems&r=&lt=649&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=341756)