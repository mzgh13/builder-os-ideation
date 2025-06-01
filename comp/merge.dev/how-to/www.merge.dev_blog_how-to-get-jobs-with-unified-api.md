---
url: "https://www.merge.dev/blog/how-to-get-jobs-with-unified-api"
title: "How to get jobs with a unified API (with an example from BambooHR)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#prerequisites)

[Configure the Authentication between Merge and BambooHR](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#configure-the-authentication-between-merge-and-bamboohr)

[Get Merge Keys](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#get-merge-keys)

[Fetch Jobs from BambooHR](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#fetch-jobs-from-bamboohr)

[Filter Jobs](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#filter-jobs)

[Conclusion](https://www.merge.dev/blog/how-to-get-jobs-with-unified-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-jobs-with-unified-api)

##### Just for you

No items found.

# How to get jobs with a unified API (with an example from BambooHR)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e1e7e186d1f5959a83db33_How_to_get_Access_to_Quality_Data_for_AI.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Lucien Chemaly

@Merge

Applicant tracking systems (ATSs) are software that helps hiring professionals manage the hiring process. Instead of sifting through stacks of applications, ATSs filter and categorize applications based on keywords, skills, work experience, and education.

Because of the valuable data in ATSs, companies often want to integrate their ATS with other software programs. One of the most common use cases for such an integration is the retrieval of jobs data. This data can be used to update job postings on your company's website or app in real time to ensure that potential applicants always have access to the most current opportunities.

In this article, you'll see how you can use [Merge's unified API](https://merge.dev/) to easily get jobs from [BambooHR](https://merge.dev/integrations/bamboohr), a popular HRIS with an ATS component.

_Note:_ This tutorial uses BambooHR because you can follow this tutorial using its free trial. However, you can easily adapt these steps to integrate with any of the other ATSs Merge supports, including dedicated ATSs such as [Greenhouse](https://merge.dev/integrations/greenhouse) and [ApplicantStack](https://merge.dev/integrations/applicantstack), as well as HRIS solutions with an ATS component, such as [Sage HR](https://merge.dev/integrations/sage-hr).

You can find the code for this tutorial in [this GitHub repository](https://github.com/See4Devs/merge-bamboohr).

## Prerequisites

Before you get started, make sure you have the following installed to follow along with this tutorial:

- [Python 3.10 or later](https://www.python.org/downloads/)
- A Merge account. You can [sign up for free](https://app.merge.dev/signup) if you don't have one.
- A BambooHR account. You can sign up for a [free trial](https://www.bamboohr.com/signup/c/) and use BambooHR's trial data for this tutorial.
- A text editor or integrated development environment (IDE) of your choice where you'll write and run your Python code. Popular options include [Visual Studio Code](https://code.visualstudio.com/) and [PyCharm](https://www.jetbrains.com/pycharm/download/).

This tutorial will use Visual Studio Code. If you want to install it, open your shell or terminal and run the following command to install virtualenv: `pip3 install virtualenv`

Create a directory for your project named merge-bamboohr, navigate to it using your shell or terminal, and create a virtual environment named merge\_bamboohr.

`mkdir merge-bamboohr && cd merge-bamboohr
virtualenv merge_bamboohr`

Activate the virtual environment using the appropriate command for your operating system.

For Windows, use the following: `merge_bamboohr\Scripts\activate`

For macOS and Linux, use the following: `source merge_bamboohr/bin/activate`

Lastly, install the Python libraries that will be used in the code. Open your shell or terminal and run the following commands: `pip3 install pandaspip3 install MergePythonClient==0.2.4`

Pandas will be used to efficiently handle and manipulate tabular data, specifically the jobs data that you will retrieve from BambooHR. The MergePythonClient v0.2.4 will be used to interact with the Merge unified API.

## Configure the Authentication between Merge and BambooHR

To integrate Merge with BambooHR, you need to configure the authentication between these tools.

Log in to your Merge account, where you'll see the Merge dashboard.

[![Merge dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053a2a7272ffd5f40a0_Zb3DXww.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053a2a7272ffd5f40a0_Zb3DXww.webp)

Click on **Linked Accounts** in the left navigation bar and then on **Test Linked Accounts**.

[![Test linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053c7424e2f175c0e6c_jSMimxK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053c7424e2f175c0e6c_jSMimxK.webp)

Click on **Create Test Linked Account**. In the pop-up, select the **Applicant Tracking System** category and then **BambooHR** from the list. Click **Continue**.

Next, you'll be asked how you would like to authenticate. Select the recommended option of authenticating through BambooHR's website and click **Next**.

[![How to authenticate](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e5405293a6c24edbdac0f6_e6v0ogs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e5405293a6c24edbdac0f6_e6v0ogs.webp)

Next, you will be asked to enter your BambooHR subdomain. You can find this information in the URL when you're logged into your BambooHR account. It should look like the following: {subdomain}.bamboohr.com.

Type in your subdomain and click **Submit**.

[![BambooHR subdomain](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e540524e2e7e0805f71a78_4r3Iktj.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e540524e2e7e0805f71a78_4r3Iktj.webp)

Follow the instructions to finish the setup. You should now see the linked account on your Merge dashboard.

[![Merge Linked Accounts dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54052ee74a5458879c9d4_Dw1XIIt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54052ee74a5458879c9d4_Dw1XIIt.webp)

Data for production links are synced automatically. However, since this is a test linked account, you need to sync the data manually. To do so, click on the **Force resync** icon next to the trash can icon.

## Get Merge Keys

Before writing your code, you need to get your account token and your Merge access key. You will use these keys in your code to authenticate with your Merge account and get data from the linked account.

In your Merge dashboard, go to your **Linked Accounts** and open the test linked account that you just created. On the right side, you should see **Account Token**.

[![Account Token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053482a6d154d43bf2a_SsVFvNv.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54053482a6d154d43bf2a_SsVFvNv.webp)

Copy and safely store this key for later use.

Next, click on **API Keys** in the left navigation bar. Copy **Default Test Key**, which is under **Test Access Keys**, and safely store it for later use.

[![Test Access Keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54052eb9b21e06c90b7aa_fYeiiD7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54052eb9b21e06c90b7aa_fYeiiD7.webp)

‍

## Fetch Jobs from BambooHR

You're now ready to write your Python code to fetch jobs data from BambooHR.

Create a new file named **bamboohr\_jobs.py** and add the following code to it:

```python

import merge
from merge.client import Merge
import csv
merge_client = Merge(
    api_key="YOUR_MERGE_API_KEY",
    account_token="YOUR_MERGE_LINKED_ACCOUNT_TOKEN")
try:
    jobsList = merge_client.ats.jobs.list()
    # Define the CSV file name
    csv_file = "bamboohr_jobs_results.csv"
    # Write the API response to a CSV file
    with open(csv_file, mode='w', newline='') as file:
        writer = csv.writer(file)
        # Write header row
        writer.writerow(["Name", "Status", "Created At"])
        # Write data rows
        for job in jobsList.results:
            name = job.name
            status = job.status
            created_at = job.remote_created_at
            writer.writerow([name, status, created_at])
    print(f"Results written to {csv_file}")
except Exception as e:
    print('Exception when getting jobs list: %s' % e)
```

This code uses the [Merge ATS API](https://merge.dev/categories/ats-recruiting-api) to retrieve jobs and write the results to a CSV file.

It starts by creating the Merge client and then calls the jobs method that is in the ats product type, after which it parses the output as a list with the list() function. If the process is successful, job details are written to **bamboohr\_jobs\_results.csv** with columns Name, Status, and Created At. If there's an exception, an error message will be printed.

_Note:_ Replace 'YOUR\_MERGE\_API\_KEY' and 'YOUR\_MERGE\_LINKED\_ACCOUNT\_TOKEN' with the Merge API key and linked account key you obtained in the previous section.

Run your code from the terminal or shell with the following command: `python3 bamboohr_jobs.py`

After the code finishes running, you should see a new CSV file named **bamboohr\_jobs\_results.csv**. If you used BambooHR's sample data, the content of the file should be similar to the following:

Name,Status,Created At

Customer Success Advocate,Filled,2023-03-30T21:25:15Z

IT Security Engineer,OPEN,2023-08-02T20:20:12Z

Account Executive,On Hold,2023-03-30T21:31:31Z

Videographer,DRAFT,2023-07-31T04:40:38Z

General Application,OPEN,2023-07-08T21:43:35Z

Software Engineer,OPEN,2023-08-02T20:22:25Z

Marketing Manager,OPEN,2023-08-02T16:05:02Z

Financial Analyst,OPEN,2023-08-02T20:21:18Z

## Filter Jobs

If you want to filter the jobs that have an OPEN status, you can do so by adding a query parameter.

Create a new file named **bamboohr\_jobs\_open.py**. Use the same code as before but add the status parameter to the list() method and name your CSV file **bamboohr\_jobs\_open\_results.csv**. Your code should look like this:

```python

import merge
from merge.client import Merge
import csv
merge_client = Merge(
    api_key="YOUR_MERGE_API_KEY",
    account_token="YOUR_MERGE_LINKED_ACCOUNT_TOKEN")
try:
    jobsOpenList = merge_client.ats.jobs.list(status="OPEN")
    # Define the CSV file name
    csv_file = "bamboohr_jobs_open_results.csv"
    # Write the API response to a CSV file
    with open(csv_file, mode='w', newline='') as file:
        writer = csv.writer(file)
        # Write header row
        writer.writerow(["Name", "Status", "Created At"])
        # Write data rows
        for job in jobsOpenList.results:
            name = job.name
            status = job.status
            created_at = job.remote_created_at
            writer.writerow([name, status, created_at])
    print(f"Results written to {csv_file}")
except Exception as e:
    print('Exception when getting open jobs list: %s' % e)
```

Run your code from the terminal or shell with the following command: `python3 bamboohr_jobs_open.py`

After the code finishes running, you should see a new CSV file named **bamboohr\_jobs\_open\_results.csv**. The content of the file should be similar to the following:

Name,Status,Created At

IT Security Engineer,OPEN,2023-08-02T20:20:12Z

General Application,OPEN,2023-07-08T21:43:35Z

Software Engineer,OPEN,2023-08-02T20:22:25Z

Marketing Manager,OPEN,2023-08-02T16:05:02Z

Financial Analyst,OPEN,2023-08-02T20:21:18Z

## Conclusion

As you saw in this tutorial, Merge's unified API makes it very simple to get jobs from an ATS like BambooHR. You can also use the [same integration to pull other data from BambooHR](https://merge.dev/integrations/bamboohr), such as activities, applications, jobs, attachments, departments, and more.

Merge also offers integrations with several other [ATS systems](https://merge.dev/categories/ats-recruiting-api#integrations) as well as HR, payroll, CRM, ticketing, and accounting systems. You can [sign up for a free trial](https://app.merge.dev/signup) to explore everything Merge has to offer.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lucien Chemaly

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c38d2505-4d1b-494a-9664-b5d72cb5de5a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=25a33c02-60ed-4510-a662-70405d3b119f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-jobs-with-unified-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c38d2505-4d1b-494a-9664-b5d72cb5de5a&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=25a33c02-60ed-4510-a662-70405d3b119f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-jobs-with-unified-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0797c7a3-eed2-44b0-87bd-cb62b7814b97&bo=2&sid=9447c0203e8d11f0a6dde5ca379577a9&vid=9447d8603e8d11f09ac30f987bfe094c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20jobs%20with%20a%20unified%20API%20(with%20an%20example%20from%20BambooHR)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-jobs-with-unified-api&r=&lt=648&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=721600)