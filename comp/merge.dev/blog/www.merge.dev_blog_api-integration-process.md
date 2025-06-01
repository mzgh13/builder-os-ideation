---
url: "https://www.merge.dev/blog/api-integration-process"
title: "A guide to the API integration process"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-integration-process#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-integration-process#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-integration-process#)

Table of contents

[What is API integration?](https://www.merge.dev/blog/api-integration-process#what-is-api-integration)

[How to integrate APIs without using a third-party tool](https://www.merge.dev/blog/api-integration-process#how-to-integrate-apis-without-using-a-third-party-tool)

[Integrating an API using an SDK](https://www.merge.dev/blog/api-integration-process#integrating-an-api-using-an-sdk)

[Final thoughts](https://www.merge.dev/blog/api-integration-process#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-process)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7438e1085d0d6f5a4b_13.webp)**‍How to calculate the costs of API integrations**](https://www.merge.dev/blog/cost-of-api-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**How to build and maintain API integrations with ease**](https://www.merge.dev/blog/easy-api-integration)

# A guide to the API integration process

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb2a6710a493b161770_Integration_statistics.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Rahul Rai

@Merge

Application programming interfaces (APIs) act as the foundation of communication between applications. They establish the channels and formats in which applications can exchange information.

In this article, you'll learn all about the process of [integrating APIs](https://www.merge.dev/blog/api-integration) and how to perform it without third-party tools.

## What is API integration?

API integration is the systematic process of connecting different software applications using their APIs, allowing them to exchange data and functionalities. This isn't merely about establishing a connection; it's about ensuring that data is transferred in a secure, efficient, and accurate way. The goal is to create a seamless flow of data between systems that enhance their functionality and the user experience.

[![A visualization of API integration](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a4eaaead23a49031a43_651ad7d1f74c5ef95cb05eb0_API%2520integration%2520visual.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a4eaaead23a49031a43_651ad7d1f74c5ef95cb05eb0_API%2520integration%2520visual.webp)

An API integration process typically involves the following components:

- The **client application** is the application that initiates the API request. For instance, if you're building a mobile application that needs to process payments, the mobile application is considered the client application.
- The **server application** is the application that receives the API request and processes it. In the previous mobile application example, the server application would be the payment gateway.
- **API middleware** acts as a translator, ensuring that data is correctly formatted and understood by both sides. Positioned within the client application, it enables communication with a third-party application. Once the server application handles the request, the middleware guarantees that the resulting response is conveyed back to your application in a format the client application understands.

Note: It's generally advised to have a dedicated API middleware component in client applications as it helps maintain the [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns). However, for simpler applications, the API middleware operations of request and response translations, as well as communication with the server application, can be performed inline. This means that sometimes you may see the middleware code inlined with the business logic of the application rather than as a separate component.

#### Add hundreds of API integrations to your product with ease via Merge

Learn how Merge's Unified API can help you add all the cross-category API integrations your product needs by scheduling a demo with our team.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-process)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## How to integrate APIs without using a third-party tool

Now that you know what an API integration process looks like, it's time to learn how to integrate with common remote API formats. To keep the demonstrations succinct, you'll find that the API middleware is inlined in the application rather than placed in a separate module. However, when dealing with complex applications, it's important to create a separate module for API middleware code.

### Integrate a remote API

Remote APIs, also referred to as remote services, are primarily web-based interfaces offered by server-side applications. Classic examples of remote services are the [Firebase Realtime Database](https://firebase.google.com/docs/database/) and [Stripe Payment Gateway](https://firebase.google.com/docs/database/). The services expose specific endpoints, which are essentially URLs, and request and response data objects (aka data contracts) that developers can interact with to retrieve or send data. The endpoints and data contracts form the remote APIs are made available for integration by the remote services.

Here are the steps you would take to integrate a remote API into your development process:

1\. Start by thoroughly reading the API documentation to identify the endpoints you need to integrate. The documentation provides critical information about each endpoint's functionality, the expected request format, and possible responses. Documentation is the blueprint for understanding how to communicate effectively with the API.

2\. Most APIs require authentication to guarantee security, which means you need to obtain the necessary credentials for the remote API. This typically entails creating an account with the API provider and generating API keys or OAuth tokens. These credentials ensure that only authorized entities can access the API.

3\. Next, in your code, you need to write network calls that correspond to the type of remote API you're using.

In the following sections, you'll look at a few examples of network calls for different types of remote APIs using .NET. Before you do, use your preferred IDE and terminal to generate a client application using the following command:

````python

```bash
mkdir ApiClient && cd ApiClient
dotnet new console --framework net7.0
```

````

_Related:_ [_How to build API integrations (5 steps)_](https://www.merge.dev/blog/api-integration-steps)

#### REST APIs

REST APIs are a popular type of remote API that uses HTTP requests to retrieve or send data. For instance, the following GET request returns a list of users from an API:

_GET https://api.example.com/users_

In your client application, you can use the HttpClient class to make HTTP requests to the API. The following code snippet demonstrates how to make a GET request to the popular comic [XKCD's REST API endpoint](https://xkcd.com/json.html) to retrieve the latest comic:

```python

using System.Net.Http;
var httpClient = new HttpClient();
var restApiresponse = await httpClient.GetStringAsync("https://xkcd.com/info.0.json");
Console.WriteLine($"{restApiresponse}\n");

```

The following screenshot shows the response object formatted as a string returned by the API:

[![Response from the REST API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff31aeda202ec517d06_M6NJipc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff31aeda202ec517d06_M6NJipc.webp)

_Related:_ [_A guide to API integration management_](https://www.merge.dev/blog/api-integration-management)

#### GraphQL APIs

GraphQL is a query language for APIs that provides a more flexible alternative to REST. GraphQL APIs expose a single POST endpoint that accepts queries and returns data in JSON format.

For instance, the following query returns the ID and name of all users: {  users {    id    name  }}

The .NET GraphQL client library, [GraphQL](https://graphql-dotnet.github.io/), provides a convenient way to make GraphQL requests. The library abstracts the request and response transformation and manages the communication per GraphQL standards, freeing developers from the hassle of writing boilerplate GraphQL API integration code. Add the library [NuGet](https://www.nuget.org/) package to your project using the following command:

```python

dotnet add package GraphQL
dotnet add package GraphQL.Client
dotnet add package GraphQL.Client.Serializer.SystemTextJson

```

The following snippet shows you how to make a GraphQL request to the [Star Wars API](https://swapi-graphql.netlify.app/) to retrieve a list of all the films and their creation dates:

```python

using GraphQL;
using GraphQL.Client.Http;
using GraphQL.Client.Serializer.SystemTextJson;

using var graphQlClient = new GraphQLHttpClient(new GraphQLHttpClientOptions
{
  EndPoint = new Uri("https://swapi-graphql.netlify.app/.netlify/functions/index")
}, new SystemTextJsonSerializer());

var request = new GraphQLRequest
{
  Query = @"query MovieQuery {
  allFilms {
    films {
      title
      created
    }
  }
}"
};

var response = await graphQlClient.SendQueryAsync(request);
Console.WriteLine(response.Data.ToString());

```

This screenshot shows the string representation of the response object returned by the API:

[![Response from the GraphQL API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff3371647caf8b75144_cm4HNQ1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff3371647caf8b75144_cm4HNQ1.webp)

_Related:_ [_What is multiple API integration? Here's what you need to know_](https://www.merge.dev/blog/multiple-api-integration)

#### SOAP APIs

Simple Object Access Protocol (SOAP) APIs are a type of remote API that uses SOAP to exchange data. SOAP APIs expose a single endpoint that accepts XML requests and returns XML responses.

The .NET SOAP client library [System.ServiceModel.Http](https://www.nuget.org/packages/System.ServiceModel.Http/) provides a convenient way to make SOAP requests. Working with SOAP requires a fair bit of XML parsing, but the library simplifies this process by offering types that facilitate the exchange of SOAP messages using HTTP. Add the library package to your project using the following command: `dotnet add package System.ServiceModel.Http`

Now that you've added the System.ServiceModel.Http library, walk through the steps to make a SOAP request to the [DataFlex Web Service](http://webservices.oorsprong.org/websamples.countryinfo/CountryInfoService.wso) to retrieve the currency of a country based on its [International Organization for Standardization (ISO) code](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes).

Before making the request, you need to add a service reference to the API endpoint using the dotnet-svcutil tool. This tool retrieves metadata from a web service on a network location or from a WSDL file and generates a WCF class containing client proxy methods that access the web service operations. To learn more about the tool, you can check out the [Microsoft Learn guide](https://learn.microsoft.com/en-us/dotnet/core/additional-tools/dotnet-svcutil-guide).

To install the dotnet-svcutil tool, navigate to your project directory in the shell and execute the following commands:

```python

dotnet tool install --global dotnet-svcutil
dotnet-svcutil http://webservices.oorsprong.org/websamples.countryinfo/CountryInfoService.wso

```

This tool generates a ServiceReference1 folder containing the Reference.cs file. Add the Reference.cs file to your project by adding the following text to the .csproj file in the element like this:

Run the following code snippet to make a SOAP request to the API to retrieve the currency of Australia:

```python

using ServiceReference;
var client = new CountryInfoServiceSoapTypeClient(CountryInfoServiceSoapTypeClient.EndpointConfiguration.CountryInfoServiceSoap);

var response = await client.CountryCurrencyAsync("AU");

Console.WriteLine(response.Body.CountryCurrencyResult.sName);

```

The following screenshot shows the response returned by the API:

[![Response from the SOAP API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff352c3098031529768_iqKou7V.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff352c3098031529768_iqKou7V.webp)

#### gRPC APIs

gRPC is a high-performance, open source framework for building remote procedure call (RPC) APIs. It was developed by Google and is now part of the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/).

gRPC uses [Protocol Buffers](https://protobuf.dev/) as its default serialization format, which is a language-agnostic binary format that is more compact and faster to serialize and deserialize than JSON or XML. gRPC also supports streaming and bidirectional communication, making it well-suited for real-time applications.

One of the main benefits of using gRPC is its performance. Because it uses binary serialization and supports streaming, gRPC can be significantly faster and more efficient than traditional REST APIs. Additionally, gRPC's support for bidirectional communication makes it well-suited for real-time applications, such as chat applications or online games.

To integrate with a gRPC API, you need to install the following NuGet packages to your project:

````python

```bash
dotnet add package Grpc.Net.Client
dotnet add package Google.Protobuf
dotnet add package Grpc.Tools
```

````

Once you've successfully installed the NuGet packages, it's time to learn how to make a gRPC request to the gRPC bin service's Hello API to retrieve a greeting message. To do so, download the [Hello API's proto file](https://github.com/moul/pb/blob/master/hello/hello.proto) and add it to your project.

Then add an item group in the project file .csproj with a element in the element that refers to the hello.proto file:

````python

```xml
<ItemGroup>
<Protobuf Include="hello.proto" GrpcServices="Client" />
</ItemGroup>
```

````

Build the project to enable the gRPC tool to generate the client classes. Use the following code to make a gRPC request to the API to retrieve a greeting message:

````python

```csharp
using Grpc.Net.Client;
using Hello;

using var channel = GrpcChannel.ForAddress("http://grpcb.in:9000");
var client = new HelloService.HelloServiceClient(channel);
var reply = await client.SayHelloAsync(new HelloRequest { Greeting = "visitor" });
Console.WriteLine("Greeting: " + reply.Reply);
```

````

This screenshot shows the response returned by the API:

[![Response from the gRPC API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff347714226b5b4aa02_qUtC9kF.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff347714226b5b4aa02_qUtC9kF.webp)

And now you've completed the process of incorporating a .NET client application with various remote APIs. However, there are certain factors you need to take into account if you're integrating with remote APIs without using a software development kit (SDK), which you'll learn more about next.

_Related:_ [_Examples of building API integrations_](https://www.merge.dev/blog/api-integration-examples)

### Pros and cons of integrating with a remote API directly

There are several benefits to integrating directly with a remote API:

- Direct integration can ensure that the behavior of your application is consistent across all platforms, providing users with a uniform experience. This means that whether you are building an Android or an iOS application, you can be confident that the API will respond in the same way.
- Direct integration helps developers avoid adding extra in-app dependencies, which preserves the application's binary size and potentially improves performance. Maintaining a lean codebase also makes it easier to debug and maintain the application.

However, there are certain drawbacks to integrating directly with a remote API as well:

- Direct integration setup can be complicated and time-consuming. Developers need to have a thorough understanding of the API's architecture and documentation to ensure that the integration is secure and reliable. This may result in a longer implementation time and higher development costs.
- Developers may experience a slowdown in the development process due to the lack of integrated IDE support for documentation. This may cause them to frequently refer to external API docs. Additionally, the available guidance may not always be consistent across APIs and may not be up-to-date, leading to confusion.
- Manual work on data objects can lead to errors and requires careful attention to maintain data integrity. This is particularly challenging when dealing with APIs that return complex data objects that need to be parsed and validated.

## Integrating an API using an SDK

Now that you've not only walked through the process of direct integration with APIs but also considered their pros and cons, take a look at another type of [API integration using SDKs](https://www.merge.dev/blog/sdk-integration).

### What Does an SDK Look Like?

SDKs are comprehensive packages containing tools, libraries, and documentation to facilitate specific software integrations. SDKs, like the [Firebase SDK](https://firebase.google.com/docs/firestore/client/libraries) or [Stripe SDK](https://stripe.com/docs/libraries), abstract the complexities of direct API calls, providing a more straightforward integration pathway. They typically provide a set of classes, modules, and functions that developers can use to interact with the API in a more intuitive manner. SDKs are language-specific, providing support for popular languages such as C#, Java, Python, and JavaScript.

[![Communication flow between client application and remote API with SDK](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a4eaaead23a49031a3f_651ad874f74c5ef95cb1133a_Communication%2520flow%2520between%2520client%2520application%2520and%2520remote%2520API%2520with%2520SDK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a4eaaead23a49031a3f_651ad874f74c5ef95cb1133a_Communication%2520flow%2520between%2520client%2520application%2520and%2520remote%2520API%2520with%2520SDK.webp)

This diagram illustrates the communication flow between a client application and a remote API using an SDK. The SDK acts as a middleware, abstracting the complexities of the API and managing the communication protocol and data format conversions between the client application and the API.

_Related:_ [How to use SDKs (3 tips)](https://www.merge.dev/blog/sdk-integration)

### Integrate an SDK Into Your Application

The following is a brief overview of the steps you need to follow to integrate an SDK into your application:

**1\. Read the SDK docs and identify the classes/modules/functions to integrate.** Before diving into integration, it's essential to understand the SDK's architecture. This involves studying its classes, modules, and functions, which are typically well-documented. This helps you identify the specific classes/modules/functions you need to integrate. For instance, if you're integrating the Firebase SDK, you might need to use the FirebaseApp class to initialize the SDK and the FirebaseDatabase class to interact with the Realtime Database.

**2\. Acquire any necessary credentials.** Similar to direct API integration, SDKs often require specific credentials for authentication. This might involve generating unique keys or tokens specific to the SDK. **‍**

**3\. Initialize the SDK** and use the relevant programming constructs to integrate with the remote API.

To demonstrate the process of integrating an SDK, integrate the [Stripe SDK](https://stripe.com/docs/development) into your .NET client application.

Add the necessary NuGet packages to your client application using the following command: `dotnet add package Stripe.net`

Then use the Stripe SDK to create a customer with the email customer@example.com:

```python

using Stripe;

StripeConfiguration.ApiKey = "";
var options = new CustomerCreateOptions
{
  Email = "customer@example.com"
};

var service = new CustomerService();
Customer customer = service.Create(options);
Console.WriteLine(customer.Email);

```

This screenshot shows you the customer email that was returned by the API:

[![Response from the Stripe API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff3822150c813937654_W0ckPBO.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651acff3822150c813937654_W0ckPBO.webp)

The SDK operation is equivalent to the following direct API call:

```python

curl https://api.stripe.com/v1/customers \
  -u  \
  --data-urlencode email="customer@example.com"

```

As you can see, the SDK provides a more intuitive way to interact with the API, abstracting the complexities of the API call, such as authentication and data formatting. Additionally, the SDK provided a typed response object, which is easier to work with than the raw JSON response.

### Pros and cons of integrating with the SDK

There are some key considerations to keep in mind while integrating with an SDK. For instance, the following are some of the benefits of integrating with an SDK:

- SDKs often simplify the integration process, abstracting many of the complexities associated with direct API calls.
- Integrated documentation in some IDEs can significantly speed up the development process, providing instant access to essential references. This can help developers avoid frequent context switching, improving productivity.
- SDKs typically handle request and response objects gracefully, reducing the need for manual data handling and potential errors. This can help developers avoid common pitfalls, such as data type mismatches and null pointer exceptions.

There are also a few drawbacks you should consider:

- While SDKs simplify integration, they might not always expose the full functionality of the underlying API, potentially limiting some advanced features. Generally, SDKs are updated less frequently than the underlying API, which means that they may not always support the latest API features.
- Incorporating SDKs can increase the application's binary size due to the added dependencies, which may impact performance, especially on resource-constrained devices. Additionally, SDKs might not always be available for all platforms, which can limit the application's cross-platform compatibility.

## Final thoughts

Integrating APIs is an essential aspect of modern software development. It guarantees that applications can work together seamlessly within a broader ecosystem.

That said, the process of implementing API integrations is, clearly, complex and extensive. This is especially true in the context of [product integrations](https://www.merge.dev/blog/product-integrations); your clients and prospects will need and want you to build and maintain an ever-growing number of integrations between their applications and your product.

You can help your developers avoid following many of the steps outlined in this article and still implement the integrations your prospects and clients need with Merge, the leading [unified API solution](https://www.merge.dev/blog/what-is-a-unified-api). Simply build to Merge’s Unified API to start offering dozens, or even hundreds, of product integrations across key software categories, from CRM to HRIS to ATS to file storage.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-process).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Rahul Rai

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ba476e10-22a6-4313-a548-680da387cea2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1d8bcc91-d5e9-4082-af58-47d0ad795fd2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-process&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=ba476e10-22a6-4313-a548-680da387cea2&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1d8bcc91-d5e9-4082-af58-47d0ad795fd2&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-process&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=b2240ee5-4ece-44d1-8062-dbea221e6445&bo=2&sid=75b4dcc03e8d11f084756bbfde8c0d13&vid=75b500c03e8d11f0be0b6b9a7377e29e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20the%20API%20integration%20process&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-process&r=&lt=609&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=2098)