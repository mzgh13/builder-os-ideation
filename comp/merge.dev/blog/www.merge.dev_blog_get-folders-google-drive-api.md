---
url: "https://www.merge.dev/blog/get-folders-google-drive-api"
title: "How to GET folders from the Google Drive API in python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/get-folders-google-drive-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/get-folders-google-drive-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/get-folders-google-drive-api#)

Table of contents

[Prerequisites and project setup](https://www.merge.dev/blog/get-folders-google-drive-api#prerequisites-and-project-setup)

[Configure your app to access the Google Drive API](https://www.merge.dev/blog/get-folders-google-drive-api#configure-your-app-to-access-the-google-drive-api)

[Get Folders](https://www.merge.dev/blog/get-folders-google-drive-api#get-folders)

[Repack your app into Flask](https://www.merge.dev/blog/get-folders-google-drive-api#repack-your-app-into-flask)

[Conclusion](https://www.merge.dev/blog/get-folders-google-drive-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-folders-google-drive-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb1a6710a493b161431_Google_Drive_API_Key.webp)**How to access your API key in Google Drive**](https://www.merge.dev/blog/google-drive-api-key)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae2a8b75b1b6143228_How_to_GET_all_files_from_the_Dropbox_API.webp)**How to GET all files from the Dropbox API**](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api)

# How to GET folders from the Google Drive API in python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Imaculate Mosha

@Merge

While a cloud storage solution like Google Drive offers many benefits on its own, such as multidevice access, backup, and easy sharing, it's value gets extended when its files can be accessed by your other internal applications or your product.

To help you do just that, we'll walk through every step you should take to get all the folders in the Google Drive API using Python.

#### Integrate with any file storage solution via Merge

Simply build to Merge's Unified API to integrate your product with Google Drive—and several other popular file storage solutions.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-folders-google-drive-api)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## Prerequisites and project setup

To get started, you can install the following on your machine:

- [Python](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/latest/installation/)

You also need a [Google Cloud project](https://developers.google.com/workspace/guides/create-project) where your app will live. Create a new one or reuse an old one. Enter your preferred name and organization settings and click **Create**:

[![Screenshot of creating a project](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce804a3d015eb4b396_YCXELlV.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce804a3d015eb4b396_YCXELlV.webp)

Finally, you will need a Google account to use as the test account for this tutorial. This account will be used with Google Drive to store and retrieve folder names.

You need to create three Google Drive folders in this Google account to test your app. Sign in to [Drive](https://drive.google.com/drive/home) with the account and add the folders:

[![Create folder](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceb4ba1d8a3296bf1f_TNO5EaS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceb4ba1d8a3296bf1f_TNO5EaS.webp)

You will need to use this same account later in the tutorial when you'll be adding a test account to the Google Cloud project.

## Configure your app to access the Google Drive API

You need to configure your app to access the Drive API following the setup [instructions](https://developers.google.com/drive/api/quickstart/python#set_up_your_environment).

To enable the Google Drive API in your project, navigate to the [Google Cloud Console](https://console.cloud.google.com/apis/enableflow?apiid=drive.googleapis.com), confirm the project, and then click on **Enable**:

[![Enable API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce528f5bdca041b836_qmnseKN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce528f5bdca041b836_qmnseKN.webp)

Next, configure the OAuth consent screen, which is the screen users will see when they request permission to access their folders. Navigate to the OAuth consent screen [console](https://console.cloud.google.com/apis/credentials/consent). Select the user type—use the **External** user type for this tutorial:

[![User type](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf307edafe3c1e6a42_i28Pszd.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf307edafe3c1e6a42_i28Pszd.webp)

You are taken to the **App Information** page next. Enter your app information, which is the information that will be presented to the end user in the consent screen. Click **Save and Continue**:

[![App information](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf07321eface8ad9f7_iisQrMH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf07321eface8ad9f7_iisQrMH.webp)

You can skip **Scopes** for this tutorial, so click **Save and Continue**.

Next, you'll add test users; these are the accounts that can use the app before it is published. For this tutorial, add the Google account in which you created the Drive folders described in the Prerequisites section:

[![Test users](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceece7daf1031fbf5c_NkCJfai.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceece7daf1031fbf5c_NkCJfai.webp)

Finally, you need to create credentials that authenticate your Python application. These credentials help Google understand that the request to retrieve Drive information is coming from an authentic application.

Navigate to the [credentials console](https://console.cloud.google.com/apis/credentials) by clicking on **Credentials** on the left of your screen. You'll be creating credentials of the OAuth Client ID type to be able to access user data:

[![Create credentials](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceece7daf1031fbf60_kZ7OweN.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ceece7daf1031fbf60_kZ7OweN.webp)

In the next screen, choose **Desktop app** as the application type since you will be running the app from your desktop in this tutorial:

[![Choose **Desktop app**](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cfce8fa74555f30c75_NyWX9U1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cfce8fa74555f30c75_NyWX9U1.webp)

In the next screen, you have the option to download a JSON file with the app's credentials. Download it to the folder in which you will be developing your app:

[![Download JSON](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cfb477c05a6d50f0f2_LP4k2AQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cfb477c05a6d50f0f2_LP4k2AQ.webp)

## Get Folders

In this section, you'll write a function that calls the Google Drive API using the Google SDK library.

Create a Python file named drivedemo.py in a folder named DriveDemo and add the following content to it:

````python

```
import os.path

from google.auth.transport.requests import Request
from google.oauth2.credentials import Credentials
from google_auth_oauthlib.flow import InstalledAppFlow
from googleapiclient.discovery import build
from googleapiclient.errors import HttpError

SCOPES = ["https://www.googleapis.com/auth/drive.metadata.readonly"]

def getCredentials():
creds = None
# The file token.json stores the user's access and refresh tokens, and is
# created automatically when the authorization flow completes for the first
# time.
if os.path.exists("token.json"):
    creds = Credentials.from_authorized_user_file("token.json", SCOPES)
# If there are no (valid) credentials available, let the user log in.
if not creds or not creds.valid:
    if creds and creds.expired and creds.refresh_token:
      creds.refresh(Request())
    else:
      flow = InstalledAppFlow.from_client_secrets_file(
          "credentials.json", SCOPES
      )
      creds = flow.run_local_server(port=0)
    # Save the credentials for the next run
    with open("token.json", "w") as token:
      token.write(creds.to_json())
return creds

def getFolders():
"""Shows basic usage of the Drive v3 API.
Returns all the folders user has access to
"""

folders = []

try:
    service = build("drive", "v3", credentials=getCredentials())
    page_token = None

    while True:
      # Call the Drive v3 API
      results = (
          service.files()
          .list(q="mimeType = 'application/vnd.google-apps.folder'",
                spaces="drive",
                fields="nextPageToken, files(id, name)",
                pageToken = page_token)
          .execute()
      )
      items = results.get("files", [])
      for item in items:
        folders.append(item['name'])

      if page_token is None:
        break
except HttpError as error:
    print(f"An error occurred: {error}")

return folders

if __name__ == "__main__":
print("Folders:\n" + "\n".join(getFolders()))
```

````

Before you can run this script, you need to install the [Google API Client](https://github.com/googleapis/google-api-python-client?tab=readme-ov-file#installation) and [Flask](https://flask.palletsprojects.com/en/3.0.x/installation/#install-flask). To do that, run the following command:

````python

```bash
pip install google-api-python-client Flask
```

````

Now run the following command to test the script: `python drivedemo.py
`

The first time you run drivedemo.py, Google's OAuth consent screen will come up, requesting permissions to the account's drive. Remember that you need to be logged in to the Google account you added as a test user account when you click on **Continue** to allow access:

[![OAuth consent screen](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf2afc96ef40e26e5f_qWkH2eA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf2afc96ef40e26e5f_qWkH2eA.webp)

The previous code snippet saves credentials to a local file called token.json to be reused for future runs. This logic is implemented in the getCredentials() method.

It authenticates with the `credentials.json` previously downloaded and the user with `token.json`.

Central to the app is the following snippet, which runs in a while loop:

````python

```
results = (
          service.files()
          .list(q="mimeType = 'application/vnd.google-apps.folder'",
                spaces="drive",
                fields="nextPageToken, files(id, name)",
                pageToken = page_token)
          .execute()
      )
```

````

`‍
` It uses the [files.list](https://developers.google.com/drive/api/reference/rest/v3/files/list) method of the REST API to pass in the query string \`mimeType = 'application/vnd.google-apps.folder\` to filter down to the folders. It extracts the \`id\` and \`name\` file fields and saves the \`page\_token\` for the next page of results.

## Repack your app into Flask

In this section, you will repackage your app into a web application so it can be accessed from the browser.

In the same folder, DriveDemo, create another file named app.py with the following content:

````python

```
from flask import Flask
from drivedemo import getFolders

app = Flask(__name__)

@app.route('/')
def home():
	return 'This is the home page'


@app.route('/folders')
def listFolders():
	folders = getFolders()
	if folders is None:
		return "No folders found."
	return "Folders:" + "".join(folders)


if __name__ == '__main__':
	app.run(debug=True)
```

````

`‍
` Your app is now running locally. You can access it by navigating to http://17.0.0.1:5000 on your browser, where you'll see the app's home page.

[![Screenshot of the home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce1fd8cc87e31d5665_bKnzeen.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348ce1fd8cc87e31d5665_bKnzeen.webp)

Navigate to http://127.0.0.1:5000/folders to see and access the folders:

[![Screenshot of the **Folders** page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf02489dc474be341a_hFtjqLr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f348cf02489dc474be341a_hFtjqLr.webp)

Congrats! You now have an app that integrates with Google Drive.

You can find the code for this tutorial in [this GitHub repository](https://github.com/imaculate/DriveDemo).

Further steps could involve publicly exposing your app on web servers such as [Apache](https://apache.org/) and [Nginx](https://nginx.org/en/).

## Conclusion

As you can tell, retrieving files from Google Drive via API requests can be technically complex and time consuming to set up (and maintain!). These issues only get exacerbated when you consider the other file storage tools your clients want to integrate with your product, such as Dropbox or Box.

To help you integrate with any of your clients' file storage solutions so that your product can access their folders (among other resources), you can simply build to Merge's File Storage Unified API.

You can learn more about Merge and its Unified API by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fget-folders-google-drive-api).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Imaculate Mosha

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d2acac26-55b1-4707-b41e-30691f531adc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b33d1451-73f7-47d1-9299-8efccca63997&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-folders-google-drive-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d2acac26-55b1-4707-b41e-30691f531adc&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b33d1451-73f7-47d1-9299-8efccca63997&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-folders-google-drive-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=54882955-7204-47da-be23-525b7707ec20&bo=2&sid=2dd45be03e8e11f08fa6ab364fa81a09&vid=2dd4a3b03e8e11f094912fba40a88e23&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20folders%20from%20the%20Google%20Drive%20API%20in%20python&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fget-folders-google-drive-api&r=&lt=651&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=539680)