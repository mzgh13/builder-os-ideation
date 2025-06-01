---
url: "https://www.merge.dev/blog/get-incidents-servicenow-api"
title: "How to Retrieve Incidents Using the ServiceNow API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-incidents-servicenow-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-incidents-servicenow-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-incidents-servicenow-api#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/get-incidents-servicenow-api#prerequisites)

[Anatomy of an Incident](https://www.merge.dev/blog/get-incidents-servicenow-api#anatomy-of-an-incident)

[How to Retrieve ServiceNow Incidents Using Python](https://www.merge.dev/blog/get-incidents-servicenow-api#how-to-retrieve-servicenow-incidents-using-python)

[How to Retrieve ServiceNow Incidents Using Webhooks](https://www.merge.dev/blog/get-incidents-servicenow-api#how-to-retrieve-servicenow-incidents-using-webhooks)

[Conclusion](https://www.merge.dev/blog/get-incidents-servicenow-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-incidents-servicenow-api)

##### Just for you

No items found.

# How to Retrieve Incidents Using the ServiceNow API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ceb25b20320c1db575b_GET_incidents_from_the_ServiceNow_API_with_Python%25252525282%2525252529.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Ndafara Tsamba

@Merge

ServiceNow is a popular, easy-to-use, ticketing platform that provides automated workflows to replace manual tasks. It has good search capabilities and defined roles, and it allows you to control access to features and capabilities based on those roles. Because it's cloud-based, it's also easily scalable.

Developers often need to integrate with ServiceNow because it provides such excellent tools to connect business-to-business systems. For example, it allows easy integration with third-party applications and data sources, which allows you to analyze incidents in more detail. [Here](https://docs.servicenow.com/bundle/rome-servicenow-platform/page/administer/integrationhub/reference/spokes-list.html) is a list of out-of-the-box integrations it offers.

In this article, you'll learn how to get incidents from the ServiceNow API using the Python programming language and by using webhooks.

The code shown in this tutorial can be found in this [GitHub repository](https://github.com/Ndafara/Get-Incidents-with-ServiceNow-API).

#### Integrate with 30+ ticketing tools via Merge

Learn how Merge can help you integrate your product with ServiceNow—and dozens of other ticketing applications—by building to Merge's Unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-incidents-servicenow-api)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Prerequisites**

You'll need the following to follow along with this tutorial:

1. A ServiceNow account: You need to [contact sales](https://www.servicenow.com/contact-us.html) to get a real account, but for this tutorial, you could simply use a developer account, which you can [sign up for on their website](https://developer.servicenow.com/dev.do).
2. A personal developer instance: Once you have a developer account, you need to request a Personal Developer Instance (PDI) to access the ServiceNow application. Follow [these instructions](https://developer.servicenow.com/dev.do#!/guides/tokyo/developer-program/pdi-guide/obtaining-a-pdi) and make sure you select the **Admin** role for the PDI.
3. [Python version 3.9 or later](https://www.python.org/downloads/)
4. A [Pipedream](https://pipedream.com/) account for testing the ServiceNow webhook

## **Anatomy of an Incident**

Before retrieving incidents from ServiceNow, you need to understand their makeup. The best way to understand what constitutes an incident is to create a few using the user interface. Later in this tutorial, you'll then use the ServiceNow API with Python to retrieve them.

### **Log in to Your PDI**

Log in to your PDI using the URL you got after creating it. The URL used for this tutorial, for example, is `https://dev139371.service-now.com`. It will take you to the login page, where you need to supply your username and password:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7717be1b43d22662da2_4mxhuiq.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7717be1b43d22662da2_4mxhuiq.webp)

### **View and Create Incidents**

Once you're logged in, select **All**, expand **Self-Service**, then click on **Incidents**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc78f2bd224152e2dfa65_d1XgZko.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc78f2bd224152e2dfa65_d1XgZko.webp)

This will open the Incidents page, which shows all the current incidents. If you had any, they would be listed here. As you can see below, there are no current incidents:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7a85219c711d97ace51_8qJt4dw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7a85219c711d97ace51_8qJt4dw.webp)

To create an incident, click on the **New** button in the top left corner. This will open up the page for creating incidents.

You have to provide the _Urgency_, which is a measure of the business criticality based on the impact and business needs of the customer. It's also a way of assigning priority for dealing with incidents. The options here are _High_, _Medium_, and _Low_.

You also have to describe your issue. The more information you can provide in this field, the better it is for the support organization to quickly resolve your issue.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7e35219c7ed857aee05_YLp032c.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc7e35219c7ed857aee05_YLp032c.webp)

Since this is only an example, you can use something simple like this:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca5d0d461b423686e953_How%20to%20Retrieve%20Incidents%20Using%20the%20ServiceNow%20API%20in%20Python.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca5d0d461b423686e953_How%20to%20Retrieve%20Incidents%20Using%20the%20ServiceNow%20API%20in%20Python.webp)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc9bcb22ec232b4f990ef_CYcH6OG.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cc9bcb22ec232b4f990ef_CYcH6OG.webp)

Once you have populated the Urgency and Description, click on **Submit** to create the incident.

As soon as the incident is created, the Incident Details page opens up, which shows other fields such as the **Incident Number**, **Date Opened**, and **State**. This page shows you the details of the incident that you just captured.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca00a9a3008fa4d0a8ed_omlyYaO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca00a9a3008fa4d0a8ed_omlyYaO.webp)

Create a few more incidents with varying urgencies to use later in this tutorial. See a few examples below:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca9ab9e412aacc38060f_How%20to%20Retrieve%20Incidents%20Using%20the%20ServiceNow%20API%20in%20Python%20%E2%80%94%20Table%202.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641cca9ab9e412aacc38060f_How%20to%20Retrieve%20Incidents%20Using%20the%20ServiceNow%20API%20in%20Python%20%E2%80%94%20Table%202.webp)

If you go to the Incidents page, you should now see a list of the incidents you just created.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641ccab6d8d1052822d48007_YX45YCk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641ccab6d8d1052822d48007_YX45YCk.webp)

## **How to Retrieve ServiceNow Incidents Using Python**

Now you have a few incidents created from the portal, you'll be fetching them using Python.

### **Create a Python Project and Activate a Virtual Environment**

Create a new directory and name it `Get_Incidents_with_ServiceNow_API`.

Navigate to the directory and run the following command to create a virtual environment called `get_incidents_with_servicenow_api`:

```“python” language-none
python -m venv get_incidents_with_servicenow_api
```

After creating the virtual environment, you need to activate it. On Windows, run the following command:

```“python” language-none
get_incidents_with_servicenow_api\Scripts\activate
```

To activate the virtual environment on Linux or Mac, run this command:

```“python” language-none
source get_incidents_with_servicenow_api/bin/activate
```

Once the virtual environment is activated, install the **requests** package by running the following command:

```“python” language-none
pip install requests
```

You will use the requests package to make HTTP calls to the ServiceNow API.

### **Get Incidents with Python Using Basic Authentication**

You'll first get the incidents using basic authentication—in other words, by using a username and password as credentials.

Create a new file in the `Get_Incidents_with_ServiceNow_API` directory and name it **get\_incidents\_basic\_authentication.py**.

Paste the following code into it:

```“python” language-none
import requests

# Set the request parameters
url = 'https://your_instance_url/api/now/table/incident'

# Set the user and password credentials
user = 'your_username'
password = 'your_password'

# Set proper headers
headers = {"Content-Type": "application/json", "Accept": "application/json"}

# Do the HTTP request
response = requests.get(url, auth=(user, password), headers=headers)

# Check for HTTP codes other than 200
if response.status_code != 200:
    print('Status:', response.status_code, 'Headers:', response.headers, 'Error Response:', response.json())
    exit()

# Decode the JSON response into a dictionary and use the data
data = response.json()
print(data)
```

Replace `your_username`, `your_password`, and `your_instance_url` with the values you got when you set up your PDI.

To execute the script, run the following command:

**python get\_incidents\_basic\_authentication.py**

If the code executes well, you should get an array with a list of your incidents as the output similar to this (your response will be significantly larger, we’ve just truncated ours for ease of use in this tutorial):

```“python” language-none
{
    "result": [\
        {\
            "parent": "",\
            "made_sla": "true",\
            "caused_by": "",\
            "watch_list": "",\
            "upon_reject": "cancel",\
            "sys_updated_on": "2023-01-08 16:48:44",\
            "child_incidents": "0",\
            "hold_reason": "",\
            "origin_table": "",\
            "task_effective_number": "INC0010003",\
            "approval_history": "",\
            "number": "INC0010003",\
            "resolved_by": "",\
            "sys_updated_by": "aes.creator",\
            "opened_by": {\
                "link": "https://dev139371.service-now.com/api/now/table/sys_user/33a5f6899710211018b7bf1e6253af7b",\
                "value": "33a5f6899710211018b7bf1e6253af7b"\
            }\
]}

```

‍ **‍** As you can see from this output, ServiceNow recorded much more information than what you entered when you created your incidents. You can filter out what you don't need.

If you get the following `401` status code, it means you're not authenticated:

```“python” language-none
Status: 401 Headers: {'Set-Cookie': 'JSESSIONID=5A78596B08BA50ACD3069B50E66E2C86; Path=/; HttpOnly;Secure, BIGipServerpool_dev139371=1032541962.60480.0000; path=/; Httponly; Secure', 'Server-Timing': 'sem_wait;dur=0, sesh_wait;dur=0
', 'Content-Encoding': 'gzip', 'WWW-Authenticate': 'BASIC realm="Service-now"', 'X-Content-Type-Options': 'nosniff', 'Pragma': 'no-store,no-cache', 'Cache-Control': 'no-cache,no-store,must-revalidate,max-age=-1', 'Expires': '0', 'Content-Type': 'application/json;charset=UTF-8', 'Transfer-Encoding': 'chunked', 'Date': 'Sun, 08 Jan 2023 21:21:03 GMT', 'Keep-Alive': 'timeout=20', 'Server': 'ServiceNow', 'Strict-Transport-Security': 'max-age=63072000; includeSubDo
mains', 'Connection': 'close'} Error Response: {'error': {'message': 'User Not Authenticated', 'detail': 'Required to provide Auth information'}, 'status': 'failure'}
```

‍

If you get this error, you then need to check your username and password credentials to ensure that they are correct and authorized.

### **Get Incidents with Python Using OAuth Authentication**

The first thing you need to do is register a new OAuth application. In your ServiceNow PDI, search for **oauth**. Under **System OAuth**, click on **Application Registry**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e022a2236318990125a3f_Qu4B1lI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e022a2236318990125a3f_Qu4B1lI.webp)

This will open up the application registry, where you have to click on **New** and then click the option **Create an OAuth API endpoint for external clients**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e024993bf751fcb98b96e_hFaiUrz.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e024993bf751fcb98b96e_hFaiUrz.webp)

