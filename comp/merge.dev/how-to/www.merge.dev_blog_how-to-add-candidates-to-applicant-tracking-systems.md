---
url: "https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems"
title: "How to add candidates to applicant tracking systems"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#)

Table of contents

[What Is Merge?](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#what-is-merge)

[How to Add Candidates to an ATS using Merge](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#how-to-add-candidates-to-an-ats-using-merge)

[Conclusion](https://www.merge.dev/blog/how-to-add-candidates-to-applicant-tracking-systems#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-add-candidates-to-applicant-tracking-systems)

##### Just for you

No items found.

# How to add candidates to applicant tracking systems

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7de0a9323838512e363_Autoprovisioning.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Osinachi Chukwujama

@Merge

Applicant tracking systems (ATSs) allow you to monitor and manage applicants for a job posting in your company. They help with tasks such as extracting data from resumes, grouping applicants based on similarities, and viewing the job status progress for each applicant.

When recruiting, you might want to post positions on more than one ATS. Or you may be managing multiple ATS platforms for different customers. In such cases, you can reduce the manual work of inputting data to each ATS platform with Merge—a platform that allows you to communicate with different ATS platforms using a single API (in this case, its [ATS Unified API](https://merge.dev/categories/ats-recruiting-api)).

In this article, you will learn how to add new candidates to different ATS platforms using the [Merge Python SDK](https://pypi.org/project/mergepythonclient/0.1.1/). But let’s first take a closer look at Merge.

{{blog-cta-100+}}

## What Is Merge?

Merge simplifies the process of integrating with various software by offering a unified API that lets you connect to [dozens of software platforms in the same category](https://merge.dev/categories)—including CRM, accounting, HR, and ticketing systems—without dealing with the differences between them.

Merge works by calling the APIs of different systems and managing their differences under the hood. This means a single API call can serve all the supported platforms, and you don't have the hassle of maintaining integration code. If you're adding candidates to different ATSs, it means you don't need to change the shape of your API request to add candidates to different platforms.

Merge integrates with [more than forty ATSs](https://merge.dev/categories/ats-recruiting-api), including popular options like Greenhouse, BambooHR, Taleo, iCIMS, and Workable, and it offers SDKs for different languages, including Typescript, Python, Java, and Ruby.

## How to Add Candidates to an ATS using Merge

This tutorial will show you how to use the Python SDK to add candidates to two ATS platforms— [Workable](https://merge.dev/integrations/workable) and [Breezy HR](https://merge.dev/integrations/breezy). These platforms all offer free trial accounts so that you can follow along, but you can also easily adapt these steps for any of [the other ATSs Merge supports](https://merge.dev/categories/ats-recruiting-api).

### Prerequisites

To follow along, you need the following:

- [Python 3.7+](https://www.python.org/downloads/)
- A [Merge.dev](http://merge.dev/) account (you can [sign up for free](https://app.merge.dev/signup))
- Free trial accounts for [Workable](https://www.workable.com/free-trial), and [BreezyHR](https://app.breezy.hr/signup)

### Connecting your ATSs to Merge

The first step with any Merge integration is to connect the relevant software platform to Merge. On your Merge dashboard, navigate to **Linked Accounts** and select **Test Linked Accounts** since you don't want to use the production space for this tutorial.

On that page, click on the **Launch Test Link** button. A modal showing all integration categories should pop up.

[![Modal showing integration categories](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af23ebd03750897dc13e_4bfWJZP.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af23ebd03750897dc13e_4bfWJZP.webp)

Select **Applicant Tracking System**, search for "Workable", and click on it. Read the terms of the integration, and then select the **API token** authentication option, as recommended.

[![API token authentication option](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af24648f050aebb3b558_e08iAUj.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af24648f050aebb3b558_e08iAUj.webp)

Input your Workable subdomain and your API on the subsequent page. [Merge provides a detailed up-to-date guide](https://help.merge.dev/en/articles/5442252-workable) on how to connect to the Workable ATS. If you successfully inputted the details, you should have a success screen at the end of the flow.

[![Workable integration success message](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af23103e6398dd6ffa88_dasaNdM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af23103e6398dd6ffa88_dasaNdM.webp)

If not, check whether your Workable subdomain and API key are correct.

You can connect to a total of three accounts in the testing workspace. Repeat the process above to connect Breezy to Merge.

### Setting Up the Demo Environment

To set up your demo environment, get the code you'll be using in this tutorial by cloning the accompanying [GitHub repo](https://github.com/vicradon/merge-ats-demo) using the command below:

```python
git clone https://github.com/vicradon/merge-ats-demo.git
```

Now, you need to follow the steps below to create a virtual environment and install dependencies. The first step is to navigate into the cloned repo. Do this by running the command below:

```python
cd merge-ats-demo
```

Then create the virtual environment using:

```python
python3 -m venv venv
```

Now, activate the virtual environment using:

```python
source venv/bin/activate # on macOS or Linux.\venv\Scripts\activate # on Windows
```

After the virtual environment is active, install the requirements using the following:

```python
pip install -r requirements.txt
```

Part of the packages listed in requirements.txt is the [Merge Python SDK](https://pypi.org/project/mergepythonclient/0.1.1/) locked at version 0.1.1. Version locking ensures that the code in this tutorial will work regardless of when it is accessed.

Next, set up your environment variables first by creating an .env file and supplying the required details. Create the .env file by copying it from the example file called **.env.example** using the command below:

```python
cp .env.example .env
```

This is what it contains:

```python
API_KEY=WORKABLE_ACCOUNT_TOKEN=BREEZY_ACCOUNT_TOKEN=RECRUITEE_ACCOUNT_TOKEN=
```

The API\_KEY environment variable is an API key you must obtain from the [keys page](https://app.merge.dev/keys) of your [Merge.dev](http://merge.dev/) dashboard. Since you set up a test account integration earlier, you need to use the test API key.

The other keys in the .env file are the account tokens of Workable and Breezy. You can obtain these tokens from each linked account page on your Merge dashboard. For example, when you navigate to Workable's linked account page, you can find the account token on the right as shown in the image below:

[![Screenshot of account token from Test Linked Accounts view](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc0943cf8255b43c8c34fb_64d2af841a297fc83b83dedc_Account%2520Token.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc0943cf8255b43c8c34fb_64d2af841a297fc83b83dedc_Account%2520Token.webp)

### Adding Candidates

Merge allows you to add candidates to different API platforms without changing the structure of the candidate biodata. It only requires you to add the account token specific to the ATS platform, the ID of the job which the candidate is applying to (application\_id), and the ID of the user Merge is acting as (remote\_user\_id).

#### Obtaining Job Application ID and Remote User ID

To add a candidate to an ATS using the Merge SDK, you need three important details apart from the candidate's personal information, such as first name, last name, and email address. These are the account\_token, application\_id, and remote\_user\_id.

The account\_token is obtained from the Merge dashboard, as explained in the section on setting up the demo environment. The application\_id and remote\_user\_id can be obtained using the applications and users modules of the Merge Python SDK.

To do that, create a file at the root of the project's directory called **ids.py** and add the following to it:

```python

from merge.client import Merge
from dotenv import load_dotenv
import os

load_dotenv()

client = Merge(api_key=os.environ['API_KEY'], account_token=os.environ['WORKABLE_ACCOUNT_TOKEN'])

mergeApplicationsResponse = client.ats.applications.list()
mergeRemoteUserId = client.ats.users.list()

output = {
    "application_id": mergeApplicationsResponse.results[0].id,
    "remote_user_id": mergeRemoteUserId.results[0].id
}

print(output)

```

The output you will obtain from running the **ids.py** file should be similar to the snippet below:

```python
{'application_id': '76322c22-85ca-4968-89a6-0ce5633b2009', 'remote_user_id': '75b30b04-25f0-42f2-b6da-c1750d00ec4c'}
```

_Note:_ The application\_id that is returned is the first job in a list of possible jobs that a candidate can apply to. In a real application context, you would have to obtain an application ID that matches the job that a candidate actually wants to apply to. The remote\_user\_id is the ID of a recruiter or hiring manager on the ATS platform. When you run a script with this user's ID, Merge adds the candidate as if the real-life user did it manually.

#### Adding a New Candidate

Now, you're ready to run the **main.py** file to add a new candidate to an ATS.

The code snippet below shows the **main.py** file with the WORKABLE\_ACCOUNT\_TOKEN environment variable set. This means running the code will add the candidate to your Workable ATS. Before running the code, you need to add the application\_id and remote\_user\_id you obtained from running the **ids.py** file to the applications array and the remote\_user\_id field respectively. After adding both IDs, go ahead and run the code:

```python

from merge.client import Merge
from dotenv import load_dotenv
import os

load_dotenv()

client = Merge(api_key=os.environ['API_KEY'], account_token=os.environ['WORKABLE_ACCOUNT_TOKEN'])

mergeCreateResponse = client.ats.candidates.create(
    model = {
            "first_name":"Jason",
            "last_name":"Grey",
            "company":"Columbia Dining App.",
            "title":"Software Engineer II",
            "last_interaction_at":'2021-10-17T00:00:00Z',
            "is_private":True,
            "can_email":True,
            "locations":["San Francisco","New York","Miami"],
            "phone_numbers":[\
                {\
                    "value":"+3198675309",\
                    "phone_number_type":"MOBILE"\
                }\
            ],
            "email_addresses":[\
                { "value":"jason-grey11@gmail.com",\
                    "email_address_type":"PERSONAL"\
                }\
            ],
            "urls":[\
                {"value":"http://alturl.com/p749b",\
                    "url_type":"BLOG"\
                }\
            ],
            "tags":["High-Priority"],
            "applications":["d9a62c50-a9fe-452b-878a-6891f6b368fd"],
    },
    remote_user_id="80aaa7a6-2f7c-4bf8-9b26-2a8f7d77c550",
)

print(mergeCreateResponse)

```

Running the code above should produce an output similar to the snippet below:

```python

CandidateResponse(
    errors=[],
    model=Candidate(
        applications=['5faed70e-2ad5-479f-94d2-9595cc1fcbf3'],
        attachments=[],
        can_email=None,
        company=None,
        email_addresses=[\
            EmailAddress(\
                email_address=None,\
                email_address_type='PERSONAL',\
                modified_at=datetime.datetime(2023,6,26,6,13,19,294481,tzinfo=datetime.timezone.utc),\
                value='jason-grey13@gmail.com'\
            )\
        ],
        field_mappings=None,
        first_name='Jason',
        id='a8cd0f25-1828-4be2-b829-5c3d66d2ebe1',
        is_private=None,
        last_interaction_at=None,
        last_name='Grey', locations=None,
        modified_at=datetime.datetime(2023, 6, 26, 6, 13, 19, 192436, tzinfo=datetime.timezone.utc),
        phone_numbers=[\
            PhoneNumber(\
                modified_at=datetime.datetime(2023, 6, 26, 6, 13, 19, 281309,\
                tzinfo=datetime.timezone.utc),\
                phone_number=None, phone_number_type='MOBILE', value='+3198675309'\
            )\
        ],
        remote_created_at=datetime.datetime(2023, 6, 26, 6, 13, 17, 977177, tzinfo=datetime.timezone.utc),
        remote_data=None,
        remote_id='54016683',
        remote_updated_at=datetime.datetime(2023, 6, 26, 6, 13, 17, 977177, tzinfo=datetime.timezone.utc),
        remote_was_deleted=False,
        tags=[],
        title=None,
        urls=[\
            URL(\
                modified_at=datetime.datetime(2023, 6, 26, 6, 13, 19, 349101, tzinfo=datetime.timezone.utc),\
                url_type=None, value='http://alturl.com/p749b'\
            )\
        ]
    ),
    warnings=[],
    logs=None
)

```

_Note:_ Your output will not be formatted like the snippet above but should have minimal differences when it is formatted.

The **main.py** script calls the merge.ats.candidates.create method to create a candidate on the target ATS platform. The platform is set from the Merge initialization where the api\_key and account\_token are set. This method requires two parameters: the model and remote\_user\_id.

The model contains the data about the candidate while the remote user ID is the ID of the user on the ATS platform that the API mocks. The model contains fields such as first\_name, last\_name, location, and email\_address. Each candidate must be added with a unique email and have an associating application ID in the applications array.

Remember to make sure that the account\_token parameter of the Merge class matches in both the **ids.py** and **main.py** files when adding a new user.

A successful run of the **main.py** script will add a new candidate to your Workable ATS. If you check your Workable ATS dashboard, you should see an output similar to the image below:

[![Applicant added for Workable](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af239f27357685152d26_2OubF6B.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af239f27357685152d26_2OubF6B.webp)

If you wish to add the other platforms, you need to change the account token to BREEZY\_ACCOUNT\_TOKEN. After setting your desired ATS platform account token, go ahead and run the **ids.py** script, then copy the application\_id and remote\_user\_id obtained and paste them in the appropriate locations in the **main.py** file.

If you run the **main.py** file, you will see the applicant added to the relevant ATS platform dashboard. For example, if you carry out all the steps above for Breezy HR, you should see a new applicant as shown below:

[![Applicant added for Recruitee](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af2319281da7d7ba99ff_xLl39F9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64d2af2319281da7d7ba99ff_xLl39F9.webp)

## Conclusion

In this article, you learned how you can use Merge to reduce the hassle of consolidating data integration within your organization. You also saw how you could use Merge to simplify adding candidates to several ATSs.

If you want to learn more, check out [how Merge has helped other companies](https://merge.dev/case-studies) integrate not only ATSs but also ticketing, CRM, accounting, file storage, accounting, and HR and payroll systems. And if you'd like to try Merge out, you can [sign up for free](https://app.merge.dev/signup) to get started.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Osinachi Chukwujama

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=571d0e38-b2fc-422e-ba0c-c543bbb68898&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d1a1f867-5213-423b-9d5d-0e877e9d0ec3&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-candidates-to-applicant-tracking-systems&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=571d0e38-b2fc-422e-ba0c-c543bbb68898&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=d1a1f867-5213-423b-9d5d-0e877e9d0ec3&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-candidates-to-applicant-tracking-systems&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=eccae7fc-24be-451d-b4a1-fd73f46dd608&bo=2&sid=6d2169d03e8d11f096b885843844ad07&vid=6d218e503e8d11f0bda9fdbfc848ea22&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20add%20candidates%20to%20applicant%20tracking%20systems&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-candidates-to-applicant-tracking-systems&r=&lt=418&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=438066)