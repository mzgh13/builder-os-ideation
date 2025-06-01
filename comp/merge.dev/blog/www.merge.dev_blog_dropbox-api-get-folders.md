---
url: "https://www.merge.dev/blog/dropbox-api-get-folders"
title: "How to GET folders from the Dropbox API in Python"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/dropbox-api-get-folders#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/dropbox-api-get-folders#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/dropbox-api-get-folders#)

Table of contents

[Prerequisites](https://www.merge.dev/blog/dropbox-api-get-folders#prerequisites)

[Authenticating to the Dropbox folders API](https://www.merge.dev/blog/dropbox-api-get-folders#authenticating-to-the-dropbox-folders-api)

[Fetching folders from the Dropbox API in Python](https://www.merge.dev/blog/dropbox-api-get-folders#fetching-folders-from-the-dropbox-api-in-python)

[Final thoughts](https://www.merge.dev/blog/dropbox-api-get-folders#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fdropbox-api-get-folders)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae2a8b75b1b6143228_How_to_GET_all_files_from_the_Dropbox_API.webp)**How to GET all files from the Dropbox API**](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74170f0f41b729c3b7_Get_all_folders_Google_Drive_API.webp)**How to GET folders from the Google Drive API in python**](https://www.merge.dev/blog/get-folders-google-drive-api)

# How to GET folders from the Dropbox API in Python

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74f43703047123799f_Anthropic_API_key.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538592637517da99427a_62eff91f58ad1560481786c6_Max.webp)

Max Gong

Platform

@Merge

While Dropbox, the widely-used file storage solution, offers many benefits on its own—such as letting you store documents, photos, and/or videos securely and from any device and location—it offers even more value when its folders can be accessed by your other internal applications or your product.

Regardless of your specific integration use case, we'll walk through every step you should take to get folders from the Dropbox API using Python.

## **Prerequisites**

To follow along, you’ll need:

- A valid [GitHub account](https://github.com/login)
- Python version 3.10 or later
- The python requests library installed in your environment (like your laptop)

## **Authenticating to the Dropbox folders API**

To access Dropbox’s API, you’ll need a sandbox Dropbox account and an OAuth application to get your access token.

To do both, you can follow these steps:

1\. Sign up for a developer account [here](https://www.dropbox.com/developers). Click **Create apps** to sign up.

2\. Once you’re done signing up, navigate [here](https://www.dropbox.com/developers/apps) and click **Create app.** ‍

3\. Choose “Scoped access” and “Full Dropbox”, so that your app has access to all files & folders.

[![Creating an app in Dropbox](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f4aea05fb37348cfe_LNHSQ620CJujj67Th1I6RXOZ-g7VLbaXm2CSZI3Li-x_ti0d0-i39-mAzXuZu4tIgjuG2qQaJFvuTvm_PC61TQIfRtvPj9Wyp_jF7F_AygGHdm-LK61qiNCtQjuzx-_BHQMAZpJWUobO5E0DXJaozms.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f4aea05fb37348cfe_LNHSQ620CJujj67Th1I6RXOZ-g7VLbaXm2CSZI3Li-x_ti0d0-i39-mAzXuZu4tIgjuG2qQaJFvuTvm_PC61TQIfRtvPj9Wyp_jF7F_AygGHdm-LK61qiNCtQjuzx-_BHQMAZpJWUobO5E0DXJaozms.png)

4\. For this article, we’ll just be showing you how to access the API. So instead of implementing the full OAuth flow, we’ll generate a temporary access token. Click **Generate access token** to generate an access token. Save the token, as we’ll be using it to make API calls.

[![Generating the access token in Dropbox](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7fe73573bdb9ff4b08_Xij3PjC5whWvw0Zo6KcDnS77-rremY87O7YRJTFmUZ7kSSid1Dwk0d5gE5LHdStGstKV6eLugLZEIreanEikaV6kbkJytpY0hwn0CAYcPZysM-wQ2tF5xY015hJVV4ke_XiVrtivAWkqfT-XMbKLah4.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7fe73573bdb9ff4b08_Xij3PjC5whWvw0Zo6KcDnS77-rremY87O7YRJTFmUZ7kSSid1Dwk0d5gE5LHdStGstKV6eLugLZEIreanEikaV6kbkJytpY0hwn0CAYcPZysM-wQ2tF5xY015hJVV4ke_XiVrtivAWkqfT-XMbKLah4.png)

To get a sandbox Dropbox account, simply sign up for a free account [here](https://www.dropbox.com/register).

_Related:_ [_How to get your Dropbox API key_](https://www.merge.dev/blog/dropbox-api-key)

## **Fetching folders from the Dropbox API in Python**

Dropbox uses bearer tokens to make authenticated calls. For any request you make, you’ll need to add `“Authorization: Bearer {ACCESS_TOKEN}”`, where {ACCESS\_TOKEN} is the token you retrieved when creating your Dropbox OAuth application in the previous step.

### 1\. Retrieve your root namespace ID

At the highest level, Dropbox is organized by namespaces. To access folders, you need your root namespace id.

To access that, make the following API call: `POST https://api.dropboxapi.com/2/users/get_current_account`

In the response body, you’ll see root\_namespace\_id under root\_info field. This defines your root namespace id.

[![API call to retrieve your root namespace AI](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104888bff769f5c49675eb_QIkZtFKL5yRJJdRUsXAe0leuX3ALUp0-BL3mulZe3v0ferCTW4W_uegzIcLAY4Eibytadefg4r_TnDUUut4jVAD0gES1V00K_HC6oHXeyBgEuDVZe7sHFOI65EhLnNKI1H2O3lLaOWytJYdq9HPOQYE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104888bff769f5c49675eb_QIkZtFKL5yRJJdRUsXAe0leuX3ALUp0-BL3mulZe3v0ferCTW4W_uegzIcLAY4Eibytadefg4r_TnDUUut4jVAD0gES1V00K_HC6oHXeyBgEuDVZe7sHFOI65EhLnNKI1H2O3lLaOWytJYdq9HPOQYE.webp)

### 2\. Get your root-level folders

Your root-level folders exist at the top-level of your namespace.

To retrieve them, make the following API call:

`method = POST`

`url = https://api.dropboxapi.com/2/files/list_folder` `data = {"path": "ns:YOURROOTNAMESPACEID", "limit": 2000”, "recursive": false}` `headers= 'Dropbox-API-path_Root: {".tag": "root", "root": "YOURROOTNAMESPACEID"}'`

[![how to get your root-level folders](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104889aa856c2369280b60_t8fB9251mAZ8Q3vxDwfiOyZ4-bn89vh7WP3pNWyL8wRI3A_MnC5og-cuY-pAW17R4pee143HYyKTChnJQfyUqk9eDjebtb4ciPxBoo8_mncMPSEVUziFX5no94oV4Yijni1fqxULFbTwm9Pc3rFYdoc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104889aa856c2369280b60_t8fB9251mAZ8Q3vxDwfiOyZ4-bn89vh7WP3pNWyL8wRI3A_MnC5og-cuY-pAW17R4pee143HYyKTChnJQfyUqk9eDjebtb4ciPxBoo8_mncMPSEVUziFX5no94oV4Yijni1fqxULFbTwm9Pc3rFYdoc.webp)

- Enter your root namespace id in the text where YOURROOTNAMESPACEID is mentioned.
- “limit” indicates the page size returned.
- “recursive=false” indicates that we don’t want to fetch all children of the root namespace, just the immediate children. Dropbox’s API “recursive=true” doesn’t provide a reliable way to understand a folder’s hierarchy, so we'll traverse it ourselves.
- “Path” indicates the path to the namespace where you want to access folders, in this case the root namespace.
- “Dropbox-API-path\_Root” indicates the namespace you’re trying to access.
- When parsing the response, you’ll notice objects with ”.tag”: “folder” and ”.tag”.: “file”. In your code, you’ll want to write an if-else loop that only looks for ”.tag”: “folder”.

### 3\. Process folders at the root level

Let’s say you get more than 2000 folders at the root-level. In the previous response, you’ll see a cursor value. To paginate, make the following API call:

`method = POST`

`url = https://api.dropboxapi.com/2/files/list_folder/continue` `data = {“cursor”: YOURCURSORFROMPREVIOUSRESPONSE}` `headers = 'Dropbox-API-path_Root: {".tag": "root", "root": "YOURROOTNAMESPACEID"}'`

- You’ll notice that this is a different endpoint and request body. Dropbox API essentially offers 2 endpoints to process folders & files—one to process the initial page and another to process any subsequent pages.
- Continue calling this endpoint with the provided cursor until has\_more=False

[![The API request for processing folders at the root level](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104888b526d17519a9f479_GrUo9694_Y9HNPzlLsKOLvhZZUmNN45O5YSr0uDhGd0jLst541Wx5Fx2YXXc5a8OsD0-IRfhdR_gwSLSu6bnGQxmPb0CCGFw7Kc1JnmyXBpUHB0PXnPMHxzwkkLPO9q3mdeSYTmUzOCCVSeEw5yn_78.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66104888b526d17519a9f479_GrUo9694_Y9HNPzlLsKOLvhZZUmNN45O5YSr0uDhGd0jLst541Wx5Fx2YXXc5a8OsD0-IRfhdR_gwSLSu6bnGQxmPb0CCGFw7Kc1JnmyXBpUHB0PXnPMHxzwkkLPO9q3mdeSYTmUzOCCVSeEw5yn_78.webp)

_Related:_ [_A guide to file storage APIs_](https://www.merge.dev/blog/file-storage-api)

### 4\. Process the folders within a folder

Now let’s get folders within folders.

To do so, make the following API call:

`method = POST`

`url = https://api.dropboxapi.com/2/files/list_folder` `data = {"path": "THEFOLDERID", "limit": 2000”, "recursive": false}` `headers = 'Dropbox-API-path_Root: {".tag": "root", "root": "YOURROOTNAMESPACEID"}'`

[![API call for processing folders within a folder](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/661048880faf5f942a64e85c_-HukdpdKR9NSgNj4AeC6uonjdt15COzLuC3p1R6I3wy6GZWZZct8g2ZBERBgB9RQNilyoWo06KBnOvn43weVy13otdJvUgC2upMaEJsnGSUVUZBpMKJZvKr0y5x3n4m1a5vqFzWXf4RbuFyNGE1ABxs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/661048880faf5f942a64e85c_-HukdpdKR9NSgNj4AeC6uonjdt15COzLuC3p1R6I3wy6GZWZZct8g2ZBERBgB9RQNilyoWo06KBnOvn43weVy13otdJvUgC2upMaEJsnGSUVUZBpMKJZvKr0y5x3n4m1a5vqFzWXf4RbuFyNGE1ABxs.webp)

- Replace THEFOLDERID with the id of the folder whose children you want to process.

- Use the same pagination method we talked about previously.

The final python code may look something like what's shown below. We can use depth-first search—which can be more reliable than breadth-first search—so that you know which root-level folder is done being processed or not (i.e. more accurately track progress).

```python

import requests

# Replace 'YOUR_ACCESS_TOKEN' with your actual Dropbox API token
ACCESS_TOKEN = 'YOUR_ACCESS_TOKEN'

def get_root_namespace_id():
    url = "https://api.dropboxapi.com/2/users/get_current_account"
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}"
    }
    response = requests.post(url, headers=headers)
    response_data = response.json()
    return response_data["root_info"]["root_namespace_id"]

def list_folder(path, root_namespace_id):
    url = "https://api.dropboxapi.com/2/files/list_folder"
    data = {
        "path": path,
        "limit": 2000,
        "recursive": False
    }
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}",
        "Content-Type": "application/json",
        "Dropbox-API-Path-Root": f'{{".tag": "root", "root": "{root_namespace_id}"}}'
    }
    response = requests.post(url, json=data, headers=headers)
    return response.json()

def list_folder_next_page(cursor, root_namespace_id):
    url = "https://api.dropboxapi.com/2/files/list_folder/continue"
    data = {
        "cursor": cursor
    }
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}",
        "Content-Type": "application/json",
        "Dropbox-API-Path-Root": f'{{".tag": "root", "root": "{root_namespace_id}"}}'
    }
    response = requests.post(url, json=data, headers=headers)
    return response.json()

def process_folders(root_namespace_id):
    folders = []
    # Initialize stack with the root namespace ID
    stack = [f"ns:{root_namespace_id}"]
    while stack:
        current_path = stack.pop()
        entries = []
        response_data = list_folder(current_path, root_namespace_id)
        entries.extend(response_data.get("entries", []))
        hasMore = response_data.get("hasMore")
        cursor = response_data.get("cursor")
        # Process folders in next pages, if any
        while hasMore:
           response_data = list_folder_next_page(cursor, root_namespace_id)
           entries.extend(response_data.get("entries", []))
           hasMore = response_data.get("hasMore")
           cursor = response_data.get("cursor")
	    for entry in entries:
            if entry[".tag"] == "folder":
                folders.append(entry)
                # For DFS, add the folder's path to the stack
                stack.append(entry["id"])
    return folders

def main():
    root_namespace_id = get_root_namespace_id()
    folders = process_folders(root_namespace_id)
    print(f"Found {len(folders)} folders")

if __name__ == "__main__":
    main()

```

## Final thoughts

As you can tell, retrieving folders from Dropbox via API requests can be technically complex and time consuming to set up (and maintain!). These issues only get exacerbated when you consider the other file storage tools your clients want to integrate with your product, such as Box or Google Drive.

To help you integrate with any of your clients' file storage solutions so that your product can access their folders (among other resources), you can simply build to [Merge's File Storage Unified API](https://www.merge.dev/categories/file-storage-api).

You can learn more about Merge and its Unified API by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fdropbox-api-get-folders).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Max Gong

Platform

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3c8038ac-079f-426b-abcf-05ef528847a8&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=90b2f424-653f-43a3-b5c8-1c04cf0bf7ab&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fdropbox-api-get-folders&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=3c8038ac-079f-426b-abcf-05ef528847a8&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=90b2f424-653f-43a3-b5c8-1c04cf0bf7ab&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fdropbox-api-get-folders&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)