Fill in the name of the application. In this tutorial, name it **OAuth Incidents Demo** and then click **Submit**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e02610af7217f1557ca5d_jPH7Qj0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e02610af7217f1557ca5d_jPH7Qj0.webp)

Your application will now show in the list of OAuth applications:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e027a93bf756be298b98d_fnJFVk1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e027a93bf756be298b98d_fnJFVk1.webp)

Click on **OAuth Incidents Demo** to see the details. Copy the _client ID_ and the _client secret_ as you're going to need to use them later in your code.

Create a file named **get\_oauth\_token.py** and put in the following code:

```“python” language-none
import requests

# Set the request parameters
url = 'https://your_instance_url/oauth_token.do'

# Set proper headers
headers = {'Content-Type': 'application/x-www-form-urlencoded'}

# Set the urlencoded body
username = 'your_username'
password = 'your_password'
grant_type = 'password'
client_id = 'your_client_id'
client_secret = 'your_client_secret'

data = {'username': username, 'password': password, 'grant_type': grant_type,
        'client_id': client_id, 'client_secret': client_secret}

# Do the HTTP request
response = requests.post(url, headers=headers, data=data)

# Check for HTTP codes other than 200
if response.status_code != 200:
    print('Status:', response.status_code, 'Headers:', response.headers, 'Error Response:', response.json())
    exit()

# Decode the JSON response into a dictionary and use the data
data = response.json()
print(data)

```

