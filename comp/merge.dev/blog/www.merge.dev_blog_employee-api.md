---
url: "https://www.merge.dev/blog/employee-api"
title: "A guide to using employee APIs"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/employee-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/employee-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/employee-api#)

Table of contents

[What is an employee API?](https://www.merge.dev/blog/employee-api#what-is-an-employee-api)

[Employee API example](https://www.merge.dev/blog/employee-api#employee-api-example)

[Employee API integration use cases](https://www.merge.dev/blog/employee-api#employee-api-integration-use-cases)

[Benefits of using an employee API](https://www.merge.dev/blog/employee-api#benefits-of-using-an-employee-api)

[Sync customers’ employee data with your product through Merge](https://www.merge.dev/blog/employee-api#sync-customers-employee-data-with-your-product-through-merge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Femployee-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**What are payroll integrations? Here's what you need to know**](https://www.merge.dev/blog/payroll-integrations)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cede4e321d978c2aa62_Lead_API.webp)**ATS integration: definition, examples, and tools**](https://www.merge.dev/blog/guide-to-ats-api-integrations)

# A guide to using employee APIs

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fbec669a2e89f9ad9cd39_QuickBooks_Online_API_guide.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

There are several ways to sync employee data, from using SFTP to deploying custom scripts. APIs, however, offer the most reliable, performant, and secure method.

We’ll break down why that is. But first, let’s align on the definition of an employee API, cover common employee API endpoints from a popular HRIS provider, and break down a few employee API integrations.

## **What is an employee API?**

It’s any endpoint from an API provider that lets you sync employee data. This can include employees’ first and last names, phone numbers, email addresses, employment statuses, and more.

In addition, you can use an employee API to sync data internally (i.e., between the applications your organization uses) or with your product (i.e., between your customers’ HRIS solutions and your product)

[![Employee API integration scenarios](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3b4800f272bbe656b_AD_4nXf4JIgst-XP-Z_tXvP2zWgQKKAres3TAyMMnosP-lWQtDuOJU5QE-zqT8G74g0DJDolVM7TzJJiO1hko1_cODrPWvOolaOss4CwDPOtln4N4KHasZiuW5Cl-KllQ28A9qvxk8YOF9TQCuWMa1DPqRpNcT-s.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3b4800f272bbe656b_AD_4nXf4JIgst-XP-Z_tXvP2zWgQKKAres3TAyMMnosP-lWQtDuOJU5QE-zqT8G74g0DJDolVM7TzJJiO1hko1_cODrPWvOolaOss4CwDPOtln4N4KHasZiuW5Cl-KllQ28A9qvxk8YOF9TQCuWMa1DPqRpNcT-s.webp)

_Related:_ [_What is HRIS integration?_](https://www.merge.dev/blog/guide-to-hris-api-integrations)

## **Employee API example**

BambooHR, a widely-used HRIS solution, offers the following employee API endpoints (among many others):

- Fetch individual employees and specific fields associated with each via the endpoint `GET https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/`

- Create individual employees and include associated fields, such as dates of birth, social security numbers, genders, and hire dates, via the endpoint `POST https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/`

- Retrieve an entire employee director to sync employee data at scale via the endpoint `GET https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/directory`

- Update specific employee fields for a certain employee through the endpoint `POST https://api.bamboohr.com/api/gateway.php/{companyDomain}/v1/employees/{id}/`

_Learn more about BambooHR’s employee endpoints by visiting_ [_their docs_](https://documentation.bamboohr.com/reference/get-company-information) _._

## **Employee API integration use cases**

To help bring our definition and example to life, let’s walk through a few use cases.

We’ll start with a couple of internal examples and then break down a few customer-facing ones.

#### **Streamline employee onboarding**

To help your HR team kickstart the onboarding process on time and for every incoming team member, you can connect your ATS (e.g., Greenhouse) with your HRIS (e.g., Gusto) and implement the following flow: Once a candidate is marked as hired in the ATS, a new employee gets created in the HRIS.

Certain fields can also populate for each employee added to the HRIS, such as first and last names, job titles, departments, addresses, etc.

[![Syncing new hires between Greenhouse and Gusto](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3f960d7f6c8ca5776_AD_4nXfJW3lgQ4sQim74LjaoxdemgJbW8Cchd-LTKqQmJLWAIr75U06wlqTegZrbdJ2iWNAlaaoAYXcn5f0gdCS_0fs0vP8u26g0Te6ZzDmz2HH_SVGmO0OhhzDzvtznTbihLP6E2ROoY1X17SxIj6BpJBMb8aI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3f960d7f6c8ca5776_AD_4nXfJW3lgQ4sQim74LjaoxdemgJbW8Cchd-LTKqQmJLWAIr75U06wlqTegZrbdJ2iWNAlaaoAYXcn5f0gdCS_0fs0vP8u26g0Te6ZzDmz2HH_SVGmO0OhhzDzvtznTbihLP6E2ROoY1X17SxIj6BpJBMb8aI.webp)

#### **Notify the company of key milestone events**

To recognize employees when they reach a certain work anniversary, get promoted, married, or reach another milestone event, you can integrate your HRIS with your business communications platform (e.g., Slack) and implement the following workflow: Once a certain employee milestone event gets detected in the HRIS, a predefined Slack message gets delivered to a specific Slack channel.

[![Sending messages Slack when employee milestone events take place ](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d35f7d5ca91c81f763_AD_4nXfIlKAZBsmjIqeZViioGDqsssuD_iwPImU6QweNfy2qEvd2RDBqA2mfVE5m7J2KyEDnhF0BTA5LWvyDeufI8mXYL-nQAdB1MelGQnp11Q2elNRuFkttKQlQBDu0Cp5os2Xy7hAhAMDbvMswSbf3cLaTkKY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d35f7d5ca91c81f763_AD_4nXfIlKAZBsmjIqeZViioGDqsssuD_iwPImU6QweNfy2qEvd2RDBqA2mfVE5m7J2KyEDnhF0BTA5LWvyDeufI8mXYL-nQAdB1MelGQnp11Q2elNRuFkttKQlQBDu0Cp5os2Xy7hAhAMDbvMswSbf3cLaTkKY.webp)

#### **Help users deliver department-specific recognitions**

Say you provide a peer-recognition solution—like Bonusly—and want customers’ employees to access and give department-specific recognitions.

To do this, you could integrate with customers’ HRIS solutions and add employees from these systems with your product, which would include the departments they work in, on a recurring cadence. Employees can then easily find and distribute their department-specific recognitions as soon as they're provisioned as users in your product.

[![Department-specific award given via Bonusly](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d46c53172a7d352e36_AD_4nXd7i76h8sDU59WrPEUP5xBWWVlH1flcOzLevy3Ijr5D0-d9EaHL-obJOh5YitW1HIV0qoEWLh1gmx8CcZ3R3lUe_tkkyX2m5kpsa4Bo8EfvC3_7G2NiNPVdTDCNSy2EHwAocpKeOc4ucL7wAdiFSHUNKFbF.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d46c53172a7d352e36_AD_4nXd7i76h8sDU59WrPEUP5xBWWVlH1flcOzLevy3Ijr5D0-d9EaHL-obJOh5YitW1HIV0qoEWLh1gmx8CcZ3R3lUe_tkkyX2m5kpsa4Bo8EfvC3_7G2NiNPVdTDCNSy2EHwAocpKeOc4ucL7wAdiFSHUNKFbF.webp)

[_Bonusly_](https://www.merge.dev/case-studies/bonusly) _uses customer-facing HRIS integrations to enable employees in certain functions to give relevant awards_

#### **Automate user provisioning and de provisioning in your product**

To help users access your product with the right level of permissions as well as remove their access once they’re terminated, you can integrate with customers’ HRIS solutions and implement the following syncs:

- Once a customer adds an employee in the integrated HRIS, that individual is queued as a user that can be added to your product. An admin in your app can then review the individual and decide whether to add them

[![Adding users in BILL Spend & Expense](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95330fc437183c8133c5_AD_4nXdpCYz_ivX_A-vdhuwJGihYy6AtR7UBhAbTxqON3ENI_JumVEC2vG5TqsGj9JuMzud8VJzKupYwOBGMP388d2jhULHroW2gXW_WAtzpIpv4xkoNb7SHF8ihZzJRDZG3wJdJVah9RnwJ98UPaYLSxuneqSPr.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa95330fc437183c8133c5_AD_4nXdpCYz_ivX_A-vdhuwJGihYy6AtR7UBhAbTxqON3ENI_JumVEC2vG5TqsGj9JuMzud8VJzKupYwOBGMP388d2jhULHroW2gXW_WAtzpIpv4xkoNb7SHF8ihZzJRDZG3wJdJVah9RnwJ98UPaYLSxuneqSPr.webp)

[_BILL Spend & Expense_](https://www.merge.dev/case-studies/bill) _admins can review new hires individually, create groups via filters, and ultimately decide who to add_

- Once a customer removes an employee in the integrated HRIS, an admin in your product can get notified and remove them with the click of a button

[![How BILL Spend & Expense users can deprovision users once they're removed or marked as terminated in the connected HRIS](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa7bb6a7ce4772855ea44e_66708f36e85cd7fe7ce8373b_AD_4nXeYql95y2xOnwwNHccfxXzPudpaCXFViav0_CNtBF2vovxXLQ863qjxGMxvnBRd9VxJ9YNDgI0E97aGwQ27-BWK7RBGHshxh71e5WeOnr8u1lGO0gujWzIkCsGyXEykWUQc4NZtOjdQkHzJczAyPd05oLXK.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa7bb6a7ce4772855ea44e_66708f36e85cd7fe7ce8373b_AD_4nXeYql95y2xOnwwNHccfxXzPudpaCXFViav0_CNtBF2vovxXLQ863qjxGMxvnBRd9VxJ9YNDgI0E97aGwQ27-BWK7RBGHshxh71e5WeOnr8u1lGO0gujWzIkCsGyXEykWUQc4NZtOjdQkHzJczAyPd05oLXK.webp)

_An admin in BILL Spend & Expense can remove users in a matter of clicks_

## **Benefits of using an employee API**

Here are just a few benefits to keep in mind:

- **Robust security:** Employee APIs can include highly-sensitive data, such as social security numbers and home addresses. By using secure authorization protocols, like OAUTH 2.0, you can keep this data limited to the appropriate requestors

- **High performance:** Your integration use cases might require syncing employee data on a frequent cadence, such as every hour or every few minutes. API-based connections can help address this requirement

- **Universal accessibility:** Most HRIS providers offer APIs, and those that do will almost certainly provide employee APIs—as employee data is a fundamental part of HRIS solutions

- **3rd-party integration support:** There are a variety of [3rd-party integration solutions](https://www.merge.dev/blog/3rd-party-integration) that can help you build to employee APIs and maintain those connections, making the process of implementing and scaling these integration builds relatively easier than in the past

## **Sync customers’ employee data with your product through Merge**

Merge, the leading unified API solution, lets you add hundreds of integrations to your product by simply building to its unified API. This includes dozens of HRIS solutions that are popular across different regions, industries, and company sizes.

[![Merge's HRIS integrations](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3580e687ffd6fd930_AD_4nXflI9xRYKgNUlycVqKfiRO8nzWBtr3oJlgDjluiZBfGZL5u_gDaA6j_Erzffv1Nj_N7nI0eeQrNDeRipdz9TFmqVP9A6t_9AC_16axQjSAWefOQ1Qer0fbOs4zWa_4HVSG15eKTt-Ua5axRy3Xm4MxBUc4q.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e9f1d3580e687ffd6fd930_AD_4nXflI9xRYKgNUlycVqKfiRO8nzWBtr3oJlgDjluiZBfGZL5u_gDaA6j_Erzffv1Nj_N7nI0eeQrNDeRipdz9TFmqVP9A6t_9AC_16axQjSAWefOQ1Qer0fbOs4zWa_4HVSG15eKTt-Ua5axRy3Xm4MxBUc4q.webp)

_A snapshot of some of the HRIS integrations Merge supports_

In addition, through each HRIS integration, you can sync a wide range of employee data via Merge’s comprehensive [Employees Common Model](https://docs.merge.dev/hris/employees/) and advanced syncing features (e.g., [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/)).

Learn more about using Merge to sync employee data with your product by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Femployee-api).

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=cf9cfe2a-2d32-436e-aed2-3b31f6f15df6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5bdf21ba-be22-45c4-b6ea-c6d68ef45534&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Femployee-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=cf9cfe2a-2d32-436e-aed2-3b31f6f15df6&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=5bdf21ba-be22-45c4-b6ea-c6d68ef45534&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Femployee-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ff20f6b7-4dac-48dc-ab1b-0ca97ecf168a&bo=2&sid=ad1d94203e8c11f08de1b196c2ea6271&vid=ad1f5cd03e8c11f0b147676ca909b0ae&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20to%20using%20employee%20APIs&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Femployee-api&r=&lt=1007&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=31153)