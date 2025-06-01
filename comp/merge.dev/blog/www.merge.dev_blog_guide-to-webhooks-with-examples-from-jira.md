---
url: "https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira"
title: "Guide to Webhooks (with Examples from Jira)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#)

Table of contents

[Why Webhooks](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#why-webhooks)

[How to Use Webhooks in Jira](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#how-to-use-webhooks-in-jira)

[Conclusion](https://www.merge.dev/blog/guide-to-webhooks-with-examples-from-jira#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-webhooks-with-examples-from-jira)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cebc1bfb5f5db304e2e_How_to_get_attachments_from_Jira_via_JavaScript.webp)**A guide to webhook events (4 examples)**](https://www.merge.dev/blog/webhook-events)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**7 best practices for polling API endpoints**](https://www.merge.dev/blog/api-polling-best-practices)

# Guide to Webhooks (with Examples from Jira)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cee22f3719980bd9c44_Guide_to_Webhooks.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Ivan Kahl

@Merge

Organizations often use multiple applications to conduct business. For example, a tech team might find that [Jira](https://www.atlassian.com/software/jira) works well for managing tasks, a support team prefers [Zendesk](https://www.zendesk.com/) to handle support tickets, and a product team likes [ClickUp](https://clickup.com/) for planning. Each application has its strengths, so it makes sense for each team to choose what works best for them.

However, using multiple applications can lead to issues if you can't easily share data between the software packages. For example, a product team might want to stay updated on the development progress of a new product, or support needs to send issues through to the tech team.

Integrating these different applications can help overcome this issue. One effective method of integration is webhooks. Webhooks allow information to be shared between applications in real time as information changes, meaning information stays consistent and updated.

This article will teach you about webhooks and how they can help you integrate different systems efficiently. You'll also see a practical demonstration of webhooks in [Jira](https://www.atlassian.com/software/jira), a popular task management application.

#### Integrate with 30+ ticketing tools via Merge

Learn how Merge can help you integrate your product with Jira—and dozens of other ticketing applications—through a unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fguide-to-webhooks-with-examples-from-jira)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## Why Webhooks

A webhook is a user-defined HTTP callback. When an event happens in one application, the application sends a notification to a URL specified by the user. This integration method allows different applications to share information in real time as information changes.

One of the benefits of webhooks is that you don't have to poll for data. Polling is when a program regularly sends requests to a server to check for new data. However, polling is inefficient as it can burden the server and use unnecessary bandwidth. Webhooks are more efficient as data is only sent when there is new data to share, reducing the load on the bandwidth and load on the server. Also, since webhooks are HTTP calls, they are compatible with many applications and programming languages.

_Related:_ [_webhooks vs polling_](https://merge.dev/blog/webhooks-vs-polling)

### Send Data in Real Time

Webhooks make it possible to send information from one system to another in real time.

Say you have a landing page built in [WordPress](https://wordpress.org/). Potential clients can submit a form on the page if they want a sales representative to contact them. Webhooks allows the form submission to be sent directly to a sales system such as [Salesforce](https://www.salesforce.com/). To do this, you'd configure the webhook in your form to send an HTTP request to your sales system whenever a prospective client submits the form. The HTTP request will contain the data from the form submission, which you can save in your sales system.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07b6a35a6cf37a76be6e9_sending-real-time-data-using-webhooks.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07b6a35a6cf37a76be6e9_sending-real-time-data-using-webhooks.webp)

_A diagram demonstrating sending data in real time using webhooks courtesy of Ivan Kahl_

As a result, your sales team can follow up with potential clients much more rapidly. This real-time data transmission between systems can be incredibly beneficial for business workflows where timing is essential.

### Send Notifications for Events

Webhooks let you send notifications via email or a messaging platform such as [Slack](https://api.slack.com/messaging/webhooks) or [Teams](https://learn.microsoft.com/en-us/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).

Say you use a project management tool such as [Jira](https://www.atlassian.com/software/jira) to manage your sprints. You want to notify all project stakeholders at the beginning of a sprint which tasks the team is working on. This workflow is possible by configuring a webhook in Jira that will be executed at the start of a sprint. When the webhook is triggered, an email or instant message notification is sent to the project shareholders.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07c0a3e9f2c48ac749f72_webhook-notifications-from-jira-to-slack.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07c0a3e9f2c48ac749f72_webhook-notifications-from-jira-to-slack.webp)

_A diagram demonstrating sending notifications to Slack when a sprint starts in Jira courtesy of Ivan Kahl_

Sending custom notifications when an event occurs in systems is easy using webhooks.

_Related:_ [_A guide to fetching projects from Jira (using Python)_](https://www.merge.dev/blog/jira-api-get-projects-python)

### Data Synchronization

You can also use webhooks to synchronize data between two systems in real time so that both systems maintain accurate, up-to-date data.

Say you have an invoicing system and use a payment service provider such as [Stripe](https://stripe.com/). First, configure a webhook in your invoicing application to send a payment request notification to your payment service. Then, set up another webhook with your payment service to notify your invoicing system when the payment request is fulfilled. These two webhooks will keep your payment service provider and invoicing application synchronized by sharing data changes with the other system as it happens.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07c82bbeb3a12cb37ac39_synching-xero-stripe-using-webhooks.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07c82bbeb3a12cb37ac39_synching-xero-stripe-using-webhooks.webp)

_A diagram demonstrating how to keep Xero and Stripe in sync using webhooks courtesy of Ivan Kahl_

You can synchronize data between the systems in real time by configuring webhooks in both systems.

_Related:_ [_REST APIs versus webhooks_](https://www.merge.dev/blog/rest-api-vs-webhooks)

## How to Use Webhooks in Jira

As you've seen above, webhooks have many use cases. You'll now see a practical demonstration of webhooks in Jira.

To follow along, you'll need a Jira account. You can sign up for a free tier [here](https://www.atlassian.com/software/jira). You'll also need a URL to which the Jira webhooks can send requests. This article uses [Request Bin](https://requestbin.com/) as it lets you visualize the data in a webhook request.

### Register a Webhook

Before Jira can execute your webhook, you'll have to register it. When registering the webhook, you need to supply the following:

- The `name` of the webhook in Jira lets you find it easily.
- The `status` determines whether the webhook is enabled or not.
- The `URL` is where the webhook should send notifications to. You can include dynamic variables in the URL, which lets you pass data about the event triggering the webhook. See [the documentation](https://developer.atlassian.com/cloud/jira/platform/webhooks/#variable-substitution-in-the-webhook-url) for more details.
- You can optionally provide the `description`, which lets you specify more details about the webhook.
- The `events` will trigger the webhook. You can configure multiple events for a single webhook. More information on webhook events can be found [here](https://developer.atlassian.com/cloud/jira/platform/webhooks/#available-webhook-events).

You can use the Jira Admin Console to manually configure the webhook or the REST API to configure a webhook programmatically.

#### Register a Webhook in the Jira Admin Console

If you are registering a custom webhook in your Jira instance, you can use the Jira Admin Console to register the webhook.

1. Log in to Jira.
2. Open the settings menu in the top right and select the **System** menu item in the **JIRA SETTINGS** section.
3. In the menu on the left of the screen, scroll down and select **WebHooks** in the **ADVANCED** section.
4. Click on the **Create a WebHook** button. Specify the **Name** and set the **Status** to **Enabled**. Generate a webhook URL in [Request Bin](https://requestbin.com/) (or whichever tool you're using to test webhooks) and paste it into the URL field.
5. Select which one or more events should trigger the webhook.
6. Click **Create** to finish registering your webhook.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07ea99855ea50e3154d7a_system-menu-jira-settings.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07ea99855ea50e3154d7a_system-menu-jira-settings.webp)

_Select the System menu item in the JIRA SETTINGS section_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07ee787cd1e1124114131_webhooks-menu-jira-advanced.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07ee787cd1e1124114131_webhooks-menu-jira-advanced.webp)

_The WebHooks menu item in the ADVANCED section_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07f29f1f838a08874a6f6_webhooks-details-jira.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07f29f1f838a08874a6f6_webhooks-details-jira.webp)

_Specify your webhook details in the form that appears_

Now that you've set up the webhook in Jira, you can execute it. You can do this by performing any task in Jira that will cause one of the webhook events to trigger. In this case, the webhook will be triggered when a new task is created in Jira. Below is the request in [Request Bin](https://requestbin.com/) after a new task was created.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07f919855ea2b601668e7_web-request-jira.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d07f919855ea2b601668e7_web-request-jira.webp)

_The web request sent by Jira_

You'll see that information is sent about the `user` and `issue` that triggered the event, and the `changelog` contains a list of changes made to the issue. You can read more about what information is sent by a webhook in [Atlassian's documentation](https://developer.atlassian.com/cloud/jira/platform/webhooks/#executing-a-webhook).

If you configured the webhook to trigger an endpoint on your application, you could process this information and update your application or send a notification in real time.

_Related:_ [_How webhooks can support your integrations_](https://www.merge.dev/blog/webhooks-integration)

#### Register a Webhook Using the Rest API

Instead of manually registering webhooks in the Jira Admin Console, you can use the Jira REST API to create these webhooks. This method is beneficial when developing third-party apps that need to add webhooks to Jira.

You'll need a REST client such as [Postman](https://www.postman.com/) or [curl](https://curl.se/) to follow along with this section.

##### Create an OAuth 2.0 Application

First, you'll need to create your own [OAuth](https://developer.atlassian.com/server/jira/platform/oauth/) app in Jira to consume the REST API.

01. Navigate to your [Developer Console](https://developer.atlassian.com/console/myapps/).
02. Click on the **Create** button and select **OAuth 2.0 integration**.
03. Give your application a name and click **Create**.
04. You will need to add the `read:jira-work` and `manage:jira-webhook` scopes to your application. In the left menu, click on **Permissions**.
05. Click on the **Add** button next to **Jira API**.
06. Configure the application to have the `read:jira-work` and `manage:jira-webhook` scopes.
07. Click on **Authorization** in the left menu and then **Add** the **OAuth 2.0 (3LO)** authorization type to your app.
08. Configure a callback URL. If you are using Postman, refer to their [authorization documentation](https://learning.postman.com/docs/sending-requests/authorization/#requesting-an-oauth-20-token) on what to use for the callback URL. Then, click **Save changes** to save the changes.
09. Finally, click on **Settings** in the left menu, and retrieve your client ID and client secret.
10. You can now use your OAuth 2.0 app in Postman to retrieve an access token for the request to create a webhook.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0844287cd1ec4d61396c6_create-oauth-integration-jira.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0844287cd1ec4d61396c6_create-oauth-integration-jira.webp)

_Click the Create button and select OAuth 2.0 integration_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0848587cd1e851f13abee_name-oauth-integration.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0848587cd1e851f13abee_name-oauth-integration.webp)

_Give your application a name and click Create_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d084d16bcf4394fdecfc5e_jira-developer-permissions.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d084d16bcf4394fdecfc5e_jira-developer-permissions.webp)

_Click on Permissions on the left_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0850db05322775748147d_add-jira-api-permission.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0850db05322775748147d_add-jira-api-permission.webp)

_Click on the Add button next to Jira API_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d085348d54b2d90600fe06_authorize-oauth.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d085348d54b2d90600fe06_authorize-oauth.webp)

_Add OAuth 2.0 (3LO) authorization to your app_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0859fe96cff790fa077d3_retrieve-client-id-secret.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0859fe96cff790fa077d3_retrieve-client-id-secret.webp)

_Retrieve your client ID and client secret on the Settings page_

##### Retrieve an Access Token

01. Create a new request in Postman and select **OAuth 2.0** as the **Authorization Type**.
02. In the **Configure New Token** section, populate the form as follows:
03. ‍ **Token Name:** `Jira Token` **_‍_**
04. **_‍_ Grant Type:** `Authorization Code` _‍_
05. _‍_ **Callback URL:** `https://oauth.pstmn.io/v1/callback` (check **Authorize using browser**) **‍**
06. **Auth URL:** `https://auth.atlassian.com/authorize?audience=api.atlassian.com` **_‍_**
07. **_‍_ Access Token URL:** `https://auth.atlassian.com/oauth/token` _‍_
08. _‍_ **Client ID:** Your OAuth app's client ID **‍**
09. **Client Secret:** Your OAuth app's client secret **‍**
10. **Scope:** `read:jira-work` `manage:jira-webhook`
11. ‍ _‍_ **State:** Your own random string **‍**
12. **Client Authentication:** Send client credentials in body
13. Click on **Get New Access Token** and follow the prompts in your browser.
14. You should see the following dialog displaying the access token. Click **Use Token** to add the access token to your request.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0867ce8066f377a83bcc6_oauth2-authorization-type.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d0867ce8066f377a83bcc6_oauth2-authorization-type.webp)

_Select OAuth 2.0 as the Authorization Type_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d087d144d323757aa0879b_configure-new-token-form.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d087d144d323757aa0879b_configure-new-token-form.webp)

_Populate the form in the Configure New Token section_

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d088034bc6aa0e1f2c81e7_access-token-dialog.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d088034bc6aa0e1f2c81e7_access-token-dialog.webp)

_Dialog displaying the access token_

Once you've retrieved the access token, you can create a webhook using the REST API.

##### Create a Webhook Using the REST API

1. Open your REST client and send a GET request to `https://api.atlassian.com/oauth/token/accessible-resources` using the access token you received when authenticating with OAuth.
2. Take note of the id property in the response.
3. Create another POST request to `https://api.atlassian.com/ex/jira//rest/api/2/webhook` where is the value of the id property from the previous step. Then, specify the webhook details in the request body as follows:

[![Take note of the id property](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17e36b2fa7209bd2de808_EWZswB7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17e36b2fa7209bd2de808_EWZswB7.webp)

_Take note of the id property_

```“python” language-none

   {
     "url": "https://envtwfu7vya.x.pipedream.net",
     "webhooks": [\
       {\
         "events": [ "jira:issue_created" ],\
         "jqlFilter": "project = TP"\
       }\
    ]
   }

```

For the url property, generate a webhook URL using your webhook testing tool—e.g., [Request Bin](https://requestbin.com/).

You must specify a JQL filter to restrict which tasks in Jira can trigger the webhook. You can find documentation on JQL [here](https://www.atlassian.com/software/jira/guides/expand-jira/jql). In this example, the webhook will fire when you create an issue in the TP project.

You must also specify one or more events that should trigger the webhook. For example, in the snippet above, the webhook will be executed when a user creates a new issue in Jira.

4\. Send the request. The response object will contain an array of objects containing the IDs for the newly created webhooks in Jira that should look something like this:

```“python” language-none

   {
     "url": "https://envtwfu7vya.x.pipedream.net",
     "webhooks": [\
       {\
         "events": [ "jira:issue_created" ],\
         "jqlFilter": "project = TP"\
       }\
    ]
   }

```

You've now set up a dynamic webhook in Jira. Execute it by performing any task in Jira that will cause one of the webhook events to trigger. Similarly to the previous webhook you created in the Jira Admin Console, this webhook will be triggered when a new task is created in Jira. Create a new task in Jira and notice how the request looks in [Request Bin](https://requestbin.com/).

[![The web request sent by Jira](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17ef0b05a7c1ec74db0e5_woETti3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17ef0b05a7c1ec74db0e5_woETti3.webp)

_The web request sent by Jira_

The request appears similar to the one sent from the webhook you created in the Jira Admin Console. However, notice that this webhook also includes an authorization header and a `matchedWebhookIds` property in the body. These would be used when integrating your own application using Jira webhooks.

You can learn more about using the Jira REST API for creating webhooks [in the documentation](https://developer.atlassian.com/cloud/jira/platform/rest/v2/api-group-webhooks/#api-rest-api-2-webhook-post).

_Related:_ [_The steps for getting comments from Jira through Python_](https://www.merge.dev/blog/jira-api-get-comments)

### Automating Jira Webhooks

Jira also lets you send webhook notifications in automations on your projects. These automations let you create more complex workflows for projects when an event occurs in the project.

For example, you can set up an automation that will get triggered when assigning someone to a task. You can add conditional statements in the automation that can trigger different webhooks depending on who got assigned the issue. Of course, this is just one example. There is so much more you can do.

01. Log in to Jira.
02. Open the settings menu in the top right and select **Projects** in the **Jira Settings** section.
03. Select the project on which you want to set up the automation.
04. Select **Project settings** in the menu on the left of the screen and then **Automation**.
05. Create a new automation by clicking on the **Create rule** button.
06. Choose an event that should trigger the automation. In this case, the automation will be triggered whenever someone comments on an issue.
07. You can build the automation by clicking on the **Add component** link on the left and adding different conditionals.
08. Click on **Add component** to trigger a webhook in the automation. Search for the **Send web request** action and select it.
09. Configure the action by specifying a test webhook URL in the URL field. In this demonstration, a URL is generated in [Request Bin](https://requestbin.com/) and specified in the URL field. You can also configure the headers and body for the web request. In this case, Jira will send through the issue data in the automation format. You can also configure the action to wait for a response from the webhook before continuing using the **Wait for response** field. Click **Save** to continue.
10. On the screen that appears, give your automation a descriptive name and click **Turn it on** to save it.
11. Save the action.

[![The Projects menu item in the Jira Settings section](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38bf253e3f7630df6f_tvttXtP.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38bf253e3f7630df6f_tvttXtP.webp)

_The Projects menu item in the Jira Settings section_

[![The project selection screen in the Projects settings](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380ca6d3c9c1a3233a_WcScsqY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380ca6d3c9c1a3233a_WcScsqY.webp)

_The project selection screen in the Projects settings_

[![The automation will be triggered when someone comments on an issue](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38bf253e343d30df9b_5pL4Zri.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38bf253e343d30df9b_5pL4Zri.webp)

_The automation will be triggered when someone comments on an issue_

[![Search for the Send web request action and select it](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380cd7f5059031d66f_UIbSvIy.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380cd7f5059031d66f_UIbSvIy.webp)

_Search for the Send web request action and select it_

[![Configure the action](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38b87c7465b8e7e625_FQSiVxH.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f38b87c7465b8e7e625_FQSiVxH.webp)

_Configure the action_

[![Give your automation a descriptive name and click Turn it on to save it](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380ca6d3cfe5a3233b_QqB65FR.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d17f380ca6d3cfe5a3233b_QqB65FR.webp)

_Give your automation a descriptive name and click Turn it on to save it_

Once you've created and enabled a new automation, you can test it. The automation above is triggered whenever a user comments on a task. If you test the automation by adding a comment to any issue in your project, you'll notice that the request object is huge. However, if you drill down, you will find information on the new comment you just added.

[![The request sent by Jira containing the new comment](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d180162361981bb753150c_299TG0z.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/63d180162361981bb753150c_299TG0z.webp)

_The request sent by Jira containing the new comment_

Automations let you build powerful workflows that can integrate into other applications from within the workflow.

## Conclusion

In this article, you learned about what webhooks are, why they're helpful, and how to use them to send data from one application to another, send a notification when an event occurs in a system, and synchronize data between two systems. The article also demonstrated how to configure webhooks in Jira.

Webhooks in Jira let you integrate your task management system with your ticketing system, project management system, and more. You can create countless more integrations with webhooks. However, you need to write code to react to webhooks and update another application using their API.

[Merge](https://merge.dev/) simplifies integrating different systems by offering a unified API that integrates with hundreds of [HR](https://www.merge.dev/categories-old/hr-payroll-api), [recruiting](https://www.merge.dev/categories-old/ats-recruiting-api), [ticketing](https://www.merge.dev/categories-old/ticketing-api), [CRM](https://merge.dev/categories/crm-api), [file storage](https://merge.dev/categories/file-storage-api), and [accounting](https://www.merge.dev/categories-old/accounting-api) platforms. Combined with the power of webhooks, and automatic webhook creation, Merge enables your business to use the best tools for the job while seamlessly synchronizing your data.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Ivan Kahl

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a23a3ef4-f975-448a-923e-9a862d35d6f4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6b225219-4f31-4c37-8a8d-3ab8cfc3db56&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-webhooks-with-examples-from-jira&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a23a3ef4-f975-448a-923e-9a862d35d6f4&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=6b225219-4f31-4c37-8a8d-3ab8cfc3db56&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-webhooks-with-examples-from-jira&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=db85e0c1-c758-4df3-bb5d-a20ecdd0e692&bo=2&sid=3953b6203e8e11f0a1ff4941b49ecedb&vid=3953dc403e8e11f0b13089103aa2f18e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Guide%20to%20Webhooks%20(with%20Examples%20from%20Jira)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fguide-to-webhooks-with-examples-from-jira&r=&lt=552&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=359911)