Replace `your_instance_url`, `your_username`, `your_password`, `your_client_id`, and `your_client_secret` **‍** with your actual values.

To execute the file, run the following command:

```“python” language-none
python get_oauth_token.py
```

If it executes successfully, you will get an access token to use in a subsequent request.

```“python” language-none
{
    "access_token": "PnVImbupAdrnEu4gn5jsnbQMTKtDD7WDbUA5CWXOy932eT7-jW1ncIj1sAVb1Li01DFLPFPbQ8NyBvL2Nzr7uQ",
    "refresh_token": "3TPvClyyUxpQoNXsjcanIQ5ROgIYFepAWR30Q-kmYKsKwlopzJEXUpMN6FzXJ2ra5Fi4TIOMnFY87FosJm6amA",
    "scope": "",
    "token_type": "Bearer",
    "expires_in": 1799
}
```

Remember to save your `access_token` in a safe place.

To get your incidents using the access token, create a file called **get\_incidents\_oauth.py** and put the following code into it:p

Remember to replace `your_instance_url` with yours, and use the access token you got from the previous step instead of `YOUR_ACCESS_TOKEN`.

Run the code with the following command:

**python get\_incidents\_oauth.py**

You should get the same output as before.

## **How to Retrieve ServiceNow Incidents Using Webhooks**

