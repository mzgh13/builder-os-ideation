---
url: "https://www.merge.dev/blog/api-integration-python"
title: "How to build API integrations in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-integration-python#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-integration-python#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-integration-python#)

Table of contents

[Performing API integration in Python](https://www.merge.dev/blog/api-integration-python#performing-api-integration-in-python)

[Final thoughts](https://www.merge.dev/blog/api-integration-python#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-python)

##### Just for you

No items found.

# How to build API integrations in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cedb4179a1346be45b1_How_to_get_org_charts_from_HR_systems.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Vivek Kumar Singh

@Merge

An API integration is the process of connecting two or more applications using an API and letting them share data and functionality with each other. This can help improve the functionality of applications, create new applications, and automate tasks. It's an especially valuable tool for companies, helping them save time and money, boost efficiency, and deliver a better user experience.

Python, with its rich set of libraries and frameworks, provides powerful tools for API integration across various domains, such as web services, databases, and cloud platforms. That's why, in this tutorial, you'll learn how to integrate APIs into your Python workflow. You'll build a functional application using [Django](https://www.djangoproject.com/) that seamlessly interacts with the [Recruitee applicant tracking system (ATS) API](https://docs.recruitee.com/reference/getting-started), showcasing both data retrieval and creation functionalities.

_Related:_ [_A guide to performing API integration in JavaScript_](https://www.merge.dev/blog/api-integration-javascript)

## Performing API integration in Python

To work with the Recruitee ATS API, you need to [create a free account](https://auth.recruitee.com/sign-up). Once you've successfully created an account, navigate to the Recruitee dashboard:

[![Recruitee dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06dc07dd14a6032aeec_MKLDDgX.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06dc07dd14a6032aeec_MKLDDgX.webp)

The Recruitee dashboard is your hub for all applicant-tracking tasks, from managing candidates to viewing hiring process reports. You can also integrate it with other recruiting tools, such as your ATS or customer relationship management (CRM) app. But what's really cool is that Recruitee offers an API, allowing you to seamlessly connect it with your own applications.

There's comprehensive [API documentation](https://docs.recruitee.com/reference/getting-started) that can help you understand and test all the API endpoints Recruitee offers. In this tutorial, we'll focus on the candidate retrieval and creation endpoints.

### Obtain an authorization token for the Recruitee API

To begin using the Recruitee API, you need to acquire your API token from your Recruitee account. These tokens serve as the key to authorization for your API requests.

To get your token, click on your account avatar in the top-right corner of the **Recruitee Dashboard** and then navigate to **Profile settings**:

[![Account settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06bae672077a24517d0_kABornz.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06bae672077a24517d0_kABornz.webp)

Within the **Profile settings**, locate the **APPS AND PLUGINS** section. Click on **Personal API tokens**, and a new page will appear:

[![Options in **APPS AND PLUGINS**](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06c928e32fabba10469_VeXv8xw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06c928e32fabba10469_VeXv8xw.webp)

Click the **New token** button to generate a fresh API token. You'll be prompted to name the token—this name can be anything you want it to be. Additionally, you'll need to provide your account password to finalize the token creation.

While you're on this page, make sure you copy the **Company ID** associated with your account. You'll need this when you're interacting with various API endpoints.

_Related:_ [_A guide to running API integration tests_](https://www.merge.dev/blog/api-integration-testing)

### Set up a new Django project

Django is a popular Python web framework we'll use to demonstrate API integration. To set up a new project, clone the starter template of this [GitHub repository](https://github.com/vivekthedev/api-integration-example) using the following command: `git clone https://github.com/vivekthedev/api-integration-example.git -b starter`.

The starter template is already set up with a new project that contains an app called ats. This app is configured with boilerplate home page templates and URLs. The app also comes configured with the necessary settings to start working with the application.

After successfully cloning the repository, navigate to the starter project path in your terminal and execute the following command to set up a Python virtual environment: `python -m venv env`

This command establishes a dedicated Python virtual environment specifically for this project. This isolation helps in managing dependencies without conflicts with global modules.

Activate the virtual environment using the following command: `source env/bin/activate`

Then proceed to install the project-specific dependencies using this command: `pip install -r requirements.txt`

After all the required dependencies are installed, you can launch the Django server to visualize your project's current state: `python manage.py runserver`

Open your web browser and visit [https://localhost:8000](https://localhost:800/) to see your current Django app:

[![Current Django app](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b9c98e6b45fc6eabb_5MMDwWa.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b9c98e6b45fc6eabb_5MMDwWa.webp)

The initial version of this app includes placeholder links that will soon be made functional using the Recruitee ATS API.

Next, locate the ENV file within the project directory and open it. This file contains the following content:

RECRUITEE\_COMPANY\_ID=

RECRUITEE\_API\_KEY=""

DJANGO\_SECRET\_KEY="f26!+lia(%7ercu+d$&i9j41xz!w#-8i5+xt^&3+!q(dh8nphn"

Modify the contents of the ENV file by inserting your specific company ID and API key, which you previously obtained from Recruitee. Once you've made these necessary modifications, save the file.

Now, you're ready to create a new Django page designed to showcase candidate information.

_Related:_ [_Our research on API integration issues_](https://www.merge.dev/blog/api-integration-challenges)

### Retrieve data using the Recruitee API

In order to begin querying the Recruitee API, you need to create a new view inside your Django project. Open the ats/views.py file and import the following modules:

from collections import namedtuple

from django.contrib import messages

from django.conf import settings

import requests

import json

These modules play distinct roles in the interaction with the Recruitee API. The json module is crucial for capturing and interpreting API responses, efficiently converting raw data into a structured format within your application. The requests module establishes a communication channel with the Recruitee API. This module enables sending requests to API endpoints, retrieving data, and transmitting information effectively.

Additionally, the settings module is used for accessing authentication parameters like API\_KEY and COMPANY\_ID, and is securely stored in your project's settings. For streamlined extraction of relevant attributes from API responses, you'll use the namedtuple data structure. It simplifies labeling and accessing specific API output elements.

After importing the necessary modules in the views.py file, you need to set up some module-level variables that can be accessed by every view function in the views.py file. Add the following code immediately after the import statements:

```python

Candidate = namedtuple("Candidate", "name emails phones avatar created_at referrer")

BASE_URL = f"https://api.recruitee.com/c/{settings.RECRUITEE_COMPANY_ID}/"

headers = {
    'accept': 'application/json',
    'authorization': f'Bearer {settings.RECRUITEE_API_KEY}',
    "Content-Type": "application/json"
}

```

The variable Candidate is designated as a module-level entity to extend its accessibility to all views tasked with retrieving candidate data. This variable has attributes such as name, emails, phones, avatar, created\_at, and referrer. This design ensures a standardized representation of candidate-related information across various view functions.

Likewise, the variable BASE\_URL serves a similar purpose. View functions can extend the BASE\_URL to enable distinct requests to be directed to various endpoints. Note that the integration of the RECRUITEE\_COMPANY\_ID variable from the settings file directly into the URL is required by the Recruitee API. This is how the Recruitee backend recognizes the company from which the data is to be extracted.

The headers variable encapsulates the necessary metadata for API communication. The accept header specifies that the desired response format is JSON. The authorization header validates the authenticity of API requests. The Content-Type header is set to application/json, indicating that the content being sent or received is in JSON format. This facilitates proper data parsing and processing.

After setting up the previous variable, your project is ready to query Recruitee API and retrieve candidate data. To achieve this, you have to write code for the all\_cadidates view. In the same views.py file, you'll find a function with the name all\_candidate. Add the following code to the function:

```python

def all_candidates(request):
    candidates = []
    URL = BASE_URL + "candidates/"
    response = requests.get(URL, headers=headers)
    candidates_dict = json.loads(response.text)

```

In this code, a list named candidates is initialized, intended to store distinct candidate records. This list serves as the foundation for data aggregation to be further utilized as context data within a Django template for rendering in HTML. The variable URL extends the core BASE\_URL to encompass the specific candidates/ endpoint. Querying this endpoint returns candidate data as a response.

Through the utilization of an HTTP GET request, the API call is executed using the constructed URL. The resulting information is captured within the response variable for further processing. Note the inclusion of the headers variable within the request headers to ensure proper authentication on the Recruitee servers. Upon obtaining the response, the subsequent task converts the JSON-formatted plaintext response into a structured Python dictionary variable named candidates\_dict. This transformation is crucial for effective querying of the data.

Now, you need to parse the received response and send it to the Django template. To achieve this, update the following code in the same view:

```python

def all_candidates(request):
    ….
    for candidate in candidates_dict["candidates"]:

        cols = (
            candidate["name"],
            " ".join(candidate["emails"]),
            " ".join(candidate["phones"]),
            candidate["photo_thumb_url"],
            candidate["created_at"],
            candidate["referrer"]
        )

        candidates.append(Candidate._make(cols))
    return render( request,'retrieve_candidate.html', {"candidates": candidates})

```

In this code, an iterative loop is used to traverse the dictionary, extracting relevant attributes from each candidate entry. These attributes are then encapsulated within a tuple named cols. This tuple is used as input to the Candidate named tuple, resulting in the creation of a structured candidate record using the \_make function, which accepts an iterable in order to initialize a labeled named tuple.

The accumulation of these named tuples, each representing a candidate within the candidates list, is then passed as context for rendering purposes within the designated Django template named retrieve\_candidate.html.

In order to view the result of the view, you need to start the Django server using the following command: `python manage.py runserver`

Open your browser and visit [http://127.0.0.1:8000/candidates](http://127.0.0.1:8000/candidates). You should see an output like this:

[![All candidates page output](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b873c8d8786fa8265_e65SN4i.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b873c8d8786fa8265_e65SN4i.webp)

This demonstrates how the view fetched the API for candidates' data, parsed it into a dictionary, and displayed the results in the earlier HTML.

_Related:_ [_An overview on the API integration process_](https://www.merge.dev/blog/api-integration-process)

### Create data using the Recruitee API

The Recruitee ATS API also supports HTTP POST request functionality, which enables you to pass a payload to the server and create a new candidate record. In this section, you'll extend your application to add this functionality. To begin, open your ats/views.py file and extend the view new\_candidate using the following code:

```python

def new_cadidate(request):
    if request.method == "POST":
        candidate_payload = {"candidate": {
            "name": request.POST.get("fullName"),
            "emails": [request.POST.get("email")],
            "phones":[request.POST.get("phone")],
            "social_links":[request.POST.get("portfolio")],
            "links": [request.POST.get("website")],
            "cover_letter": request.POST.get("coverLetter")
        }}

```

In this code snippet, the new\_candidate view is defined to determine if the incoming request method is indeed a POST request. Django provides a straightforward means to retrieve this form data through the request.POST.get('keyname') method.

Within this context, the code constructs a dictionary called candidate\_payload. This payload plays a crucial role as it will be sent to the Recruitee API in JSON format. The dictionary is populated with candidate data and formatted to meet the API's expectations. This sets the groundwork for interacting with the Recruitee API and creating new candidate records using the provided data.

Now, you need to send this data to the appropriate endpoint. Add the following code to the same view:

```python

def new_cadidate(request):
    if request.method == "POST":
        …..
        URL = BASE_URL + "candidates/"
        response = requests.post(URL, headers=headers, json=candidate_payload)
        if response.status_code == 201:
            messages.success(request, "New candidate created successfully.")
            return redirect("/candidates")

    return render( request,'create_candidate.html', {})

```

After the construction of the candidate\_payload dictionary, the next step is to initiate an HTTP POST request to a specified URL. This URL is formed by concatenating the BASE\_URL and candidates/. The request is executed using the requests.post() method, where the headers variable and candidate\_payload are included as headers and JSON data, respectively.

Upon receiving the API response, the code checks its status code. If the status code equals 201, it signifies that the candidate creation was successful, leading to a notification message: "New candidate created successfully." Subsequently, the user is redirected to a /candidates page where all the candidates are shown.

However, in cases where the response status code does not equal 201, the code renders the create\_candidate.html template, providing an opportunity for further action or correction. This systematic approach ensures a smooth and reliable interaction with the API, enhancing the user experience and application functionality.

In order to test this view, run the Django server using the following command: `python manage.py runserver`

After running the server, visit [http://127.0.0.1:8000/candidates/new](http://127.0.0.1:8000/candidates/new), where you'll see a candidate form. Fill out the form using some dummy data:

[![New candidate form](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b4ab4032dc5b293b1_zNtYT3U.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b4ab4032dc5b293b1_zNtYT3U.webp)

Click on **Submit** to send the form data to the API. After the request is executed, you'll see the following newly created candidate page:

[![Candidate created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b2e585d5d72ebf00e_1cFcyWN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652ff06b2e585d5d72ebf00e_1cFcyWN.webp)

At this point, you have a fully functional API-integrated app that supports retrieving and creating data objects on the server.

You can also use the [Recruitee API documentation](https://docs.recruitee.com/reference/getting-started) to extend your app with new functionalities, like getting specific users or making changes to existing users.

_Related:_ [_What is API integration management?_](https://www.merge.dev/blog/api-integration-management)

## Final thoughts

Unfortunately, directly integrating APIs can be intricate, especially when juggling multiple APIs with varying authentication methods and details.

In addition, [API integrations require consistent upkeep and adjustments as services evolve](https://www.merge.dev/blog/a-guide-to-application-integration-maintenance?utm_campaign=2023-10%20The%20Pain%20of%20Integrations&utm_source=linkedin&utm_medium=social&utm_term=guide-to-maintenance&utm_content=Merge%20marketing%20halloween%20carousel). You may also find having to build features like [handling rate limiting](https://www.merge.dev/blog/how-to-stop-being-rate-limited-best-practices-for-making-api-calls-at-scale) as your integration continues to gain traction and onboard larger customers. To simplify this process at scale, you can leverage Merge, the leading unified API platform.

Simply build once to one of Merge's Unified APIs to access a whole category of integrations for your product, whether that's HRIS, ATS, CRM, file storage, marketing automation, accounting, or ticketing. Merge also provides a variety of Integration Management capabilities to ensure your customer-facing teams can easily track integration activities, identify errors, and pinpoint the solution to any error.

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-python) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Vivek Kumar Singh

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=95a3e944-e3fe-4a19-9820-9c5cfccecacc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5d15a5b9-b6f5-4e0f-b76d-338b21efac25&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=95a3e944-e3fe-4a19-9820-9c5cfccecacc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5d15a5b9-b6f5-4e0f-b76d-338b21efac25&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-python&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=302c8b63-67e5-4701-b77f-3003aba24e8d&bo=2&sid=328df8503e8e11f0a791b3219b92b49a&vid=328e09f03e8e11f0bfb3c9e6762b83a7&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20build%20API%20integrations%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-python&r=&lt=396&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=941977)