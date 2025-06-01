---
url: "https://www.merge.dev/blog/field-mapping-features"
title: "3 newly-launched Field Mapping features that can help you sync custom data easily and effectively"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/field-mapping-features#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/field-mapping-features#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/field-mapping-features#)

Table of contents

[Pick out the right set of remote fields with Field Coverage](https://www.merge.dev/blog/field-mapping-features#pick-out-the-right-set-of-remote-fields-with-field-coverage)

[Access custom fields within objects or lists with Advanced Mapping](https://www.merge.dev/blog/field-mapping-features#access-custom-fields-within-objects-or-lists-with-advanced-mapping)

[Confirm that your mappings are correct with Preview Values](https://www.merge.dev/blog/field-mapping-features#confirm-that-your-mappings-are-correct-with-preview-values)

[Final thoughts](https://www.merge.dev/blog/field-mapping-features#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffield-mapping-features)

##### Just for you

No items found.

# 3 newly-launched Field Mapping features that can help you sync custom data easily and effectively

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Since our inception, we’ve been heavily focused on building out comprehensive Common Models to help customers access and sync all the data they need.

However, there’s always custom data that’s impossible to account for proactively.

This led us to offer [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/), which enables a customer or end-user to add a custom field to one of our Common Models and map them to an end-user’s application.

[![An example of using Field Mapping](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/669fe5784890db3dab96d193_AD_4nXcnJPwnupjXmzH6O_irhkYArNKMeYPXC9G2p_S8JjhqPLgYz372E27cyF3kRI4d4B0sUy904sK2r7kFgHg4i5skKq6Gf3xM9U2mqMS07Lgp6THzTtm_D2MHlS2P7xNjvGozKF3E0lj8lWNOVK-F1jJanMr3.webp)

_Using Field Mapping, you can hypothetically map the field “custom\_score” in Greenhouse to a new Common Model field in Merge’s ATS Unified API, “technical\_assessment\_score”_

And while we already have more than a hundred customers using Field Mapping successfully, we want to make the experience of mapping remote fields (or fields that aren’t mapped to one of Merge’s Common Models by default) through the feature even easier.

To that end, we’re excited to announce that we’ve released 3 new features for Field Mapping: Advanced Mapping, Field Coverage, and Preview Values.

You can read on to learn how they work, why they’re valuable, and how you can use them.

## **Pick out the right set of remote fields with Field Coverage**

As your customers’ businesses mature, they’ll likely deprecate old fields and replace them. In a customer’s CRM alone, this can happen to lead stages, forecast categories, customer segments, and so on.

To ensure you avoid mapping fields that are rarely—if at all—in use and pick the popular versions instead, you can use Field Coverage.

The feature can be accessed in your Merge Dashboard or via the GET /remote-fields endpoint. In either case, you’ll learn the percentage of “Coverage”, which denotes how frequently data is populated for a given remote field in an end-user’s application.

[![A screenshot example of Field Coverage](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd92_666729f3792de6aad3e2c40b_fieldmapping%2520(1).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd92_666729f3792de6aad3e2c40b_fieldmapping%2520(1).webp)

The higher this percentage is in relation to a similar remote field, the more likely it's the remote field you want to map.

## **Access custom fields within objects or lists with Advanced Mapping**

Certain custom objects can be incredibly complex and extensive, especially in enterprise applications like Workday, NetSuite, Salesforce, among others. This can make it difficult to map, let alone find, a specific remote field.

For example, an employment type object may have several objects, each with nested fields. If you only want to map an individual field, like a description of the employment type, it can be difficult to isolate it from the others successfully.

To help you only sync a specific field or to apply unique business logic, you can, within the Merge Dashboard, use JMESPath to create a JSON query that helps you select the individual field. We make this easy with our default click-to-generate query functionality but you can also write your own complex queries.

[![A screenshot example of Advanced Mapping](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd95_6667299713ef70e946f69f95_Enterprise%2520Grade%2520Field%2520Mapping%2520(2).webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd95_6667299713ef70e946f69f95_Enterprise%2520Grade%2520Field%2520Mapping%2520(2).webp)

_You can use a JSON query to select the field "Home" from a nested employee object_

_Interested in using Advanced Mapping? Learn more about leveraging it on_ [_our Help Center_](https://help.merge.dev/en/articles/9269164-advanced-field-mapping-with-jmespath) _._

## **Confirm that your mappings are correct with Preview Values**

Despite your best efforts, you may accidentally map the wrong fields to Merge’s Common Models, preventing you from syncing data in the way you intended.

To help you avoid this scenario, you can use Preview Values to double check the mapped data.

The way it works is simple: Within the Merge Dashboard, add an ID associated with one of Merge’s Common Models (e.g., an employee ID in Merge). If the mapping is set up correctly, the right set of remote field values from the end-user’s application will appear automatically. You’ll also see how each remote field maps to the corresponding normalized field in Merge.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd8d_66636be04e7a9197a7040af6_AD_4nXeAGWP0wFLhE9otFQCaLrSQSRMEgnzuGEnMGCZWTiGgSKNG0FFbDt_X8au7KniKDrExDVDJDzqwJSOyTaj-FwcgumJHtKMlvjftT238ayFVvmPdqO8rsk1b-0MxcSba7Pu-MF4naOdwRDwP1sRcLx0o34U.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67858c79d27e448824fdcd8d_66636be04e7a9197a7040af6_AD_4nXeAGWP0wFLhE9otFQCaLrSQSRMEgnzuGEnMGCZWTiGgSKNG0FFbDt_X8au7KniKDrExDVDJDzqwJSOyTaj-FwcgumJHtKMlvjftT238ayFVvmPdqO8rsk1b-0MxcSba7Pu-MF4naOdwRDwP1sRcLx0o34U.webp)

_You can use Preview Values to confirm that the right values appear for a candidate in an end-user’s ATS_

Since this feature works for any Common Model ID, you can use it for any integration that uses Field Mapping. It also works quickly and—as our screenshot shows—is intuitive to use, so it should become part of your testing process for any integration that uses Field Mapping.

## **Final thoughts**

As we keep adding Common Models and enhancing existing ones, the need for Field Mapping will continue to decline.

But if and when the feature is needed for any of our customers, we want it to help them or their end users map custom data quickly, easily, and successfully.

We think these Field Mapping features, along with others we plan to release in the future, will go a long way in helping us meet these goals.

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

#### Ready to build highly-custom product integrations?

Learn how, exactly, Merge can support your unique integration requirements by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Ffield-mapping-features)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b068b3c7-3dac-49ca-bc6b-62aea6ccc8fd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=87951c15-5bd5-48ec-97fa-552a00819399&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffield-mapping-features&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=b068b3c7-3dac-49ca-bc6b-62aea6ccc8fd&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=87951c15-5bd5-48ec-97fa-552a00819399&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffield-mapping-features&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=664f7333-0b49-49ee-a397-7411827d273f&bo=2&sid=e6c6c3403e8c11f09b36f3750107e0e9&vid=e6c71c203e8c11f0ac72b725fe84bcd2&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=3%20newly-launched%20Field%20Mapping%20features%20that%20can%20help%20you%20sync%20custom%20data%20easily%20and%20effectively&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Ffield-mapping-features&r=&lt=474&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=182415)