You can also retrieve incidents from ServiceNow using webhooks.

You create webhooks in ServiceNow by specifying business rules. Business rules are essentially server-side logic that gets executed when database records are updated, queried, inserted, or deleted. For the use case of this tutorial, when you create a new incident, the incident will be automatically pushed to an endpoint you specify.

Let's see how it works.

Navigate to the Incidents homepage.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e037048959ffec014623c_mmG5K5y.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e037048959ffec014623c_mmG5K5y.webp)

Right-click anywhere on the Incidents headings ( **Number**, **Opened**, and **Short description**):

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e0383405bf833e59facc0_CJ9mRw7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e0383405bf833e59facc0_CJ9mRw7.webp)

It will open a context menu from where you should select **Configure** and then **Business Rules**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e039abf92ec496deedf4b_EBruzu8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e039abf92ec496deedf4b_EBruzu8.webp)

Once the Business Rules page is open, click on **New** at the top right corner to create a new business rule.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e03b0ccfec7c010c7c411_HT73Dz3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e03b0ccfec7c010c7c411_HT73Dz3.webp)

You need to name the business rule. For this tutorial, use **Send Incident**. The incident table is preselected, which works for this tutorial as this is where incidents are written to when they are created. You could also select another table.

Take note that the **Active** option is selected. This means that as soon as you create the rule, it will start listening for inserts into the Incident table.

Also select the **Advanced** checkbox to show the **Advanced Tab**, where you will put the script for this example.

Select the **When to run** tab. For **When**, choose the dropdown option **after** and select the _Insert_ checkbox. This means that you want your business rule to be executed after an insert into the incident table.

Your business rule should look as follows:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e03ca405bf800559ffd70_pCbQlqL.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e03ca405bf800559ffd70_pCbQlqL.webp)

Open the Advanced tab, leave the condition field blank, and paste in the following script:

```“javascript” language-none
(function executeRule(current, previous /*null when async*/ ) {
    try {
        var r = new sn_ws.RESTMessageV2();
        r.setEndpoint("<INSERT YOUR WEBHOOK URL HERE>");
        r.setHttpMethod("post");

        var usr = new GlideRecord('sys_user');

        var number = current.getValue("number");
        var opened_at = current.getValue("opened_at");
        var impact = current.getValue("impact");
        var urgency = current.getValue("urgency");
        var short_description = current.getValue("short_description");
        var category = current.getValue("category");
        var priority = current.getValue("priority");
        var sys_id = current.getValue("sys_id");
        var state = current.getValue("state");

        var obj = {
            "number": number,
            "opened_at": opened_at,
            "impact": impact,
            "urgency": urgency,
            "short_description": short_description,
            "category": category,
            "priority": priority,
            "sys_id": sys_id,
            "state": state
        };

        var body = JSON.stringify(obj);
        gs.info("Webhook body: " + body);
        r.setRequestBody(body);

        var response = r.execute();
        var httpStatus = response.getStatusCode();
    } catch (ex) {
        var message = ex.message;
        gs.error("Error message: " + message);
    }

    gs.info("Webhook target HTTP status response: " + httpStatus);

})(current, previous);
```

