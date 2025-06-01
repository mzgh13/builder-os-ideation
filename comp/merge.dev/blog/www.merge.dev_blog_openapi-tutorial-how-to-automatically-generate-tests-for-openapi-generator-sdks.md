---
url: "https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks"
title: "OpenAPI tutorial: How to automatically generate tests for OpenAPI generator SDKs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks#)

Table of contents

[Intro](https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks#intro)

[Custom Templating With OpenAPI](https://www.merge.dev/blog/openapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks#custom-templating-with-openapi)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fopenapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How to use SDKs to build and maintain API integrations**](https://www.merge.dev/blog/sdk-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c722dc8eb7739cb26c1_SDK_examples.webp)**6 real-world examples of SDKs**](https://www.merge.dev/blog/examples-of-sdks)

# OpenAPI tutorial: How to automatically generate tests for OpenAPI generator SDKs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb10b382a09b6075231_How_to_Fetch_Opportunities_from_Microsoft_Dynamics_365_Sales_with_Merge_CRM_Unified_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387ca3e2516664e369a_62eff9710897772d5f67ff9d_lee.webp)

Lee Wang

Software Engineer

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 180+  integrations across HR, ATS, CRM, Accounting, and Project Management platforms with one_ [_unified API_](https://merge.dev/).

## **Intro**

At Merge, our customers build their products in a variety of different programming languages. We take our role as a Unified API provider seriously and meet their needs by offering SDKs in each of those languages. We found early on we needed to build custom templates in order to ensure we support and test every SDK in a scalable way.

If you’re interested in building your own testing framework for your SDKs - continue reading! We’ll use Merge’s use-case and API as examples, but our process and methodology can apply to any schema looking to utilize OpenAPI.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a76b1f17830d622073f_62d72b76adbd5e35e934102d_OpenAPI_Diagram.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cc9a76b1f17830d622073f_62d72b76adbd5e35e934102d_OpenAPI_Diagram.webp)

### **What is OpenAPI?**

The [OpenAPI](https://www.openapis.org/) initiative offers an industry-standard interface definition language, or IDL. That’s a fancy way of saying it describes an API, like Merge’s API, in a patterned, uniform way. You can see our API specifications here:

- [Accounting Specification](https://api.merge.dev/api/accounting/v1/schema)
- [ATS Specification](https://api.merge.dev/api/ats/v1/schema)
- [HRIS Specification](https://api.merge.dev/api/hris/v1/schema)

### **Why Do We Need OpenAPI?**

To lead by example, here is some sample json that describes our ATS’ `get-candidate-by-id endpoint`, generated through OpenAPI. It lists url, input properties and response type:

```json
"/candidates/{id}": {
    "get": {
        "operationId": "candidates_retrieve",
        "description": "Returns a `Candidate` object with the given `id`.",
        "parameters": [\
            {\
                "in": "header",\
                "name": "X-Account-Token",\
                "schema": {\
                    "type": "string"\
                },\
                "description": "Token identifying the end user.",\
                "required": true\
            },\
            {\
                "in": "query",\
                "name": "expand",\
                "schema": {\
                    "type": "string",\
                    "enum": [\
                        "applications",\
                        "applications,attachments",\
                        "attachments"\
                    ]\
                },\
                "description": "Which relations should be returned in expanded form. Multiple relation names should be comma separated without spaces.",\
                "examples": {\
                    "ExpandApplications,Attachments": {\
                        "value": "applications,attachments",\
                        "summary": "Expand Applications, Attachments"\
                    }\
                }\
            },\
            {\
                "in": "path",\
                "name": "id",\
                "schema": {\
                    "type": "string",\
                    "format": "uuid"\
                },\
                "required": true\
            },\
            {\
                "in": "query",\
                "name": "include_remote_data",\
                "schema": {\
                    "type": "boolean"\
                },\
                "description": "Whether to include the original data Merge fetched from the third-party to produce these models."\
            }\
        ],
        "tags": [\
            "candidates"\
        ],
        "security": [\
            {\
                "tokenAuth": []\
            }\
        ],
        "responses": {
            "200": {
                "content": {
                    "application/json": {
                        "schema": {
                            "$ref": "#/components/schemas/Candidate"
                        }
                    }
                },
                "description": ""
            }
        }
    }
},

```

The whole point of this json is so we can then use a well-formatted interface definition to generate SDK/client code for us. **In order for the SDKs and Clients we provide to properly call our API we need our packages to be:**

- In a programming language our customers already use
- Well-tested and safe

SDKs provided through templating and code generation are a more scalable approach, given the diverse array of API clients our customers need to call Merge.

## **Custom Templating With OpenAPI**

While the OpenAPI specification is very well-defined, there are a few options for generating SDK code with a given specification json:

- [Swagger CodeGen](https://swagger.io/tools/swagger-codegen/) \- the original tool
- [OpenAPI Generator](https://openapi-generator.tech/) \- what Merge uses

For the purposes of this guide, we’ll specifically focus on the OpenAPI Generator tool.

### **The Basics of OpenAPI**

The OpenAPI Generator project comes with a lot of default templates for generating SDKs from API specifications. Here are some examples, and note how they’re written in  the syntax:

- [Template for model classes in Golang](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator/src/main/resources/go/model.mustache)
- [Template for API classes in Python](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator/src/main/resources/python/api.mustache)
- [Template for enums in Kotlin with Spring framework](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator/src/main/resources/kotlin-spring/enumClass.mustache)
- [Folder for all language/framework options](https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator/src/main/resources)

When generating an SDK, the tool uses these Mustache template files to define what the final code output looks like. The [README of the OpenAPI Generator github repository](https://github.com/OpenAPITools/openapi-generator) has good instructions on how to run the tool, and for what it’s worth Merge uses the [docker method](https://github.com/OpenAPITools/openapi-generator#public-pre-built-docker-images).

Here’s an example command for generating our SDK:

```bash
docker run -v ${PWD}/:/local \
--entrypoint='java' \
openapitools/openapi-generator-cli:v5.1.1 \
-jar /opt/openapi-generator/modules/openapi-generator-cli/target/openapi-generator-cli.jar \
generate -i https://api.merge.dev/api/ats/v1/schema \
-g python \
-o ./local/python-sdk

```

### **Customizing Your Own Templates Files**

Knowing where the templates come from is the biggest hurdle when working with OpenAPI. However, once you’re armed with this information, you can override these template files for your own custom configuration simply by creating a new file locally that has the same name! Since we are focusing on unit tests in this article, let’s first consider this Python template, which uses the `.mustache` syntax:

- [Python model\_test.mustache](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator/src/main/resources/python/model_test.mustache)

Next we’ll:

1. Learn the basics of `.mustache` syntax
2. Configure the override of this file
3. Talk about limitations and apply a slightly different approach to Golang

You can download that file to your local directory, and use it in the docker SDK generation command from the previous section [by adding this flag](https://openapi-generator.tech/docs/templating/):

```json
-t ./local/REPLACE-WITH-YOUR-TEMPLATES-FOLDER$
```

### **Mustache Basics**

Mustache started out as an HTML templating language. Personally, I think this is a rather awkward choice for code templating since it lacks things like if x == y { output this } (though we’ll see how to get around that later). Because HTML is full of tags organized in a tree-like manner, Mustache does make it easy to traverse the OpenAPI specification json (I guess that’s why they chose it).

Let’s take a super simplified example of a json specification:

```json
{
    "list1": [\
        "item1",\
        "item2"\
        ...\
    ],
    "existingName": "foo"
}

```

And a file called `test.mustache`, like so:

```json
{{#list1}}
	{{{.}}}
{{/list1}}
```

This is very reminiscent of HTML in that it has both a start and an end “tag”. In this case, it uses {{}} instead of <> in HTML, and the start tag has a #, but it is structurally the same. The result of the above would be a file called test that contains:

item1

item2

While there is no `if` statement, you can test for the absence of a tag by doing the following:

```json
{{^notExistName}}
// There was no input
{{/notExistName}}
```

Which would print the “There was no input” comment because the sample json above had `"existingName"` not the `notExistName` tag here. Lastly, you may occasionally encounter a bug where you have a Mustache like:

```json
{{#list1}}
    {{.}}
{{/list1}}

```

And you see output like &quot;item1&quot. Remember how HTML was the original target language of Mustache? Well, Mustache will HTML-escape your values by default unless you use three braces like {{{.}}} instead of {{.}} when iterating through values.

### **Test Strategy**

Before we get to templating out a test, let’s first decide what we are going to test. The SDK is going to contain:

1. Client code which wraps http connections and auth configuration
2. API methods that correspond to endpoints we have in our OpenAPI specification
3. Model classes that correspond to request and response payloads

We’ll start with the last point, since the other two are better suited to integration tests rather than unit tests. **We’ll work through a good basic test: deserializing a model class from an example json payload.** First, we’ll need an example json payload. Remember that the input to the `*.mustache` template files is the OpenAPI json specification of your API. We, therefore, need to add our example payloads in there. At Merge, we use OpenAPI custom vendor extensions for this, which is just a fancy way of saying we add a property that begins with `x-`. You can see this in practice by going to [one of our specifications](https://api.merge.dev/api/ats/v1/schema) and looking for `x-merge-sample-json`.

### **Modifying an Existing Python Template**

Now let’s modify that `model_test.mustache` template file to output our deserialization test. If at any point your generated output does not match expectations, use this Mustache line to see what raw data you are dealing with:

{{{.}}}

There’s not really an easy way to set breakpoints and debug, so the only option is to guess and check based on what the input is and where you are in the Mustache template. For example, modifying the file like so:

```python
def test{{classname}}(self):
        """Test {{classname}}"""
        # FIXME: construct object with mandatory attributes with example values
        # model = {{classname}}()  # noqa: E501
        # Add this
{{{.}}}
```

‍

Will show you the json payload of the model from your API specification as it is seen by the OpenAPI Generator tool.

There are a great many properties which we don’t care about, but with some work, we find the sample json custom property we added to the API spec earlier can be output by modifying the Mustache file:

```json
{{#vendorExtensions}}
	raw_json = ""
  	{{x-merge-sample-json}}
  	"""
{{/vendorExtensions}}
```

Unfortunately, this will produce some weird stuff if we don’t plan on adding a test to every model class. This is where we run into difficulties with a lack of `if` statements, so instead we have to think like a browser and do something more verbose:

```json
{{#vendorExtensions}}
{{#x-merge-sample-json}}
	raw_json = """
  	{{{.}}}
  	"""
{{/x-merge-sample-json}}
{{^x-merge-sample-json}}
	"""
  	No test json responses were defined for {{classname}}
  	"""
  	raw_json = None
{{/x-merge-sample-json}}
{{/vendorExtensions}}
```

Remember how the Mustache tag like {{^name}} gets applied when name is missing from your input? This is how we simulate an if statement, and you’ll see this pattern all over the default template files in the OpenAPI Generator repository.

From here, we can write standard json into our template file:

And there you have it, a generated file like so:

- [Merge Python SDK templated model test](https://github.com/merge-api/merge-hris-python/blob/a71a9c219c1d2eb7a2e1c1b966e33c507141a7e3/test/test_sync_status.py)
- [Merge Go SDK templated model test](https://github.com/merge-api/merge-hris-go/blob/e2cf1a566343d3c03d5eed3044f51ddbf9c2736f/model_sync_status_test.go)

### **Generating Your Own Output Files**

OpenAPI Generator also provides [the ability to generate files not in the default templates folder](https://openapi-generator.tech/docs/customization).

Specifically, the [go template directory](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator/src/main/resources/go) has no `model_test.mustache` file at all so we can use a config file like this:

```json
{
	"templateDir": "/local",
    "files": {
      "PATH_TO_YOUR_TEMPLATES/go_test.mustache": {
        "templateType": "Model",
        "destinationFilename": "_test.go"
      }
    }
}
```

‍

to create a file as opposed to overriding one. The example above, along with Merge’s `go_test.mustache` file, is what generated the Go test class linked above.

### **Conclusion**

Perhaps you find yourself in a similar situation to Merge, where you need to generate SDKs for a variety of languages and you want the model classes to have test coverage without writing each one by hand. With the approach outlined here, we can now test our SDKs for every language to provide a baseline guarantee that the model changes we make to our API specification will result in functional request and response classes. Additionally, we’ve added these tests to our continuous integration and delivery processes so that any time we change our API we re-validate against our SDK client code. This is all to ensure that the SDKs our customers rely on are tested thoroughly, as our customers are relying on these classes to communicate with Merge API in order to support the features they are shipping that need [HR, Payroll](https://merge.dev/categories/hr-payroll-api), [Accounting](https://merge.dev/categories/accounting-api), and [Recruiting](https://merge.dev/categories/ats-recruiting-api) data.

Curious about learning about what Merge does, or interested in joining? Check out our [careers](https://www.merge.dev/careers) page, or poke around in our [docs](https://www.merge.dev/docs/) for more info!

‍

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lee Wang

Software Engineer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7c849fa3-af95-4a83-b27d-93466f2372fe&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=56d38cc9-8657-4f9a-b4e4-bb16a7a42d73&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fopenapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=7c849fa3-af95-4a83-b27d-93466f2372fe&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=56d38cc9-8657-4f9a-b4e4-bb16a7a42d73&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fopenapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=743e1425-8e36-4038-baab-7ac25f12163d&bo=2&sid=763783e03e8c11f0bf750f2a05a20d7f&vid=763795803e8c11f090f0b398e50a187f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=OpenAPI%20tutorial%3A%20How%20to%20automatically%20generate%20tests%20for%20OpenAPI%20generator%20SDKs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fopenapi-tutorial-how-to-automatically-generate-tests-for-openapi-generator-sdks&r=&lt=664&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=19063)