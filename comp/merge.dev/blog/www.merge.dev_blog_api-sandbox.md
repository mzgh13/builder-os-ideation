---
url: "https://www.merge.dev/blog/api-sandbox"
title: "API sandbox: definition, examples, best practices, benefits"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-sandbox#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-sandbox#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-sandbox#)

Table of contents

[What is an API sandbox?](https://www.merge.dev/blog/api-sandbox#what-is-an-api-sandbox)

[Examples of sandbox environments](https://www.merge.dev/blog/api-sandbox#examples-of-sandbox-environments)

[Best practices for using API sandboxes](https://www.merge.dev/blog/api-sandbox#best-practices-for-using-api-sandboxes)

[Benefits of API sandboxes](https://www.merge.dev/blog/api-sandbox#benefits-of-api-sandboxes)

[Drawbacks of API sandboxes](https://www.merge.dev/blog/api-sandbox#drawbacks-of-api-sandboxes)

[How to create an API sandbox](https://www.merge.dev/blog/api-sandbox#how-to-create-an-api-sandbox)

[Access all the sandboxes you need for your customer-facing integrations with Merge](https://www.merge.dev/blog/api-sandbox#access-all-the-sandboxes-you-need-for-your-customer-facing-integrations-with-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-sandbox)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**How to develop a best-in-class API integration strategy**](https://www.merge.dev/blog/api-integration-strategy)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/653701f08e0b1aa5e418eb97_Integration_Marketplace.webp)**What is an integration marketplace? Here’s what you need to know**](https://www.merge.dev/blog/integration-marketplace)

# API sandbox: definition, examples, best practices, benefits

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Any issues in a single API integration can lead to harmful outcomes for your business.

Sensitive employee or customer data can get leaked; data can be synced incorrectly; endpoints can be polled too frequently, leading to unnecessary costs—and so on.

To prevent issues and optimize your integration builds before they’re pushed to production, you can test them through API sandboxes.

We’ll explain how an API sandbox can help by covering several real-world examples and the benefits they provide. We’ll also help you leverage them effectively by covering some best practices.

But to get us started, let’s define an API sandbox and outline its key features.

## **What is an API sandbox?**

It’s the process of simulating API calls and responses with dummy data for a given 3rd-party API provider. The end goal is to detect and diagnose integration issues as well as improve on the build before it’s pushed to production.

An API sandbox involves two components: a 3rd-party tool (e.g., Postman) or your own code base to simulate the API calls and responses; and the 3rd-party tool’s test environment to see how the information in the application's UI is returned by their API.

[![A visualization of an API sandbox](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620be8baa14857446a76_6_mhBute8ifce3mj5HERrKuUVF5PLS2jEMmeXqLrfTdlovAOhVzBgF8pt7S-J5aMao_NQMORolWnIpxbGO0ChzUkg2yTftbagB30Y9c-F-OQ40UQiSxxmYsS_ONOLwTaVb1Y7ZICmHjjCo65KNlljjo.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620be8baa14857446a76_6_mhBute8ifce3mj5HERrKuUVF5PLS2jEMmeXqLrfTdlovAOhVzBgF8pt7S-J5aMao_NQMORolWnIpxbGO0ChzUkg2yTftbagB30Y9c-F-OQ40UQiSxxmYsS_ONOLwTaVb1Y7ZICmHjjCo65KNlljjo.webp)

### **API sandbox features and capabilities**

While API sandboxes vary, they generally allow you to:

- **Access endpoints and HTTP requests supported by the API.** The sandbox environment should  help developers make a variety of simulated API calls, regardless of the resource they’re interested in or how they want to interact with it.

- **Use dummy data to test the integrations.** You’ll likely be able to access default data from the provider and/or provide your own data at any time.

- **Test the API’s authentication and authorization mechanisms.** Using a simulated environment, you can see if your authentication and authorization protocols work properly, whether that’s API keys, authentication tokens, etc.

- **Simulate a wide range of errors to evaluate your error handling processes.** APIs can fail for a wide range of reasons, many of which are out of your control. Through the API sandbox, you can replicate these errors and see how the associated [API error handling processes](https://www.merge.dev/blog/api-error-handling) perform; this lets you fine tune and address your processes before real errors actually occur.

- **Assess your integration’s performance.** Your integration should deliver responses quickly, accurately, and securely—all while abiding by the API provider’s imposed rate limits. Sandbox environments can evaluate your integration’s performance across each of these areas, and even provide metrics (e.g. response time) so that you can track improvements over time.

_Related:_ [_A guide to API integration security_](https://www.merge.dev/blog/api-integration-security)

## **Examples of sandbox environments**

The sandbox environments of 3rd-party API providers often look similar, if not identical, to their associated production instances. That said, it’s still worth reviewing a few of them to give you a sense of how they can look and work.

### **BambooHR**

The widely-used HRIS solution’s sandbox provides a broad range of test data, which allows you to start testing and developing the integration quickly.

[![Screeshot of BambooHR's sandbox environment](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620bd7c49b5fde594e7b_pQk4rrTnnb1Klk2mzFG6YEbJmmSQ595bEztR2GZ7bf0YtSBUT15YcJZHVg7w3x2GEOQH9lMicDT4KMt9ujJdq4AXu2vuyQzN-bHWjcCgGEeLag-b1T7FcPgmnsg5fCpkV3d1UPE7wBBV9WlUrkdsJ2s.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620bd7c49b5fde594e7b_pQk4rrTnnb1Klk2mzFG6YEbJmmSQ595bEztR2GZ7bf0YtSBUT15YcJZHVg7w3x2GEOQH9lMicDT4KMt9ujJdq4AXu2vuyQzN-bHWjcCgGEeLag-b1T7FcPgmnsg5fCpkV3d1UPE7wBBV9WlUrkdsJ2s.webp)

_You can test your BambooHR integration to see whether specific types of employee data get modified, added, or removed correctly._

### **Pipedrive**

The CRM system’s sandbox environment allows you to add a variety of standard and custom objects and fields to test a broad array of your integration’s functionality. That said, unlike BambooHR, their sandbox environment doesn’t provide test data; you’ll need to add it yourself.

[![Screenshot of Pipedrive's sandbox environment](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620b1591b8b8ed474353_Koeooa2HOUBpa9dqCcLvT1nJA3R8vDGLlOHxUF4-83_3z0apYEcTsOG1h9NSnBvze0RcwCo5QM2So8JNzeLgbyRrbYs6pmaA-g_o-0shf84ICOtAa9goIiFj5QuU94n42_h_2fpFYEp18lKfQ1fth6A.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620b1591b8b8ed474353_Koeooa2HOUBpa9dqCcLvT1nJA3R8vDGLlOHxUF4-83_3z0apYEcTsOG1h9NSnBvze0RcwCo5QM2So8JNzeLgbyRrbYs6pmaA-g_o-0shf84ICOtAa9goIiFj5QuU94n42_h_2fpFYEp18lKfQ1fth6A.webp)

_Related:_ [_Examples of API polling_](https://www.merge.dev/blog/api-polling-examples)

### **Box**

The file storage solution’s sandbox environment is similar to Pipedrive’s in that it allows you to access and interact with standard and custom objects and fields, but your team needs to provide the data.

[![Screenshot of Box's sandbox environment](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620b9ddb9b462ece2645_bOrO6N-iy6kbtwk0IDIzAUr36DCK4Hv5XbJT9CNtOhSnwvbJRm8vIgp9odchaBLhtcEEMlWbwm_NEBhirr2k44hlNRrV2ZBxQ3-adi9rpXrvTriZcIbfMpXu-9Y4EmTXCSO898G3DSSlcpyIYYIRBh8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c1620b9ddb9b462ece2645_bOrO6N-iy6kbtwk0IDIzAUr36DCK4Hv5XbJT9CNtOhSnwvbJRm8vIgp9odchaBLhtcEEMlWbwm_NEBhirr2k44hlNRrV2ZBxQ3-adi9rpXrvTriZcIbfMpXu-9Y4EmTXCSO898G3DSSlcpyIYYIRBh8.webp)

## **Best practices for using API sandboxes**

Here are some tips and tricks to help you develop and test your integrations effectively.

- **Take the time to explore and understand each sandbox environment.** As you saw in our examples, some 3rd-party API providers’ sandboxes include a variety of pre-populated data while others don’t. Moreover, some providers may not allow you to perform certain API calls, and they may enforce strict—or generous—rate limits. Taking the time to understand all of these areas for each sandbox account can help you prioritize the integrations you test and the ways you test them.

- **Use test data that closely resembles the data you’d use in production.** This can help you identify the errors that are most likely to crop up and prioritize fixing them.

- **Test all of your error handling processes until they work exactly how you want.** Each process likely serves a critical purpose; to ensure it’s fulfilled, you should aim to test every error handling workflow until it works as intended.

- **Confirm that you’re testing the API version you plan to use in production.** Different versions of an API are occasionally incompatible with one another; you can mitigate this risk by simply using the same versions in your production and testing environments.

- **Follow the API provider’s rate limits in their sandbox environment.** Similar to their production environment, the provider likely imposes limits that, if exceeded, can lead your API calls to be blocked and throttled.

## **Benefits of API sandboxes**

Here are just a few benefits that come with using API sandboxes:

### **Build robust error handling processes**

By testing each process until it works exactly how you want, you’ll be able to build reliable and performant integrations. Moreover, if any error handling process stops working as well or breaks, you can easily troubleshoot and fix the issue in your sandbox environment.

### **Save development time**

During testing, your engineers will likely uncover a variety of bugs and issues that need to be addressed. By addressing them then, your engineers are saving themselves time, as these issues could lead to larger problems once they take place in a production environment.

### **Implement secure integrations**

By confirming that your authentication and authorization protocols work properly during testing, you’re able to ensure that your integrations and the data they handle are secure from the get-go.

_Related:_ [_The benefits of integration partnerships_](https://www.merge.dev/blog/integration-partners)

## **Drawbacks of API sandboxes**

As our examples showed, API sandboxes aren't created equal. Here are a few potential drawbacks from using them:

### **Don’t store all the data you need**

Many API sandboxes can’t store all of the data you care about. As a result, you may not be able to run all the [integration tests](https://www.merge.dev/blog/api-integration-testing) you want, let alone any.

### **Misleading performance**

Just because the integration appears to be performing well in the sandbox environment doesn’t mean that it’ll perform well in production. Simple differences, whether it's the volume of data getting processed, how data is cached, the network infrastructure that's used, and so on, can drive significant discrepancies in each environment’s performance.

### **Different features than production environment**

The sandbox environment may use a different set of rate limits, authentication methods, etc. than the production instance. This prevents you from testing these areas, which limits the sandbox’s value.

## **How to create an API sandbox**

In case you’re an API provider and want to provide a sandbox for consumers, here are some steps you should follow:

- **Replicate the key components of your production environment.** By providing the same features and data types as your production instance, you’re allowing API consumers to test their integrations more thoroughly

- **Provide realistic dummy data in the sandbox.** This saves your API consumers time, as it allows them to avoid looking for and adding data themselves. In addition, if you can add dummy data that’s representative of the data your clients would use, your tests can produce output that's more realistic and easier to review.

- **Create and maintain documentation on the sandbox.** Similar to how you’d document other components of your APIs, you should take the time to outline various facets of the sandbox environment. This includes everything from the endpoints consumers can call to the authentication methods they should use to the rate limits they need to abide by. Equally important, you should regularly update these details in the documentation so that consumers can continue using the sandbox successfully.

- **Monitor your sandbox’s performance through its API logs.** As consumers use your sandbox, you’ll want to know how they’re using it and how it’s performing. That way, you’ll know how, exactly, to improve it over time. To that end, you can collect and add [API logs](https://www.merge.dev/blog/api-logs) to a monitoring tool (e.g., Datadog). Using the tool, you can analyze the logs and generate alerts based on the information they provide (e.g., response times exceed a certain threshold).


- **Provide support channels to help consumers receive direct support.** Your consumers may have certain questions that aren’t covered in your documentation; and even if it is, they may not have time to search for the answer. To help them get the support they need, quickly and easily, you can provide several avenues of support, from chat to email.

## **Access all the sandboxes you need for your customer-facing integrations with Merge**

Merge offers sandbox accounts for developing and testing your product integrations as well as a feature that allows you to call the third-party's API directly in the Merge dashboard.

You can learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-sandbox).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jon Gitlin is the Managing Editor of Merge's blog. He has several years of experience in the integration and automation space; before Merge, he worked at Workato, an integration platform as a service (iPaaS) solution, where he also managed the company's blog. In his free time he loves to watch soccer matches, go on long runs in parks, and explore local restaurants.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=228f1391-5058-4e6b-a21c-ca5bfe74dec2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=621c881d-64e3-4847-b4fd-e6e54540feba&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-sandbox&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=228f1391-5058-4e6b-a21c-ca5bfe74dec2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=621c881d-64e3-4847-b4fd-e6e54540feba&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-sandbox&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)