It should look like this:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e0452c9e583ab27683ad6_dB8uGMV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e0452c9e583ab27683ad6_dB8uGMV.webp)

This script gets the current incident details using the `current keyword`. In this example, it gets the incident _number_, _opened\_at_, _impact_, _urgency_, _short\_description_, _category_, _priority_, _sys\_id_, and _state_. You will have seen these fields on the output when you ran **get\_incidents\_basic\_authentication.py** or **get\_incidents\_oauth.py**.

Make sure to replace `YOUR WEBHOOK URL HERE` with your actual endpoint URL. This is the URL of the application that will be listening for new incidents—in other words, where you want to get the incident updates. For example, this can be your Flask or FastAPI application endpoint that is listening for requests.

Once you have the script inserted, click **Submit** to create it.

To verify that your business rule was created, search for it in the list of business rules.

And congrats! When a new incident is created, the business rule will send the details of the incident to the endpoint you specified.

To test this webhook, log into your Pipedream account and select **Sources**:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e046d67758a7784cbb3f6_sZ7ViWS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e046d67758a7784cbb3f6_sZ7ViWS.webp)

Click on **New** to create a new source.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e048ac07c46bb2db7d295_45mTP23.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e048ac07c46bb2db7d295_45mTP23.webp)

Click on **New Requests**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04a4aa0f1df6e57a6f41_nvMqXG6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04a4aa0f1df6e57a6f41_nvMqXG6.webp)

Name the source **ServiceNow**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04b9aa0f1dd3427a8b79_7IdF5Yq.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04b9aa0f1dd3427a8b79_7IdF5Yq.webp)

Click on **Create source**.

If the source is created successfully, you will get an endpoint URL, and Pipedream will let you know that it is waiting for an event.

Copy the endpoint URL.

Navigate to the script in your business rule from earlier and replace `YOUR WEBHOOK URL HERE` with the endpoint URL you got from Pipedream:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04f7549c8a3e889536f3_2wSOG36.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e04f7549c8a3e889536f3_2wSOG36.webp)

Now, back in your ServiceNow instance, create an incident using the following details:

- Number: INC0010013
- Short description: Demonstrating Webhook
- Urgency: 1 - High

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e053867758a8b0ccbb50c_wm2Uf2q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e053867758a8b0ccbb50c_wm2Uf2q.webp)

When you click **Submit**, the business rule will execute and send the incident details to your endpoint. You should be able to see the details of this incident as the body in your Pipedream ServiceNow source.

You should now have one event in the ServiceNow source in Pipedream.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e05537533bc243d951c6b_v0wKMmI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e05537533bc243d951c6b_v0wKMmI.webp)

If you click on the event, you can see the details of the incident that you just created in ServiceNow in the body tag. This shows that the webhook is working.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e056baa0f1d53757b97a2_vjxGRFr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/641e056baa0f1d53757b97a2_vjxGRFr.webp)

## **Conclusion**

In this article, you learned how to get incidents from the ServiceNow API with Python. You created a few incidents using the user interface and read those incidents using the API. You also learned how to retrieve incident details using webhooks.

Getting this wealth of information is important, but doing it manually for each ServiceNow product you use can be tedious. So consider [Merge](https://merge.dev/), a unified API with more than 15 integrations that include [ticketing](https://merge.dev/categories/ticketing-api) in a single API. Instead of managing several integrations, you only need to build and maintain your integration with Merge and let it handle all the new updates on partner integrations.

_Learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-incidents-servicenow-api) _._

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d1f67f27-2e70-4eae-94c7-858c9dcb3693&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0e0ad4ca-a9c3-4c3d-9663-195eafe0f4b9&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-incidents-servicenow-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d1f67f27-2e70-4eae-94c7-858c9dcb3693&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=0e0ad4ca-a9c3-4c3d-9663-195eafe0f4b9&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-incidents-servicenow-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e9c0b707-54b1-459d-b4fa-09d2fd463bab&bo=2&sid=699220c03e8d11f0be3c2baa7fd5ca87&vid=6992c7803e8d11f086b7533f25c0455d&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20Retrieve%20Incidents%20Using%20the%20ServiceNow%20API%20in%20Python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-incidents-servicenow-api&r=&lt=559&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=433680)