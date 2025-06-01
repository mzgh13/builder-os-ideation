---
url: "https://www.merge.dev/blog/hr-api"
title: "HR API: what you should know about using any"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/hr-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/hr-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/hr-api#)

Table of contents

[What is an HR API?](https://www.merge.dev/blog/hr-api#what-is-an-hr-api)

[HR API examples](https://www.merge.dev/blog/hr-api#hr-api-examples)

[HR API integration examples](https://www.merge.dev/blog/hr-api#hr-api-integration-examples)

[Add dozens of HR integrations to your product through a single API](https://www.merge.dev/blog/hr-api#add-dozens-of-hr-integrations-to-your-product-through-a-single-api)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhr-api)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/671fbec669a2e89f9ad9cd39_QuickBooks_Online_API_guide.webp)**A guide to using employee APIs**](https://www.merge.dev/blog/employee-api)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**‍A guide to integrating with Workday’s API**](https://www.merge.dev/blog/workday-api-integration)

# HR API: what you should know about using any

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c70df1981ff41ecb808_HR_API.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

HR APIs can help you access and sync a wide range of employee data—from full names to job titles to employment statuses.

Using them effectively, however, isn’t necessarily easy.

To help you get the most from any HR API, we’ll align on common endpoints, impactful use cases, and a solution to connect to HR endpoints at scale.

But first, let’s define an HR API.

## **What is an HR API?**

It’s a set of API endpoints that HRIS solutions provide. Using these endpoints, you can either keep employee data synced between your internal applications or between your product and customers’ HR applications.

_Related:_ [_What is HRIS integration?_](https://www.merge.dev/blog/guide-to-hris-api-integrations)

## **HR API examples**

Here’s a look at common API endpoints for a few popular HR software vendors:

#### **Workday**

- `Get /workers`: access all of your employees and their associated information, such as location, title, supervisor, etc.
- `Get /entries`: fetch expense entries that employees have submitted, along with key associated details, like amounts, memos, dates, etc.
- `POST /programs`: create benefit programs in Workday

Learn more about [the endpoints Workday supports](https://community.workday.com/sites/default/files/file-hosting/restapi/index.html).

#### **BambooHR**

- `GET /v1/time_tracking/timesheet_entries`: receive timesheet entries across your employee base and for a specific timeframe
- `GET /v1/employees/{id}`: get employee information associated with the ID provided (e.g., their first and last names)
- `POST /v1/employees/{id}/files`: add a file for a specific employee in their BambooHR profile (e.g., their signed offer letter)

See the full list of [endpoints BambooHR supports](https://documentation.bamboohr.com/reference/account-information-1).

#### **Paylocity**

- `GET /v1/companies/{companyId}`: receive information on the company, such as the company’s name, industry, and their employer identification number
- `GET /v1/companies/{companyId}/payGrades`: fetch pay grades, or pay scales, across roles within the company
- `PUT /v1/companies/{companyId}/costCenterLevels/{level}/costCenters/{code}`: update or create a cost center resource within Paylocity

Here’s the [full list of endpoints Paylocity supports](https://developer.paylocity.com/integrations/reference/authentication).

## **HR API integration examples**

We’ll break down a couple of internal HR integrations and then highlight a few real-world, customer-facing use cases.

#### **Add new hires to your HRIS as soon as they sign their offer letters**

To help your HR team become aware of incoming employees and take the appropriate steps to pre-board them, you can provide the team with access to new hire data within your HRIS as soon as possible.

Here’s an integration that lets you do just that: Once a candidate is marked as hired in your ATS (e.g., Greenhouse), their profile gets created in your HRIS. Several fields associated with the employee also get populated in the latter, including the new hire’s full name, job title, department, and address.

[![Sync between Greenhouse and Workday](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a4132774f3ae0306d2d1_AD_4nXd4HpyheG9LdKcAjCqpuIfLmdx-55pTw99U9VJqttGzLt97i48tuBXZrMSYssCJFXMBIUUEybaCa4xOJc6O6Rx9AZ5Ulfpt9477HUs3XlU0lpkqgWD0069qg792vG-EuU21Hl7b.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a4132774f3ae0306d2d1_AD_4nXd4HpyheG9LdKcAjCqpuIfLmdx-55pTw99U9VJqttGzLt97i48tuBXZrMSYssCJFXMBIUUEybaCa4xOJc6O6Rx9AZ5Ulfpt9477HUs3XlU0lpkqgWD0069qg792vG-EuU21Hl7b.webp)

#### **Import key employee documents into your file storage solution**

Throughout the course of an employee’s time at your company, they’ll likely receive and sign a range of documents, from offer letters to NDAs.

To help your HR team (along with other relevant teams) access these documents easily, quickly, and securely, you can integrate your HRIS with a file storage solution like Box and build the following flow: Once a certain document gets added or updated in the HRIS, it’s also added or updated within the employee’s folder in your file storage tool.

[![Sync between BambooHR and Box](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a41305aea69b463ef607_AD_4nXdU9699Gr7Sn2Y-SiMtriNUdOmIB_GhlK8t0J2HFwvIa6bcTkMN5zzNzlEueVFdZudVyeO61CNW_jsH7xI7GtwGLbO8am8dpLzlTSmSpE-5Exl3QsO9DYcE3L_H3V8pOI57OlaVDw.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a41305aea69b463ef607_AD_4nXdU9699Gr7Sn2Y-SiMtriNUdOmIB_GhlK8t0J2HFwvIa6bcTkMN5zzNzlEueVFdZudVyeO61CNW_jsH7xI7GtwGLbO8am8dpLzlTSmSpE-5Exl3QsO9DYcE3L_H3V8pOI57OlaVDw.webp)

_Related:_ [_Examples of HR integration_](https://www.merge.dev/blog/hr-integration)

#### **Provide a best-in-class cap table management platform**

Say you offer a platform that helps organizations manage their employees’ equity packages (e.g., AngelList Equity).

To help your platform kick off and end vesting on time for a given employee, you can connect with customers’ HRIS solutions and build data flows that keep employee data—including employment status—synced.

[![Screenshot of a terminated employee's profile in AngelList Equity](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/664766d53bf8fa8229c7df87_silJHkmuH2R-To494E7GsjJjqRPXhGaeIrkNxiJipbhSVrzBfY7ygQN21Wse8AqcOSY1Jhqaxv2z3RnQLYEiVFvCq4FZndnNFWjQhrjHO1kJELcqjctqRyGedU0vX_88c2Aty8qe9p9K1J2YuMKG2I4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/664766d53bf8fa8229c7df87_silJHkmuH2R-To494E7GsjJjqRPXhGaeIrkNxiJipbhSVrzBfY7ygQN21Wse8AqcOSY1Jhqaxv2z3RnQLYEiVFvCq4FZndnNFWjQhrjHO1kJELcqjctqRyGedU0vX_88c2Aty8qe9p9K1J2YuMKG2I4.webp)

_AngelList Equity automatically updates when an employee is marked as terminated in a customer’s HRIS_

#### **Kick off your user onboarding workflow seamlessly**

Regardless of the platform you provide, you'll likely want to add users to it quickly so that they can see value from it as soon as possible.

To help you do just that, you can connect with customers’ HRIS solutions and implement a flow where once an employee is added to a customer's HRIS, their profile gets created in your product, triggering the onboarding flow that the customer has set for new users in your product.

For example, Electric, an IT management software company, integrated with customers’ HRIS solutions and built a flow where once a customer adds an employee, their information would get added to the customer’s instance of Electric.

An admin user for Electric would then get prompted to select the group that the newly-added employee should be part of, which would determine the applications and devices they’d need. Electric can then go on to ship equipment to the employee and provision them with the appropriate set of applications.

[![Screenshot of adding an employee to a group in Electric](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa9533531374e349f1b2c8_AD_4nXcZe88VUE5zGy2gLL8Un32IsAFaVx-RNAirMXpPyRf9AODy3jEPGX1ynb31PJooIIPE6IXibwAKM9Vv5GGmULhE55xdqDbiyjUF8E9o2s1rdsPMan573gBc09iPvm9Sz23o3sBy-bztK54YoPnka0mQWzM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66aa9533531374e349f1b2c8_AD_4nXcZe88VUE5zGy2gLL8Un32IsAFaVx-RNAirMXpPyRf9AODy3jEPGX1ynb31PJooIIPE6IXibwAKM9Vv5GGmULhE55xdqDbiyjUF8E9o2s1rdsPMan573gBc09iPvm9Sz23o3sBy-bztK54YoPnka0mQWzM.webp)

_Once an admin user selects “Begin onboarding”, Electric would go on to ship equipment to and provision applications for an employee_

## **Add dozens of HR integrations to your product through a single API**

Merge, the leading unified API solution, lets you add 70+ HRIS integrations through its [HRIS Unified API](https://www.merge.dev/categories/hr-payroll-api).

[![A screenshot of the HR integrations Merge supports](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a4145a72f78cb69d52bc_AD_4nXeCtEWd8A3QR_k3aV-vN7JU0IC-XHuzVys-ZVpOtTax-tqfewEdoEslgpasoqhzQHx_y5Gr-DbUmc1zmEjdKlYsC-kQnV6ykwh0-sB0jQd2uIphB_3nP3tUce-LdnTz49S3wGHOIg.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6737a4145a72f78cb69d52bc_AD_4nXeCtEWd8A3QR_k3aV-vN7JU0IC-XHuzVys-ZVpOtTax-tqfewEdoEslgpasoqhzQHx_y5Gr-DbUmc1zmEjdKlYsC-kQnV6ykwh0-sB0jQd2uIphB_3nP3tUce-LdnTz49S3wGHOIg.webp)

_A snapshot of the HR integrations Merge supports_

Merge also provides [comprehensive Common Models (or normalized data models) for HR applications](https://docs.merge.dev/hris/overview/), along with advanced features to help you sync custom data; tooling to help your customer success team identify, diagnose, and resolve integration issues quickly; and integration maintenance support on behalf of your engineers.

Learn more about how Merge can support your HR integration needs by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhr-api).

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