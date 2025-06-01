---
url: "https://www.merge.dev/blog/get-org-charts-from-hr-systems"
title: "How to get org charts from HR systems"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-org-charts-from-hr-systems#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-org-charts-from-hr-systems#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-org-charts-from-hr-systems#)

Table of contents

[What is Merge?](https://www.merge.dev/blog/get-org-charts-from-hr-systems#what-is-merge)

[Using Merge to unify HRIS data](https://www.merge.dev/blog/get-org-charts-from-hr-systems#using-merge-to-unify-hris-data)

[Conclusion](https://www.merge.dev/blog/get-org-charts-from-hr-systems#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-org-charts-from-hr-systems)

##### Just for you

No items found.

# How to get org charts from HR systems

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cedb4179a1346be45b1_How_to_get_org_charts_from_HR_systems.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Ndafara Tsamba

@Merge

Even though human resource information systems (HRISs) serve as central repositories of employee data, the data a specific HRIS captures and manages varies depending on the capabilities of the system and the organization or team that uses it. This makes unifying or integrating data from various HR systems a complex endeavor. Something as simple as pulling data from different HR systems for an internal org chart can quickly become a nightmare.

Firstly, various types of employee data—from information about recruitment, qualifications, and performance to attendance and payroll data—must be gathered across several systems using different APIs. Inconsistent and duplicate data is also common, especially if different functions manage different systems. You might also deal with inaccurate and outdated data as teams who maintain records across several systems often prioritize maintaining some, such as payroll, over less critical ones.

In this article, you'll learn more about how to use Merge, a Unified API platform, to overcome these challenges. You'll also see how to get the employee data you'd need to build an org chart from three well-known HRIS systems— [BambooHR](https://merge.dev/integrations/bamboohr), [BreatheHR](https://merge.dev/integrations/breathe), and [Humaans](https://merge.dev/integrations/humaans).

Note: we're using these HRISs because they offer free trial accounts. You can easily adapt the tutorial to use any of the [more than fifty other HRISs that Merge integrates with](https://www.merge.dev/categories/hr-payroll-api), including [UKG Pro](https://merge.dev/integrations/ukg-pro), [Paylocity](https://merge.dev/integrations/paylocity), and more.

## What is Merge?

Merge is a Unified API platform that allows you to integrate with multiple categories of third-party software, including HRISs, CRMs, accounting software, ticking software, and marketing automation software, with a single API.

Merge makes it much easier to unify your HR systems. In addition to being easy to use and scalable, it's designed to simplify integrations by:

- providing a single schema for all the data that is synced between your applications. This makes it easy to build and maintain integrations as you don't need to worry about different schemas for different platforms
- allowing you to customize the sync frequency for each integration to improve performance and reduce costs
- supporting webhooks so you can be notified when changes are made to data in your applications, which is useful for triggering workflows or sending notifications
- securing and protecting your information, which is especially important when you're working with confidential employee data. It does so through data encryption at rest as well as in transit, personally identifiable information (PII) protection, multi region infrastructure, and compliance with GDPR, SOC 2 Type II, ISO 27001, and HIPAA

_Related:_ [_What is a universal API?_](https://www.merge.dev/blog/universal-api)

### Benefits of using Merge to unify HR data

Using Merge to unify HR data across your organization has many benefits. First, it ensures data consistency and accuracy across integrated systems. Developers can use Merge's data transformation capabilities to map and standardize data from different sources, aligning it with a unified data model. This results in reliable and consistent HR data, reducing the risk of errors and discrepancies.

It also simplifies the integration and development process. Merge's standardized endpoints and data models allow you to save time and effort by leveraging prebuilt connectors and APIs that abstract away the complexities of integrating different HR systems. By providing a single interface for accessing and manipulating HR data from various sources, developers do not need to work with multiple APIs or [custom integration solutions](https://www.merge.dev/blog/custom-api-integration), leading to a more streamlined development workflow.

Merge offers scalability and flexibility to handle growing data volumes and accommodate future changes in HR systems. The Merge infrastructure and architecture let you handle large data sets and increasing API traffic. If your organization adopts new HR systems or existing ones are updated, using Merge ensures continued data integration and unification without extensive redevelopment efforts.

Unifying data from HR systems can also benefit employees and HR professionals if it's used to simplify access, reduce training needs, and promote self-service capabilities.

## Using Merge to unify HRIS data

Let's return to our use case of needing to pull employee data from three different HRISs to build an org chart and see how Merge can simplify the process.

### Prerequisites

To follow this tutorial, you need the following:

- Accounts for the three HRISs you'll be using in this tutorial
- You can sign up for a [seven-day free trial with BambooHR](https://www.bamboohr.com/signup/)
- You can sign up for a [fourteen-day trial with BreatheHR](https://www.bamboohr.com/signup/). _This one requires you to provide your contact number in the correct format_
- You can sign up [for a free trial for Humaans](https://app.humaans.io/signup)

You also need a free [Merge account](https://app.merge.dev/signup).

This tutorial uses the [Merge Python SDK](https://pypi.org/project/mergepythonclient/) version 0.2.6+, so you need to have Python installed. Make sure you're using Python version 3.11 or later. You can run the command `` `python --version` `` to see which Python version you have: ```` ```bashPython 3.11.0``` ````

### Link the HR systems

Before you can use Merge's Unified API to interact with an HR system, you must link it with Merge.

Start by logging in to your Merge account, then select **Linked Accounts** and click on **Test Linked Accounts**. For production, you would have clicked on **Production Linked Accounts**.

[![Linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bceb4c8343d9b842b_MrL47Er.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bceb4c8343d9b842b_MrL47Er.webp)

If you've not used Merge before, there will be no linked accounts. Click on **Launch Test Link**. In the dialog box that opens, click on **View more** under **Human Resource Information System**.

[![Select category](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bcecceea1c4736ce2_qWZaSON.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bcecceea1c4736ce2_qWZaSON.webp)

In the **Select Integration** dialog that comes up, click on **BambooHR**.

[![Select integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bbc0779a09c50913d_QQVqlN7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bbc0779a09c50913d_QQVqlN7.webp)

Setting up the integration can take a bit of time.

[![Setting up integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bde89a1233ff96dca_gvsoywO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bde89a1233ff96dca_gvsoywO.webp)

When that's complete, Merge will ask you for read access to certain types of data in the relevant HR system.

[![Access request to BambooHR](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b461bd44aedc8b6f9_0JTZfH2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b461bd44aedc8b6f9_0JTZfH2.webp)

After clicking **Continue**, you will choose the authentication method you want to use. Use the recommended default of authenticating through BambooHR's website.

[![Authentication to BambooHR](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b77d8c613f058c4b3_XSlyobt.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b77d8c613f058c4b3_XSlyobt.webp)

Click on **Next** and then enter your BambooHR subdomain as prompted.

[![BambooHR sign in with subdomain](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c46f4af37c561deff_nCaWXhl.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c46f4af37c561deff_nCaWXhl.webp)

When you click on **Submit**, a dialog will open up requiring you to sign in with your BambooHR credentials.

[![BambooHR login](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79ab783888c04b2e5e4_xReNEzw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79ab783888c04b2e5e4_xReNEzw.webp)

If everything was completed correctly, you will get a confirmation that the integration was successfully set up.

[![BambooHR integration successful](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a6ea265e1f9b17036_Ytf8mdm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a6ea265e1f9b17036_Ytf8mdm.webp)

Click _Finish Setup_ to see BambooHR on your list of linked accounts.

[![Linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79946f4af37c561de1d_3MAfPWG.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79946f4af37c561de1d_3MAfPWG.webp)

#### Link BreatheHR

The steps to link BreatheHR are very similar to those used for BambooHR, so you can use the instructions in the previous section to set it up.

One difference with BreatheHR is that Merge will ask you to authenticate by pasting the BreatheHR API into a dialog box.

To locate it, log into your BreatheHR account and click **Configure** and then **Settings**. On the settings page, click on **API Setup** in the bottom right corner in the integrations section.

[![BreatheHR API setup](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bd49c5ec1692bdf1d_mLaY8Zk.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bd49c5ec1692bdf1d_mLaY8Zk.webp)

If it's disabled, you need to enable it.

[![Enable API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b492e162570633899_loCR6iJ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b492e162570633899_loCR6iJ.webp)

You will get a warning that sharing the API key will allow developer access to individuals' information, such as salary information and bank details. Select the checkbox for **I understand and want to continue** and then click **enable**.

[![BreatheHR warning](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a28f2f2aa43ac548b_y6I0Ut0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a28f2f2aa43ac548b_y6I0Ut0.webp)

This view will now show your production API Key and sandbox API key.

[![BreatheHR API keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b81fc029e7ca8a3c3_TfztOvO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b81fc029e7ca8a3c3_TfztOvO.webp)

Copy the production API key and paste it into the dialog back in Merge, and then click **Submit**.

[![Input BreatheHR API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bd6c5ee6177f091f1_UDoWiE6.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bd6c5ee6177f091f1_UDoWiE6.webp)

This will complete the integration, and if everything went well, you will get a confirmation that the integration was successfully set up.

[![BreatheHR integration successful](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a6ea265e1f9b17032_Ytf8mdm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a6ea265e1f9b17032_Ytf8mdm.webp)

Click on **Finish Setup**. You will now have two linked accounts:

[![BreatheHR listed on linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bbc0779a09c509145_eMVoFfp.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bbc0779a09c509145_eMVoFfp.webp)

#### Link Humaans HR System

The steps to link Humaans is again very similar to what you've done previously, with the only difference being in how you obtain API access tokens from Humaans.

When you're prompted to do so by Merge, get your Humaans API access token by logging in to your Humaans account as an owner of the organization. Click on the three dots on the upper left side to expand the drop-down and then click on **API access tokens**.

[![Humaans API access tokens](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bb91d4d5c92c42d69_5Nf8f84.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79bb91d4d5c92c42d69_5Nf8f84.webp)

The dialog that opens will list your tokens. If this is your first time working with Humaans, you will have no tokens, as shown below:

[![Humaans no tokens](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c956a6f9d23f0d61d_eVuC3p5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c956a6f9d23f0d61d_eVuC3p5.webp)

Click **Generate new token**. Add a label (you can use _mergeTest_) and enable all scopes, which determine which data the access token can view or modify. Then click on **Create access token**.

[![Humaans create access token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b90d6062f806a8512_7PJE8Iw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b90d6062f806a8512_7PJE8Iw.webp)

You will get a confirmation that your access token was created.

[![Humaans access token created](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79aac63e1e14403c90e_WLgIOW1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79aac63e1e14403c90e_WLgIOW1.webp)

Copy the access token and make sure to store it in a safe place as you won't be able to see it again.

Back in your Merge window, paste the access token in the dialog and click **Submit**.

[![Input Humaans API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79da2c281fcec2d4966_8rZQtgj.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79da2c281fcec2d4966_8rZQtgj.webp)

After clicking **Finish Setup**, you should now see all three linked accounts.

[![Humaans listed on linked accounts](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c24f3ebc6ed985221_lHgwRWn.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79c24f3ebc6ed985221_lHgwRWn.webp)

_Related:_ [_Common challenges of API integration management_](https://www.merge.dev/blog/api-integration-management)

### Get API key and account tokens

To make calls to Merge using the SDK, you need an API Key, which you can get by logging in to the Merge console and clicking on **API Keys**. You will then be shown the **Production Access Key** and the **Test Access Keys**.

[![API keys](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a4e89a4433e89aae8_8Z2WDFB.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79a4e89a4433e89aae8_8Z2WDFB.webp)

Since your accounts are linked to Testing, copy the default test key.

To get the account token, select **Linked Accounts** in the Merge console and click on the integration that you want to get the account token for. Let's start with BambooHR:

[![BambooHR account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b34eec8eae9b7f829_13oKiCL.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79b34eec8eae9b7f829_13oKiCL.webp)

Repeat the process to get the BreatheHR and Humaans account tokens:

[![BreatheHR account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc799ac63e1e14403c851_ZcrVYVS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc799ac63e1e14403c851_ZcrVYVS.webp)

[![Humaans account token](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79ad47e3558ace58f4f_HJGQwee.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc79ad47e3558ace58f4f_HJGQwee.webp)

### Pulling data with Merge SDK

You're now ready to use Merge's SDK to pull the employee data you need for your org chart from the three HR systems. This example is in Python, but the SDK is available in other languages, such as Java, Ruby, and Node TypeScript.

Create a new directory and name it GettingDataFromHRSystems.

Navigate to the directory and run the following command to create a virtual environment called gettingDataFromHrSystems: `python -m venv gettingDataFromHrSystems`

To activate the virtual environment on Windows, run the following command: `gettingDataFromHrSystems\Scripts\activate`

Alternatively, if you are on Linux or Mac, run the following command: `source gettingDataFromHrSystems/bin/activate`

Once the virtual environment is activated, you have to install the Merge SDK. Fortunately, the SDK is available on the Python package index Pypi.org at https://pypi.org/project/MergePythonSDK/.

To install it, simply run the following command in the same terminal where you activated the virtual environment: `pip install --upgrade MergePythonClient`

After installing the SDK, create a file called **fetch\_employees.py** in your working directory and paste in the following code:

```python

import merge
from merge.client import Merge
from pprint import pprint
import json

merge_api_token = 'YOUR_API_TOKEN'
bamboohr_account_token = 'YOUR_BAMBOOHR_ACCOUNT_TOKEN'
breathehr_account_token = 'YOUR_BREATHEHR_ACCOUNT_TOKEN'
humaans_account_token = 'YOUR_HUMAANS_ACCOUNT_TOKEN'

bamboohr_client = Merge(api_key=merge_api_token, account_token=bamboohr_account_token)
breathehr_client = Merge(api_key=merge_api_token, account_token=breathehr_account_token)
humaans_client = Merge(api_key=merge_api_token, account_token=humaans_account_token)

# Create a new list of refined employees with desired attributes
refined_employees = []

try:
    # Get the BambooHR Employees
    bamboohr_employees = bamboohr_client.hris.employees.list().dict()
    bamboohr_employees_count = len(bamboohr_employees['results'])
    pprint(f"BambooHR Employees: {bamboohr_employees_count}")

    # Get the BreatheHR Employees
    breathehr_employees = breathehr_client.hris.employees.list().dict()
    breathehr_employees_count = len(breathehr_employees['results'])
    pprint(f"BreatheHR Employees: {breathehr_employees_count}")

    # Get the Humaans Employees
    humaans_employees = humaans_client.hris.employees.list().dict()
    humaans_employees_count = len(humaans_employees['results'])
    pprint(f"Humaans Employees: {humaans_employees_count}")

    # Combine all the employees
    combined_employees = bamboohr_employees['results'] + breathehr_employees['results'] + humaans_employees['results']
    pprint(f"Total Employees: {len(combined_employees)}")

    for employee in combined_employees:
        new_employee = {
            "id": employee["id"],
            "manager": employee["manager"],
            "first_name": employee["first_name"],
            "last_name": employee["last_name"]
        }
        refined_employees.append(new_employee)

except Exception as e:
    print(f"Exception occurred: {e}")

def create_hierarchy(employees, manager_id=None):
    hierarchy = []
    for emp in employees:
        if emp['manager'] == manager_id:
            emp['subordinates'] = create_hierarchy(employees, emp['id'])
            hierarchy.append(emp)
    return hierarchy

def display_hierarchy(hierarchy):
    print(json.dumps(hierarchy, indent=4))

def display_simplified_hierarchy(hierarchy, indent=0):
    for emp in hierarchy:
        name = emp["first_name"] + " " + emp["last_name"]
        pprint(" " * indent + "- " + name)
        if emp["subordinates"]:
            display_simplified_hierarchy(emp["subordinates"], indent + 4)

complete_hierarchy = create_hierarchy(refined_employees)

display_hierarchy(complete_hierarchy)

```

Be sure to replace YOUR\_API\_KEY, YOUR\_BAMBOOHR\_ACCOUNT\_TOKEN, YOUR\_BREATHEHR\_ACCOUNT\_TOKEN, and YOUR\_HUMAANS\_ACCOUNT\_TOKEN with the values you got in the previous steps.

To execute the preceding script, run the following command: `python fetch_employees.py`

If the script executes successfully, you should get the following output:

```python

'BambooHR Employees: 30'
'BreatheHR Employees: 1'
'Humaans Employees: 30'
'Total Employees: 61'
[\
    {\
        "id": "9d138bbd-677b-4f6c-ab7d-0e775d5eb990",\
        "manager": null,\
        "first_name": "Vie",\
        "last_name": "Wag",\
        "subordinates": []\
    },\
    {\
        "id": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
        "manager": null,\
        "first_name": "Vie",\
        "last_name": "Wag",\
        "subordinates": [\
            {\
                "id": "d5974f25-ef4b-43dc-98ab-6f2a5a8fef0e",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Walter",\
                "last_name": "Silvestri",\
                "subordinates": [\
                    {\
                        "id": "4ae4ff58-57c1-4762-9bb1-fddf5c464e9d",\
                        "manager": "d5974f25-ef4b-43dc-98ab-6f2a5a8fef0e",\
                        "first_name": "Roy",\
                        "last_name": "Perrot",\
                        "subordinates": []\
                    },\
                    {\
                        "id": "54442c67-cd3e-4a2d-b57c-9e5ca57512a5",\
                        "manager": "d5974f25-ef4b-43dc-98ab-6f2a5a8fef0e",\
                        "first_name": "Vincent",\
                        "last_name": "Barni",\
                        "subordinates": []\
                    }\
                ]\
            },\
            {\
                "id": "e77f975b-b097-4c4b-b314-70f7299eeb35",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Gilbert",\
                "last_name": "Harper",\
                "subordinates": []\
            },\
            {\
                "id": "840e6fc9-1269-47f4-87e0-e3141c784b63",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Florence",\
                "last_name": "Padilla",\
                "subordinates": [\
                    {\
                        "id": "8cb3a313-2c0b-47c6-a3b1-9bb11769e63f",\
                        "manager": "840e6fc9-1269-47f4-87e0-e3141c784b63",\
                        "first_name": "Rose",\
                        "last_name": "Fisher",\
                        "subordinates": [\
                            {\
                                "id": "e8b61c98-fe43-47b6-adf5-c9064dd4d593",\
                                "manager": "8cb3a313-2c0b-47c6-a3b1-9bb11769e63f",\
                                "first_name": "Walter",\
                                "last_name": "Stefanini",\
                                "subordinates": []\
                            }\
                        ]\
                    },\
                    {\
                        "id": "43acbbcb-2dd5-4915-a8e3-6e81ee8b83b1",\
                        "manager": "840e6fc9-1269-47f4-87e0-e3141c784b63",\
                        "first_name": "Phoebe",\
                        "last_name": "Saunders",\
                        "subordinates": []\
                    }\
                ]\
            },\
            {\
                "id": "6ed6fb75-589f-492d-a155-7205223dc5d6",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Mabel",\
                "last_name": "Giuntini",\
                "subordinates": [\
                    {\
                        "id": "2c79e91e-a5ef-4c96-8efa-dd9dd7ce2eea",\
                        "manager": "6ed6fb75-589f-492d-a155-7205223dc5d6",\
                        "first_name": "Harold",\
                        "last_name": "Vink",\
                        "subordinates": []\
                    }\
                ]\
            },\
            {\
                "id": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Lelia",\
                "last_name": "Jonker",\
                "subordinates": [\
                    {\
                        "id": "c38652e9-2660-4759-a39a-6ce060cd936e",\
                        "manager": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                        "first_name": "Antonio",\
                        "last_name": "Newton",\
                        "subordinates": []\
                    },\
                    {\
                        "id": "8eade56b-f4a8-41a0-b4d9-b7f8e4c23082",\
                        "manager": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                        "first_name": "Rodney",\
                        "last_name": "Piras",\
                        "subordinates": []\
                    },\
                    {\
                        "id": "1da1f189-4ab1-4f23-850b-1e27ebc02158",\
                        "manager": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                        "first_name": "Susan",\
                        "last_name": "Bourgeois",\
                        "subordinates": []\
                    },\
                    {\
                        "id": "183689eb-7058-40ed-8953-83af99cc1858",\
                        "manager": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                        "first_name": "Jorge",\
                        "last_name": "Blom",\
                        "subordinates": []\
                    },\
                    {\
                        "id": "d781a7f0-acda-426e-ad75-6c801cd87463",\
                        "manager": "0e9880d4-e01c-4039-a93c-4091fc284346",\
                        "first_name": "Madge",\
                        "last_name": "Hodgson",\
                        "subordinates": [\
                            {\
                                "id": "6e2b9bf6-561a-4e47-ace4-6fd28623d470",\
                                "manager": "d781a7f0-acda-426e-ad75-6c801cd87463",\
                                "first_name": "Bessie",\
                                "last_name": "Miah",\
                                "subordinates": []\
                            }\
                        ]\
                    }\
                ]\
            },\
            {\
                "id": "53912410-d427-49ad-91ef-2727c5478822",\
                "manager": "c43525d6-a9bf-4b8a-af22-f99233a07bdb",\
                "first_name": "Jack",\
                "last_name": "Ueda",\
                "subordinates": []\
            }\
        ]\
    },\
    {\
        "id": "01786aec-a469-4613-b61b-8d6a477b24d6",\
        "manager": null,\
        "first_name": "Chris",\
        "last_name": "Ferrante",\
        "subordinates": []\
    },\
    {\
        "id": "b81c723d-a289-4508-9795-6d6208939d63",\
        "manager": null,\
        "first_name": "Miguel",\
        "last_name": "Klein",\
        "subordinates": []\
    },\
    {\
        "id": "aa830b6e-8aec-4209-957a-ae399f8a1704",\
        "manager": null,\
        "first_name": "Tyler",\
        "last_name": "Romani",\
        "subordinates": []\
    }\
]

```

It's worh noting that the number of employees shown can be different from yours as they are based on the number of employees within your HRIS systems as well as the relationships between them.

Merge allows you to get the data for all employees regardless of which HRIS their data is housed in. In this example, you got the data in a hierarchical way to allow you to create organization charts. However, you can use it for various other purposes, such as employee reporting and analytics or integrating with other third-party systems, such as payroll or performance management.

Leveraging this combined data offers you a seamless data flow across different HR and business systems while minimizing manual data entry and ensuring data consistency.

## Conclusion

In this article, you learned how Merge's Unified API can help you simplify this process significantly. You also saw how you can use Merge to pull employee data from three popular HR systems—BambooHR, BreatheHR, and Humaans—for the use case of building an org chart. You can easily adapt this tutorial for any of the fifty-plus other HRISs that Merge integrates with.

To explore Merge's full capabilities, [sign up to get started for free](https://app.merge.dev/signup).

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=825552e5-f2c7-4601-acd6-af8c96185b44&bo=2&sid=2bcbd8c03e8c11f08351fdcc35657561&vid=2bcc9d603e8c11f0ba36effe782e80b2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20get%20org%20charts%20from%20HR%20systems&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-org-charts-from-hr-systems&r=&lt=864&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=65143)