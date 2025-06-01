---
url: "https://www.merge.dev/blog/how-to-read-api-documentation"
title: "How to read API documentation"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-read-api-documentation#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-read-api-documentation#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-read-api-documentation#)

Table of contents

[Why you need to learn how to read API docs](https://www.merge.dev/blog/how-to-read-api-documentation#why-you-need-to-learn-how-to-read-api-docs)

[How to read API docs](https://www.merge.dev/blog/how-to-read-api-documentation#how-to-read-api-docs)

[Final thoughts](https://www.merge.dev/blog/how-to-read-api-documentation#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-read-api-documentation)

##### Just for you

No items found.

# How to read API documentation

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Alen Kalac

@Merge

Leveraging an API effectively requires understanding how to use it—that's where API documentation comes in.

API documentation is like a manual for the API. It should tell the reader what the API can do as well as how to use it. It also covers additional topics, such as security and rate limits. At the end of the day, good API documentation facilitates API adoption, which is, ultimately, its aim.

You can read on to learn about the importance of reading API docs as well as how to actually read them. We'll also cover some of the commonly-used API terminology and response status codes, and how to familiarize yourself with an API's overview, references, tutorials, examples, security, and guides.

_Related:_ [_Popular API integration use cases_](https://www.merge.dev/blog/api-integration-examples)

## Why you need to learn how to read API docs

By reading API documentation, you'll learn how you can use the API itself. The documentation should present the functionalities the API offers as well as how to get started using those functionalities. By reading the docs, you also go through tutorials and examples of the API usage, which give you ideas on how to integrate it.

Apart from how-to guides, the API docs should also cover other important aspects. For example, APIs have limits on the number of requests that can be sent over a select period of time. If you're planning to use an API, you need to be aware of any such limits by checking the documentation beforehand. Security is another crucial aspect of APIs. By reading through the API docs, you can find out how to get API keys and authenticate your requests.

An important distinction regarding API docs is that they aren't only geared toward developers. While it's true that developers are the ones who actually use the API, product managers may also read the documentation. This helps them evaluate the API and make decisions on how it can be used in their business.

## How to read API docs

Reading API documentation is a crucial step in learning about and implementing an API. In the next sections, we'll review some commonly-used terms and response status codes as well as some best practices you can implement to help you get the most from every API you use.

### Commonly-used terms

If you're going to read API docs, there is some common terminology you'll likely run into, including the following:

#### HTTP/HTTPS

[HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) is a standardized protocol used to transfer data, such as HTML pages, images, or videos, over a network. HTTP stands for Hypertext Transfer Protocol and is responsible for virtually all data exchanged through the internet. Thanks to HTTP, every time you input a URL in your browser or click on a link, the browser sends a request to a server and gets a response back, enabling you to get to the website you want in mere seconds (or less).

HTTPS is similar, but it uses [Secure Sockets Layer (SSL)](https://www.techtarget.com/searchsecurity/definition/Secure-Sockets-Layer-SSL) to encrypt the requests your browser sends and the response from the server. Since the connection is encrypted, HTTPS is more secure than HTTP. Even the _S_ in HTTPS stands for "Secure".

#### HTTP verbs

As previously mentioned, the way HTTP works is that the client sends an HTTP request to the server and the server sends a response back. In this process, HTTP request methods (verbs) are essentially the messenger between the client and the server.

One of the most common [HTTP verbs](https://www.freecodecamp.org/news/http-request-methods-explained/) is GET, which is used to retrieve data from a server. The server from which the client wants to retrieve the data is specified through the URL. Conversely, POST is used to send data, such as a username and a password on a form, to a server. There are other HTTP methods, such as PUT, DELETE, or PATCH, but they're used less frequently compared to GET and POST.

#### Endpoint

When using APIs, you want your application to interact with other systems. The touchpoints of such an interaction are called endpoints. In other words, when you request some data, the endpoint gives you the location where that data can be retrieved from.

#### Request

When the client wants to retrieve some data, it sends an API request to the server. The API request usually includes information such as the endpoint of the data the client needs, the HTTP method, and the headers.

#### Response

Once an API request is sent to a server, it returns the requested data to the client. The requested data is known as a response and is commonly in a JSON format, although it could also be in XML, CSV, or another format.

#### Header

When an API request or an API response is sent, some metadata is sent along with it. The metadata usually contains information, such as the type of content included in the request body, the client's authentication token or credentials, as well as the cache policy defined by the server. This metadata is contained in an API header, and it offers additional details that facilitate the communication between the client and the server.

_Related:_ [_A guide to API integration management_](https://www.merge.dev/blog/api-integration-management)

### Commonly-used response status codes

The response that the API server returns to the API client includes a status code. These codes are standardized three-digit numbers, and they're essential to signal success or failure. Not only does the status code signal failure (if there is one), but it also signals the type of failure that occurred. That's why there are many different status codes, each signifying either a success or a different type of failure. Since there are so many status codes, let's look at the most common ones.

#### 200

Typically, the most desirable status code to get back is 200 (OK), which means that the request was successful. If the HTTP request is GET, a status code of 200 means that the requested data has been retrieved and returned to the API client. In general, all status codes whose first digit is 2 signal a success.

#### 404

One of the HTTP status codes that most people are familiar with is the 404 (Not Found) code. Even if you've never dealt with APIs, you've probably encountered a 404 Not Found message. In essence, this status code means that the server can't find the data requested by the API client. In general, status codes whose first digit is 4 signal an error on the client side.

#### 401

The 401 (Unauthorized) status code means that the client is unauthorized to get the requested data. In this case, the API server doesn't know who is sending the request. The client must first authenticate itself before getting a response with the data.

#### 403

Another common status code is 403 (Forbidden). This simply means that the client doesn't have permission to get the requested response. Unlike with error 401, the server in this case knows the client's identity.

#### 500

Apart from 400s, status codes whose first digit is 5 also signal errors. However, in this case, the error is on the server's side. A status code of 500 (Internal Server Error) means that the server simply doesn't know how to handle a certain situation.

_Related:_ [_The top differences between webhooks and REST APIs_](https://www.merge.dev/blog/rest-api-vs-webhooks)

### Read the API Overview

Now that you know some of the most common terminology, it's time to dive into reading the API docs.

The first step when getting familiarized with API documentation is to check its overview. Virtually all API documentation has an overview section. The coverage of overview sections differs between different API docs, but it generally covers some basic information about the API. This includes information about what the API does, how to connect to it, and how to start using it. In short, the overview gives you a high-level understanding of how the API works.

Note that there's no general template for an API overview, so what's mentioned earlier may not always hold. For example, look at [OpenAI's API Overview section](https://platform.openai.com/overview). It's a simple page with links to tutorials and examples, as well as a list of some of the things you can do with the API:

‍

[![OpenAI API docs overview section](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882e6a31211c01a9503_pWINtTr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882e6a31211c01a9503_pWINtTr.webp)

### Read the API references

Once you have some understanding of what the API does, your next step should be to check the API reference. Unlike the overview, which only glances at the API's functionalities, the API reference lists all the methods that the API offers; it's usually a very large document.

However, you don't have to read or know all of it in order to use the API. You might only be interested in a few specific methods. If that's the case, you can familiarize yourself with only those methods as well as analyze if those fulfill your API needs.

Looking at the OpenAI API docs, its **API reference** section starts with **Introduction**, followed by **Authentication** and then **Making requests**, detailing how to make your first API request:

[![OpenAI API reference 1](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882b078c65127aee6e3_b5SRqUO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882b078c65127aee6e3_b5SRqUO.webp)

Then the API reference goes through a list of all the endpoints the OpenAI API offers. Here's what the reference for one of those endpoints looks like:

[![OpenAI API reference 2](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882d860d37503db3f68_5qdVC9R.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882d860d37503db3f68_5qdVC9R.webp)

‍

_Related:_ [_Why integrating APIs is challenging_](https://www.merge.dev/blog/api-integration-challenges)

### Look at the example requests and responses

[According to surveyed API users and developers](https://smartbear.com/resources/ebooks/the-state-of-api-2019-report/), "examples" is an extremely popular section in API docs; 70% percent of participants list it in the top 5 things they look for when reading API docs.

Examples are very useful since they show the reader how the API can be used in practice. If you look at the OpenAI API **Examples** sections, you'll find dozens of examples of what the API can do. By reviewing these examples, you get an idea of whether the API in question suits your needs:

[![OpenAI API examples](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882df479ad0fc58726b_ipPGSg9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d882df479ad0fc58726b_ipPGSg9.webp)

### Look at the security guides

In order to keep the API's data safe, users need to be authenticated. The API docs generally show the reader how to authenticate themselves so that they can access the API. An API may have multiple authentication methods, all of which should be discussed in the docs.

### Look at the limitations

Generally, APIs have a limit on their usage (i.e. rate limits). The limits are usually stated as a certain number of requests in a given period (seconds, hours, days, etc.).

Limits are necessary as they prevent API abuse, but it's important to look at the limits before deciding to use an API. That way, you'll know if the way you plan to use the API falls under the set limits.

The **Rate limits** section of the API docs can differ between different API docs, but here's how it looks in OpenAI API's documentation:

[![OpenAI API rate limits](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d881f33d9680e8efe4a0_o2LWjuD.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6542d881f33d9680e8efe4a0_o2LWjuD.webp)

### Look at the tutorials

If you've checked out all the previously described sections of API docs, you probably know if the API in question suits your application's needs. If it does, you can proceed to check out tutorials for API usage. Tutorials may come in both text and video formats. Whatever the format, most good API documentation has some tutorials.

The usefulness of tutorials stems from their comprehensiveness. A tutorial generally goes into much more detail compared to examples and API references. Its job is to walk you step-by-step through a use case of the API.

_Related:_ [_4 steps for planning an API integration project_](https://www.merge.dev/blog/api-integration-project-plan)

## Final thoughts

Reading through a few API documents may seem feasible, but when you're looking to integrate your product with dozens, if not hundreds, of applications, the process of reading and keeping up with changes to API documentation becomes extremely difficult—if not impossible.

Merge, which lets you offer a category of integrations (e.g. CRM or HRIS) by integrating with a single unified API, lets your team avoid sifting through and understanding API documentation over time; our team of partner engineers keeps up with 3rd-party APIs and helps maintain the integrations on your behalf.

_To learn more about Merge, you can_ [_schedule a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-read-api-documentation) _!_

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=59bbd2bb-b6e3-4b2f-95db-b5d6c35dcce6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e3480894-d0d9-4f0e-8d22-8bb62ae66204&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-read-api-documentation&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=59bbd2bb-b6e3-4b2f-95db-b5d6c35dcce6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=e3480894-d0d9-4f0e-8d22-8bb62ae66204&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-read-api-documentation&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=baf23d0c-49b2-4c41-90b9-e07333c139ad&bo=2&sid=f60ccc703e8d11f08d20458cc61ec74b&vid=f60d0b803e8d11f0a40925c767b466ef&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20read%20API%20documentation&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-read-api-documentation&r=&lt=570&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=79813)