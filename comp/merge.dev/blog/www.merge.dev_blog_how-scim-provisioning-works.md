---
url: "https://www.merge.dev/blog/how-scim-provisioning-works"
title: "How SCIM provisioning works"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-scim-provisioning-works#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-scim-provisioning-works#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-scim-provisioning-works#)

Table of contents

[What is SCIM and Why Use It?](https://www.merge.dev/blog/how-scim-provisioning-works#what-is-scim-and-why-use-it)

[How SCIM Works](https://www.merge.dev/blog/how-scim-provisioning-works#how-scim-works)

[Understanding the SCIM Schema](https://www.merge.dev/blog/how-scim-provisioning-works#understanding-the-scim-schema)

[Conclusion](https://www.merge.dev/blog/how-scim-provisioning-works#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-scim-provisioning-works)

##### Just for you

No items found.

# How SCIM provisioning works

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cebeb2554fdcf3699ba_How_SCIM_Provisioning_Works.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Karl Hughes

@Merge

As the number of tools your company uses grows, you’ll naturally have to share or transfer user data between tools, and this can lead to many challenges. New employees must have all their accounts set up with the same personal information and that information must be kept in sync as things change.

[SCIM (System for Cross-domain Identity Management)](https://www.simplecloud.info/) is a standard that can help you simplify employee or user management. By providing a common set of rules for how systems exchange user identity information, SCIM makes it easier to integrate internal and external systems by automating the process of adding, updating, and removing users. This ensures that user information is consistent across the board while improving security and reducing the risk of errors.

In this article, you'll learn more about SCIM and how it works. You’ll learn how it relates to other standards like SAML and SSO. I’ll share a bit about the data types and resources that comprise the SCIM schema, and some use cases for SCIM to show you how it can improve user management and security across your software ecosystem.

## What is SCIM and Why Use It?

SCIM is an open, HTTP-based protocol that describes methods for provisioning, managing, and deprovisioning users across multiple systems.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645d22cd9e4482f5259c98db_PXAYt6z_d.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645d22cd9e4482f5259c98db_PXAYt6z_d.webp)

This comes in handy at large organizations when a new employee joins and needs to be added to email, payroll, project management, benefits, and a dozen other services all at once. If you’re just onboarding 1-2 employees per month, you can probably get away with doing this manually, but if you’re onboarding hundreds of employees every day, you need a standard and automated way to facilitate this.

Similarly, if you’re managing a web application and new users who sign up also need to be added to billing and customer support systems, manually copying this data is sure to lead to errors.

Setup is just the first challenge, though, as things get even more complicated when data changes. What happens when an employee gets married and changes their last name? Will HR, payroll, finance, and operations teams all have to go into their systems and manually update their records?

Initially defined in 2011, SCIM was designed as a solution to this challenge. It defines standard REST API endpoints that any SCIM-compliant client can use to create, read, update, and delete data about users. The SCIM core schema defines a set of common data types, attributes, and groups to allow for maximum interoperability between SCIM services. In other words, SCIM makes it significantly easier for multiple systems (internal and external) to keep user information up-to-date.

SCIM 1.0 was replaced by SCIM 2.0 in September 2015 and has since been adopted by most of the major identity providers. In addition to helping you keep user data synced across systems, SCIM also improves security. By ensuring you can remove access to all applications at once, you can deactivate and block malicious user accounts quickly so bad actors can’t cause further damage.

SCIM is also useful when migrating identities. For example, if your company changes benefits providers from one company to another, both being on the SCIM standard will allow you to seamlessly transfer user information between the two systems and ensure no data is lost in the process.

_Related:_ [_How auto-provisioning works_](https://www.merge.dev/blog/automated-provisioning)

## How SCIM Works

Now that you understand why SCIM is useful and what it does, let’s dig into the specifics of _how_ it works and the terminology it uses.

### SCIM Clients and Service Providers

SCIM relies on a central source of truth for user identities called the “client.” Typically, this role is filled by an identity provider like [Okta](https://www.okta.com/) or [FusionAuth](https://fusionauth.io/), which handles user authentication and stores identifying information for that user.

The SCIM protocol can then be implemented by many “service providers,” typically software services that rely on the user’s identity. When a change is made to the user’s information (e.g., they update their email address, phone number, etc.), the SCIM client broadcasts these changes to the service providers based on the SCIM protocol.

I’ll show you what the actual API calls look like later in this piece, but first, let’s clarify a bit more about how SCIM works with identity providers.

### SAML, SCIM, and SSO

If you’re familiar with identity management protocols and standards, you probably know a bit about SAML and SSO, but let’s clarify how these two relate to SCIM.

**SSO (single sign-on)** is a blanket term that refers to a user’s ability to sign into a single system and get access to multiple systems. For example, you are likely familiar with using social or Google as an authentication method for other websites. This is a form of SSO.

**SAML (security assertion markup language)** is just one of the possible standards for implementing SSO. It defines the way in which a user should be verified and how their identity can be passed between systems. SAML isn’t the only standard for implementing authentication, though; OAuth and OpenID are also popular options.

Finally, as you’ve already read, **SCIM** defines the way in which a single user can be kept up-to-date across multiple services. So, SCIM typically works with an SSO provider to help keep a user’s identity information correct.

In a typical workflow, a user would log in through an identity provider (a SCIM client). This identity provider might implement a standard like SAML to offer single sign-on to multiple services. When a user makes a change to a key part of their identity in the identity provider, it will call the endpoints defined by the SCIM protocol to update that user in all service providers. This keeps the user’s information up-to-date as they do things like update their name, email, phone number, or contact information.

_Related:_ [_Real-world examples of automating user onboarding in your product_](https://www.merge.dev/blog/user-onboarding-automation)

## Understanding the SCIM Schema

As mentioned, the [SCIM protocol defines a REST API](https://www.rfc-editor.org/rfc/rfc7643.html) that allows data about users or groups to be passed between various services. When a user makes an update to their identity information, all services in the system that implement the SCIM protocol will be notified of the change using this REST API.

Below are some example URLs for users under the SCIM protocol:

- Create new user: `POST https://example.com/v1/User`
- Retrieve a single user: `GET https://example.com/v1/User/{id}`
- Delete a user by ID: `DELETE https://example.com/v1/User/{id}`
- Update a user by ID: `PATCH https://example.com/v1/User/{id}`
- Search for a user: `GET https://example.com/v1/User?ﬁlter={attribute}{op}{value}&sortBy={attributeName}&sortOrder={ascending|descending}`

As you can see, SCIM allows for versioning and provides standard REST endpoints, as well as endpoints for searching and [bulk operations](https://is.docs.wso2.com/en/latest/apis/scim2-batch-operations/). The groups resource has a similar set of endpoints and allows you to add users to groups so you can implement department-level rules about users and how they relate to one another.

Responses are represented using JSON and have [a set of common data types](https://www.rfc-editor.org/rfc/rfc7643#section-2.3) to ensure maximum interoperability between systems. It’s important to know how these data types work if you’re going to implement SCIM across your ecosystem because improperly handling types or converting them incorrectly can lead to big problems.

SCIM’s standard data types include:

- `string` \- a sequence of characters, and it represents text data such as names, addresses, and email addresses.
- `boolean` \- a data type having only true or false values. It represents binary data, such as whether a user is active or inactive.
- `integer` \- a whole number that can be positive, negative, or zero. It represents numerical data such as user IDs or group IDs.
- `decimal` \- contains decimal digits ( `0–9`) that are used to represent numerical values with a decimal point. This is good for values that require precision, such as monetary values, measurements, and scientific calculations.
- `dateTime` \- represents a specific point in time. It's used for timestamps, such as a user’s creation or modification time.
- `reference` \- references another resource. This allows you to capture relationships between users and groups.
- `complex` \- contains multiple attributes and is used to represent more complex data, such as a user's address or access policies for a group. For example, the `name` attribute in the `user` resource is a “complex” type that contains `givenName` and `familyName`.

Users and groups each have different attributes, but they share four common attributes:

- `schema` \- defines the set of schemas that a SCIM service provider supports.
- `id` \- a unique identifier for the resource.
- `externalId` \- stores an identifier that's external to the SCIM service. This can be used to link users across multiple systems.
- `meta` \- includes information about the resource, such as the resource's creation and last modified time.

The core resource type in the SCIM schema is the `User`, which represents each account in the system. The `User` resource type includes attributes that define the user, such as `userName`, `name`, and `email`. Here's an example of a user resource in JSON format:

```json
{
    "schemas": [\
        "urn:ietf:params:scim:schemas:core:2.0:User"\
    ],
    "id": "2819c223-7f76-453a-919d-413861904646",
    "userName": "HarryPotter",
    "name": {
        "givenName": "Harry",
        "familyName": "Potter"
    },
    "emails": [\
        {\
            "value": "harry.potter@hogwarts.edu",\
            "type": "work",\
            "primary": true\
        }\
    ],
    "active": true
}

```

This is a pretty simple record, but note that the email attribute is an array that contains the user's email addresses, the type of email address, and whether it's the user's primary email address or not.

Each SCIM client can also implement custom attributes, but it should offer [endpoints to get more detailed information about the specific schema and resource types it exposes](https://www.rfc-editor.org/rfc/rfc7644#section-4). This means that even if a SCIM client implements things slightly differently than others, it will still offer a “source of truth” for the correct resource schemas.

## Conclusion

In this article, you’ve learned about the SCIM standard, why it’s useful, and the basics of how to implement and use it. SCIM is one of the most common protocols for migrating identities, integrating with external identity providers, and improving interoperability throughout your software, so it’s important to understand its strengths and limitations.

As a next step, you can check out [Merge](https://merge.dev/), a service that gives you a Unified API to integrate with hundreds of human resources, recruiting, ticketing, CRM, and accounting platforms. Merge can be used to integrate with [SCIM-compliant services](https://merge.dev/blog/the-fastest-way-to-sync-directory-data), such as [identity providers and HR systems](https://merge.dev/categories/hr-payroll-api), making it even easier to put your service onto the SCIM standard.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Karl Hughes

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fc75e985-4020-404b-8d21-eceb25fcd605&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=063913a0-087a-4bdf-bd4c-b5ec7ad57210&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-scim-provisioning-works&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=fc75e985-4020-404b-8d21-eceb25fcd605&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=063913a0-087a-4bdf-bd4c-b5ec7ad57210&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-scim-provisioning-works&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=9b91781e-9089-4cd4-ac70-61122716e35a&bo=2&sid=583b42503e8d11f0a746f3917290864c&vid=583b68a03e8d11f090fe29ded421285c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20SCIM%20provisioning%20works&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-scim-provisioning-works&r=&lt=404&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=941560)