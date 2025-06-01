---
url: "https://www.merge.dev/blog/examples-of-sdks"
title: "6 real-world examples of SDKs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/examples-of-sdks#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/examples-of-sdks#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/examples-of-sdks#)

Table of contents

[What is an SDK?](https://www.merge.dev/blog/examples-of-sdks#what-is-an-sdk)

[6 real-world examples of SDKs](https://www.merge.dev/blog/examples-of-sdks#6-real-world-examples-of-sdks)

[Merge: one SDK for managing all your integrations](https://www.merge.dev/blog/examples-of-sdks#merge-one-sdk-for-managing-all-your-integrations)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fexamples-of-sdks)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ceba6710a493b164a4a_API_vs_screen_scraping.webp)**API vs screen scraping: how the two approaches differ**](https://www.merge.dev/blog/screen-scraping-vs-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb2a6710a493b161770_Integration_statistics.webp)**‍9 integration statistics you should know about in 2025**](https://www.merge.dev/blog/integration-statistics)

# 6 real-world examples of SDKs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c722dc8eb7739cb26c1_SDK_examples.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Kumar Harsh

@Merge

Imagine building a sleek, feature-rich app—and then realizing you need to reinvent the wheel for basic functionalities, like maps, payments, or social logins. Enter software development kits (SDKs): the prebuilt toolkits that allow developers to integrate third-party features into their applications.

Apart from allowing you to reuse prebuilt logic, SDKs also offer access to cutting-edge technology, boost engagement, and even open doors to new revenue streams.

Curious how this translates to the real world? This article explores six SDKs across industries that allow you to do the following:

- **Enhance the customer experience:** Integrate payment gateways, social logins, and chatbots
- **Boost operational efficiency:** Connect to logistics platforms, analytics tools, and marketing automation services
- **Unlock new revenue streams:** Offer in-app purchases, targeted advertising, and subscription models

But before we dive into our SDK examples, let's align on the definition of an SDK.

## What is an SDK?

It's a collection of tools and resources that application developers can use to build applications for a specific platform. SDKs typically include prewritten code, libraries, and documentation that make it easier for developers to create applications that interact with the platform.

SDKs help companies save time and money by using prewritten code and libraries. They give access to features and functionality that are not available through other means. They also allow you to create applications that are compatible with a specific platform.

SDKs rely on a crucial ingredient: APIs (application programming interfaces). You can think of APIs as messengers that relay information between your app and the service. They define the specific commands and responses your app can use to access data, features, and functionality.

_Related:_ [_How to use SDKs effectively_](https://www.merge.dev/blog/sdk-integration)

### SDK vs API

Just to avoid any confusion, let's clarify the differences between SDKs and APIs.

- **Scope:** SDKs are broader, encompassing prewritten code, libraries, and documentation alongside APIs. APIs are more focused, strictly defining the communication protocol
- **Purpose:** SDKs empower developers to build entire applications, while APIs facilitate specific interactions between apps and platforms
- **Depth:** SDKs delve deeper, providing platform-specific tools and resources. APIs stick to the surface, defining communication rules
- **Flexibility:** SDKs are language-specific, which means that a provider may not necessarily offer an SDK for your preferred programming language or framework. In contrast, APIs are language-agnostic and can be implemented in most cases. Since SDKs are language-specific, you can use language-related features, such as code autocomplete and syntax highlighting, but only as long as an SDK is available (and maintained) in the language of your choice
- **Error handling:** SDKs handle HTTP requests and responses for you cleanly, freeing you from the burden of handling failed network requests, interpreting error codes, and setting up retries

SDKs may contain one or more platform-specific APIs to help you achieve the task they are intended for. However, since they usually encompass prewritten libraries and documentation, they are usually easier to get started with when integrating a service into your application.

#### Avoid using several SDKs with Merge

Merge lets you add hundreds of integrations to your product through our single, aggregated API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fexamples-of-sdks)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## 6 real-world examples of SDKs

Let's take a look at some real-world SDKs to better understand how they work and what to look for when choosing one for yourself.

### HRIS: Freshteam

[![Freshteam SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440967972ac05852d1e_L9W1dxE.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440967972ac05852d1e_L9W1dxE.webp)

[Freshteam](https://support.freshteam.com/support/home), a leading cloud-based HR platform owned by Freshworks, offers an SDK to allow developers to integrate features such as automating tasks and building custom workflows into their applications to improve the overall HR experience in the organization.

The Freshteam SDK provides prewritten code and libraries in various programming languages, such as Python, Java, and Node.js, for interacting with its APIs. This code lets you manage employee data, create and track job applications, process time-offs, and do much more without having to handle HTTP requests and responses manually.

Here's how you can integrate the Freshteam SDK in Node.js:

````python

```python
# Install using `npm install @freshworks/api-sdk`

const { Freshteam } = require("@freshworks/api-sdk");

const client = new Freshteam(domain, apiKey);

const response = await client.employees.list({ first_name: "John", last_name: "Doe" });

const employees = response.json();
```

````

`‍
` Freshteam provides comprehensive documentation with code examples, tutorials, and reference guides for each supported language. You can take a look at [the Freshworks API SDK documentation](https://developers.freshworks.com/api-sdk/freshteam/) to learn more about how you can use it.

### Accounting: FreshBooks

[![FreshBooks SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440b5ba77962755053f_yosPqn4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440b5ba77962755053f_yosPqn4.webp)

[FreshBooks](https://www.freshbooks.com/), a popular cloud accounting platform, provides an SDK that developers can use to automate tedious accounting tasks and integrate financial data into their applications to save time and ensure accuracy.

The FreshBooks SDKs provide prewritten code and libraries for languages such as [Python](https://github.com/freshbooks/freshbooks-python-sdk), [Node.js](https://github.com/freshbooks/freshbooks-python-sdk), [Java](https://github.com/freshbooks/freshbooks-nodejs-sdk), and [PHP](https://github.com/amcintosh/freshbooks-java-sdk), for interacting with the FreshBooks APIs. You can use it to automate tasks like creating and sending invoices, capturing and categorizing expenses directly from your app, and accessing client data.

Here's an example that uses the Python SDK to access the details of a client from your FreshBooks instance:

````python

```python
from freshbooks import Client

freshBooksClient = Client(
    client_id=,
    access_token=
)

client = freshBooksClient.clients.get(account_id, client_user_id)

print(client.email)
```

````

_Related:_ [_5 webhook use cases_](https://www.merge.dev/blog/webhook-examples)

### Ticketing: Asana

[![Asana SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440b195e20e82316cd3_mdWY1NT.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440b195e20e82316cd3_mdWY1NT.webp)

[Asana](https://asana.com/), a popular project management platform, offers an SDK to help you integrate task management functionalities into your application. Integrating with your ticketing system allows you to streamline workflows, helps you automate tasks, and enables collaboration within your applications.

The Asana SDKs provide prewritten code and libraries in various languages, such as [JavaScript (Node)](https://developers.asana.com/docs/javascript), [Ruby](https://developers.asana.com/docs/ruby), and [Java](https://developers.asana.com/docs/java), to interact with its APIs. You can use it to create and manage tasks, assign tasks to members, and trigger actions based on events to automate workflows, like sending notifications and responding to customer emails.

Here's a quick example of how to use the Asana SDK in a Node.js app:

````python

```js
// Install by running `npm i asana`

const Asana = require('asana');

let asanaClient = Asana.ApiClient.instance;
let clientToken = asanaClient.authentications['token'];
clientToken.accessToken = '';

let tasksApiInstance = new Asana.TasksApi();
let options = {
    "limit": 50,
    "project": "",
};

const response = await tasksApiInstance.getTasks(options)

console.log(response)
```

````

`‍` The Asana SDKs lack a dedicated documentation page on their [developer website](https://developers.asana.com/). However, the GitHub repos contain detailed README files with a substantial number of example code snippets to help you get started quickly.

### CRM: Zoho CRM

[![Zoho SDKs home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f0644026fc1c37608940b5_sMlD0rm.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f0644026fc1c37608940b5_sMlD0rm.webp)

[Zoho CRM](https://www.zoho.com/crm/), a popular CRM platform, offers an [SDK](https://www.zoho.com/crm/developer/docs/server-side-sdks/) that can help streamline lead management, automate workflows, and integrate CRM data into your applications. This toolkit unlocks a range of possibilities for boosting sales, improving customer relationships, and gaining valuable insights.

The Zoho CRM SDK provides prewritten code and libraries for various languages, such as [Java](https://www.zoho.com/crm/developer/docs/server-side-sdks/v2/java.html), [Python](https://www.zoho.com/crm/developer/docs/server-side-sdks/v2/py-overview.html), and [Node.js](https://www.zoho.com/crm/developer/docs/server-side-sdks/v2/node-js.html), to interact with the Zoho CRM APIs. You can use the SDKs to do the following:

- **Manage leads and contacts:** create, update, and track leads and contacts
- **Automate sales processes:** trigger actions and send notifications based on specific events
- **Integrate with other applications:** connect your CRM data with other tools for seamless workflows
- **Gain insights with reports and dashboards:** analyze customer data and track key performance indicators (KPIs)

Here's how you can get started with the Node.js SDK:

````python

```js
// Install using `npm install @zohocrm/nodejs-sdk-2.0`

const fs = require("fs");
const {RecordOperations, DeleteRecordParam, DeleteRecordsParam, GetDeletedRecordsHeader, GetDeletedRecordsParam, GetMassUpdateStatusParam, GetRecordHeader, GetRecordParam, GetRecordsHeader, GetRecordsParam, SearchRecordsParam} = require("zcrmsdk/core/com/zoho/crm/api/record/record_operations");
const ResponseWrapper = require("zcrmsdk/core/com/zoho/crm/api/record/response_wrapper").ResponseWrapper;
const Comment = require("zcrmsdk/core/com/zoho/crm/api/record/comment").Comment;

class Record{
    static async getRecord(moduleAPIName, recordId, destinationFolder) {
        let recordOperations = new RecordOperations();

        let paramInstance = new ParameterMap();

        let fieldsArray = ["id", "Company"];
        let headerInstance = new HeaderMap();

        let response = await recordOperations.getRecord(recordId, moduleAPIName, paramInstance, headerInstance);

        if(response != null){

            // Get the status code from response
            console.log("Status Code: " + response.getStatusCode());

            if([204, 304].includes(response.getStatusCode())){
                console.log(response.getStatusCode() == 204? "No Content" : "Not Modified");

                return;
            }

            //Get object from response
            let responseObject = response.getObject();

            if(responseObject != null){

                //Check if ResponseWrapper instance is received
                if(responseObject instanceof ResponseWrapper){

                    //Get the array of obtained Record instances
                    let records = responseObject.getData();

                        //To get particular field value
                        console.log("Record Field Value: " + record.getKeyValue("Last_Name"));// FieldApiName

                        console.log("Record KeyValues: " );

                        let keyValues = record.getKeyValues();

                        let keyArray = Array.from(keyValues.keys());

                        for (let keyIndex = 0; keyIndex  0){
                                    if(value[0] instanceof Comment) {
                                        let comments = value;

                                        comments.forEach(comment => {
                                            console.log("Record Comment CommentedBy: " + comment.getCommentedBy());

                                            console.log("Record Comment CommentedTime: " + comment.getCommentedTime().toString());

                                            console.log("Record Comment CommentContent: " + comment.getCommentContent());

                                            console.log("Record Comment Id: " + comment.getId());
                                        });
                                    }
                                }

                            }

                        }
                    }
                }
            }
        }
    }
}
module.exports = {Record}
```

````

`‍` As you can see in the preceding example, the Zoho CRM SDK offers several wrappers and helper modules to help you write reliable integrations. However, the documentation may be a little tricky to navigate, especially the [pretty large code blocks](https://www.zoho.com/crm/developer/docs/nodejs-sdk/v2/record-samples.html?src=convert) shared as part of the example code snippets in the docs.

_Related:_ [_APIs vs integrations_](https://www.merge.dev/blog/integration-vs-api)

### Marketing automation: SendGrid

[![SendGrid SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f064409553ca561d2cea9c_hNod2me.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f064409553ca561d2cea9c_hNod2me.webp)

[SendGrid](https://app.sendgrid.com/), a leading cloud-based email delivery platform, offers a detailed SDK to help developers send and manage emails programmatically. This toolkit simplifies email sending, streamlines automation, and ensures exceptional deliverability to help you reach your audience effectively.

The SendGrid SDKs provide prewritten code and libraries in various languages, such as [Python](https://github.com/sendgrid/sendgrid-python), [Node.js](https://github.com/sendgrid/sendgrid-nodejs), and [Ruby](https://github.com/sendgrid/sendgrid-ruby), to interact with the SendGrid APIs. The SDKs allow you to do the following:

- **Send transactional emails:** trigger automated emails based on events in your app, such as order confirmations or password resets
- **Track email performance:** monitor open rates, click-throughs, and other key metrics for data-driven insights
- **Segment your audience:** send targeted emails to specific groups based on preferences and behavior

Here's a quick code snippet to help you get started with the SendGrid Python SDK:

````python

```python
import sendgrid
from sendgrid.helpers.mail import *

sg = sendgrid.SendGridAPIClient(api_key="YOUR_SENDGRID_API_KEY")

from = Email("test@example.com")
to = To("test@example.com")
sub = "Sending with SendGrid is Fun"
text = Content("text/plain", "and easy to do anywhere, even with Python")

email = Mail(from, to, sub, text)

response = sg.client.mail.send.post(request_body=email.get())

print(response.body)
```

````

`‍` Compared to some of the other SDKs discussed, SendGrid offers more comprehensive [documentation](https://docs.sendgrid.com/for-developers/sending-email) and getting-started guides for its SDK. Since it's backed by Twilio, the developer experience offered by SendGrid is better than that of most companies offering SDKs.

### File Storage: Box

[![Box SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440a58f41d8feeed9b6_sMPbQWc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440a58f41d8feeed9b6_sMPbQWc.webp)

[Box](https://box.com/), a cloud-based content management platform, offers an SDK that lets developers integrate secure file-sharing and collaboration features into their applications. This developer-friendly toolkit unlocks a range of possibilities for managing files, streamlining workflows, and boosting team collaboration.

Box provides prewritten code and libraries for various languages, such as [Python](https://github.com/box/box-python-sdk), [Java](https://github.com/box/box-python-sdk), and [Node.js](https://github.com/box/box-node-sdk), to interact with its APIs. The SDKs allow you to do the following:

- **Upload and download files:** manage various file types securely within your application
- **Collaborate on documents:** enable real-time editing and sharing of files within teams
- **Automate workflows:** trigger actions based on specific events, such as file uploads or approvals

Getting started with the Box SDK is easy. Here's an example in Node.js:

````python

```python
// Install using `npm i box-node-sdk`

// Get your user object from the Box SDK
const BoxSDK = require("box-node-sdk");

var sdk = new BoxSDK({
clientID: 'CLIENT_ID',
clientSecret: 'CLIENT_SECRET'
});

let client = sdk.getBasicClient('DEVELOPER_TOKEN');

client.users.get(client.CURRENT_USER_ID)
	.then(user => console.log('Hi', user.name, '!'))
	.catch(err => console.log('Encountered error!', err));
```

````

`‍
` While Box offers SDKs [across a wide range of platforms](https://developer.box.com/sdks-and-tools/), including [TypeScript](https://developer.box.com/sdks-and-tools/) and mobile, the documentation is bare-bones. It's provided in the GitHub repositories of the SDKs as a collection of Markdown files, and navigating through the files and finding the relevant methods and examples can sometimes get tricky.

## Merge: one SDK for managing all your integrations

[![Merge SDK home page](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440c4327e1b67dc7e58_4isfCQe.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f06440c4327e1b67dc7e58_4isfCQe.webp)

Merge—a single API that lets you add hundreds of integrations to your product—allows you to build to hundreds of APIs through one SDK, saving your engineers countless time and effort.

The [Merge SDK](https://docs.merge.dev/sdk/) also provides prewritten code libraries for various languages such as [Python](https://github.com/merge-api/merge-python-client/), [Node.js](https://github.com/merge-api/merge-node-client/), [Go](https://github.com/merge-api/merge-node-client/), [Java](https://github.com/merge-api/merge-go-client/), and [Ruby](https://github.com/merge-api/merge-ruby-client/), all but ensuring your team can use it in their preferred language.

You can learn more about Merge's SDK and its platform more broadly by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fexamples-of-sdks).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Kumar Harsh

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=90a44122-6675-4361-9c56-2b88b00f6049&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ed92b86e-2687-4bec-bf3f-e0a66f0879e8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fexamples-of-sdks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=90a44122-6675-4361-9c56-2b88b00f6049&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ed92b86e-2687-4bec-bf3f-e0a66f0879e8&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fexamples-of-sdks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=75c9be30-6164-49dd-bdbf-485f0996bcf4&bo=2&sid=155ea6e03e8d11f0a19e7bd030c4f590&vid=156140103e8d11f0bdd7496a11b95c02&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=6%20real-world%20examples%20of%20SDKs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fexamples-of-sdks&r=&lt=546&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=129510)