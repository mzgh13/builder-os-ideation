---
url: "https://www.merge.dev/blog/google-drive-api-key"
title: "How to access your API key in Google Drive"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/google-drive-api-key#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/google-drive-api-key#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/google-drive-api-key#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgoogle-drive-api-key)

##### Just for you

No items found.

# How to access your API key in Google Drive

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cb1a6710a493b161431_Google_Drive_API_Key.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/654bad6e0e1f83371b19230f_Thomas%27%20headshot.webp)

Thomas Pauly

@Merge

Google Drive, which allows users to store files in the cloud, synchronize files across devices, and share files with others, includes productivity tools like Google Docs, Sheets, Slides, and more.

While you can benefit from Google Drive’s standalone features and capabilities in a variety of ways, you can get even more value by integrating Google Drive with your product or your internal applications.

To do so, you’ll first need to procure your unique API key. We’ll break down the steps for doing exactly that below!

### Prerequisites

To access your API key, you’ll need to have a Google Cloud Platform (GCP) account.

If you don't have one, you can create it [here](https://console.cloud.google.com/getting-started); but If you’re already logged into Gmail/any Google app, you’ll be automatically logged into your GCP.

#### Integrate with several file storage solutions via Merge

Learn how Merge can help you integrate your product with Google Drive—and many other file storage applications—through a single unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgoogle-drive-api-key)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### Step 1: Visit the Google Cloud Console

