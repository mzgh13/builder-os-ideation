---
url: "https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr"
title: "How to automate user provisioning with Merge's Unified API and BambooHR"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#)

Table of contents

[What is BambooHR?](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#what-is-bamboohr)

[Trigger user deprovisioning with the Merge Unified API and BambooHR](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#trigger-user-deprovisioning-with-the-merge-unified-api-and-bamboohr)

[Conclusion](https://www.merge.dev/blog/automate-user-provisioning-with-merge-unified-api-and-bamboohr#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fautomate-user-provisioning-with-merge-unified-api-and-bamboohr)

##### Just for you

No items found.

# How to automate user provisioning with Merge's Unified API and BambooHR

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c722dc8eb7739cb26c1_SDK_examples.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Osinachi Chukwujama

@Merge

Merge is a Unified API platform that consolidates APIs from different services into one unified hub. With Merge, you can seamlessly gather data from a human resource information system (HRIS), applicant tracking system (ATS), and similar platforms, all in one convenient place. This is particularly convenient for software-as-a-service (SaaS) companies, enabling them to offer multiple integrations to their customers.

Merge has a number of existing integrations with different SaaS services, including HRIS providers like Workday, , and BambooHR. These integrations unlock a multitude of use cases—with automated user provisioning being one of the most popular.

To help you [automate user provisioning](https://www.merge.dev/blog/automated-provisioning) via Merge, we'll break down each step you need to follow and use BambooHR as an example.

## What is BambooHR?

BambooHR is a comprehensive directory and ATS platform designed to simplify employee management (including prospective employees). While BambooHR offers a public API, Merge helps streamline the data on BambooHR to follow its standard API spec. The data can then be accessed using the available SDKs or the Merge Unified REST API.

Merge performs periodic syncs with BambooHR, ensuring its own database aligns with the HR platform's data. This setup enables Merge to detect any changes that occur. When such changes occur, Merge can send a webhook notification. Alternatively, the connecting application has the option to manually retrieve the updated data from Merge's synced database through the API or SDK.

## Trigger user deprovisioning with the Merge Unified API and BambooHR

To help you better understand how Merge and BambooHR work together, you'll be creating a Python pipeline. This pipeline's purpose is to trigger a user deprovisioning process when BambooHR records a termination of employment.

Here's the scenario: you have a Python FastAPI application that displays daily tasks for users. When a user's employment is terminated, it's crucial to ensure they can no longer access this application. One way to achieve this is by updating the is\_active flag in the user's application. Before letting the user log on, the application checks if the flag is true.

Take a look at what you need before you begin:

### Prerequisites

To follow along with this tutorial, you need the following:

- **A** [**Merge account**](https://app.merge.dev/signup) **.**
- **A BambooHR account.** You can sign up for a [free trial](https://www.bamboohr.com/signup/) if you don't already have an account.
- **An** [**ngrok account**](https://dashboard.ngrok.com/signup) **.** You'll use this to receive webhooks from Merge. You also need to make sure [ngrok is installed on your local development machine](https://www.bamboohr.com/signup/).
- [**Python 3 installed locally**](https://www.python.org/downloads/) **.**
- **A PostgreSQL database.** You can [use a local installation](https://www.postgresql.org/download/) or create an instance in the cloud using a service like [Neon](https://neon.tech/).

Additionally, you need to clone this [GitHub repo](https://github.com/vicradon/merge-user-deprovisioning-demo) with the following command: `git clone https://github.com/vicradon/merge-user-deprovisioning-demo.gitcd merge-user-deprovisioning-demo`

You'll run all the commands for this tutorial in the merge-user-deprovisioning-demo folder. This means that if you're using [Visual Studio Code](https://code.visualstudio.com/) or any other IDE, you need to make sure your terminal points to this directory. For instance, if you run pwd in your terminal to view the current working directory, you should see something like this: /home/user/projects/merge-user-deprovisioning-demo

### Create your virtual environment and install dependencies

Following best practices, it's recommended that you create a virtual environment for this application. To do so, you'll use the [venv package](https://code.visualstudio.com/) that is part of the Python 3 standard library.

The following snippet contains the command for creating the virtual environment. It might not work as expected on your system if your system is pointing the python command to your Python 2.7 installation. If that's the case, make sure you replace python with python3.

Run the following command in your merge-user-deprovisioning-demo directory: `python -m venv venv # replace python with python3 if necessary`

After the virtual environment is created, this command adds a venv directory to the merge-user-deprovisioning-demo directory.

Next, you need to source the virtual environment, which gives you access to all the installed dependencies as executables. Run the following command for your operating system (OS) to source the virtual environment: `source ./venv/bin/activate # for Mac and Linuxsource ./venv/scripts/activate # for Windows using Git-Bash. .\venv\Scripts\activate.ps1 # for Windows using Powershell`

Install the dependencies listed in the requirements.txt file by running this command: `pip install -r requirements.txt`

On successful implementation, your output looks like this:

Collecting alembic==1.11.3

Downloading alembic-1.11.3-py3-none-any.whl (225 kB)

     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 225.4/225.4 KB 12.6 MB/s eta 0:00:00

Collecting anyio==3.7.1

Downloading anyio-3.7.1-py3-none-any.whl (80 kB)

     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 80.9/80.9 KB 32.5 MB/s eta 0:00:00

...

_Related:_ [_A guide to the process of integrating APIs_](https://www.merge.dev/blog/api-integration-process)

### Connect Merge to BambooHR

In order for Merge to communicate with BambooHR, you need to set up a connection between the two platforms. You can do this by navigating to your Merge dashboard under the **Linked Accounts** section:

[![**Linked Accounts** page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9f12d956487f2b623_RCpRi8R.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9f12d956487f2b623_RCpRi8R.webp)

On the **Linked Accounts** page, you'll see two tabs: **Production Linked Accounts** and **Test Linked Accounts**. When you're developing a new feature or testing things out, you'll want to choose **Test Linked Accounts**. After your feature has been tested, you can then link a **Production Linked Accounts**. Click on the **Test Linked Accounts** tab to get started.

On the **Test Linked Accounts** page, click on **Create Test Linked Account** to start the setup process. You'll see a modal with six steps to complete the connection process.

Before you proceed, make sure you already have a BambooHR account because Merge uses the current authenticated session of your BambooHR account to complete the linking process:

[![**Create Test Linked Account** button](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9c9a54050da425db3_g3zEGRH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9c9a54050da425db3_g3zEGRH.webp)

Clicking on the **Create Test Linked Account** button triggers a flow that takes you through the process of adding your BambooHR subdomain and authenticating it in the current browser. The first screen you'll see asks you to select a category. Since BambooHR is under the HRIS category, select **Human Resource Information Systems** from the list:

[![Select **Human Resource Information Systems**](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1ddc_8tf3zeB.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1ddc_8tf3zeB.webp)

Next, you need to select the integration, which in this case is **BambooHR**.

[![Select **BambooHR** as the SaaS application](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfaa8835429e4bed112_0LrSDTW.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfaa8835429e4bed112_0LrSDTW.webp)

After selecting **BambooHR**, you'll see a list of resources that Merge would like to access. Click on **Continue** to proceed:

[![Resources that Merge is requesting to access](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df92512b91842942715_zGV53mW.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df92512b91842942715_zGV53mW.webp)

Next, you need to choose how you want to authenticate, and there are two options: using the BambooHR website's current authenticated session or using an API key. Because it's more convenient to use the BambooHR website, go ahead and select this option:

[![Choose your authentication method](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a1f_nqA1qmN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a1f_nqA1qmN.webp)

On the next screen, you need to input your domain name so that Merge can discover the API to call. You can find your BambooHR subdomain on the BambooHR website in the address bar ( _ie_ "mailserve"):

[![BambooHR subdomain](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1e03_mJaRIbn.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1e03_mJaRIbn.webp)

Copy the subdomain and paste it into the input box on the Merge linked account flow. Then click **Submit**:

[![Set the domain name](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0bd_FGO3PqN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0bd_FGO3PqN.webp)

Click **Finish Setup** to finish your setup:

[![Setup complete screen](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1df1_zYwzt9h.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9d3b521a890fb1df1_zYwzt9h.webp)

### Add the required API keys

Now that you've connected BambooHR to Merge, it's time to obtain the API keys you need in order to complete the Merge-BambooHR integration in your local application.

On the **Test Linked Accounts** page, you should see BambooHR listed as a linked account. Refresh the page if you don't see BambooHR as an option:

[![BambooHR test linked account](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0cf_ad6e0pQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0cf_ad6e0pQ.webp)

Navigate into this linked account by clicking on the entry; then locate the API on the right:

[![Location of API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df92512b9184294281b_H9ALL4M.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df92512b9184294281b_H9ALL4M.webp)

Next, you need to copy the API key and paste it into a .env.local file in the cloned codebase. However, you don't have this file, so you need to create it from the existing .env.example file. You can either duplicate .env.example and rename the duplicate to .env.local or run the following command: `cp .env.example .env.local`

After creating the .env.local file, paste the account token from the **BambooHR Test Linked** account page to the BAMBOO\_HR\_ACCOUNT\_TOKEN value section. Your .env.local file should look something like this:

API\_KEY=BAMBOO\_HR\_ACCOUNT\_TOKEN=u6YH27nVO-iTGlrtF5-CF9IovsA19iZIEGiyGIk2uIyY6\_uOmzMEsgPOSTGRES\_URL=JWT\_SECRET=

Then on your **Merge** dashboard, click the **API Keys** section on the left:

[![**API Keys** page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a31_KQ40EJv.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a31_KQ40EJv.webp)

You are navigated to the **API Keys** page. Scroll to the bottom and click on **\+ Test Key**. This brings up a form requesting a name for the API key. Give it a name ( _eg_ "Task-List-Application-Key") and click **Create**:

[![Creating the API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df925ab947daccccc4b_cgrif17.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df925ab947daccccc4b_cgrif17.webp)

If the key creation operation worked, you'll be shown the key in a dialog like this:

[![Created key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9cf3223b7b1e7c8cf_2SwLBKf.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9cf3223b7b1e7c8cf_2SwLBKf.webp)

Copy the key and add it as the value of the API\_KEY key in your .env.local file. At this point, your file should look like this:

API\_KEY=OIz7LMrljnLDtXL2mVTSXGYqW4y1OKOuyZFz4EmVb-8IqZ-KJxCy6w

BAMBOO\_HR\_ACCOUNT\_TOKEN=u6YH27nVO-iTGlrtF5-CF9IovsA19iZIEGiyGIk2uIyY6\_uOmzMEsg

POSTGRES\_URL=

JWT\_SECRET=

### Create a settings.py file for secrets

Now that your API\_KEY and BAMBOO\_HR\_ACCOUNT\_TOKEN are set, you'll use them in the main.py and database.py files. For that reason, it makes sense to consolidate and expose them from one file. To do so, create a settings.py file in the root directory and add the following to it:

```python

from dotenv import dotenv_values

config = dotenv_values(".env.local")

API_KEY=config["API_KEY"]
BAMBOO_HR_ACCOUNT_TOKEN=config["BAMBOO_HR_ACCOUNT_TOKEN"]
POSTGRES_URL=config["POSTGRES_URL"]
JWT_SECRET=config["JWT_SECRET"]
JWT_ALGORITHM="HS256"

```

This code uses the dotenv\_values from the dotenv package to load environment variables from the .env.local file and then assigns them to Python variables.

### Create the PostgreSQL database and JWT secret

Now that you can access your Merge API key and BambooHR account token from the settings.py file, you need to add the PostgreSQL database URL and JSON Web Token (JWT) secret values to your .env.local file so that your application can store data and generate tokens. To add the PostgreSQL URL, [create a PostgreSQL database](https://www.postgresql.org/docs/current/sql-createdatabase.html) named merge\_demo and structure your URL like this: postgresql://:@/merge\_demo

Paste the resulting URL in the POSTGRES\_URL value field of the .env.local file.

To add the JWT secret, create a 32-bit secret in a bash shell using the following command: `openssl rand -hex 32# Outputs a random hexadecimal string that should look like f0373b9d0ac8369eb0b5887e18174af17d1c075a272cc1450244294734ecee43`

If you don't have access to a bash shell, [use this online hex generator on Replit](https://replit.com/@Vicradon/openssl-random-bit-generator).

After obtaining the 32-bit hex, paste it into your .env.local file as a value of the JWT\_SECRET key. With every value supplied for the available keys, the file should look similar to the following:

API\_KEY=W2hck--9wEP6Gb8hUl9-hF6BSDw4zpsOYnoRfjfr1syfJqORL9sgnw

BAMBOO\_HR\_ACCOUNT\_TOKEN=u6YH27n98-iTGlrtF5-CF9IovsA19iZIEGiyGIk2uIyY6\_uOmzMEsg

POSTGRES\_URL=postgresql://postgres:password@127.0.0.1/merge\_demo

JWT\_SECRET=b3f0667ec2ff0b2adf0a0da841b31556dc662b1e9da30089e66456a553c89511

### Fetch employee data updates from Merge

Merge performs periodic syncs to match up its data with data on configured integrations. Since BambooHR is integrated, Merge can fetch all employees based on when they were last modified and check which of those have been terminated based on their termination\_date and employment\_status properties.

After Merge performs its sync with BambooHR, you can fetch all the synced employee data using the SDK. You can achieve this by defining a function in your main.py file called fetch\_updated\_data and then adding the following to the function's definition:

```python

# fetch updated dataasync def fetch_updated_data(last_sync_timestamp, cursor=None, page_size=None):   modified_employees = client.hris.employees.list(modified_after=last_sync_timestamp,cursor=cursor, page_size=page_size)   return modified_employees

```

This function uses the [list method](https://docs.merge.dev/hris/employees/#employees_list) under the HRIS module of the Merge SDK. last\_sync\_timestamp is passed as an argument and fetches all the employees that have been modified since the last sync. You can set the sync time to whatever you need it to be; for instance, if you want to sync every twenty-four hours, you could perform a time subtraction of the current datetime and the datetime twenty-four hours ago. This timestamp is then passed to the function to get all the records that have been updated and synced to Merge within the last twenty-four hours.

Now, go to BambooHR under the employee list and terminate one or two employees. If you're working in a production environment, you might want to create dummy employee details so that you don't accidentally end a real employee's employment:

[![Employees to be terminated](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0ee_TQhdbh1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed0ee_TQhdbh1.webp)

Click on one of the employees to be terminated, and you'll be taken to the employee's management page. On this page, hover over the employment status section to reveal the edit button:

[![Edit button](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a47_OXHEtwL.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a47_OXHEtwL.webp)

Once you click the edit button, it opens a dialog with a form where you can set the employment status to **Terminated**:

[![Setting the employment status to **Terminated**](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a59_9qpku4P.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9b247512d4e1e7a59_9qpku4P.webp)

Click **Save** to save your changes, and you should now see that this employee has been terminated:

[![Updated employee page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed100_lTov7ea.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047df9a8835429e4bed100_lTov7ea.webp)

Repeat the process for the second employee; then navigate to your **Merge dashboard**, and under **Test Linked Accounts**, find and click the **Resync all** button:

[![**Resync all** button](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfac9a54050da425e1b_1FVzq7B.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfac9a54050da425e1b_1FVzq7B.webp)

After syncing, you should be able to fetch updated data in your application. If you want to test to make sure the sync worked, define a function ( _i.e._ get\_employee\_modifications) that responds to an HTTP GET request and receives last\_sync\_timestamp as a query parameter:

```python

@app.get('/employee-modifications')async def get_employee_modifications(last_sync_timestamp, cursor=None, page_size=None):   updated_data = await fetch_updated_data(last_sync_timestamp, cursor, page_size)   return updated_data

```

This function uses the existing fetch\_updated\_data function but is connected to your application's routing stack through a GET request. That means if you make a GET request and set the required query parameter ( _ie_ last\_sync\_timestamp) as the current date minus one, you should get a response with the modified employees.

Before proceeding, start the application by running the following command: `python main.py`

Make sure you run this command in a shell that has the virtual environment activated.

Next, use curl to test out the employee-modifications endpoint. In this case, the GET request looks something like this:

```python

curl http://localhost:8000/employee-modifications?last_sync_timestamp=2023-08-25

```

You should get a response that looks like this:

```python

{   "next": null,   "previous": "cj0xJnA9MjAyMy0wOC0yNCsyMCUzQTU5JTNBMjcuMjQ3NzY0JTJCMDAlM0EwMA==",   "results": [       {           "id": "2f6446c5-fcda-4007-804a-85245dbd6141",           "remote_id": "46",           "employee_number": "82",           "company": null,           "first_name": "Michelle",           "last_name": "Hannon",…\
\
```\
\
### Sync updates at an interval\
\
So far, you've defined a function that can fetch employees given a last timestamp. Now, you need to periodically sync data between Merge and your application.\
\
**Please note:** Merge periodically syncs data between itself and the integrations you define on **Production Linked Accounts**. On **Test Linked Accounts**, you need to manually trigger the syncing on Merge.\
\
Regardless of whether you're using a **Production Linked Account** or **Test Linked Account**, you need to define a crontab function in your application that syncs your application data with that of Merge. The simplest implementation of this functionality is a function that uses the [fastapi\_utils @repeat\_every decorator](https://dashboard.ngrok.com/get-started/your-authtoken) to run the sync function at twenty-four-hour intervals. Define it by adding the following snippet to the main.py file:\
\
```python\
\
# sync every 24 hours@app.on_event("startup")@repeat_every(seconds=60 * 60 * 24)def sync():   now = datetime.datetime.now()   twentyfour_hours_ago = now - datetime.timedelta(hours=24)   updated_data = fetch_updated_data(last_sync_timestamp=twentyfour_hours_ago.isoformat())   deprovision_users(updated_data.results)\
\
```\
\
This sync() function runs when the app restarts and repeats once every day. That means if downtime occurs in production and the app has to restart, this function runs again to ensure proper syncing every day.\
\
The function uses two methods from the datetime module: datetime and timedelta. The deprovision\_users function is called on the updated\_data.results array. This function goes through every updated result and sets the user.is\_active flag to False. Define this function by pasting the following snippet into your main.py file:\
\
```python\
\
async def deprovision_users(users):   db = SessionLocal()   for user in users:       if user.employment_status == "INACTIVE" and user.termination_date is not None and user.termination_date <= datetime.now().isoformat():           user_in_db = get_user_by_email(db, user.work_email)           if user_in_db is not None:               user_in_db.is_active = False   db.commit()   db.close()\
\
```\
\
Pasting this code into your main.py file makes the deprovision\_users function available, which means the sync function can run. Once it runs, it deprovisions the two users you terminated earlier. If you query your database, you should find the is\_active flag set to False for both users. This prevents the terminated employees from being able to log in and fetch their tasks.\
\
### Use webhooks to fetch data\
\
Now that you've set up syncing on your local application, you can go ahead and add webhook-based syncing. This involves setting up a webhook receiver hook that receives a POST request from Merge whenever data changes on BambooHR. The behavior of the webhook can be configured on Merge.\
\
Before setting up webhooks, you want to expose your application to the internet via ngrok so that Merge can communicate with your local application. Log into your ngrok account and [find your auth token on your account dashboard](https://dashboard.ngrok.com/get-started/your-authtoken). Then run the following command to authenticate your local ngrok agent:\
\
ngrok config add-authtoken TOKEN\
\
After you authenticate your ngrok agent, run the following command: `ngrok http 8000`\
\
This command fires up ngrok and forwards port 8000 (which your FastAPI app is running at) to the internet:\
\
[![Terminal screen](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfa4ded52d4e4bcbb14_IhnjWhk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfa4ded52d4e4bcbb14_IhnjWhk.webp)\
\
Take note of the **Forwarding URL** as you'll use it in the next step. It should look something like this: https://a9a3-129-205-113-167.ngrok-free.app.\
\
Now, navigate to the Merge dashboard under the **Configure** section in the side navigation and click on the **Advanced** menu item. This takes you to a page with two tabs: **Link** and **Webhooks**. Click on **Webhooks > Add webhook**:\
\
[![Add webhook](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfacf3223b7b1e7c8e4_A7McWZ5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfacf3223b7b1e7c8e4_A7McWZ5.webp)\
\
This opens up a form where you can set the details of your webhook. Input the URL you obtained from ngrok as the **Webhook URL**:\
\
[![ngrok Webhook URL](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfa25ab947dacccccc8_9ehNU1c.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfa25ab947dacccccc8_9ehNU1c.webp)\
\
Additionally, select the **Send me instances of select data types when they're created, updated, or deleted** option under the **Changed Data** section. Finalize the process by selecting the data type as **Employee** and setting the change data mode to **Updated**:\
\
[![Webhook details](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfab247512d4e1e7a6b_BbjBMmi.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65047dfab247512d4e1e7a6b_BbjBMmi.webp)\
\
You can test that your webhook works by clicking the **Send test POST request** button to receive dummy JSON data. Finish up by clicking on **Add webhook**.\
\
With the webhook added, you can go ahead and perform actions in your applications when changes are detected on Merge. All you need to add to your main.py file is the following snippet:\
\
```python\
\
# respond to webhook requests@app.post('/employee-modifications')async def respond_to_employee_modification_webo(webhook_object: Dict[str, Any]):   deprovision_users([webhook_object.data])\
\
```\
\
To test the webhook functionality, make a change in BambooHR and manually trigger a sync on Merge. The webhook is fired when any employee object modified on BambooHR is synced to Merge. Your FastAPI app then performs user deprovisioning if it detects that the employment status is **INACTIVE** and the termination date is less than or equal to the current date.\
\
## Conclusion\
\
In this tutorial, you learned how to carry out an employee termination in a task-list application. While this use case is straightforward, the actual process isn't easy. You need to establish a method to periodically verify data updates and inform the task-list application of these changes. [Merge](https://merge.dev/) plays a pivotal role in simplifying this process. It detects modifications in BambooHR and then relays updated notifications via webhooks or through a simple data sync.\
\
Merge simplifies the process of connecting to different platforms and services, including BambooHR, Workable, [Breezy](https://www.merge.dev/integrations/breezy), Jira, and [QuickBooks](https://www.merge.dev/integrations/quickbooks-online). Merge allows you to focus on your business logic, removing the need to maintain integration code. [Try it out for free today](https://app.merge.dev/signup)!\
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
Osinachi Chukwujama\
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
![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d5dd4c78-c85f-468a-96cf-8d6e8b99eaa4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=81afeb22-0ef6-4359-922c-0f3b48123dfd&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-provisioning-with-merge-unified-api-and-bamboohr&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d5dd4c78-c85f-468a-96cf-8d6e8b99eaa4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=81afeb22-0ef6-4359-922c-0f3b48123dfd&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-provisioning-with-merge-unified-api-and-bamboohr&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)\
\
td.doubleclick.net\
\
# This site can’t be reached\
\
**td.doubleclick.net** unexpectedly closed the connection.\
\
Try:\
\
- Checking the connection\
- [Checking the proxy and the firewall](chrome-error://chromewebdata/#buttons)\
\
ERR\_CONNECTION\_CLOSED\
\
Reload\
\
\
Details\
\
\
Check your Internet connection\
\
Check any cables and reboot any routers, modems, or other network\
devices you may be using.\
\
Allow Chrome to access the network in your firewall or antivirus\
settings.\
\
If it is already listed as a program allowed to access the network, try\
removing it from the list and adding it again.\
\
If you use a proxy server…\
\
Go to\
the Chrome menu >\
Settings\
>\
Show advanced settings…\
>\
Change proxy settings…\
and make sure your configuration is set to "no proxy" or "direct."\
\
**td.doubleclick.net** unexpectedly closed the connection.\
\
![](<Base64-Image-Removed>)![](<Base64-Image-Removed>)\
\
![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=c05b9a84-5a67-4d41-97f4-7e0d839b7a20&bo=2&sid=3b7d8b003e8e11f08bd2d532c5e05149&vid=3b7e5ed03e8e11f0a575f744fdc16d13&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20automate%20user%20provisioning%20with%20Merge%27s%20Unified%20API%20and%20BambooHR&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fautomate-user-provisioning-with-merge-unified-api-and-bamboohr&r=&lt=393&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=240907)