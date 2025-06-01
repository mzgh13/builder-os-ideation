---
url: "https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript"
title: "How to fetch users from Okta using JavaScript"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#)

Table of contents

[Okta API authentication configuration](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#okta-api-authentication-configuration)

[Fetching users from Okta](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#fetching-users-from-okta)

[Conclusion](https://www.merge.dev/blog/how-to-fetch-users-from-okta-using-javascript#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-users-from-okta-using-javascript)

##### Just for you

No items found.

# How to fetch users from Okta using JavaScript

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c76e1896d1b5abd82c0_How_to_fetch_Users_from_Okta_with_Merge_HRIS_Unified_API_using_JavaScript.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd53831f80f118f3af61fa_62eff2893d1cea398f23f57b_Shensi.webp)

Shensi Ding

CEO and co-founder

@Merge

‍ **_Editor's note_** _: This article is part of a series on building third-party API integrations. Explore Merge if you’re looking to add 180+ integrations across HR, SCIM, payroll, ATS, CRM, accounting, ticketing, marketing automation, and file storage with one_ [_unified API_](https://www.merge.dev/) _._

[Okta](https://www.okta.com/) is a robust and flexible access management tool that offers identity management services. It serves as a consolidated platform for managing employees' identities, encompassing single sign-on, multi-factor authentication, and lifecycle management features. Furthermore, its ability to integrate smoothly with various applications streamlines the HR process and boosts productivity by automating user management tasks.

Integrations with Okta often require pulling user data to other platforms for use cases like auto-provisioning, org chart management, etc. Integrations like these can oftentimes enhance the system's security and efficiency, among [other benefits](https://www.merge.dev/blog/api-integration-benefits).

In this article, we'll walk through how you can build an integration with Okta by successfully authenticating and and fetch users using Python!

## Okta API authentication configuration

When interacting with the Okta API, it's crucial to apply the correct authentication configuration. Okta supports multiple types of authentication, but we will walk through how to make an API request using Basic Authentication.

The format of this header for Okta should be `Authorization: SSWS {API-KEY}`.

Replace `{API-KEY}` with your actual Okta API key. This API key is a unique identifier that allows you to communicate securely with the Okta API. It's important to keep your API key confidential to protect the security and integrity of your data. If you need help finding your API key, [we have a help center article with instructions on how to find it](https://help.merge.dev/en/articles/7129484-okta-api-key-authentication).

Remember, every request to the Okta API must include this Authorization header -- failure to include it could result in your requests being denied.

## Fetching users from Okta

Below is a sample JavaScript code using `fetch` to pull users from Okta API. Remember to replace `your-okta-domain` and `your-api-key` with your actual Okta domain and API key. This script will fetch users from the Okta API in a paginated manner by following the `next` URL in each response's Link header until no `next` URL is found, indicating that it has reached the last page of users.

```javascript
javascript
const DOMAIN = 'your-okta-domain';
const API_KEY = 'your-api-key';

async function fetchUsers(url) {
    let users = [];
    let nextUrl = url;

    while (nextUrl) {
        const response = await fetch(nextUrl, {
            method: 'GET',
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json',
                'Authorization': `SSWS ${API_KEY}`
            }
        });

        if (!response.ok) {
            throw new Error('HTTP error ' + response.status);
        }

        const data = await response.json();
        users = users.concat(data);

        // Look for the 'next' link in the Link header
        let linkHeader = response.headers.get('Link') || '';
        let nextLink = linkHeader.split(',').find(s => s.includes('rel="next"'));

        // If found, prepare the URL for the next round
        if (nextLink) {
            nextUrl = nextLink.split(';')[0].slice(1, -1);
        } else {
            nextUrl = null; // End while loop when no 'next' link is found
        }
    }

    return users;
}

// Start fetching users
fetchUsers(`https://${DOMAIN}/api/v1/users`)
    .then(users => console.log(users))
    .catch(error => console.error(error));
```

‍

Once you have successfully made a request, you should see the list of Users from Okta as the output.

```javascript
[\
  {\
    "id": "00ub0oNGTSWTBKOLGLNR",\
    "status": "ACTIVE",\
    "created": "2013-06-24T16:39:18.000Z",\
    "activated": "2013-06-24T16:39:19.000Z",\
    "statusChanged": "2013-06-24T16:39:19.000Z",\
    "lastLogin": "2013-06-24T17:39:19.000Z",\
    "lastUpdated": "2013-07-02T21:36:25.344Z",\
    "passwordChanged": "2013-07-02T21:36:25.344Z",\
    "profile": {\
      "firstName": "Isaac",\
      "lastName": "Brock",\
      "email": "isaac.brock@example.com",\
      "login": "isaac.brock@example.com",\
      "mobilePhone": "555-415-1337"\
    },\
    "credentials": {\
      "password": {},\
      "recovery_question": {\
        "question": "Who's a major player in the cowboy scene?"\
      },\
      "provider": {\
        "type": "OKTA",\
        "name": "OKTA"\
      }\
    },\
    "_links": {\
      "self": {\
        "href": "https://{yourOktaDomain}/api/v1/users/00ub0oNGTSWTBKOLGLNR"\
      }\
    }\
  }\
]
```

‍

## Conclusion

Congratulations! You have now successfully authenticated and fetched users from Okta with Javascript!

But what happens when Okta is merely one among many integrations that your team must develop and sustain, and your next customer asks you for a JumpCloud, Azure Active Directory or OneLogin integration?

This is where a [Unified API](https://www.merge.dev/blog/what-is-a-unified-api), such as [Merge](https://merge.dev/), comes into play. At Merge, we’ve built an API that lets you easily integrate once to offer 40+ HRIS, SCIM and Payroll integrations. Our [Unified API](https://merge.dev/categories/hr-payroll-api) has also normalized response bodies, pagination and authentication. _‍_

_You can learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-fetch-users-from-okta-using-javascript) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/682eca5e5f0f5cfb164fe164_Shensi%20Ding%20-%20Merge.png)

Shensi Ding

CEO and co-founder

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a3d61326-37c4-4f33-9c2b-72ed05efea33&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c91506ff-ac20-41df-bb9b-c25262f1a445&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=a3d61326-37c4-4f33-9c2b-72ed05efea33&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=c91506ff-ac20-41df-bb9b-c25262f1a445&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-javascript&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=dd309dda-902e-4af9-8dc3-b1bdae06b95e&bo=2&sid=950fffc03e8c11f0a24e5b8aa9677769&vid=95102fe03e8c11f0b08b3d947f6ca57a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20fetch%20users%20from%20Okta%20using%20JavaScript&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-fetch-users-from-okta-using-javascript&r=&lt=458&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=620090)