Go to the [Google Cloud Console](https://console.cloud.google.com/getting-started?pli=1).

### Step 2: Select a project (or create a new project)

In the top bar, find and click on “Select a project.”

‍

[![Selecting a project in Google Drive](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349d8505e4b7dcf5ee0_7Zawm-I4Ezs0KQlf05fP91nMyQu4v6BblTwbYb-GDZxffcrQ6WzjWE1P5UHrR6R8Vsdm1JQ2Wrr0LCueDd2DlpaMcK_1GfDXXCub987mnUF35CtsBnLE5n54i2f2cShDOyZGIEKpc-zYJX8aner5BJs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349d8505e4b7dcf5ee0_7Zawm-I4Ezs0KQlf05fP91nMyQu4v6BblTwbYb-GDZxffcrQ6WzjWE1P5UHrR6R8Vsdm1JQ2Wrr0LCueDd2DlpaMcK_1GfDXXCub987mnUF35CtsBnLE5n54i2f2cShDOyZGIEKpc-zYJX8aner5BJs.webp)

A window will open up, allowing you to select an existing project or create a new one.

[![Creating a new project](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349dd5e847552931174_uJc024WJuawduPBh9Y9jYS2MkDVgnoR5tsHm06EMVVWLSlQ_AdTjkSW4sAg80reXeUsXOLwWMHqN9r_xrNM-RTXcNUWcnsOD4xHp6CRCw6lIjCz9TkkbqnSRratfusz4xqwVgObPPLiW9c7pD5EXcqY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349dd5e847552931174_uJc024WJuawduPBh9Y9jYS2MkDVgnoR5tsHm06EMVVWLSlQ_AdTjkSW4sAg80reXeUsXOLwWMHqN9r_xrNM-RTXcNUWcnsOD4xHp6CRCw6lIjCz9TkkbqnSRratfusz4xqwVgObPPLiW9c7pD5EXcqY.webp)

If you’re creating a new project, go through the steps of setting it up.

‍

[![Setting up the project](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e534970c6faff4ea02fa1_NEKt6dXKdDPXO9kosivG4dNJQEruyTapKeH2DKonaiEJ1XzecESjaXbi3ReeKaioztJYsnB091P6H3b8gOL7N03XwCNz1PPmiTLDFicVNwCTBXyvqzHxuSJ43P1kNyPWW7UIBkwGuivkYgwXuec9Jh4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e534970c6faff4ea02fa1_NEKt6dXKdDPXO9kosivG4dNJQEruyTapKeH2DKonaiEJ1XzecESjaXbi3ReeKaioztJYsnB091P6H3b8gOL7N03XwCNz1PPmiTLDFicVNwCTBXyvqzHxuSJ43P1kNyPWW7UIBkwGuivkYgwXuec9Jh4.webp)

_Related:_ [_A guide to retrieving your Dropbox API key_](https://www.merge.dev/blog/dropbox-api-key)

### Step 3: Navigate to API & Services

Once you create your new project, you’ll see its name at the top of the page.

You’ll then need to hover your cursor over API & Services and click “Enabled APIs & services.”

[![Clicking on Enabled APIs and Services](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349fd6e85b86c2dd685_Yx45A1-8nrTvo3QRPwzMa6Zf1wrmSOJiRlYwE6mLoq9CRNUeinNq57JiwNba7h0vx4MzbgVbcYCuI4yRdBPLiJOfzRu9tuzbENC0_5tjFj60T6OfBn6AzVzMdOG6lbFYUWgsEmqOEdXhffgLkwGJBiI.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349fd6e85b86c2dd685_Yx45A1-8nrTvo3QRPwzMa6Zf1wrmSOJiRlYwE6mLoq9CRNUeinNq57JiwNba7h0vx4MzbgVbcYCuI4yRdBPLiJOfzRu9tuzbENC0_5tjFj60T6OfBn6AzVzMdOG6lbFYUWgsEmqOEdXhffgLkwGJBiI.webp)

_Related:_ [_How to get your API key in Box_](https://www.merge.dev/blog/box-api-key)

### Step 4: Enable your API

If you haven't already, you need to enable the API you want to use. In the top search bar, search for the API you want to enable. In this case” Google Drive API”

[![Enabling your API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e53498345ba6fd48988f3_qlJGcf-Bxm8JQsZG6SeMuKhqoD_8zJV5TyVTpo9N8zgyM5ceQvwLhDSVgM8wjiu-JOfl8uhKQDuVtDHi2UuRKXHDIjv2EJQFEaoVgmS5TNbV2z51OD1FShTNNG3sbrtxSvqqUmpTkkQK2XZZPHtaZ70.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e53498345ba6fd48988f3_qlJGcf-Bxm8JQsZG6SeMuKhqoD_8zJV5TyVTpo9N8zgyM5ceQvwLhDSVgM8wjiu-JOfl8uhKQDuVtDHi2UuRKXHDIjv2EJQFEaoVgmS5TNbV2z51OD1FShTNNG3sbrtxSvqqUmpTkkQK2XZZPHtaZ70.webp)

After searching, you’ll see a handful of results. Select the Google Drive API you want to enable.

[![Results for the Google Drive API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349dbe758f59a75b7fa_uGrbTdAeQ9kXuqNRP9COELl3lZvlwD_dKFaa6jURHfhHS_g0xDyEWBjKo9Ij0y1rmynuO2xqmBNamAF3ejL5szGvUffGK4dw2sj0WsB1IkEia831zXJYvye95NfytM7B2eU-REVBxcWqjRBTVW_0Wdc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349dbe758f59a75b7fa_uGrbTdAeQ9kXuqNRP9COELl3lZvlwD_dKFaa6jURHfhHS_g0xDyEWBjKo9Ij0y1rmynuO2xqmBNamAF3ejL5szGvUffGK4dw2sj0WsB1IkEia831zXJYvye95NfytM7B2eU-REVBxcWqjRBTVW_0Wdc.webp)

Then click “Enable”

[![Enabling the Google Drive API](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349b2109df8c8fa866d_AqpQq7LWVTobktoF_VkWjErav_CiCz54jeNcWGdW0aG5mFW4n3saJCcbIi2wQG3b6uU9dLCpJJBXOK-PoJJBH_qe9tTTNroF2RiXB8oSgN8NlMYFHeCsiJKMAwR9GbFSXzdj47KOKBrxCe_djEyGCRY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349b2109df8c8fa866d_AqpQq7LWVTobktoF_VkWjErav_CiCz54jeNcWGdW0aG5mFW4n3saJCcbIi2wQG3b6uU9dLCpJJBXOK-PoJJBH_qe9tTTNroF2RiXB8oSgN8NlMYFHeCsiJKMAwR9GbFSXzdj47KOKBrxCe_djEyGCRY.webp)

### Step 5: Create your credentials

After enabling the API, you’ll be able to create credentials.

To do so, click “Create Credentials”

[![Creating credentials](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349a1fcb81741490b82_0KqHqZKN56qM7eP8wUQuPINQwFOwsIWqYf9qWFXX2AoJzPIzkwu8gKE6DrmrZWVDljEHi-4sswWZCPfKet1ALDKKvj6_LlndtY7g5hAQPhqbjDUJLsMvRRMldJ2GCyqSji6e95gRSm0fKHmzYLx8He0.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349a1fcb81741490b82_0KqHqZKN56qM7eP8wUQuPINQwFOwsIWqYf9qWFXX2AoJzPIzkwu8gKE6DrmrZWVDljEHi-4sswWZCPfKet1ALDKKvj6_LlndtY7g5hAQPhqbjDUJLsMvRRMldJ2GCyqSji6e95gRSm0fKHmzYLx8He0.webp)

Then choose the type of credentials you need (API key, OAuth client ID, etc.), and fill in the required information.

[![Setting up credentials](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e534951b1f60dd75ee881_gmcnsJ8sPnmIANYlkg083UyD5s9AmoCdiRo8X1Fgpm5otr_Xkv_VV6sdjYPiitFKvpTaiD6pnPr2ZBIcFoK7qggGO962zFrapgfGJQv1nWh-6Xl241fgs71pvqLUBCPXpSzhT2ZPpCTYQoqLM-m5PqM.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e534951b1f60dd75ee881_gmcnsJ8sPnmIANYlkg083UyD5s9AmoCdiRo8X1Fgpm5otr_Xkv_VV6sdjYPiitFKvpTaiD6pnPr2ZBIcFoK7qggGO962zFrapgfGJQv1nWh-6Xl241fgs71pvqLUBCPXpSzhT2ZPpCTYQoqLM-m5PqM.webp)

### 6\. Configure your API Key

If you're creating an API key, you might need to configure its settings, such as restricting its usage to certain websites, IP addresses, or APIs.

[![Configuring your API key](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349bc4824526e7139f6_SWSsz8EvhP5EfOHEKAYf0bpWT-aKE7sAIqkCuNAxldbwwVlSqRo16FocWxXa8L3eFk9Hy5xSatCx14ZmFkdkTASli9DLJ3zF-rxZZXE797HHf0SnBitcFvSmRPmhuk04VMBXGEBUzSCuvN4PgoDJDes.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349bc4824526e7139f6_SWSsz8EvhP5EfOHEKAYf0bpWT-aKE7sAIqkCuNAxldbwwVlSqRo16FocWxXa8L3eFk9Hy5xSatCx14ZmFkdkTASli9DLJ3zF-rxZZXE797HHf0SnBitcFvSmRPmhuk04VMBXGEBUzSCuvN4PgoDJDes.webp)

### 7\. Get your API key

Once you've configured your API key, it’ll be generated. You can go ahead and use it!

### Other key considerations for building to the Google Drive API

Before integrating with Google Drive’s API, it’s worth considering other items:

#### Pricing

The pricing for a Google Workspace comes in 4 tiers. Business Starter, Business Standard, Business Plus, and Enterprise.

- ‍ **Business starter**: $6/per user/month with a custom and secure business email, 30 GB pooled storage per user, security and management controls, and more. **‍**
- **Business Standard:** $12/per user/month with a custom and secure business email, 2 TB pooled storage per user, security and management controls, and more. **‍**
- **Business Plus:** $18/per user/month with a custom and secure business email, 5 TB pooled storage per user, enhanced security and management controls, advanced endpoint management, and more. **‍**
- **Enterprise:** You’ll need to contact Google for pricing. That said, it comes with a custom and secure business email, 5 TB pooled storage per user, enhanced security and management controls, advanced endpoint management, and more.

[![Google Workspace pricing](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349122d9c6268963215_6IiGQzrvaSE_f1Y641GGKguY4t3iSNuwM89gYdGlFJ3F4tjtc56VwsF8WyL89jOwsd7jJqq4oHsmZtvfTgHoYOkX-voMH9f0StBqpanMDzyyNKfMdz1VpNaLt_qQXmS9GdsVhta-qWAx3TPs4XU7oaY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349122d9c6268963215_6IiGQzrvaSE_f1Y641GGKguY4t3iSNuwM89gYdGlFJ3F4tjtc56VwsF8WyL89jOwsd7jJqq4oHsmZtvfTgHoYOkX-voMH9f0StBqpanMDzyyNKfMdz1VpNaLt_qQXmS9GdsVhta-qWAx3TPs4XU7oaY.webp)

#### Rate Limits

All use of the Google Drive API is available at no additional cost. But since the Google Drive API is a shared service, they apply quotas and limitations to make sure it's used fairly by all users and to protect the overall performance of the Google Workspace system.

For queries, the limits are 12,000 per 60 seconds and 12,000 per 60 seconds per user.

[![Query limits](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349ebce226714f15d88_q1H5DjK-D3cWQEI0EQefGD8Ng0UQ8-hoiEwdxeHAgcqiroyLWtpVZTU8l_uJKsf3bE16BVN7NqijY2B2gElWGPnGOcqbF3qNl0J34CJ3zVkevnEdG20UviGDEA5eE0ObQhEqmQ0wiFuqW2Xs2ORZzWY.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e5349ebce226714f15d88_q1H5DjK-D3cWQEI0EQefGD8Ng0UQ8-hoiEwdxeHAgcqiroyLWtpVZTU8l_uJKsf3bE16BVN7NqijY2B2gElWGPnGOcqbF3qNl0J34CJ3zVkevnEdG20UviGDEA5eE0ObQhEqmQ0wiFuqW2Xs2ORZzWY.webp)

Note: Exceeding the quota request limit doesn’t incur extra charges and your account isn’t billed. You can learn more about Google Drive’s API rate limits [here](https://developers.google.com/drive/api/guides/limits).

_Related:_ [_How to stop getting rate limited by APIs_](https://www.merge.dev/blog/how-to-stop-being-rate-limited-best-practices-for-making-api-calls-at-scale)

#### Errors to look out for

The Google Drive API returns two levels of error information:

- HTTP error codes and header messages
- A JSON object in the response body with additional details that can help you determine how to handle the error

[![Error code summaries](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e53490842f91804827d35_qhfRI0JwKJviaH5Ze2kEfVtFuKq8yTs5UOC0buZ-6GlKjyCrg3ylgXGqtIRb4lonq4VPfnfcIBbl0BbAu-PN3F6KeYe_oj5SFGmM_phZ3pu5QdZKkVF9Ho-n7pPHvzFVXJsQHua4k5KAVj3G0CJdU0I.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656e53490842f91804827d35_qhfRI0JwKJviaH5Ze2kEfVtFuKq8yTs5UOC0buZ-6GlKjyCrg3ylgXGqtIRb4lonq4VPfnfcIBbl0BbAu-PN3F6KeYe_oj5SFGmM_phZ3pu5QdZKkVF9Ho-n7pPHvzFVXJsQHua4k5KAVj3G0CJdU0I.webp)

To get a deeper look into error handling, visit Google’s documentation [here](https://developers.google.com/drive/api/guides/handle-errors)

### Final thoughts

Many of your customers use other File Storage tools, like Box, Dropbox, or OneDrive.

You can offer integrations with any of the file storage applications your clients use by building to [Merge’s File Storage Unified API](https://www.merge.dev/categories/file-storage-api).

To learn more about the API, and Merge’s platform more broadly, you can [schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fgoogle-drive-api-key) with one of our integration experts!

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Thomas Pauly

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6115ebe4-d52c-4b96-8281-b5b62bcc81d1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=3da352bb-fcd7-4893-bd81-c98bdae50f03&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgoogle-drive-api-key&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6115ebe4-d52c-4b96-8281-b5b62bcc81d1&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=3da352bb-fcd7-4893-bd81-c98bdae50f03&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgoogle-drive-api-key&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=04d67cb9-9d22-4083-9465-86df29967f44&bo=2&sid=d562a6d03e8b11f09f7969867af06acd&vid=d56328803e8b11f0ac2b230611e2e59c&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20access%20your%20API%20key%20in%20Google%20Drive&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fgoogle-drive-api-key&r=&lt=316&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=643563)