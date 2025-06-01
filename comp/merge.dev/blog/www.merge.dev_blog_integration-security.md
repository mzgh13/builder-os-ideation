---
url: "https://www.merge.dev/blog/integration-security"
title: "How to build secure integrations (5 tips)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/integration-security#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/integration-security#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/integration-security#)

Table of contents

[Overview on integration security](https://www.merge.dev/blog/integration-security#overview-on-integration-security)

[Integration security challenges](https://www.merge.dev/blog/integration-security#integration-security-challenges)

[Integration security best practices](https://www.merge.dev/blog/integration-security#integration-security-best-practices)

[How to evaluate integration security features in 3rd-party solutions](https://www.merge.dev/blog/integration-security#how-to-evaluate-integration-security-features-in-3rd-party-solutions)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-security)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7300295f40b50718fc_7.webp)**How Merge helps companies in Europe build secure, reliable, and powerful product integrations at scale**](https://www.merge.dev/blog/how-merge-supports-europe)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74f43703047123799f_Anthropic_API_key.webp)**How to run API integration tests**](https://www.merge.dev/blog/api-integration-testing)

# How to build secure integrations (5 tips)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Integrations often deal with a range of sensitive data, whether it's personally identifiable information (PII) on employees, business financials, sensitive information on customers, and so on.

To ensure this information is kept secure over time, you should adopt a variety of security measures and, if you’re using a 3rd-party integration solution, use a platform that’s adopted the proper security protocols and features.

We’ll break down best practices for protecting your integration data and the security features to look for in 3rd-party platforms. But first, let’s align on the definition of integration security and the challenges of securing this data successfully.

## **Overview on integration security**

It's a set measures that your business and your 3rd-party vendors take to protect integration data. These measures can take the form of authentication processes, policies for storing and using sensitive data, scopes for restricting the data that’s synced, and more.

_Related:_ [_An overview on API integration security_](https://www.merge.dev/blog/api-integration-security)

## **Integration security challenges**

While integration security is critical, performing it successfully is anything but.

Here are a few common challenges to keep in mind when building and maintaining your integrations:

### **Certain integration methods are less secure**

Integrating data through files or scripts is often less secure than using application programming interfaces (APIs).

When [integrating data via files](https://www.merge.dev/blog/flat-file-integration), for example, you may need to store the files in an intermediate system that’s vulnerable to unauthorized access. And, in the case of scripts, they may fail to encrypt data during transmissions effectively, making their data prone to interceptions.

Since APIs aren’t always available—whether that’s because the 3rd-party application doesn’t offer APIs or doesn’t provide the specific endpoints you need—you may be forced to adopt file or script-based integrations, which means facing the security risks of either approach.

_Related:_ [_Hows APIs and screen scraping compare_](https://www.merge.dev/blog/screen-scraping-vs-api)

### **Difficult to set up and maintain scopes at scale**

Many 3rd-party integration tools don’t offer scopes—or the ability to customize the data that can be accessed and synced for a given authorized client—out of the box. And tasking in-house engineers with setting them up can prove difficult; it can be extremely time and resource intensive to implement and maintain each scope, and as the number of integrations you implement increases, the work around setting up and maintaining scopes only grows.

The sheer amount of work involved in managing scopes—if managed in-house—can also lead to human errors that either provide API consumers with too much access (which naturally poses a security risk) or not enough (which is a poor experience for your API consumers).

### **Hard to use API logs effectively for identifying and addressing security issues**

[API logs](https://www.merge.dev/blog/api-logs) can play a critical role in surfacing security issues, but in order for them to do so, they'll need to collect and display enough information from a given API request.

This can easily turn to overly-comprehensive logs that are difficult to sift through, analyze, and take action from—especially as you scale your integrations and the number of API calls you make.

You’ll ultimately need to strike the right balance of information, which can be an exercise that your team doesn’t figure out successfully or quickly.

## **Integration security best practices**

To help you build secure integrations, it’s worth keeping the following in mind:

### **Use APIs when possible**

As mentioned previously, APIs offer a more secure integration method than alternative approaches. They use authentication and authorization mechanisms like API keys and tokens; they often use HTTPS to encrypt data in transit; they generate detailed logs, and more.

With this in mind, prioritize [API-based integrations](https://www.merge.dev/blog/api-integration) when thinking through your integration approaches.

### **Build automated processes for resolving security issues**

You’re likely to run into certain integration security issues frequently, such as consumers exceeding their API rate limits. To help you pinpoint and resolve these issues on time, you can build internal workflow automations.

[![Integration issue detection workflow](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c7f3cf7336d21f437c_AD_4nXeeKXZct0SoJXQ9LCFX1Tz9VE9NSw_mPkzQdJOQykNF-6InZOcE_xAn_apeQ_x2dWA-txJkPimCSEsNqBQM4mg1wcutjXZTRy2tvZC2de0OzRJoGIgyhm0asCIZf_ExSUQy2exesaipGHQb7ppsT-p9ZBU.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c7f3cf7336d21f437c_AD_4nXeeKXZct0SoJXQ9LCFX1Tz9VE9NSw_mPkzQdJOQykNF-6InZOcE_xAn_apeQ_x2dWA-txJkPimCSEsNqBQM4mg1wcutjXZTRy2tvZC2de0OzRJoGIgyhm0asCIZf_ExSUQy2exesaipGHQb7ppsT-p9ZBU.webp)

For example, you can connect the tool that generates API logs and detects issues (e.g., Datadog) with the application your engineers already work in (e.g., Slack) and build a flow where once a certain issue is detected in the former, a preconfigured message gets to a specific channel in the latter. The message can alert your team of the issue and the suggested steps to troubleshoot and resolve it.

_Related:_ [_A guide handling API errors_](https://www.merge.dev/blog/api-error-handling)

### **Perform extensive integration security tests**

You can build significantly more secure integrations by testing them extensively and addressing any of their security vulnerabilities before pushing them to production.

This can be performing routine code reviews to look for potential vulnerabilities, conducting penetration testing to uncover weaknesses, authentication testing to verify that your authentication mechanisms work correctly, and so on.

### **Protect your API keys and tokens**

If your [API keys](https://www.merge.dev/blog/api-key) or tokens get leaked, malicious actors may be able to access highly-sensitive data. To prevent this from happening, you can limit the lifespans of your tokens and API keys; use a secure vault service to store credentials; avoid hardcoding them in your source code, and more.

### **Carefully review the 3rd-party integration solutions from a security lens**

Every 3rd-party integration solution has a unique set of features, policies, and processes when it comes to handling and protecting sensitive data.

It’s in your best interest to review each of these aspects across potential vendors to ensure you pick the solution that has the best overall approach to security (among other areas).

With this in mind, we’ll review the top areas you should evaluate for a given vendor in the following section.

## **How to evaluate integration security features in 3rd-party solutions**

Here’s the criteria you should use during your vendor evaluations:

### **Assess the vendors’ security and compliance credentials**

By simply scanning vendors’ sites, you should be able to tell whether they adhere to compliance frameworks, like GDPR, SOC 2 Type II, ISO 27001, etc.

[![The frameworks Merge adheres to](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c74af8ad7c78d5c78c_AD_4nXeaFoTiT7zfozZKVb8p7dXb-iP9iAzxuKqKMemAFpyj0fb2qzJIaWew8y4_WQJ4Duq4Usu1BcnWCaZ_ErISoc8Ay3CId4KApwtH9ZGNt2QO3GGK-NYUVZ3KCU6OhY-tBN6WuNuoFfcED14NFbfzrPX7t68.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c74af8ad7c78d5c78c_AD_4nXeaFoTiT7zfozZKVb8p7dXb-iP9iAzxuKqKMemAFpyj0fb2qzJIaWew8y4_WQJ4Duq4Usu1BcnWCaZ_ErISoc8Ay3CId4KApwtH9ZGNt2QO3GGK-NYUVZ3KCU6OhY-tBN6WuNuoFfcED14NFbfzrPX7t68.webp)

_Merge, the leading unified API solution, explicitly lists the compliance frameworks it adheres to on_ [_its security page_](https://www.merge.dev/security)

You should also double check these claims by reviewing the documentation that validates a given vendor’s compliance with a security framework. And if this documentation isn’t available on their site, you can ask your assigned sales rep for a copy.

### **Review the vendors’ security features and capabilities**

There’s a wide range of features that can help you protect your integration data.

Scopes, as an example, can help ensure that you follow the principle of least privilege, as it lets you restrict the data you’re able to access from a given integration.

‍

[![A screenshot of Scopes in Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c7d773ba4edcf385fa_AD_4nXc_Xp5Uby0z6xeS21KbpWPixWKLohiusIZ9UBmEIuc6ly_dGKC1d_L-Q6H3tlJhGggRfDEomOjxk3Gsw3swgnoP6YBojI76pwC22P9QvBLv9to1u4jHfhZyWOv435JKvN4rwdkAExK9q3qRJedIIERe4sb5.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c7d773ba4edcf385fa_AD_4nXc_Xp5Uby0z6xeS21KbpWPixWKLohiusIZ9UBmEIuc6ly_dGKC1d_L-Q6H3tlJhGggRfDEomOjxk3Gsw3swgnoP6YBojI76pwC22P9QvBLv9to1u4jHfhZyWOv435JKvN4rwdkAExK9q3qRJedIIERe4sb5.webp)

_Merge lets you pick and choose the fields that you sync. This can apply to individual customers or any that uses a certain type of integration (e.g., HRIS integrations)_

Scopes should also provide fine-grained features for accessing and performing actions on data. For example, it should let you select from actions like “Read” or “Write”; and it should let you apply scopes for either individual customers (with especially stringent security needs) or everyone.

Here are just a few more features to look for:

- **Role-based access control:** You should be able to assign roles to different users so that only the right set of individuals can view and perform actions on specific types of data

- **Audit trail:** You should be able to view all of the activities that users take in the integration solution so that you can easily identify the sources of issues over time

[![Screenshot of Merge's Audit Trails feature](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c891aa43629242a94d_AD_4nXdDVE5V207CHI_t90aFVbuIYgxdw1JgTi-QI6iuFK4V38-WDgdKk33KOCboKQFibyXCb7Hme8pg9I-AjYbXZjNC4Ns7D_KZy0tN8p5zEjrhHnJaJ2ohXYnTRcZwwIDGf6FUT0v_tyAM_PHmi0QZT5i1Kp5y.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667ae3c891aa43629242a94d_AD_4nXdDVE5V207CHI_t90aFVbuIYgxdw1JgTi-QI6iuFK4V38-WDgdKk33KOCboKQFibyXCb7Hme8pg9I-AjYbXZjNC4Ns7D_KZy0tN8p5zEjrhHnJaJ2ohXYnTRcZwwIDGf6FUT0v_tyAM_PHmi0QZT5i1Kp5y.webp)

_Merge’s Audit Trail feature lets you see all of the activities specific users performed, when they were performed, and from where—along with filters to find specific activities faster_

- **Multi-tenant support:** You should be able to store data in the regions that you and your customers operate in, as doing so is likely necessary for meeting your data residency requirements and that of your customers

_Related:_ [_Merge now offers a multi-tenant in APAC_](https://www.merge.dev/blog/apac-multi-tenant)

### **Review the types of integrations the platforms support**

As mentioned earlier, API-based integrations are generally the most secure, so it’s worth verifying with vendors that the integrations you care about are supported by APIs—or through another mechanism.

For example, [Finch offers “assisted integrations”](https://www.merge.dev/blog/automated-vs-assisted-integrations), which are performed manually and in a way that’s problematic from a security (and performance) perspective:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665f3a9d76b3064b8c83d022_AD_4nXfMbisNtvq_mdFEE2IAbaYh6KYD-_Pe82Wc8fYcTt4iNe0PLKPK80pwfx8bpnXk0JYWoKqORwZGgsBjTAzwzdsIX5zRosvAekX7ifn-KhqNUuPQ9_7hqLHTfppKC-Lq6oZe1DPOU2G4Gm8VsfzgpLgpPZ62.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665f3a9d76b3064b8c83d022_AD_4nXfMbisNtvq_mdFEE2IAbaYh6KYD-_Pe82Wc8fYcTt4iNe0PLKPK80pwfx8bpnXk0JYWoKqORwZGgsBjTAzwzdsIX5zRosvAekX7ifn-KhqNUuPQ9_7hqLHTfppKC-Lq6oZe1DPOU2G4Gm8VsfzgpLgpPZ62.webp)

‍

If there's ambiguous language around the integration method involved—such as assisted integrations—you should ask for specifics on how it works so that you can get a full picture of the security risks you'd take on.

#### Ready to build secure integrations?

Learn how Merge can support your security and compliance needs by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fintegration-security)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1da7dc0a-6259-4c28-81a7-9145007b3aff&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b0109ff5-12b1-44be-b291-587f3f622d1a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-security&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=1da7dc0a-6259-4c28-81a7-9145007b3aff&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b0109ff5-12b1-44be-b291-587f3f622d1a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-security&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=3ea31e89-e1f5-49ba-bcfb-f6383477244f&bo=2&sid=f497afb03e8b11f09ea96fce89e33683&vid=f497e7e03e8b11f0b28e314c3600c03f&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20build%20secure%20integrations%20(5%20tips)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fintegration-security&r=&lt=1039&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=386403)