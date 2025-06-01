---
url: "https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api"
title: "How to add a subscriber (and more) with the Mailchimp API"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#)

Table of contents

[Setting Up the Environment](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#setting-up-the-environment)

[Authentication](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#authentication)

[Testing Your Setup](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#testing-your-setup)

[Creating a New Subscriber](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#creating-a-new-subscriber)

[Updating and Deleting Subscribers](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#updating-and-deleting-subscribers)

[Managing Lists and Campaigns](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#managing-lists-and-campaigns)

[Conclusion](https://www.merge.dev/blog/how-to-add-a-subscriber-and-more-with-the-mailchimp-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-add-a-subscriber-and-more-with-the-mailchimp-api)

##### Just for you

No items found.

# How to add a subscriber (and more) with the Mailchimp API

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cafe4e321d978c26d34_Marketing_Automation_-_How_to_Add_a_Subscriber_with_the_Mailchimp_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Alen Kalac

@Merge

# How to Add a Subscriber (and More) with the Mailchimp API

Among all email marketing automation platforms, [Mailchimp](https://mailchimp.com/) is by far the most popular, with a [market share of 66 percent](https://www.datanyze.com/market-share/email-marketing--13) and over [10,000 emails sent every second](https://www.emailaudience.com/what-is-mailchimp/).

If you want to build custom features for Mailchimp or integrate it with third-party applications, plugins, and services, you can use the Mailchimp API to programmatically interact with Mailchimp. The Mailchimp API has numerous features, so you can use it to create campaigns, create and manage lists, automate workflows, and much more.

In this article, you'll learn how to use the Mailchimp API even if you've never used it before. You will see how to create a Mailchimp account, install the necessary packages and libraries to work with the API, obtain an API key, authenticate with the API, create new subscribers, update or delete existing subscribers, and manage your lists and campaigns.

Let's dive in!

## Setting Up the Environment

Before you can use the Mailchimp API, you need to set up the necessary environment.

First, you need to create a Mailchimp account. Mailchimp offers multiple plans and prices depending on your needs and the number of contacts you have. It's free to use for up to 500 contacts and 1,000 monthly emails, so you can [sign up for a free account](https://login.mailchimp.com/signup/) for this tutorial if you don't yet have one.

The free account gives you access to more than 300 integrations, reporting and analytics, forms and landing pages, some prebuilt email templates, and email support for the first 30 days. However, only one user can use the account and you can create only one audience.

[![Mailchimp sign-up page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935926df5ea28dc451ba32_xveCNGl.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935926df5ea28dc451ba32_xveCNGl.webp)

On the sign-up page, enter your email, username (Mailchimp recommends that you use your email as your username), and a password. You'll receive an email with a link to activate your account. Click on the link to take you to a page (pictured below) where you'll be asked to enter your first name, last name, business name, and optionally, your phone number. These details can be easily changed later on, so don't overthink it.

[![Mailchimp account setup page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/649359a6c994b9ab690ae5cd_35b4gM3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/649359a6c994b9ab690ae5cd_35b4gM3.webp)

You'll also have to enter your address, city, and country as required by the [US CAN-SPAM Act](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business), which stipulates that your address must appear in the footer of every email you send, whether with Mailchimp or any other email service provider. The aim of this act is to protect users from spam. If your business doesn't have a physical address, check out some of the [alternatives Mailchimp suggests](https://mailchimp.com/help/alternative-physical-address-ideas/).

You can skip the questions Mailchimp asks to get to know your business better. You'll be prompted to choose between staying with the free plan or upgrading to a paid plan. You can stick with the free plan for this tutorial, for which you don't have to provide any payment information.

Before you can use the Mailchimp API, you also have to install some packages and libraries. The specific ones needed, if any, depend on the programming language you use. Since this tutorial uses Python, you only need to install the `mailchimp-marketing` client library.

Install this library using the following line:

```python
pip install mailchimp-marketing
```

## Authentication

Once you have created a Mailchimp account, you can obtain an API key for yourself, which you'll use to authenticate your requests to the Mailchimp API.

To generate an API key, you need to navigate to the API keys section of your account. Click on your profile picture on the top right of the screen and then on **Profile**.

[![Mailchimp account dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a5533510cf98882801e_4vAiJLA.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a5533510cf98882801e_4vAiJLA.webp)

Click on the drop-down menu for the **Extras** tab and then on **API Keys**.

[![Mailchimp profile page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55e1c7b7a4a95f1bf7_L03Eeex.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55e1c7b7a4a95f1bf7_L03Eeex.webp)

This page will show any API keys you might have. You can also generate new keys here as well as review or revoke existing ones. Since you don't have any API keys at this point, click on **Create A Key**.

[![Mailchimp API keys page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55cb6dd7cfc8b2d71a_HSt2zNS.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55cb6dd7cfc8b2d71a_HSt2zNS.webp)

You have to name the key before you can generate it. Always use a descriptive name so that you can remember what the key is for. Name your key for this tutorial **Merge**, then click on **Generate Key**.

[![Creating a new API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55bdc74cb461fb7ebb_MXd48X2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a55bdc74cb461fb7ebb_MXd48X2.webp)

Copy and save the API key somewhere secure, as you would an important password.

_Note:_ You won't be able to see this key again. Only its name and first four digits will be shown. If you lose the key, you'll have to generate a new one and update it everywhere the lost API key was used.

[![A generated API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9da3ee1b9a5cac66f4_Vmza4yd.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9da3ee1b9a5cac66f4_Vmza4yd.webp)

If you now check the API keys section, you'll see the key you just created. As you can see, only its name and the first four digits are visible. You can revoke the API key or create new ones if needed in the future.

[![Mailchimp API keys section](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9d3ee9d7eb808e8d3f_QtmExH5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9d3ee9d7eb808e8d3f_QtmExH5.webp)

## Testing Your Setup

Before you start using the Mailchimp API to manage your lists and campaigns, it's a good idea to first test if you've set up everything correctly. The best way to do this with the Mailchimp API is to make a request to the ping endpoint. Doing so has no effect on your account. It only acts like a test to check whether everything's set up as it should be.

You can make a request to the ping endpoint with the following piece of code from the [Mailchimp documentation](https://mailchimp.com/developer/marketing/guides/quick-start/):

```python
from mailchimp_marketing import Clientmailchimp = Client()mailchimp.set_config({  "api_key": "YOUR_API_KEY",  "server": "YOUR_SERVER_PREFIX"})response = mailchimp.ping.get()print(response)
```

Remember to change the `api_key` and `server` in this code. For the `api_key`, copy and paste the API key that you previously generated. For the `server`, log in to Mailchimp and look at the URL in your browser. It should look similar to this:

[![Mailchimp profile URL](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9dca115e9b6edb5c6b_JRL1GgJ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935a9dca115e9b6edb5c6b_JRL1GgJ.webp)

The part that comes before the `.admin.mailchimp.com` is your server prefix. In the case of this tutorial, that's `us12`, so that's what will be inputted as the value for `server`. You'll have to input the value that you find in your browser, which may or may not be the same as the one in this tutorial, into your code.

If you've set up everything correctly and inputted the correct `api_key` and `server`, running the piece of code above will give you the following response:

```python
{'health_status': "Everything's Chimpy!"}
```

## Creating a New Subscriber

Now that everything is set up correctly, you can proceed with creating new subscribers, updating or deleting existing ones, managing your lists and campaigns, and much more. Let's start with creating new subscribers.

To add a subscriber, you need a list to which you can add them. Mailchimp creates a list (or an _audience_—the Mailchimp API uses the two terms interchangeably) by default when you create your account.

To manage this audience, you'll need its ID, so the first step is to find it. From your **Dashboard**, navigate to the **Audience** drop-down menu and then to **All contacts**.

[![Mailchimp dashboard](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14c732705e0da8ec07_iFxOh00.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14c732705e0da8ec07_iFxOh00.webp)

From there, go to the **Settings** drop-down menu and click on **Audience name and defaults**.

[![Mailchimp audience section](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b151f98c3e9e8eda7f4_oXXO3I3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b151f98c3e9e8eda7f4_oXXO3I3.webp)

This is where you can see your **Audience ID**.

[![Mailchimp audience settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14798906e906c6a9ac_BpXCgJP.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14798906e906c6a9ac_BpXCgJP.webp)

You can now construct a POST request that will add a subscriber to your list by running the following code that's been slightly modified from the [Mailchimp API documentation](https://mailchimp.com/developer/marketing/guides/create-your-first-audience/):

```python
import mailchimp_marketing as MailchimpMarketingfrom mailchimp_marketing.api_client import ApiClientErrormailchimp = MailchimpMarketing.Client()mailchimp.set_config({  "api_key": "YOUR_API_KEY",  "server": "YOUR_SERVER_PREFIX"})list_id = "YOUR_LIST_ID"member_info = {    "email_address": "jane.doe@example.com",    "status": "subscribed",    "merge_fields": {      "FNAME": "Jane",      "LNAME": "Doe"    }  }try:  response = mailchimp.lists.add_list_member(list_id, member_info)  print("response: {}".format(response))except ApiClientError as error:  print("An exception occurred: {}".format(error.text))
```

This example uses three fields: the contact's email address, first name, and last name. You could also add other fields, such as the address, phone number, or birthday, or you could ask for no information except the email address, not even the name.

The exact piece of code above will result in an exception since the `email_address` isn't valid. If the `email_address` had been valid, this code would have immediately added the contact "Jane Doe" with the email address "jane.doe@example.com" to the list with "YOUR\_LIST\_ID".

To test the code, replace the email address with your own. You should see the new subscriber in your **Audience Dashboard**.

[![Audience section after adding a subscriber](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14fa9906d1a6e5c8cf_YqRO4mM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b14fa9906d1a6e5c8cf_YqRO4mM.webp)

Optionally, you can change the `status` field in the code from `subscribed` to `pending`. That way, the contact won't be added to the list immediately. Instead, they will get a confirmation email, and they'll only be added to the list if they confirm the subscription.

_Note:_ Test with your own email addresses instead of random ones since you don't want to send subscription confirmation emails to random people.

## Updating and Deleting Subscribers

Once you have subscribers on your list, you can update their status or even delete them. Since you already have your API key, server prefix, and list ID, unsubscribing or updating a contact from your list is quite straightforward. All it takes to unsubscribe a contact is running the following code:

```python
import hashlibimport mailchimp_marketing as MailchimpMarketingfrom mailchimp_marketing.api_client import ApiClientErrormailchimp = MailchimpMarketing.Client()mailchimp.set_config({  "api_key": "YOUR_API_KEY",  "server": "YOUR_SERVER_PREFIX"})list_id = "YOUR_LIST_ID"member_email = "jane.doe@example.com"member_email_hash = hashlib.md5(member_email.encode('utf-8').lower()).hexdigest()member_update = {"status": "unsubscribed"}try:  response = mailchimp.lists.update_list_member(list_id, member_email_hash, member_update)  print("Response: {}".format(response))except ApiClientError as error:  print("An exception occurred: {}".format(error.text))
```

To delete a subscriber from a list, all you need to input is the `list_ID` and the `member_email`. Any email address you input into the `member_email` field will immediately be removed from the list, and you will see one less subscriber in your **Audience Dashboard**. Note, though, that the contact will stay in your audience. They will only be unsubscribed from the list.

[![Audience section after deleting a subscriber](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b73fa9906d1a6e63138_zUwYDQm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64935b73fa9906d1a6e63138_zUwYDQm.webp)

You can update the status of a subscriber as easily as deleting them. All you need to do is change the value of the `status` field in the code above from `unsubscribed` to any status you want, such as `subscribed`, `pending`, or `cleaned`.

## Managing Lists and Campaigns

Until now, all the actions you performed are on an existing list. But you can also use the Mailchimp API to create, manage, or delete lists and campaigns.

Here's an [example from the Mailchimp documentation](https://mailchimp.com/developer/marketing/guides/create-your-first-audience/) on how to create a list with the Mailchimp API:

```python
import mailchimp_marketing as MailchimpMarketingfrom mailchimp_marketing.api_client import ApiClientErrormailchimp = MailchimpMarketing.Client()mailchimp.set_config({  "api_key": "YOUR_API_KEY",  "server": "YOUR_SERVER_PREFIX"})body = {  "permission_reminder": "You signed up for updates on our website",  "email_type_option": False,  "campaign_defaults": {    "from_name": "Mailchimp",    "from_email": "freddie@mailchimp.com",    "subject": "Python Developers",    "language": "EN_US"  },  "name": "JS Developers Meetup",  "contact": {    "company": "Mailchimp",    "address1": "675 Ponce de Leon Ave NE",    "address2": "Suite 5000",    "city": "Atlanta",    "state": "GA",    "zip": "30308",    "country": "US"  }}try:  response = mailchimp.lists.create_list(body)  print("Response: {}".format(response))except ApiClientError as error:  print("An exception occurred: {}".format(error.text))
```

This code snippet may seem intimidating since many fields are required ( `name`, `contact`, `permission_reminder`, `email_type_option`, and `campaign_defaults`), but it's not as complicated as it looks:

- The `name` is what you want to call the list.
- In `contact`, you should input your business's contact information, which is required by anti-spam laws.
- The `campaign_defaults` should include the default values for created campaigns, which are **from name**, **from email**, and **subject** for emails sent to the list, as well as the default language for the list's forms.
- The `permission_reminder` should show the subscriber where they subscribed to your email list. (People often forget that they've subscribed to a certain email list!)
- The `email_type_option` sets whether subscribers can choose the format of the email (if set to **True**) or if they'll receive HTML emails (if set to **False**).

Remember that you can have only one audience on the free plan, though. Since you already have the default one, you won't be able to create new ones. If you want to add a new audience with the Mailchimp API using the free plan, make sure to delete your default audience from the **Audience Dashboard**.

Updating a list is quite straightforward too. You simply need to change the information you want changed in the `body` in the code above. Once the `body` is updated, run the following piece of code, which will include your list ID:

```python
try:  response = mailchimp.lists.update_list("YOUR_LIST_ID", body)  print("Response: {}".format(response))except ApiClientError as error:  print("An exception occurred: {}".format(error.text))
```

Finally, deleting a list if you don't need it anymore is also very straightforward. All you need to know is your list ID, which you already know how to find, and then use it to run the following code:

```python
try:  response = mailchimp.lists.delete_list("YOUR_LIST_ID")  print("Response: {}".format(response))except ApiClientError as error:  print("An exception occurred: {}".format(error.text))
```

If you run this code and then check your **Audience Dashboard**, you'll see that the audience with that particular list ID is not there anymore.

Finally, let's see how to add campaigns using the Mailchimp API. Again, it is quite straightforward. You just need to decide between the [different types of campaigns](https://mailchimp.com/help/getting-started-with-campaigns/) that the Mailchimp API offers, namely **regular**, **plaintext**, **absplit**, **rss**, or **variate**.

Here's how to create a **regular** campaign:

```python
import mailchimp_marketing as MailchimpMarketingfrom mailchimp_marketing.api_client import ApiClientErrortry:  client = MailchimpMarketing.Client()  client.set_config({    "api_key": "YOUR_API_KEY",    "server": "YOUR_SERVER_PREFIX"  })  response = client.campaigns.create({"type": "regular"})  print(response)except ApiClientError as error:  print("Error: {}".format(error.text))
```

Note that this piece of code merely creates a blank campaign. It doesn't actually send the campaign to your audience. However, it's a necessary first step. Once you've created a campaign this way, you can choose to send it to your audience or to schedule it for delivery.

## Conclusion

As you've seen, it's pretty straightforward to use the Mailchimp API to add new subscribers, delete existing ones, and create and manage new lists and campaigns programmatically.

However, if your product requires you to connect not only to Mailchimp but to several marketing platforms like it, doing it all manually can be labor-intensive. [Merge's Unified API](https://merge.dev/) lets you add numerous integrations in mere days so you can focus on your core product. Apart from being quick and straightforward to use, Merge also has [extensive documentation](https://docs.merge.dev/) to make your life as easy as possible.

To get started, you can sign up for the [Merge Unified Marketing Automation API](https://merge.dev/categories/marketing-automation-api) for free.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Alen Kalac

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e87f63ec-4f89-4b76-913a-95962bcacca6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5762f2c0-8791-4a87-a05c-421f5671e3d8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-a-subscriber-and-more-with-the-mailchimp-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e87f63ec-4f89-4b76-913a-95962bcacca6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5762f2c0-8791-4a87-a05c-421f5671e3d8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-a-subscriber-and-more-with-the-mailchimp-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=222382ac-4041-4756-975a-98d842ce4474&bo=2&sid=cdc91d703e8d11f080fe81034e0af444&vid=cdc941903e8d11f0866475d04d4970ee&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20add%20a%20subscriber%20(and%20more)%20with%20the%20Mailchimp%20API&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-add-a-subscriber-and-more-with-the-mailchimp-api&r=&lt=537&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=18894)