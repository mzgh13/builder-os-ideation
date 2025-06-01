---
url: "https://www.merge.dev/blog/bamboohr-api-python-post-candidates"
title: "How to POST candidates using the BambooHR API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#prerequisites)

[Generate an API key](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#generate-an-api-key)

[Retrieve job listings from BambooHR](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#retrieve-job-listings-from-bamboohr)

[Make a POST request using Python](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#make-a-post-request-using-python)

[Run and test your code](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#run-and-test-your-code)

[Final thoughts](https://www.merge.dev/blog/bamboohr-api-python-post-candidates#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbamboohr-api-python-post-candidates)

##### Just for you

No items found.

# How to POST candidates using the BambooHR API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Lucien Chemaly

@Merge

BambooHR is a popular human resources information system (HRIS) that allows you to manage everything from recruitment to payroll through an easy-to-use interface.

The BambooHR API lets you programmatically access and manipulate HR data, which can be useful for tasks like posting jobs or candidates, syncing employee data with other systems, or automating HR processes.

For instance, you can use the BambooHR API to integrate with other platforms, such as applicant tracking systems (ATS), learning management systems (LMS), or custom in-house applications. This allows you to automatically transfer candidate information from an ATS to BambooHR once they are hired or to sync employee training records from an LMS with BambooHR to inform performance evaluations.

In this article, you'll learn how to programmatically POST candidates to BambooHR using Python—in other words, to add candidate details to your BambooHR platform directly through a Python script that can be integrated into your larger recruitment or HR management system.

## Prerequisites

Before you start, ensure you have the following installed:

- [Python 3.10 or newer](https://www.python.org/downloads/).
- A text editor, such as [Visual Studio Code](https://code.visualstudio.com/).
- A BambooHR account. You can sign up for a [free trial](https://www.bamboohr.com/signup/b4) and use BambooHR's trial data for this tutorial.

You also need the requests library to make HTTP requests. You can install it from your terminal or shell using pip: `pip3 install requests`

## Generate an API key

BambooHR provides multiple authentication options, including OAuth and API keys. In this tutorial, you'll authenticate with an API key.

Sign into your BambooHR account and navigate to your profile by clicking on your profile icon in the upper-right corner. From the drop-down menu, select **API Keys**:

[![BambooHR API keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f18e6958bc18d90bd_BIuzovY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f18e6958bc18d90bd_BIuzovY.webp)

In the **API Keys** section, press **Add New Key**. Name your new API app-key and click **Generate Key**:

[![Generate BambooHR API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934fd8af98a933a90a04_1PFdQqN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934fd8af98a933a90a04_1PFdQqN.webp)

Once the key is generated, use the **COPY KEY** option to copy it to your clipboard:

[![BambooHR API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f6871102b69d78ac4_wM66Cmj.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f6871102b69d78ac4_wM66Cmj.webp)

Make sure to save your key in a secure location as you'll use it in your Python code later in this tutorial.

Close the key generation dialog by clicking **Done**.

## Retrieve job listings from BambooHR

Before creating a candidate in BambooHR, you must know which job you're associating them with. Each job posting in BambooHR has a unique identifier called jobId. You need this jobId when posting a new candidate to link them to the job they're applying for.

### Fetch the list of jobs

Make a GET request to the BambooHR API's jobs endpoint to get the list of jobs. Create a new Python file named get\_bamboohr\_jobs.py and add the following code to it:

```python

import requests
import base64

# Your BambooHR subdomain and API key
subdomain = 'your_subdomain'
api_key = 'your_api_key'

# Encode your API Key in base64 as required for Basic Auth
encoded_api_key = base64.b64encode(f"{api_key}:".encode('utf-8')).decode('utf-8')

# The API URL for fetching jobs
jobs_url = f'https://api.bamboohr.com/api/gateway.php/{subdomain}/v1/applicant_tracking/jobs'

# The headers for authorization
headers = {
   'Authorization': f'Basic {encoded_api_key}'
}

# Fetch the list of jobs
response = requests.get(jobs_url, headers=headers)

# Check for a successful response and print the jobs
if response.status_code == 200:
   jobs = response.json()
   for job in jobs:
       print(f"Job ID: {job['id']}, Job Title: {job['title']}")
else:
   print(f"Failed to fetch jobs. Status code: {response.status_code}")
   print('Response:', response.text)

```

This code begins by importing the requests library to make HTTP requests and the base64 library for encoding. It sets your BambooHR subdomain and API key, which are used to construct the request URL and authenticate your API request. The API key is encoded in Base64 format to comply with the Basic Auth header requirements.

It then defines the URL to fetch job listings from BambooHR's ATS and sets the necessary headers that include your encoded API key for authorization. It makes a GET request to the API, and if it's successful, it iterates over the jobs and prints out their IDs, titles, and other related details. If the request fails, it prints out the status code and response to troubleshoot the issue.

Note that the subdomain variable should be replaced with the unique subdomain assigned to your BambooHR account, which is the custom URL prefix that you use to access your BambooHR dashboard. For instance, if you access your account at https://companyname.bamboohr.com, then companyname is your subdomain.

Also, replace the api\_key variable with the personal API key you generated earlier.

### Run the script to get job IDs

Open your terminal or shell, navigate to the directory where your script is located, and run the following command: `python3 get_bamboohr_jobs.py`

The output is a list of job IDs and their corresponding titles:

Job ID: 22, Job Title: {'id': None, 'label': 'Financial Analyst'}

Job ID: 21, Job Title: {'id': None, 'label': 'Marketing Manager'}

Job ID: 20, Job Title: {'id': None, 'label': 'Software Engineer'}

Job ID: 19, Job Title: {'id': None, 'label': 'General Application'}

Job ID: 18, Job Title: {'id': None, 'label': 'Videographer'}

Job ID: 15, Job Title: {'id': None, 'label': 'IT Security Engineer'}

Make a note of the job ID you want to use when posting candidates. For testing purposes, use Job ID: 22 for Financial Analyst.

## Make a POST request using Python

Now that you have your job ID, you're ready to create your POST request.

Create a new Python file named post\_bamboohr\_candidates.py and add the following code to it:

```python

import requests
import json
import base64

# Your BambooHR subdomain and API key
subdomain = 'your_subdomain'
api_key = 'your_api_key'

# Encode your API Key in base64 as required for Basic Auth
encoded_api_key = base64.b64encode(f"{api_key}:".encode('utf-8')).decode('utf-8')

# The API URL for creating a candidate
url = f'https://api.bamboohr.com/api/gateway.php/{subdomain}/v1/applicant_tracking/application'

# The headers for authorization
headers = {
   'Authorization': f'Basic {encoded_api_key}',
   'Content-Type': 'application/json'
}

candidate_data = {
   'firstName': 'Jane',
   'lastName': 'Doe',
   'email': 'jane.doe@email.com',
   'jobId': '22',
}

try:
   # Create a Candidate Request
   response = requests.post(url, headers=headers, data=json.dumps(candidate_data))

   # Successful POST
   if response.status_code == 200:
       print('Candidate successfully posted to BambooHR.')
   else:
       # Handle specific response codes here, if needed
       print(f'Failed to post candidate. Status code: {response.status_code}')
       print('Response:', response.reason)
except requests.exceptions.RequestException as e:
   # Handle different exceptions such as connection errors, timeouts, etc.
   print('An error occurred: ', e)

```

This code uses requests to post candidate information to BambooHR's API. It encodes your API key using base64 to meet the Basic Auth requirements and includes it in the headers for authorization. The candidate\_data dictionary holds the candidate's details, including the job ID you obtained in the previous step.

The requests.post call attempts to add the candidate to BambooHR. If the response is successful, a confirmation message is printed. If there's an error, the status code and reason are printed out to help you understand what went wrong. Any request issues, like network problems, are caught, and an error message is displayed.

Remember to replace the subdomain and api\_key fields as before.

## Run and test your code

To run your script, open your terminal or shell and navigate to the directory where your Python script is saved. Run the script by typing the following command: `python3 post_bamboohr_candidates.py`

If the script runs successfully, you should see Candidate successfully posted to BambooHR. printed in your terminal or shell: `Candidate successfully posted to BambooHR.`

Note that running your `post_bamboohr_candidates.py` script associates the new candidate with the job posting you specified in the jobId.

If there's an error, the script prints the status code and the response from the API, which can help you troubleshoot the issue:

`Failed to post candidate. Status code: XXX
Response: {detailed error message from the API}`

‍

To confirm that the candidate was created, go to your BambooHR account, navigate to **Hiring** from the top navigation bar, and then select **Candidates**. Search for the candidate you've created. In this case, you should see Jane Doe:

[![BambooHR candidate](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f3b6453af576210f4_URA1U5Q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6567934f3b6453af576210f4_URA1U5Q.webp)

And that's it! You can find the code for this article in [this GitHub repository](https://github.com/See4Devs/create-candidates-bamboohr-python).

For more information on other applicant tracking APIs, check out the [BambooHR Official API documentation](https://documentation.bamboohr.com/docs).

## Final thoughts

Your clients likely use a variety of HRIS solutions.

You can broaden the integrations you offer quickly and easily by building to [Merge's HRIS Unified API](https://www.merge.dev/categories/hr-payroll-api). Once connected to the API, you’ll be able to offer 50+ integrations, which include tools like BambooHR, Workday, Namely, and UKG.

‍ _To get a deeper understanding of Merge, you can_ [_schedule a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fbamboohr-api-python-post-candidates) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=63193687-1759-4400-8fb8-50833c89546b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=35823843-0e29-46ad-a578-5396d5d5bd55&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbamboohr-api-python-post-candidates&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=63193687-1759-4400-8fb8-50833c89546b&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=35823843-0e29-46ad-a578-5396d5d5bd55&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbamboohr-api-python-post-candidates&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=4fd686ce-33d4-4750-8e55-1184bff3532c&bo=2&sid=813a48903e8d11f09c3c4d716752cb34&vid=813a4ab03e8d11f0b26015b37b2a89ad&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20POST%20candidates%20using%20the%20BambooHR%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fbamboohr-api-python-post-candidates&r=&lt=329&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=432313)